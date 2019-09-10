---
title: JS-slice()方法返回一个新的数组对象
date: 2019-09-10 20:19:20
categories: 前端
tags: JS
---
`slice()` 方法返回一个新的数组对象，这一对象是一个由 `begin` 和 `end` 决定的原数组的浅拷贝（包括 `begin`，不包括 `end`）。原始数组不会被改变。
##### 实现strStr（）函数。
给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置（从0开始）。如果不存在，则返回-1。
示例1：
``` bash
输入：haystack="hello"，needle="11"
输出：2
```
示例2：
``` bash
输入：haystack="aaaaa"，needle="bbal"
输出：-1
```
`JS代码如下：`
``` bash
var strStr = function (haystack, needle) {
  if (needle === '') {
  	return 0;
  }
  const length = needle.length;
  let index = 0;
  while (index + length <= haystack.length) {
    const str = haystack.slice(index, index + length);
    if (str === needle) {
    return index;
    }
	index++;
  }
  return -1;
}
var haystack = "20190818";
var needle = "1953";
```
[参考文献](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice "MDN")
