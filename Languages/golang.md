> Golang CHEATSHEET (中文速查表) - by chlins (created on 2020/08/18)  
> Version: 2, Last Modified: 2020/08/19 00:06  
> https://github.com/LLiuHuan/cn-awesome-cheatsheets

### Go 编译器命令

```golang
go command [arguments]                              // go 命令 [参数]
go build                                            // 编译包和依赖包
go clean                                            // 移除对象和缓存文件
go doc                                              // 显示包的文档
go env                                              // 打印go的环境变量信息
go bug                                              // 报告bug
go fix                                              // 更新包使用新的api
go fmt                                              // 格式规范化代码
go generate                                         // 通过处理资源生成go文件
go get                                              // 下载并安装包及其依赖
go install                                          // 编译和安装包及其依赖
go list                                             // 列出所有包
go run                                              // 编译和运行go程序
go test                                             // 测试
go tool                                             // 运行给定的go工具
go version                                          // 显示go当前版本
go vet                                              // 发现代码中可能的错误
```

### ENV

```golang
GOOS                                                 // 编译系统
GOARCH                                               // 编译arch
GO111MODULE                                          // gomod开关
GOPROXY                                              // go代理 https://goproxy.io  https://goproxy.cn
GOSSAFUNC                                            // 生成SSA.html文件，展示代码优化的每一步 GOSSAFUNC=func_name go build
```

### HelloWord

```golang
// main.go
package main // 包名

import "fmt" // 导入fmt包

func main() { // 主函数
	fmt.Println("Hello World") // 打印输出
}
// go run main.go                                   // 直接运行
// go build && ./main                               // 先编译成二进制文件再运行
```

### 操作符

```golang
// 算数操作符
+ - * / %                                           // 加 减 乘 除 取余
& | ^ &^                                            // 位与 位或 位异或 位与非
<< >>                                               // 左移 右移
// 比较操作
== !=                                               // 等于 不等于
< <=                                                // 小于 小于等于
> >=                                                // 大于 大于等于
// 逻辑操作
&& || !                                             // 逻辑与 逻辑或 逻辑非
// 其他
& * <-                                              // 地址 指针引用 通道操作
```

### 声明

```golang
a := 1                                             // 直接给一个未声明的变量赋值
var b int                                           // var 变量名 数据类型 来声明
var c float64                                       // 注意：使用var声明过的变量不可再使用 := 赋值
a = 2
const d = 1                                         // 常量
var (                                               // 声明多个变量
	e = 1
	f = 2
	g = 3
)
h ,i := 1,2
const (
	b = 1 << (10 * iota)
	kb
	mb
	gb
	tb
	pb
)
```

### 数据类型

```golang
s := "hello"                                       // 字符
a := 1                                             // int
b := 1.2                                           // float64
c := 1 + 5i                                        // complex128
// 数组
arr1 := [3]int{4, 5, 6}                            // 手动指定长度
arr2 := [...]int{1, 2, 3}                          // 由golang自动计算长度
// 切片
sliceInt := []int{1, 2}                            // 不指定长度
sliceByte := []byte("hello")
// 指针
a := 1
point := &a                                        // 将a的地址赋给point
```

### 流程控制

```golang
// for
i := 10
for i > 0 {
    println(i--)
}
for var i = 1; i < 10; i++{
    print(i)
}
a := [...]int{1,2,3}
for i := range a {
    fmt.Println(a[i])
}
// 省略初始条件 相当于while
// 死循环
for {
    fmt.Println("Go")
}
// if else
if i == 10 {
    println("i == 10")
} else {
    println("i != 10")
}
// 简写版 if
if contents, err := ioutil.ReadFile(filename); err != nil {
    fmt.Println(err)
} else {
    fmt.Printf("%s \n", contents)
}
// switch
switch i {
case 10:
    println("i == 10")
default:
    println("i != 10")
}
// 判断版 switch
switch {
case i > 10:
    println("i > 10")
default:
    println("i < 10")
}
```

### 函数

```golang
// 以func关键字声明
func test() {}
// 匿名函数
f := func() {println("Lambdas function")}
f()
// 函数多返回值
func get() (a,b string) {
    return "a", "b"
}
a, b := get()
// 多参数多返回值
func add(a,b int)(c int) {
    return a+b
}
add(5,5)
// 函数作为参数
func apply(op func(int, int) int, a, b int) int {
    // 取op函数名
	p := reflect.ValueOf(op).Pointer()
	opName := runtime.FuncForPC(p).Name()
	fmt.Println(opName)
	return op(a, b)
}
apply(add, 3, 4)
```

### 结构体

```golang
// golang中没有class只有struct
type People struct {
  Age int                                       // 大大写开头的变量在包外可以访问
  name string                                   // 小小写开头的变量仅可在本包内访问
}
p1 := People{25, "Kaven"}                       // 必须按照结构体内部定义的顺序
p2 := People{name: "Kaven", age: 25}            // 若不按顺序则需要指定字段

// 也可以先不赋值

p3 := new(People)
p3.Age = 25
p3.name = "Kaven"

var p4 People
p4.Age = 18

// 函数体方法
func (node *People) print(){
    fmt.Println(node.Age, " ")
}
p4.print()
```

### 方法

```golang
// 方法通常是针对一个结构体来说的
type Foo struct {
  a int
}
                                                // 值接收者
func (f Foo) test() {
  f.a = 1                                       // 不会改变原来的值
}
                                                // 指针接收者
func (f *Foo) test() {
  f.a = 1                                       // 会改变原值
}
```

### 封装

```golang
// 首字母大写：public
// 首字母小写：private

```

### go 协程

```golang
go func() {
    time.Sleep(10 * time.Second)
    println("hello")
}()                                              // 不会阻塞代码的运行 代码会直接向下运行
// channel 通道
c := make(chan int)
// 两个协程间可以通过chan通信
go func() {c <- 1}()                            // 此时c会被阻塞 直到值被取走前都不可在塞入新值
go func() {println(<-c)}()
// 带缓存的channel
bc := make(chan int, 2)
go func() {c <- 1; c <-2}()                     // c中可以存储声明时所定义的缓存大小的数据，这里是2个
go func() {println(<-c)}()
```
