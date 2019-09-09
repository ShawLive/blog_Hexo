---
title: HTML中清除浮动的几种方式
date: 2019-08-22 17:46:45
categories: 前端
tags: HTML
---
### 浮动产生的原因：
子级盒子对象使用了CSS中`float`属性，导致父级盒子对象不能被撑开。
### 浮动产出的副作用：
1. 父级盒子对象的背景不能显示
2. 父级盒子对象的边框不能撑开
3. 父级盒子对象的`margin`和`padding`设置值不能正确显示

### 清除浮动的方法：
1. 对父级设置适合CSS高度
2. `clear:both`清除浮动

`HTML代码如下：`
``` bash
<div class="fatherDiv">
    <div class="boyLeft">左浮动<div>
    <div class="boyRight">右浮动<div>
    <div calss="clear">
<div>
```
`CSS代码如下：`
``` bash
.fatherDiv {
    width: 168px; 
    background:red;
}
.boyLeft {
    float: left;
}
.boyRight {
    float: right;
}
/* 清除浮动代码 */
.clear {
    clear: both;
}
```
3. 父级div定义`overflow:hidden`

`HTML代码如下：`
``` bash
<div class="fatherDiv">
    <div class="boyLeft">左浮动<div>
    <div class="boyRight">右浮动<div>
<div>
```
`CSS代码如下：`
``` bash
.fatherDiv {
    width: 168px; 
    background:red; 
    overflow:hidden;/* 清除浮动代码 */
}
.boyLeft {
    float: left;
}
.boyRight {
    float: right;
}
```
4. 使用伪元素:`after`清除浮动(缺点：ie6-7不支持伪元素：after，使用zoom:1触发hasLayout)
 
`HTML代码如下：`
``` bash
<div class="fatherDiv">
    <div class="boyLeft">左浮动<div>
    <div class="boyRight">右浮动<div>
<div>
```
`CSS代码如下：`
``` bash
.fatherDiv {
    width: 168px; 
    background:red; 
    zoom:1;/*IE浏览器的专有属性*/
}
.fatherDiv:after {
    /* 这三句必须写 */
    display:block;  /*变成块级元素*/
    clear:both;/*清除浮动*/
    /* 必须有这样写 */
    content:""; /*内容为空*/

    /* 这两句写不写无所谓 */
    visibility:hidden; /*将元素隐藏，但是在网页中该占的位置还是占着*/
    height:0;
}
.boyLeft {
    float: left;
}
.boyRight {
    float: right;
}
```

