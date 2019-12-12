***
## let关键字
> 用于定义变量 与var关键字不同:let关键字支持块作用域 无法声明前置 无法被window挂在 无法重复定义 在for循环中可以保存变量

无法被window挂载:
```js
var a = 1;
let b = 2;
console.log(window.a);  // 1
console.log(window.b);  // undefined
```
最重要的: for循环保存变量
```js
let arr = [];
for (let i = 0; i < 5; i++) {
    arr[i] = function() {
        console.log(i);
    }
}
arr[1]();   // 仍然是1
arr[2]();   // 仍然是2
```
***
## 对象和属性语法简化
> ES6中, 对象中定义已经存在的属性可以省略属性名称以及冒号, 而定义方法时可以省略冒号以及function关键字

定义已经存在的属性
```js
let color = "red";
let obj = {
    // color: "red"
    color,  // 省略属性名称以及括号
}
```
定义一个方法
```js
let color = "red";
let obj = {
    // print: function() {
    //     console.log(this.num, this.color);
    // }
    print() {   // 省略冒号以及function关键字
        console.log(this.num, this.color);
    }
}
```
***
## 箭头函数
箭头函数示例:
```js
let arr = [1, 2, 3];
// 使用箭头函数求数组元素的平方
let result = arr.map((item) => {
    return item * item;
})
```
箭头函数 语法:    
`let fun = () => {}`    
* () 表示参数集合
* => 箭头函数的标志
* {} 表示函数体

特点:
1. 无法使用arguments
2. 无法作为构造函数使用
3. this指向定义时

省略语法:
1. 如果参数集合中只有一个参数的时候, 即可省略参数集合
2. 如果函数体中只有一句话或者只有返回值的时候, 即可省return关键字以及函数体

省略语法箭头函数示例:
```js
let arr = [1, 2, 3];
// 使用箭头函数语法简化版
let result = arr.map(item => item * item);
console.log(result);
```