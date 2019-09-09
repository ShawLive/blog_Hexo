---
title: JS之数据转换
date: 2019-08-22 18:43:59
categories: 前端
tags: JS
---
### 声明变量注意：
1、声明变量时虽然可以不加`var`关键字，但是…
``` bash
var stuname1 = “赵小臭”；
stuname2 = “凑凑”;
```
如果省略了`var`关键字，那么声明的就是“`全局变量`”，有可能造成“`全局污染`”。（建议每个变量前最好加上`var`）。
2、如果声明变量没有赋值的话，那么将自动赋值为`underfined`。

### 数据类型：
1、`number`类型（数字类型，表示32位整数，也可以表示64位的浮动数）
``` bash
var num1 = 520;
var num2 = 13.14;
```
2、`string`类型（字符串类型）
``` bash
var n1 = "520";
var n2 = "like"
```
3、`boolean`类型（布尔类型，仅有两个值：true和false，做算术运算时，true = 1，false= 0）
``` bash
var result1 = true;//真
var result2 = false;//假
var result3 = "true";//string类型
```
4、`undefinde`类型（不存在该数据，未定义。场合：1、声明变量未赋值2、对象属性不存在）

### 代码调试
``` bash
alert();//弹出框
console.log();//控制台打印输出
prompt ();弹出输入框
document.write();//文档页面输出内容
```

### 数据隐式转换
1、`typeof`（运算符，查看数据类型, 有2种使用方式：`typeof(表达式)`和`typeof 变量名`，第一种是对表达式做运算，第二种是对变量做运算。）
``` bash
console.log(typeof a);//'undefined'
console.log(typeof(true));//'boolean'
```
2、`NaN`(`NaN`属性代表一个“`不是数字`”的值)
Not a Number：不是一个数字
IsNaN();是（不是一个数字）
返回结果：true或false
true：不是一个数字
false：是一个数字
虽然 NaN 意味着“不是数字”，但是它的类型，不管你信不信，是 Number：
``` bash
console.log(typeof NaN === "number");// logs "true"
```
NaN 和任何东西比较——甚至是它自己本身！——结果是false：
``` bash
console.log(NaN === NaN);// logs "false"
```
3、总结
1. 数字 + 字符串 ：将数字转换为字符串
2. 数字 + boolean ：将 boolean 转换为 number类型
3. 数字 + undefined ：结果为 NaN，NaN的类型为 number
4. 字符串 + boolean ：将boolean 转换为 字符串
5. boolean + boolean ：都转换成number在做相加运算
6. 不同类型的数据在计算过程中会进行”自动转换”

### 数据强制转换
1、`String();`——将任意数据类型的数据转换为“字符串”
``` bash
var num = 1314;
var result = String(num);
console.log(result);// logs 1314
console.log(typeof result);// logs string
```
2、`parseInt();`——将任意类型的数据转换为整数
``` bash
var r1 = "520";
var result1 = parseInt(r1);
console.log(result1);// logs 520
var r2 = 13.14;
var result2 = parseInt(r2);
console.log(result2);// logs 13
```
3、`parseFloat();`——将指定数据转换为小数（浮点数）
``` bash
var r1 = "5.20";
var result1 = parseFloat(r1);
console.log(result1);// logs 5.2
var r2 = "13ABC";
var result2 = parseFloat(r2);
console.log(result2);// logs 13
```
4、`Number();`——把一个string解析为number类型，如果待转换字符中包含非法字符，则返回NaN
``` bash
var r1 = "5.20";
var result1 = Number(r1);
console.log(result1);// logs 5.2
var r2 = "13ABC";
var result2 = Number(r2);
console.log(result2);// logs NaN
```