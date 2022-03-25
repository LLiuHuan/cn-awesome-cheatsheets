<!--
 * @Description: 
 * @Author: LLiuHuan
 * @Date: 2022-03-25 16:28:01
 * @LastEditTime: 2022-03-25 19:05:44
 * @LastEditors: LLiuHuan
-->

> 官网：http://www.lua.org/  
> 下载：http://www.lua.org/download.html  
> 运行：lua lua.lua  
### 	Lua 特性：
- 轻量级：它用标准C语言编写并以源代码形式开放，编译后仅仅一百余K，可以很方便的嵌入别的程序里。
- 可扩展：Lua提供了非常易于使用的扩展接口和机制：由宿主语言(通常是C或C++)提供这些功能，Lua可以使用它们，就像是本来就内置的功能一样。
- 可移植：跨平台
- 其它特性：支持面向过程(procedure-oriented)编程和函数式编程(functional programming)；  
        自动内存管理；只提供了一种通用类型的表（table），用它可以实现数组，哈希表，集合，对象；  
        语言内置模式匹配；闭包(closure)；函数也可以看做一个值；提供多线程（协同进程，并非操作系统所支持的线程）支持；  
        通过闭包和table可以很方便地支持面向对象编程所需要的一些关键机制，比如数据抽象，虚函数，继承和重载等。  
- 入门书籍《lua程序设计》  
    推荐：云风翻译的《Lua 5.3参考手册》	
    http://cloudwu.github.io/lua53doc/manual.html  
- 源码：http://www.lua.org/ftp/

### Lua 类型：

> 变量: 作为动态类型语言，变量本身没有类型， 赋值决定某一时刻变量的类型。私有静态变量带local, 公有静态变量不带local。

| 数据类型 | 描述 |
| -- | -- |
| nil | 这个最简单，只有值nil属于该类，表示一个无效值（在条件表达式中相当于false） |
| boolean | 包含两个值：false和true |
| number | 表示双精度类型的实浮点数 |
| string | 字符串由一对双引号或单引号来表示 |
| function | 由 C 或 Lua 编写的函数 |
| userdata | 表示任意存储在变量中的C数据结构 |
| thread | 表示执行的独立线路，用于执行协同程序 |
| table | Lua 中的表（table）其实是一个"关联数组"（associative arrays），数组的索引可以是数字、字符串或表类型。在 Lua 里，table 的创建是通过"构造表达式"来完成，最简单构造表达式是{}，用来创建一个空表 (和js中的Object，其他语言中的Map类似) |

```lua
print(type(value))						--nil
print(type(nil))					  	--nil

value = true				
print(type(value))						--boolean

value = 1024
print(type(value))						--number

value = "Hello world"
print(type(value))						--string			

value = function() 
    print(type(value))
end 	
print(type(value))						--function  
print(print)	       					--function  

value = {}								
print(type(value))						--table

value = coroutine.create(function()
print(type(value))
end)
print(type(value))						--coroutine
```

### Lua变量：

> Lua 变量有三种类型：全局变量、局部变量、表中的域。  
> Lua 中的变量全是全局变量，哪怕是语句块或是函数里，除非用 local 显式声明为局部变量。  
> 局部变量的作用域为从声明位置开始到所在语句块结束。  
> 变量的默认值均为 nil。  

```lua
a = 1024                          -- 全局变量
local b = 2048                    -- 局部变量

function func()
    c = 4096                        -- 全局变量
    local d = 8192                  -- 局部变量
end

func()

print(c, d)                       -- 4096 nil

do
    local a = 16384
    b = 16384
    print(a, b)                   -- 16384 16384
end

print(a, b)                       -- 1024 16384
```

### Lua流程控制：

```lua
-- if ... else
--[[
if(布尔表达式)
then
   --[ 在布尔表达式为 true 时执行的语句 --]
end

在布尔表达式为 true 时会if中的代码块会被执行，在布尔表达式为 false 时，紧跟在 if 语句 end 之后的代码会被执行。

Lua认为false和nil为假，true 和非nil为真。要注意的是Lua中 0 为 true。
--]]


ty_signal = type(signal)
if ty_signal == "coroutine" 
then
    print("signal type is coroutine")
elseif ty_signal == "table" then
    print("signal type is table")
else
    print("signal type is other")
end

-- while 
--[[
while(condition)
do
   statements
end

statements(循环体语句) 可以是一条或多条语句，condition(条件) 可以是任意表达式，在 condition(条件) 为 true 时执行循环体语句。
--]]
ut_companys = {"beijing company", "shanghai company", "nanjing company", "wuxi company", "guangzhou company", "yunfu company", "wuhan company", "chengdu company", "xian company"}
count = 0
while count <= #ut_companys 
do
    count = count + 1
    print("ut_companys[", count, "] is ", ut_companys[count])
end

-- for
--[[
for var=exp1,exp2,exp3 do  
    <执行体>  
end  

var 从 exp1 变化到 exp2，每次变化以 exp3 为步长递增 var，并执行一次 "执行体"。exp3 是可选的，如果不指定，默认为1。
--]]

for i=#ut_companys, 1, -2 do        --以2为步长反向遍历
    print("num: ", i, "company: ", ut_companys[i])
end
```

### Lua Table：

> 迭代器：pairs

```lua
-- table 简单事例

fruits = {"banana","orange","apple"}

-- table 连接
-- table.concat (table [, sep [, start [, end]]]):
print("连接后的字符串 ",table.concat(fruits,", ", 2,3))

-- table 插入和移除
-- 在末尾插入
table.insert(fruits,"mango")
print("索引为 4 的元素为 ",fruits[4])

-- 在索引为 2 的键处插入
table.insert(fruits,2,"grapes")
print("索引为 2 的元素为 ",fruits[2])

print("最后一个元素为 ",fruits[5])
table.remove(fruits)
print("移除后最后一个元素为 ",fruits[5])

-- table 排序
table.sort(fruits)
for k,v in ipairs(fruits) do
    print(k,v)
end
--[[
排序后
1    apple
2    banana
3    orange
--]]

```

```lua
-- table 复杂事例
for i, c in ipairs(ut_companys) do
	print(string.format("1 UnionTech company: %d		%s", i, c))
end

table.sort(ut_companys)
for i=#ut_companys, 1, -1 do
	print(string.format("2 UnionTech company: %d		%s", i, ut_companys[i]))
end

--table当hash map用
ut_cptypes = {}

ut_cptypes["adapter"] = {"beijing company", "wuhan company", "guangzhou company"}
ut_cptypes["developer"] = {"beijing company", "wuhan company", "nanjing company", "chengdu company", "xian company", "guangzhou company"}
ut_cptypes["general"] = {"beijing company"}

for ty, cps in pairs(ut_cptypes) do
	for i, cp in ipairs(cps) do
		print(string.format("3 UnionTech companys: type:%s  identifier:%s	company:%s", ty, i, cp))
	end
end
```

### Lua 函数/模块/包：

> 函数：在Lua中函数也是第一类型值， 可赋值给变量， 也可以在函数体内定义并使用函数，或者是直接使用匿名匿名函数。  

```lua
--多重返回值
ut_types = {"adapter", "developer", "general"}
function company_types(cp, cptypes)
	local adpt, dvlp, genl = nil, nil, nil
	for i, ty in ipairs(ut_types) do
		for _, _cp in ipairs(cptypes[ty]) do
			if _cp == cp then
				if i == 1 then
					adpt = true
				elseif i == 2 then
					dvlp = true
				elseif i == 3 then
					genl = true
				end
				break
			end
		end
	end
	return adpt, dvlp, genl
end

cp = "wuhan company"
types = {company_types(cp, ut_cptypes)}

for i, ty in ipairs(types) do
	if ty then
		print(string.format("%s  is %s", cp, ut_types[i]))
	end
end 

--变参
function printf(str, ...)
	print(string.format(str, ...))
end

function add_companys(...)
	local newcps = {...}
	local num = #newcps
	for _, cp in ipairs(newcps) do
		table.insert(ut_companys, cp)
	end
	return ut_companys, num
end

_, _ = add_companys("changsha company", "zhengzhou company", "hefei company")
for i=1, #ut_companys do
	--print(string.format("4 UnionTech company: %d		%s", i, ut_companys[i]))
	printf("4 UnionTech company: %d		%s", i, ut_companys[i])
end

--闭包
function all_companys(cps)
	local companys, n = {}, 0
	for _, v in ipairs(cps) do
		table.insert(companys, v)
	end
	return function()
		n = n + 1
		if n > #companys then
			return ""
		else
			return companys[n]
		end
	end
end

get_company = all_companys(ut_companys)
while true
do
	cp = get_company()
	if cp == "" then
		break
	else	
		printf("get company: %s", cp)
	end
end
```

```lua
-- 文件名为 module.lua
-- 定义一个名为 module 的模块
module = {}
 
-- 定义一个常量
module.constant = "这是一个常量"
 
-- 定义一个函数
function module.func1()
    io.write("这是一个公有函数！\n")
end
 
local function func2()
    print("这是一个私有函数！")
end
 
function module.func3()
    func2()
end
 
return module
```

```lua
-- 文件名为 test_module.lua
require "module"

print(module.constant)

module.func3()

--[[
这是一个常量
这是一个私有函数！
--]]
```

### Lua 协程：

> 协程(coroutine)：Lua协同程序(coroutine)与线程比较类似：拥有独立的堆栈，独立的局部变量，独立的指令指针，同时又与其它协同程序共享全局变量和其它大部分东西。  

| 方法 | 描述 ｜
| -- | -- |
| coroutine.create() | 创建 coroutine，返回 coroutine， 参数是一个函数，当和 resume 配合使用的时候就唤醒函数调用 |
| coroutine.resume() | 重启 coroutine，和 create 配合使用 |
| coroutine.yield() | 挂起 coroutine，将 coroutine 设置为挂起状态，这个和 resume 配合使用能有很多有用的效果 |
| coroutine.status() | 查看 coroutine 的状态  注：coroutine 的状态有三种：dead，suspended，running |
| coroutine.wrap() | 创建 coroutine，返回一个函数，一旦你调用这个函数，就进入 coroutine，和 create 功能重复 |
| coroutine.running() | 返回正在跑的 coroutine，一个 coroutine 就是一个线程，当使用running的时候，就是返回一个 corouting 的线程号 |

```lua
function foo (a)
    print("foo 函数输出", a)
    return coroutine.yield(2 * a) -- 返回  2*a 的值
end
 
co = coroutine.create(function (a , b)
    print("第一次协同程序执行输出", a, b) -- co-body 1 10
    local r = foo(a + 1)
     
    print("第二次协同程序执行输出", r)
    local r, s = coroutine.yield(a + b, a - b)  -- a，b的值为第一次调用协同程序时传入
     
    print("第三次协同程序执行输出", r, s)
    return b, "结束协同程序"                   -- b的值为第二次调用协同程序时传入
end)
       
print("main", coroutine.resume(co, 1, 10)) -- true, 4
print("main", coroutine.resume(co, "r")) -- true 11 -9
print("main", coroutine.resume(co, "x", "y")) -- true 10 end
print("main", coroutine.resume(co, "x", "y")) -- cannot resume dead coroutine
--resume将主协程数据传入次协程， yield将次协程中数据传回主协程
```

### Lua 元表：

> 元表(Metatable)：本质上来说就是存放元方法的表结构， 通过元表实现对表中数据和行为的改变。  
> Lua 查找一个表元素时的规则，其实就是如下 3 个步骤:  
>   1.在表中查找，如果找到，返回该元素，找不到则继续  
>   2.判断该表是否有元表，如果没有元表，返回 nil，有元表则继续。  
>   3.判断元表有没有 __index 方法，如果 __index 方法为 nil，则返回 nil；如果__index 方法是一个表，则重复 1、2、3；如果 __index 方法是一个函数，则返回该函数的返回值  

```lua
father = {
	colourofskin = "yellow",
	weight = 70,
	work = "programming",
	otherwork = function() 
		print "do housework"
	end
}
father.__index = father

son = {
	weight = 50,
	like = "basketball"
}

setmetatable(son, father)
printf("weight:%d 	like:%s  	work:%s		colourofskin:%s ", son.weight, son.like, son.work, son.colourofskin)
son.otherwork()

```

### 面向对象：

> 因为lua本身不是面向对象的语言， 在lua中， 通过table和function来模拟一个对象， 用metatable来模拟面向对象中的继承，但是在使用的时候需要考虑lua作为脚本语言， 变量的类型随所赋值类型而改变。

```lua
--父类
rect = {
    area = 0,
    length = 0, 
    width = 0,
}

function rect:getArea()
    if self.area == 0 then
        self.area = self.length * self.width
    end
    
    return self.area
end

function rect:getLength()
    return self.length
end

function rect:new(leng, wid)
    self.length = leng
    self.width = wid
    return self    
end

--子类
cuboid = {
    volume = 0,
    height = 0,
}

function cuboid:getVolume()
    if self.volume == 0 then
        self.volume = self.height * self:getArea()
    end
    return self.volume
end

function cuboid:new(_rect, _height)
    setmetatable(self, _rect)
    _rect.__index = _rect
    self.height = _height
    return self
end

rect1 = rect:new(5, 10)
print("rect1 rectangle:", rect1:getArea())

cuboid1 = cuboid:new(rect1, 2)
print("cuboid1 volume: ", cuboid1:getVolume())
print("cuboid1 rectangle: ", cuboid1:getArea())             --子类调用父类方法getArea
print("cuboid1 length function: ", cuboid1:getLength())     --子类调用父类方法getLength
print("cuboid1 length variable: ", cuboid1.length)          --子类使用父类变量length

--重写子类接口getArea， lua中没有重载
function cuboid:getArea()                                   
    return 2 * (self.height * self.length + self.height * self.width + self.length * self.width)
end

cuboid2 = cuboid:new(rect1, 2)
print("cuboid2 function: getArea: ", cuboid2:getArea())                     --调用子类重写的方法getArea
print("cuboid2 base function: getArea: ", getmetatable(cuboid2):getArea())  --显示调用父类方法getArea
```

### Lua 常用标准库

```lua
---------------------------------------------------------------------------------
--[[
	lua标准库： 标准库中接口可直接使用不需要require
	常用标准库：
		math		数学计算
		table		表结构数据处理
		string	    字符串处理
		os			系统库函数
		io			文件读写
		coroutine	协程库
		debug	    调式器
		LuaSQL	    操作数据库
--]]
---------------------------------------------------------------------------------
```

### Lua 虚拟机

```lua
---------------------------------------------------------------------------------
--[[
	lua虚拟机：脚本语言没有像编译型语言那样直接编译为机器能识别的机器代码，这意味着
	解释性脚本语言与编译型语言的区别：由于每个脚本语言都有自己的一套字节码，与具体的
	硬件平台无关，所以无需修改脚本代码，就能运行在各个平台上。硬件、软件平台的差异都
	由语言自身的虚拟机解决。由于脚本语言的字节码需要由虚拟机执行，而不像机器代码那样
	能够直接执行，所以运行速度比编译型语言差不少。有了虚拟机这个中间层，同样的代码可
	以不经修改就运行在不同的操作系统、硬件平台上。Java、Python都是基于虚拟机的编程语
	言，Lua同样也是这样。
--]]
---------------------------------------------------------------------------------
```

### Lua 简单示例

```lua
-- 文件I/O

--[[
可以使用 file:方法的方式
--]]

-- 以只读方式打开文件
file = io.open("test.lua", "r")

-- 设置默认输入文件为 test.lua
io.input(file)

-- 输出文件第一行
print(io.read())

-- 关闭打开的文件
io.close(file)
-- file:close()

-- 以附加的方式打开只写文件
file = io.open("test.lua", "a")

-- 设置默认输出文件为 test.lua
io.output(file)

-- 在文件最后一行添加 Lua 注释
io.write("--  test.lua 文件末尾注释")
-- file:write("--test")

-- 关闭打开的文件
io.close(file)
-- file:close()
```


### Lua 错误处理

```lua
-- pcall：接收一个函数和要传递给后者的参数，并执行，执行结果：有错误、无错误；返回值true或者或false, errorinfo。
=pcall(function(i) print(i) error('error..') end, 33)
-- 33 false        stdin:1: error..

-- xpcall：接收第二个参数 一个错误处理函数，当错误发生时，Lua会在调用桟展开（unwind）前调用错误处理函数，于是就可以在这个函数中使用debug库来获取关于错误的额外信息了。
=xpcall(function(i) print(i) error('error..') end, function() print(debug.traceback()) end, 33)
--[[
33
stack traceback:
stdin:1: in function <stdin:1>
[C]: in function 'error'
stdin:1: in function <stdin:1>
[C]: in function 'xpcall'
stdin:1: in main chunk
[C]: in ?
false        nil
--]]
```