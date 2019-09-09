---
title: JS之元素显示隐藏效果
date: 2019-08-22 18:29:20
categories: 前端
tags: JS
---
`HTML代码如下：`
``` bash
<img src="img/love.jpg" alt="" id="img">
<button id="btn_show">显示</button>
<button id="btn_hidden">隐藏</button>
```
`JS代码如下：`
``` bash
<script>
    window.onload = function(){
        /*window表示窗口 onload是加载 意思是页面加载完毕后，才执行里面的js，所以可以放在顶端*/
        var img = document.gitElementById("img");
        var btn_show = document.gitElementById("btn_show");
        var btn_hidden = document.gitElementById("btn_hidden");

        btn_show.onclick = function(){
            img.style.display = "block";
        }
        /*点击显示按钮时，img的样式style的display属性赋值为"block"，下同理*/
        btn_hidden.onclick = function(){
            img.style.display = "none";
            /*display: none隐藏后的元素不占据任何空间*/
        }
    }
</script>
```
