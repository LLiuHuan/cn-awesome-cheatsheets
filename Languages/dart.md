> Golang CHEATSHEET (中文速查表) - by chlins (created on 2021/08/04)  
> Version: 2, Last Modified: 2021/08/04 09:50  
> https://github.com/LLiuHuan/cn-awesome-cheatsheets

## 一个简单的 Dart 程序

下面的代码用到了很多 Dart 的基本功能：

```dart
// 定义一个函数
printInteger(int aNumber) {
  print('The number is $aNumber.'); // 打印到控制台。
}

// 应用从这里开始执行。
main() {
  var number = 42; // 声明并初始化一个变量。
  printInteger(number); // 调用函数。
}
```

以下是此程序使用的代码，这些代码适用于所有（或几乎所有）的 Dart 应用：

`// *代码注释。*`

单行注释。 Dart 同样支持多行注释和文档注释。 有关更多信息，参考 [注释](https://www.dartcn.com/guides/language/language-tour#comments).

`int`

数据类型。一些其他 [内置类型](https://www.dartcn.com/guides/language/language-tour#built-in-types) 包括 `String` , `List` , 和 `bool` 。

`42`

字面量。字面量是一种编译型常量。

`print()`

便利输出方式。

`'...'` (or `"..."`)

字符串常量。

`$*variableName*` (或 `${*expression*}`)

字符串插值： 包括字符串文字内部的变量或表达式的字符串。 有关更多信息，参考 [Strings](https://www.dartcn.com/guides/language/language-tour#strings).

`main()`

程序开始执行函数，该函数是特定的、*必须的*、顶级函数。 有关更多信息，参考 [The main() function](https://www.dartcn.com/guides/language/language-tour#the-main-function).

`var`

定义变量，通过这种方式定义变量不需要指定变量类型。



## 关键字

| [abstract](https://www.dartcn.com/guides/language/language-tour#抽象类) | [dynamic](https://www.dartcn.com/guides/language/language-tour#重要的概念) | [implements](https://www.dartcn.com/guides/language/language-tour#隐式接口) | [show](https://www.dartcn.com/guides/language/language-tour#导入库的一部分) |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [as](https://www.dartcn.com/guides/language/language-tour#类型判定运算符) | [else](https://www.dartcn.com/guides/language/language-tour#if-和-else) | [import](https://www.dartcn.com/guides/language/language-tour#使用库) | [static](https://www.dartcn.com/guides/language/language-tour#类变量和方法) |
| [assert](https://www.dartcn.com/guides/language/language-tour#assert) | [enum](https://www.dartcn.com/guides/language/language-tour#枚举类型) | [in](https://www.dartcn.com/guides/language/language-tour#for-循环) | [super](https://www.dartcn.com/guides/language/language-tour#扩展类继承) |
| [async](https://www.dartcn.com/guides/language/language-tour#异步支持) | [export](https://www.dartcn.com/guides/libraries/create-library-packages) | [interface](https://stackoverflow.com/questions/28595501/was-the-interface-keyword-removed-from-dart) | [switch](https://www.dartcn.com/guides/language/language-tour#switch-和-case) |
| [await](https://www.dartcn.com/guides/language/language-tour#异步支持) | [extends](https://www.dartcn.com/guides/language/language-tour#扩展类继承) | [is](https://www.dartcn.com/guides/language/language-tour#类型判定运算符) | [sync](https://www.dartcn.com/guides/language/language-tour#生成器) |
| [break](https://www.dartcn.com/guides/language/language-tour#break-和-continue) | [external](https://stackoverflow.com/questions/24929659/what-does-external-mean-in-dart) | [library](https://www.dartcn.com/guides/language/language-tour#库和可见性) | [this](https://www.dartcn.com/guides/language/language-tour#构造函数) |
| [case](https://www.dartcn.com/guides/language/language-tour#switch-和-case) | [factory](https://www.dartcn.com/guides/language/language-tour#工厂构造函数) | [mixin](https://www.dartcn.com/guides/language/language-tour#为类添加功能mixins) | [throw](https://www.dartcn.com/guides/language/language-tour#throw) |
| [catch](https://www.dartcn.com/guides/language/language-tour#catch) | [false](https://www.dartcn.com/guides/language/language-tour#booleans) | [new](https://www.dartcn.com/guides/language/language-tour#使用构造函数) | [true](https://www.dartcn.com/guides/language/language-tour#booleans) |
| [class](https://www.dartcn.com/guides/language/language-tour#实例变量) | [final](https://www.dartcn.com/guides/language/language-tour#final-和-const) | [null](https://www.dartcn.com/guides/language/language-tour#默认值) | [try](https://www.dartcn.com/guides/language/language-tour#catch) |
| [const](https://www.dartcn.com/guides/language/language-tour#final-和-const) | [finally](https://www.dartcn.com/guides/language/language-tour#finally) | [on](https://www.dartcn.com/guides/language/language-tour#catch) | [typedef](https://www.dartcn.com/guides/language/language-tour#typedefs) |
| [continue](https://www.dartcn.com/guides/language/language-tour#break-和-continue) | [for](https://www.dartcn.com/guides/language/language-tour#for-循环) | [操作](https://www.dartcn.com/guides/language/language-tour#重写运算符) | [var](https://www.dartcn.com/guides/language/language-tour#变量) |
| [covariant](https://www.dartcn.com/guides/language/sound-problems#the-covariant-keyword) | [Function](https://www.dartcn.com/guides/language/language-tour#函数) | [part](https://www.dartcn.com/guides/libraries/create-library-packages#organizing-a-library-package) | [void](https://medium.com/dartlang/dart-2-legacy-of-the-void-e7afb5f44df0) |
| [default](https://www.dartcn.com/guides/language/language-tour#switch-和-case) | [get](https://www.dartcn.com/guides/language/language-tour#getters-和-setters) | [rethrow](https://www.dartcn.com/guides/language/language-tour#catch) | [while](https://www.dartcn.com/guides/language/language-tour#while-和-do-while) |
| [deferred](https://www.dartcn.com/guides/language/language-tour#延迟加载库) | [hide](https://www.dartcn.com/guides/language/language-tour#导入库的一部分) | [return](https://www.dartcn.com/guides/language/language-tour#函数) | [with](https://www.dartcn.com/guides/language/language-tour#为类添加功能mixins) |
| [do](https://www.dartcn.com/guides/language/language-tour#while-和-do-while) | [if](https://www.dartcn.com/guides/language/language-tour#if-和-else) | [set](https://api.dartlang.org/stable/dart-core/Set-class.html) | [yield](https://www.dartcn.com/guides/language/language-tour#生成器) |


## 内建类型

| 类型 | 解释 | 示例 |
| :-- | :-- | :-- |
| Number | Dart 语言的 Number 有两种类型: int double | var x = 1 or  var x = 1.1 |
| String | Dart 字符串是一组 UTF-16 单元序列。 字符串通过单引号或者双引号创建。 | var s = 'hello' |
| Boolean | Dart 使用 bool 类型表示布尔值。Dart 只有字面量 true and false 是布尔类型 |  |
| List (也被称为 Array) | 在 Dart 中的 Array 就是 List 对象， 通常称之为 List 。 | var list = [1, 2, 3] |
| Map | 通常来说， Map 是用来关联 keys 和 values 的对象。 | var gifts = {'first': 'partridge','second': 'turtledoves','fifth': 'golden rings'}; |
| Set | 在 Dart 中 Set 是一个元素唯一且无需的集合。 | var halogens = {'fluorine', 'chlorine', 'bromine', 'iodine', 'astatine'}; |
| Rune (用于在字符串中表示 Unicode 字符) | 在 Dart 中， Rune 用来表示字符串中的 UTF-32 编码字符。 | var clapping = '\u{1f44f}'; |
| Symbol | 一个 Symbol 对象表示 Dart 程序中声明的运算符或者标识符。  | |

### 1. 变量
| 支持的类型：Number、String、Boolean、List (也被称为 Array)、Map、Set、Rune (用于在字符串中表示 Unicode 字符)、Symbol

1. 不指定类型  
`var name = '小明';`

2. 指定类型  
`String name = '小明';`

3. 类型不明确  
`dynamic name = '小明';`

### 2. 默认值  

未初始化的变量默认值是 `null`。即使变量是数字 类型默认值也是 null，因为在 Dart 中一切都是对象，数字类型 也不例外。  

```dart
int lineCount;
assert(lineCount == null);
```

**提示：** 在生产环境代码中 `assert()` 函数会被忽略，不会被调用。 在开发过程中, `assert(*condition*)` 会在非 `true` 的条件下抛出异常.有关更多信息，参考 [Assert](https://www.dartcn.com/guides/language/language-tour#assert).

### 3. 常量
使用过程中从来不会被修改的变量， 可以使用 final 或 const, 而不是 var 或者其他类型， Final 变量的值只能被设置一次； Const 变量在编译时就已经固定 (Const 变量 是隐式 Final 的类型.) 最高级 final 变量或类变量在第一次使用时被初始化。

```dart
final name = '小明';
const age = 18;
```

## 函数

```dart
bool isNoble(int atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
```

如果函数中只有一句表达式，可以使用简写语法：

```dart
bool isNoble(int atomicNumber) => _nobleGases[atomicNumber] != null;
```

### 1. 可选参数

```dart
// 命名可选参数
void enableFlags({bool bold, bool hidden}) {...}

// @required
// 必须输入参数child 否则报错
const Scrollbar({Key key, @required Widget child})

// 位置可选参数
String say(String from, String msg, [String device]) {
  var result = '$from says $msg';
  if (device != null) {
    result = '$result with a $device';
  }
  return result;
}

// 默认参数值
void enableFlags({bool bold = false, bool hidden = false}) {...}
```

### 2. main() 函数
| 任何应用都必须有一个顶级 main() 函数，作为应用服务的入口。 main() 函数返回值为空，参数为一个可选的 List<String> 。

```dart
// 下面是 web 应用的 main() 函数：
void main() {
  querySelector('#sample_text_id')
    ..text = 'Click me!'
    ..onClick.listen(reverseText);
}

// 下面是一个命令行应用的 main() 方法，并且使用了输入参数：
// 这样运行应用： dart args.dart 1 test
void main(List<String> arguments) {
  print(arguments);

  assert(arguments.length == 2);
  assert(int.parse(arguments[0]) == 1);
  assert(arguments[1] == 'test');
}
```

### 3. 函数是一等对象

一个函数可以作为另一个函数的参数。 例如：

```dart
void printElement(int element) {
  print(element);
}

var list = [1, 2, 3];

// 将 printElement 函数作为参数传递。
list.forEach(printElement);
```

同样可以将一个函数赋值给一个变量，例如：

```dart
var loudify = (msg) => '!!! ${msg.toUpperCase()} !!!';
assert(loudify('hello') == '!!! HELLO !!!');
```

### 4. 匿名函数

多数函数是有名字的， 比如 `main()` 和 `printElement()`。 也可以创建没有名字的函数，这种函数被称为 *匿名函数*， 有时候也被称为 *lambda* 或者 *closure* 。 匿名函数可以赋值到一个变量中， 举个例子，在一个集合中可以添加或者删除一个匿名函数。

匿名函数和命名函数看起来类似— 在括号之间可以定义一些参数或可选参数，参数使用逗号分割。

后面大括号中的代码为函数体：

```
([[*Type*] *param1*[, …]]) { *codeBlock*;};
```

下面例子中定义了一个包含一个无类型参数 `item` 的匿名函数。 list 中的每个元素都会调用这个函数，打印元素位置和值的字符串。

```dart
var list = ['apples', 'bananas', 'oranges'];
list.forEach((item) {
  print('${list.indexOf(item)}: $item');
});
```

如果函数只有一条语句， 可以使用箭头简写。

```dart
list.forEach(
    (item) => print('${list.indexOf(item)}: $item'));
```

### 5. 词法作用域

Dart 是一门词法作用域的编程语言，就意味着变量的作用域是固定的， 简单说变量的作用域在编写代码的时候就已经确定了。 花括号内的是变量可见的作用域。

下面示例关于多个嵌套函数的变量作用域：

```dart
bool topLevel = true;

void main() {
  var insideMain = true;

  void myFunction() {
    var insideFunction = true;

    void nestedFunction() {
      var insideNestedFunction = true;

      assert(topLevel);
      assert(insideMain);
      assert(insideFunction);
      assert(insideNestedFunction);
    }
  }
}
```

注意 `nestedFunction()` 可以访问所有的变量， 一直到顶级作用域变量。

### 6. 词法闭包

*闭包* 即一个函数对象，即使函数对象的调用在它原始作用域之外， 依然能够访问在它词法作用域内的变量。

函数可以封闭定义到它作用域内的变量。 接下来的示例中， `makeAdder()` 捕获了变量 `addBy`。 无论在什么时候执行返回函数，函数都会使用捕获的 `addBy` 变量。

```dart
/// 返回一个函数，返回的函数参数与 [addBy] 相加。
Function makeAdder(num addBy) {
  return (num i) => addBy + i;
}

void main() {
  // 创建一个加 2 的函数。
  var add2 = makeAdder(2);

  // 创建一个加 4 的函数。
  var add4 = makeAdder(4);

  assert(add2(3) == 5);
  assert(add4(3) == 7);
}
```

### 7. 测试函数是否相等

下面是顶级函数，静态方法和示例方法相等性的测试示例：

```dart
void foo() {} // 顶级函数

class A {
  static void bar() {} // 静态方法
  void baz() {} // 示例方法
}

void main() {
  var x;

  // 比较顶级函数。
  x = foo;
  assert(foo == x);

  // 比较静态方法。
  x = A.bar;
  assert(A.bar == x);

  // 比较实例方法。
  var v = A(); // A的1号实例
  var w = A(); // A的2号实例
  var y = w;
  x = w.baz;

  // 两个闭包引用的同一实例（2号）,
  // 所以它们相等。
  assert(y.baz == x);

  // 两个闭包引用的非同一个实例，
  // 所以它们不相等。
  assert(v.baz != w.baz);
}
```

### 8. 返回值

所有函数都会返回一个值。 如果没有明确指定返回值， 函数体会被隐式的添加 `return null;` 语句。

```dart
foo() {}

assert(foo() == null);
```

## 运算符

| Description              | 操作                                                |
| ------------------------ | ------------------------------------------------------- |
| unary postfix            | `*expr*++`  `*expr*--`  `()`  `[]`  `.`  `?.`           |
| unary prefix             | `-*expr*`  `!*expr*`  `~*expr*`  `++*expr*`  `--*expr*` |
| multiplicative           | `*`  `/`  `%` `~/`                                      |
| additive                 | `+`  `-`                                                |
| shift                    | `<<`  `>>`  `>>>`                                       |
| bitwise AND              | `&`                                                     |
| bitwise XOR              | `^`                                                     |
| bitwise OR               | `\|`                                                     |
| relational and type test | `>=`  `>`  `<=`  `<`  `as`  `is`  `is!`                 |
| equality                 | `==`  `!=`                                              |
| logical AND              | `&&`                                                    |
| logical OR               | `\|\|`                                                    |
| if null                  | `??`                                                    |
| conditional              | `*expr1* ? *expr2* : *expr3*`                           |
| cascade                  | `..`                                                    |
| assignment               | `=`  `*=`  `/=`  `+=`  `-=`  `&=`  `^=`  *etc.*         |


```dart
// 实例
a++
a + b
a = b
a == b
c ? a : b
a is T
```

### 1. 算术运算符

| 操作  | 含义                                                      |
| --------- | ------------------------------------------------------------ |
| `+`       | 加                                                          |
| `–`       | 减                                                     |
| `-*expr*` | 一元负号，也称为否定（将表达式的符号反转） |
| `*`       | 乘                                                     |
| `/`       | 除                                                       |
| `~/`      | 除，返回整数结果                          |
| `%`       | 取余            |

```dart
// 实例
assert(2 + 3 == 5);
assert(2 - 3 == -1);
assert(2 * 3 == 6);
assert(5 / 2 == 2.5); // 结果是双浮点型
assert(5 ~/ 2 == 2); // 结果是整型
assert(5 % 2 == 1); // 余数

assert('5/2 = ${5 ~/ 2} r ${5 % 2}' == '5/2 = 2 r 1');
```

Dart 还支持前缀和后缀，自增和自减运算符。

| 操作  | 含义                                               |
| --------- | ----------------------------------------------------- |
| `++*var*` | `*var* = *var* + 1` (表达式为 `*var* + 1`) |
| `*var*++` | `*var* = *var* + 1` (表达式为 `*var*`)     |
| `--*var*` | `*var* = *var* – 1` (表达式为 `*var* – 1`) |
| `*var*--` | `*var* = *var* – 1` (表达式为 `*var*`)     |

```dart
var a, b;

a = 0;
b = ++a; // a自加后赋值给b。
assert(a == b); // 1 == 1

a = 0;
b = a++; // a先赋值给b后，a自加。
assert(a != b); // 1 != 0

a = 0;
b = --a; // a自减后赋值给b。
assert(a == b); // -1 == -1

a = 0;
b = a--; // a先赋值给b后，a自减。
assert(a != b); // -1 != 0
```

### 2. 关系运算符

| 操作 | 含义                     |
| -------- | --------------------------- |
| `==`     | 等于 |
| `!=`     | 不等于                   |
| `>`      | 大于                |
| `<`      | 小于                   |
| `>=`     | 大于等于    |
| `<=`     | 小于等于       |

```dart
assert(2 == 2);
assert(2 != 3);
assert(3 > 2);
assert(2 < 3);
assert(3 >= 3);
assert(2 <= 3);
```

### 3. 类型判定运算符

| 操作 | 含义                                                      |
| -------- | ------------------------------------------------------------ |
| `as`     | 强制转换为特定类型 |
| `is`     | 如果对象具有指定的类型，则为True                    |
| `is!`    | 如果对象具有指定的类型，则为False                   |

```dart
if (emp is Person) {
  // Type check
  emp.firstName = 'Bob';
}

(emp as Person).firstName = 'Bob';
```

### 4. 赋值运算符

| `=`  | `–=` | `/=`  | `%=`  | `>>=` | `^=` |
| ---- | ---- | ----- | ----- | ----- | ---- |
| `+=` | `*=` | `~/=` | `<<=` | `&=`  | `\|=` |

```dart
var a = 2; // 使用 = 复制
a *= 3; // 复制并做乘法运算： a = a * 3
assert(a == 6);
```

### 5. 逻辑运算符

| 操作  | 含义                                                      |
| --------- | ------------------------------------------------------------ |
| `!*expr*` | 取反 |
| `\|\|`      | 或                                                   |
| `&&`      | 与                                                  |

```dart
if (!done && (col == 0 || col == 3)) {
  // ...Do something...
}
```

### 6. 按位和移位运算符

| 操作  | 含义                                               |
| --------- | ----------------------------------------------------- |
| `&`       | 与                                                   |
| `\|`       | 或                                                    |
| `^`       | 异或                                                   |
| `~*expr*` | 一元位补码 (0s 变 1s; 1s 变 0s) |
| `<<`      | 左移                                           |
| `>>`      | 右移                                           |

```dart
final value = 0x22;
final bitmask = 0x0f;

assert((value & bitmask) == 0x02); // 与
assert((value & ~bitmask) == 0x20); // AND NOT(非与？)
assert((value | bitmask) == 0x2f); // 或
assert((value ^ bitmask) == 0x2d); // 异或
assert((value << 4) == 0x220); // 左移
assert((value >> 4) == 0x02); // 右移
```