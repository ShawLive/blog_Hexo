---
title: ES6之箭头函数
date: 2019-08-25 23:48:36
categories: 前端
tags: ES6
---
ES6标准新增了一种新的函数：Arrow Function（箭头函数）。
``` bash
x => x * X
```
上面的箭头函数相当于：
``` bash
function (x) {
  return x * x;
}
```
箭头函数看上去是匿名函数的一种简写，但实际上，箭头函数和匿名函数有个明显的区别：箭头函数内部的`this`是词法作用域，由上下文确定。
`JS代码如下：`
``` bash
var factory = function () {
  this.a = 'a';
  this.b = 'b';
  this.c = {
    a: 'a+',
    b: function () {
      return this.a
    }
  }
}
console.log(new factory().c.b());// a+

var factory = function () {
  this.a = 'a';
  this.b = 'b';
  this.c = {
    a: 'a+',
    b: () => {
      return this.a
    }
  } 
} 
console.log(new factory().c.b());// a
```
使用箭头函数简化排序时传入的函数：
`JS代码如下：`
``` bash
// 正序
{
  var arr = [18, 8, 2019, 0];
  arr.sort((x, y) => {
   return x < y ? -1 : ((x = y) ? 0 : 1)
  })
  console.log(arr);// [0, 8, 18, 2019]
}

//倒叙
{
  var arr = [18, 8, 2019, 0];
  arr.sort((x, y) => {
    return x > y ? -1 : ((x = y) ? 0 : 1)
  })
  console.log(arr);// [2019, 18, 8, 0]
}
```
注：`sort()`方法用对数组的元素进行排序，并返回数组。默认排序顺序是在将元素转换为字符串，然后比较它们的UTF-16代码单元值序列时构建的。由于它取决于具体实现，因此无法保证排序的时间和空间复杂性。
[参考文献1](https://www.liaoxuefeng.com/wiki/1022910821149312/1031549578462080 "廖雪峰")
[参考文献2](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)



