<!--
 * @Description: 
 * @Author: LLiuHuan
 * @Date: 2021-04-26 15:40:07
 * @LastEditTime: 2022-06-28 22:03:42
 * @LastEditors: LLiuHuan
-->

### Docker
```bash
docker build -t friendlyname .              # 使用该目录的 Dockerfile 创建镜像
docker run -p 4000:80 friendlyname          # 运行“friendlyname”映射端口 4000 到 80
docker run -d -p 4000:80 friendlyname       # 相同，但处于分离模式
docker exec -it [container-id] bash         # 进入一个正在运行的容器
docker ps                                   # 查看所有正在运行的容器列表
docker stop <hash>                          # 优雅地停止指定容器
docker ps -a                                # 查看所有容器的列表，包括那些没有运行的容器
docker kill <hash>                          # 强制关闭指定容器
docker rm <hash>                            # 从本机移除指定容器
docker rm $(docker ps -a -q)                # 移除本机所有容器
docker images -a                            # 显示本机所有镜像
docker rmi <imagename>                      # 从本机移除指定的镜像
docker rmi $(docker images -q)              # 删除本机所有镜像
docker logs <container-id> -f               # 实时查看一个容器的日志
docker login                                # 使用您的 Docker 凭据登录此 CLI 会话
docker tag <image> username/repository:tag  # 标签 <image> 用于上传到注册表
docker push username/repository:tag         # 上传标签镜像到注册表
docker run username/repository:tag          # 从注册表运行镜像
docker system prune                         # 删除所有未使用的容器、网络、图像（包括悬空的和未引用的）以及可选的卷。（Docker 17.06.1-ce 及更高版本）
docker system prune -a                      # 删除所有未使用的容器、网络、图像，而不仅仅是悬空的（Docker 17.06.1-ce 及更高版本）
docker volume prune                         # 删除所有未使用的本地卷
docker network prune                        # 删除所有未使用的网络
```

### DOCKER COMPOSE

```bash
docker-compose up                               # 创建并启动容器
docker-compose up -d                            # 以分离模式创建和启动容器
docker-compose down                             # 停止并移除容器、网络、镜像和卷
docker-compose logs                             # 查看容器的日志
docker-compose restart                          # 重启所有服务
docker-compose pull                             # 拉取所有镜像服务
docker-compose build                            # 构建所有镜像服务
docker-compose config                           # 验证并查看 Compose 文件
docker-compose scale <service_name>=<replica>   # 缩放服务
docker-compose top                              # 显示正在运行的进程
docker-compose run -rm -p 2022:22 web bash      # 启动 web 服务并运行 bash 作为它的命令，删除旧容器。
```

### DOCKER SERVICES 
```bash
docker service create <options> <image> <command>   # 新建服务
docker service inspect --pretty <service_name>      # 显示详细信息
docker service ls                                   # 列出服务
docker service ps                                   # 列出指定服务的任务
docker service scale <service_name>=<replica>       # 缩放服务
docker service update <options> <service_name>      # 更新服务选项
```

### DOCKER STACK 
```bash
docker stack ls                                 # 列出此 Docker 主机上所有正在运行的应用程序
docker stack deploy -c <composefile> <appname>  # 运行指定的Compose文件
docker stack services <appname>                 # 列出一个应用关联的服务
docker stack ps <appname>                       # 列出与某个应用关联的正在运行的容器
docker stack rm <appname>                       # 删除一个应用
```

### DOCKER MACHINE
```
docker-machine create --driver virtualbox myvm1                           # 创建一个虚拟机（Mac、Win7、Linux）
docker-machine create -d hyperv --hyperv-virtual-switch "myswitch" myvm1  # Win10
docker-machine env myvm1                                                  # 查看你的节点的基本信息
docker-machine ssh myvm1 "docker node ls"                                 # 列出集群中的节点
docker-machine ssh myvm1 "docker node inspect <node ID>"                  # 检查一个节点
docker-machine ssh myvm1 "docker swarm join-token -q worker"              # 查看加入令牌
docker-machine ssh myvm1                                                  # 打开与虚拟机的 SSH 会话；输入“exit”结束
docker-machine ssh myvm2 "docker swarm leave"                             # 让worker离开swarm
docker-machine ssh myvm1 "docker swarm leave -f"                          # 让master离开，杀死swarm
docker-machine start myvm1                                                # 启动一个当前没有运行的虚拟机
docker-machine stop $(docker-machine ls -q)                               # 停止所有正在运行的虚拟机
docker-machine rm $(docker-machine ls -q)                                 # 删除所有虚拟机及其磁盘镜像
docker-machine scp docker-compose.yml myvm1:~                             # 复制文件到节点的主目录
docker-machine ssh myvm1 "docker stack deploy -c <file> <app>"            # 部署一个应用
```
