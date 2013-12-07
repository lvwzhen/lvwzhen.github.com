---
layout: post
title: 用 CSS3 gradient 绘制iOS7图标
---

随着css3的推广，css3的各种属性也都尝试着使用在现代浏览器中了。今天也来熟悉下css3的gradient渐变属性。

**gradient 语法** 

    /* 语法，参考自: http://webkit.org/blog/175/introducing-css-gradients/ */
    -webkit-gradient(<type>, <point> [, <radius>]?, <point> [, <radius>]? [, <stop>]*)
    -webkit-linear-gradient([ <point>,]? <color-stop>[, <color-stop>]+);
    /* 实际用法... */
    background: -webkit-gradient(linear, 0 0, 0 100%, from(#FFDD0A), to(#FA130B));
    background: -webkit-linear-gradient(top, #FFDD0A,#FA130B);

实例如下：

![test1](http://iout.in/demo/apple-icon/test1.png)

从上到下

参数用法：

    <point>
    left：设置左边为渐变起点的横坐标值。
    right：设置右边为渐变起点的横坐标值。
    top：设置顶部为渐变起点的纵坐标值。
    bottom：设置底部为渐变起点的纵坐标值。
    <angle>：用角度值指定渐变的方向（或角度）。
    <color-stop>：指定渐变的起止颜色。
    <length>：用长度值指定起止色位置。不允许负值
    <percentage>：用百分比指定起止色位置。

下面是不同方向，不同渐变方式的用法。

从左到右：

![test2](http://iout.in/demo/apple-icon/test2.png)

`background:  -webkit-linear-gradient(left, #FFDD0A, #FA130B);`

角度渐变：

![test3](http://iout.in/demo/apple-icon/test3.png)

`background:  -webkit-linear-gradient(60deg, #A80F81, #FFDD0A);`

径向渐变:

![test4](http://iout.in/demo/apple-icon/test4.png)

`background:  -webkit-radial-gradient(#FFDD0A, #FA130B, #A80F81);`

多色渐变:

![test5](http://iout.in/demo/apple-icon/test5.png)

`background:  -webkit-gradient(linear, center top,center bottom, from(#66B828), color-stop(0.32, #FFDD0A), color-stop(0.48, #FF6D06), color-stop(0.60, #FA130B), color-stop(0.76,#A80F81), to(#0895C3));`

[Demo](http://iout.in/demo/apple-icon/test.html)

以上demo都只写了webkit的前缀，如需要支持其他浏览器还需要加上"-moz,-ms,-o"等厂商前缀，想不这么麻烦就等着web标准一统天下那时候吧。

了解了gradient的基本属性就可以根据自己的需要，组合使用渐变做出自己想要的效果。以下便是利用gradient做出两个简单的苹果图标，等有时间把一套iOS7一套图标都画出来玩玩。

<a href="http://iout.in/demo/apple-icon/" target="_blank"><img src="http://iout.in/demo/apple-icon/demo.png" alt=""></a>
