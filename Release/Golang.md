<!--
 * @Description: 
 * @Author: LLiuHuan
 * @Date: 2021-04-26 15:07:14
 * @LastEditTime: 2021-04-26 15:39:13
 * @LastEditors: LLiuHuan
-->
###########################################  
全平台 部署 Golang项目  
###########################################

> 暂未更新完毕，等有时间在继续更新

## 打包到本地
> 执行go build

**0x00 前言**
> 使用go方便之处就在于可以直接打包成二进制文件，不需要配置环境和依赖就可以运行


**0x01 打包到CentOS**
```
set GOOS=linux
set GOARCH=amd64
# open in Terminal
go build main.go
```

**0x02 打包到Windows**
```
set GOOS=windows
set GOARCH=amd64
# open in Terminal
go build main.go
```

**0x03 打包可附加参数**
```
go build 可附加的参数
-v  编译时显示包名
-p n    开启并发编译，默认情况下该值为 CPU 逻辑核数
-a  强制重新构建
-n  打印编译时会用到的所有命令，但不真正执行
-x  打印编译时会用到的所有命令
-race   开启竞态检测
```

**0x04 查询可支持的OS跟ARCH**
`go tool dist list`

```
aix/ppc64
android/386
android/amd64
android/arm
android/arm64
darwin/amd64
darwin/arm64
dragonfly/amd64
freebsd/386
freebsd/amd64
freebsd/arm
freebsd/arm64
illumos/amd64
ios/amd64
ios/arm64
js/wasm
linux/386
linux/amd64
linux/arm
linux/arm64
linux/mips
linux/mips64
linux/mips64le
linux/mipsle
linux/ppc64
linux/ppc64le
linux/riscv64
linux/s390x
netbsd/386
netbsd/amd64
netbsd/arm
netbsd/arm64
openbsd/386
openbsd/amd64
openbsd/arm
openbsd/arm64
openbsd/mips64
plan9/386
plan9/amd64
plan9/arm
solaris/amd64
windows/386
windows/amd64
windows/arm
```


## 打包到Docker
**0x01 编写Dockerfile(基础版)**
> 要创建Docker镜像（image）必须在配置文件中指定步骤。这个文件默认我们通常称之为Dockerfile。（虽然这个文件名可以随意命名它，但最好还是使用默认的Dockerfile。）

```
# 我们正在使用的基础镜像，来创建我们的镜像
FROM golang:alpine

# 为我们的镜像设置必要的环境变量
ENV GO111MODULE=on \
    CGO_ENABLED=0 \
    GOOS=linux \
    GOARCH=amd64

# 移动到工作目录：/build
WORKDIR /build

# COPY 将代码复制到容器中
COPY . .

# 将我们的代码编译成二进制可执行文件app
RUN go build -o app .

# 移动到用于存放生成的二进制文件的 /dist 目录
WORKDIR /dist

# 将二进制文件从 /build 目录复制到这里
RUN cp /build/app .

# 声明服务端口
EXPOSE 8888

# 启动容器时运行的命令
CMD ["/dist/app"]
```

**0x02 构建镜像并运行**
1. 在项目目录下(和Dockerfile同级)，执行下面的命令创建镜像，并指定镜像名称为goweb：  
`docker build . -t goweb`  

# 2. 等待结束，输出如下内容  
```
...
Successfully built 90d9283286b7
Successfully tagged goweb:latest
```

# 3. 执行下面的命令来运行镜像  
`docker run -p 8888:8888 goweb`

# 4. 然后就可以访问8888端口了


**0x03 编写Dockerfile(分阶段版)**
> 因为我们go编译完成后的二进制文件并不需要go环境就可以运行，所以可以在带go的docker中将源码打包成二进制，然后将二进制文件放在一个最小的基础镜像中来运行

```
FROM golang:alpine AS builder

# 为我们的镜像设置必要的环境变量
ENV GO111MODULE=on \
    CGO_ENABLED=0 \
    GOOS=linux \
    GOARCH=amd64

# 移动到工作目录：/build
WORKDIR /build

# 将代码复制到容器中
COPY . .

# 将我们的代码编译成二进制可执行文件 app
RUN go build -o app .

###################
# 接下来创建一个小镜像
###################
FROM scratch

# 从builder镜像中把/dist/app 拷贝到当前目录
COPY --from=builder /build/app /

# 需要运行的命令
ENTRYPOINT ["/app"]
```