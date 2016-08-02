## 基本语法
typeof运算符

```
typeof 123 // "number"
typeof '123' // "string"
typeof false // "boolean"

function f() {}
typeof f
// "function"

typeof undefined
// "undefined"

typeof window // "object"
typeof {} // "object"
typeof [] // "object"
typeof null // "object"
```
parseInt方法用于将字符串转为整数。

```
parseInt('123') // 123
parseInt('8a') // 8
parseInt('12**') // 12
parseInt('12.34') // 12
parseInt('15e2') // 15
parseInt('15px') // 15

进制转换
parseInt('1000', 10) // 1000
parseInt('1000', 2) // 8
parseInt('1000', 6) // 216
parseInt('1000', 8) // 512
```
转义

```
\0 null（\u0000）
\b 后退键（\u0008）
\f 换页符（\u000C）
\n 换行符（\u000A）
\r 回车键（\u000D）
\t 制表符（\u0009）
\v 垂直制表符（\u000B）
\' 单引号（\u0027）
\" 双引号（\u0022）
\ 反斜杠（\u005C）

```
## 对象
谓对象，就是一种无序的数据集合，由若干个“键值对”（key-value）构成。

```
var o = {
  p1: 'Hello',
  p2: 'World'
};
```

查看一个对象本身的所有属性，可以使用Object.keys方法
```
var o = {
  key1: 1,
  key2: 2
};

Object.keys(o);
// ['key1', 'key2']
```

for...in循环用来遍历一个对象的全部属性。

```
var o = {a: 1, b: 2, c: 3};

for (var i in o) {
  console.log(o[i]);
}
// 1
// 2
// 3
```

## 数组

数组属于一种特殊的对象。

```
typeof [1, 2, 3] // "object"
```

数组的slice方法将类似数组的对象，变成真正的数组。
```
var arr = Array.prototype.slice.call(arrayLike);
```
## 函数
由于函数与其他数据类型地位平等，所以在JavaScript语言中又称函数为第一等公民。

```
function add(x, y) {
  return x + y;
}

// 将函数赋值给一个变量
var operator = add;

// 将函数作为参数和返回值
function a(op){
  return op;
}
a(add)(1, 1)
// 2
```
函数参数如果是原始类型的值（数值、字符串、布尔值），传递方式是传值传递（passes by value）。这意味着，在函数体内修改参数值，不会影响到函数外部。

```
var p = 2;

function f(p) {
  p = 3;
}
f(p);

p // 2
```
但是，如果函数参数是复合类型的值（数组、对象、其他函数），传递方式是传址传递（pass by reference）。也就是说，传入函数的原始值的地址，因此在函数内部修改参数，将会影响到原始值。

```
var obj = {p: 1};

function f(o) {
  o.p = 2;
}
f(obj);

obj.p // 2
```
