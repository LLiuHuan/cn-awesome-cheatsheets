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

**提示：**以上代码中的 `..` 语法为 级联调用 使用级联调用， 可以简化在一个对象上执行的多个操作。


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

下表是 Dart 定义的运算符。 多数运算符可以被重载，详情参考 [重写运算符](https://www.dartcn.com/guides/language/language-tour#重写运算符)。

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

**提示：** 上述表格中描述的运算符优先级近似于Dart 解析器实际行为。 更准确的描述，请参阅 [Dart language specification](https://www.dartcn.com/guides/language/spec) 中的语法。

创建表达式的时候会用到运算符。 下面是一些运算符表达式的实例：

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

### 7. 条件表达式

Dart有两个运算符，有时可以替换 [if-else](https://www.dartcn.com/guides/language/language-tour#if-和-else) 表达式， 让表达式更简洁：

- `*condition* ? *expr1* : *expr2*`

  如果条件为 true, 执行 *expr1* (并返回它的值)： 否则, 执行并返回 *expr2* 的值。

- `*expr1* ?? *expr2*`

  如果 *expr1* 是 non-null， 返回 *expr1* 的值； 否则, 执行并返回 *expr2* 的值。

如果赋值是根据布尔值， 考虑使用 `?:`。

```dart
var visibility = isPublic ? 'public' : 'private';
```

如果赋值是基于判定是否为 null， 考虑使用 `??`。

```dart
String playerName(String name) => name ?? 'Guest';
```

下面给出了其他两种实现方式， 但并不简洁：

```dart
// Slightly longer version uses ?: operator.
String playerName(String name) => name != null ? name : 'Guest';

// Very long version uses if-else statement.
String playerName(String name) {
  if (name != null) {
    return name;
  } else {
    return 'Guest';
  }
}
```

### 8. 级联运算符 (..)

级联运算符 (`..`) 可以实现对同一个对像进行一系列的操作。 除了调用函数， 还可以访问同一对象上的字段属性。 这通常可以节省创建临时变量的步骤， 同时编写出更流畅的代码。

考虑一下代码：

```dart
querySelector('#confirm') // 获取对象。
  ..text = 'Confirm' // 调用成员变量。
  ..classes.add('important')
  ..onClick.listen((e) => window.alert('Confirmed!'));
```

第一句调用函数 `querySelector()` ， 返回获取到的对象。 获取的对象依次执行级联运算符后面的代码， 代码执行后的返回值会被忽略。

上面的代码等价于：

```dart
var button = querySelector('#confirm');
button.text = 'Confirm';
button.classes.add('important');
button.onClick.listen((e) => window.alert('Confirmed!'));
```

级联运算符可以嵌套，例如：

```dart
final addressBook = (AddressBookBuilder()
      ..name = 'jenny'
      ..email = 'jenny@example.com'
      ..phone = (PhoneNumberBuilder()
            ..number = '415-555-0100'
            ..label = 'home')
          .build())
    .build();
```

在返回对象的函数中谨慎使用级联操作符。 例如，下面的代码是错误的：

```dart
var sb = StringBuffer();
sb.write('foo')
  ..write('bar'); // Error: 'void' 没哟定义 'write' 函数。
```

`sb.write()` 函数调用返回 void， 不能在 `void` 对象上创建级联操作。

**提示：** 严格的来讲， “两个点” 的级联语法不是一个运算符。 它只是一个 Dart 的特殊语法。

### 9. 其他运算符

大多数剩余的运算符，已在示例中使用过：

| Operator | Name                      | Meaning                                                      |
| -------- | ------------------------- | ------------------------------------------------------------ |
| `()`     | 函数      | 表示调用函数                                   |
| `[]`     | 列表               | 从列表中指定索引处的值       |
| `.`      | 访问成员             | 指表达式的属性；示例：`foo.bar`从表达式`foo'中选择属性`bar`` |
| `?.`     | 有条件的访问成员 | 与`.`类似，但最左边的操作数可以为null；示例：`foo？.bar`从表达式`foo`中选择属性`bar'，除非`foo`为null（在这种情况下，`foo？.bar`的值为null） |

## 控制流程语句

- `if` and `else`
- `for` loops
- `while` and `do`-`while` loops
- `break` and `continue`
- `switch` and `case`
- `assert`

### 1. if 和 else

Dart 支持 `if - else` 语句，其中 `else` 是可选的， 比如下面的例子。

  ```dart
  if (isRaining()) {
    you.bringRainCoat();
  } else if (isSnowing()) {
    you.wearJacket();
  } else {
    car.putTopDown();
  }
  ```

  和 JavaScript 不同， Dart 的判断条件必须是布尔值，不能是其他类型。

### 2. for 循环

进行迭代操作，可以使用标准 `for` 语句。 例如：

```dart
var message = StringBuffer('Dart is fun');
for (var i = 0; i < 5; i++) {
  message.write('!');
}
```

闭包在 Dart 的 `for` 循环中会捕获循环的 index 索引值， 来避免 JavaScript 中常见的陷阱。 请思考示例代码：

```dart
var callbacks = [];
for (var i = 0; i < 2; i++) {
  callbacks.add(() => print(i));
}
callbacks.forEach((c) => c());
```

和期望一样，输出的是 `0` 和 `1`。 但是示例中的代码在 JavaScript 中会连续输出两个 `2` 。

I如果要迭代一个实现了 Iterable 接口的对象， 可以使用 forEach() 方法， 如果不需要使用当前计数值， 使用 `forEach()` 是非常棒的选择；

```dart
candidates.forEach((candidate) => candidate.interview());
```

实现了 Iterable 的类（比如， List 和 Set）同样也支持使用 `for-in` 进行迭代操作 iteration：

```dart
var collection = [0, 1, 2];
for (var x in collection) {
  print(x); // 0 1 2
}
```

### 3. while 和 do-while

`while` 循环在执行前判断执行条件：

```dart
while (!isDone()) {
  doSomething();
}
```

`do`-`while` 循环在执行`后`判断执行条件：

```dart
do {
  printLine();
} while (!atEndOfPage());
```

### 4. break 和 continue

使用 `break` 停止程序循环：

```dart
while (true) {
  if (shutDownRequested()) break;
  processIncomingRequests();
}
```

使用 `continue` 跳转到下一次迭代：

```dart
for (int i = 0; i < candidates.length; i++) {
  var candidate = candidates[i];
  if (candidate.yearsExperience < 5) {
    continue;
  }
  candidate.interview();
}
```

如果对象实现了 Iterable 接口 （例如，list 或者 set）。 那么上面示例完全可以用另一种方式来实现：

```dart
candidates
    .where((c) => c.yearsExperience >= 5)
    .forEach((c) => c.interview());
```

### 5. switch 和 case

在 Dart 中 switch 语句使用 `==` 比较整数，字符串，或者编译时常量。 比较的对象必须都是同一个类的实例（并且不可以是子类）， 类必须没有对 `==` 重写。枚举类型可以用于 `switch` 语句。

**提示：** 在 Dart 中 Switch 语句仅适用于有限的情况下， 例如在 interpreter 或 scanner 中。

在 `case` 语句中，每个非空的 `case` 语句结尾需要跟一个 `break` 语句。 除 `break` 以外，还有可以使用 `continue`, `throw`，者 `return`。

当没有 `case` 语句匹配时，执行 `default` 代码：

```dart
var command = 'OPEN';
switch (command) {
  case 'CLOSED':
    executeClosed();
    break;
  case 'PENDING':
    executePending();
    break;
  case 'APPROVED':
    executeApproved();
    break;
  case 'DENIED':
    executeDenied();
    break;
  case 'OPEN':
    executeOpen();
    break;
  default:
    executeUnknown();
}
```

下面的 `case` 程序示例中缺省了 `break` 语句，导致错误：

```dart
var command = 'OPEN';
switch (command) {
  case 'OPEN':
    executeOpen();
    // ERROR: 丢失 break

  case 'CLOSED':
    executeClosed();
    break;
}
```

但是， Dart 支持空 `case` 语句， 允许程序以 fall-through 的形式执行。

```dart
var command = 'CLOSED';
switch (command) {
  case 'CLOSED': // Empty case falls through.
  case 'NOW_CLOSED':
    // Runs for both CLOSED and NOW_CLOSED.
    executeNowClosed();
    break;
}
```

在非空 `case` 中实现 fall-through 形式， 可以使用 `continue` 语句结合 `lable` 的方式实现:

```dart
var command = 'CLOSED';
switch (command) {
  case 'CLOSED':
    executeClosed();
    continue nowClosed;
  // Continues executing at the nowClosed label.

  nowClosed:
  case 'NOW_CLOSED':
    // Runs for both CLOSED and NOW_CLOSED.
    executeNowClosed();
    break;
}
```

`case` 语句可以拥有局部变量， 这些局部变量只能在这个语句的作用域中可见。

### 6. assert

如果 `assert` 语句中的布尔条件为 false ， 那么正常的程序执行流程会被中断。 在本章中包含部分 assert 的使用， 下面是一些示例：

```dart
// 确认变量值不为空。
assert(text != null);

// 确认变量值小于100。
assert(number < 100);

// 确认 URL 是否是 https 类型。
assert(urlString.startsWith('https'));
```

**提示：** assert 语句只在开发环境中有效， 在生产环境是无效的

assert 的第二个参数可以为其添加一个字符串消息。

```dart
assert(urlString.startsWith('https'),
    'URL ($urlString) should start with "https".');
```

assert 的第一个参数可以是解析为布尔值的任何表达式。 如果表达式结果为 true ， 则断言成功，并继续执行。 如果表达式结果为 false ， 则断言失败，并抛出异常。

## 异常

Dart 代码可以抛出和捕获异常。 异常表示一些未知的错误情况。 如果异常没有被捕获， 则异常会抛出， 导致抛出异常的代码终止执行。

和 Java 有所不同， Dart 中的所有异常是非检查异常。 方法不会声明它们抛出的异常， 也不要求捕获任何异常。

Dart 提供了 Exception 和 Error 类型， 以及一些子类型。 当然也可以定义自己的异常类型。 但是，此外 Dart 程序可以抛出任何非 null 对象， 不仅限 Exception 和 Error 对象。

### 1. throw

下面是关于抛出或者 *引发* 异常的示例：

```dart
throw FormatException('Expected at least 1 section');
```

也可以抛出任意的对象：

```dart
throw 'Out of llamas!';
```

**提示：** 高质量的生产环境代码通常会实现 [Error](https://api.dartlang.org/stable/dart-core/Error-class.html) 或 [Exception](https://api.dartlang.org/stable/dart-core/Exception-class.html) 类型的异常抛出。

因为抛出异常是一个表达式， 所以可以在 => 语句中使用，也可以在其他使用表达式的地方抛出异常：

```dart
void distanceTo(Point other) => throw UnimplementedError();
```

