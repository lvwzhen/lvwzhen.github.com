---
layout: post
title: Markdown+Pandoc 最佳写作拍档
date: 2013-12-08 00:22
---


###我们为什么写作？
自从人们开始写作，写作便是记录、抒发、批判、反省的好工具。从石板上的刻印到笔墨纸砚，再到如今的信息时代。从静态的个人主页到托管博客，从个人博客到微博，从wordpress到jekyll。无数投入写作中的人们写作的目的大同，写作的方式越简单越好，这样才能让我们专注于写作而不是为其他格式所困扰。另外现在智能终端快速普及，文件格式的多平台使用也成为了写作的一大问题。

为了更好的写作,今天介绍的 Markdown & Pandoc 便能提供完美的辅助。

###Markdown的用法

####1 .Markdown是什么?

>Markdown 是一种轻量级标记语言，创始人为John Gruber和Aaron Swartz。它允许人们“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档”。这种语言吸收了很多在电子邮件中已有的纯文本标记的特性。 [[1]](https://zh.wikipedia.org/wiki/Markdown)

####2 .为什么要用Markdown?

windows下常用的编辑工具是word,mac上常用的编辑工具是page,linux上常用的编辑工具就是vim了，一份文章编辑完后为了要在不同平台中保存完整的模样时就必需同时准备多种文本格式的文件，这是多么痛苦的一件事。我们写作的初衷是为了写作呀，反而被这些格式烦恼。所以我们要用Markdown,它让你关注内容，格式怎么显示不是要你在写得时候关注的。而在写Markdown时你只需要用一个纯文本的方式进行，不用担心平台与格式的困扰。

####3 .Markdown的语法

Markdown 的语法全由一些符号所组成，这些符号经过精挑细选，其作用一目了然。比如：在文字两旁加上星号，看起来就像*强调*。Markdown 的列表看起来，嗯，就是列表。Markdown 的区块引用看起来就真的像是引用一段文字，就像你曾在电子邮件中见过的那样。


**最常用格式**

	 空一行（两个回车）分段
	 行末加两个或多个空格才是真正的换行，否则正常的一个回车就像在 HTML 代码中一样，被当作空格处理
	 插入链接： 	[链接文字](url) 
	 图片跟链接很像，在前面加个叹号：![alt 文字](图片 URL)

**列表**

	* 无序(没有编号的)列表中的一项
    * 一个子项，要以一个制表符或者4个空格缩进
	* 无序列表中的另一个项
	1. 有序(排好序，有编号的)列表中的一项
	2. 有序列表中的另一个项

**标题**

    # 一级标题

    #### 四级标题

	一级标题
	===================

	二级标题
	--------------------

**代码**

代码可以采取两种方法：

一是用（`）将代码包起来
	
	夹杂着`一些代码`的文字内容,

二是在代码块前面加上4个空格或者一个TAB

			
		import random

		class CardGame(object):
		    """ a sample python class """
		    NB_CARDS = 32
		    def __init__(self, cards=5):
		        self.cards = random.sample(range(self.NB_CARDS), 5)
		        print 'ready to play'

代码高亮可以由github提供的js实现

**分割线**

要生成水平分割线，可以在单独一行里输入3个或以上的短横线、星号或者下划线实现。短横线和星号之间可以输入任意空格。以下每一行都产生一条水平分割线。

	===========
	************
	_ _ _ _ _

Markdown的常用语法差不多就是这些了，详细的介绍请参考[Markdowm 语法说明](http://wowubuntu.com/markdown/)

####4 .Markdown的常用编辑工具

* Mac等平台下推荐[Mou](http://mouapp.com/)
* Windows平台推荐[MarkdownPad](http://markdownpad.com/)
* [Sublime Text](http://www.sublimetext.com/)编辑器是我的最爱，并且它是跨平台的，结合[Markdown preview](https://github.com/revolunet/sublimetext-markdown-preview)插件能更好的编辑
* [markdown-here](https://github.com/adam-p/markdown-here)借助Chrome插件，将gmail、Evernote、Hotmail等写作窗口变为Markdown在线写作窗口
* web版推荐国人[草依山](http://jser.me/)写的[MaHua](http://mahua.jser.me),支持vim快捷键和多种主题。

Markdown越来越流行，不是因为它复杂，而是因为它足够简单。尝试过MD后就能体会到单纯的写作带来的快乐，一般Markdown文件保存格式都是以md、mdownx现实。为了文档的分享,多平台的使用，需要对MD进行格式转化。这是就更体现了它的方便之处，它是本身是一个结构标记语言，能对多种格式文档进行转换，这里介绍一款强大的格式转换工具 **Pandoc** 。

###Pandoc 格式转换的瑞士军刀

####1 .Pandoc的介绍

>Pandoc是一个用于从一种标记格式转换为另一种的Haskell库，它的功能是在多种常见的标记语言进行相互转换。

其中包括 Markdown, reStructuredText, Textilte, HTML, PDF,LaTeX 等。利用它，你可以用简单的 Markdown 语法生成pdf文档，还可以写 Beamer 演示文稿。更强大的是，它还能将以上提到的这些语言所写文件转换成 xdoc 文档。下面这张图展示了 Pandoc 让人吃惊 的功能集，不愧为文件转换中的瑞士军刀：

![ pandoc ](http://iout.in/demo/pic/pandoc.jpg)

####2 .Pandoc的用法

#####2.1 Web版Pandoc
首先我们可以看下Pandoc的官网 <http://johnmacfarlane.net/pandoc/>

在介绍中我们知道Pandoc支持linux,Mac OS,Win多平台，还有简易的web版提供我们在线转换格式。打开web版 <http://johnmacfarlane.net/pandoc/try>,便可以进行简单的格式转换了。不过网页版的反应速度不是很快，不适合大型文件的格式转换，一两篇文章还是可以的。

![webpandoc](http://iout.in/demo/pic/webpandoc.png)

#####2.2 Linux版Pandoc
就我自己用的ubuntu下安装Pandoc,还算是非常简单的。以下是ubuntu下的使用步骤:

	sudo apt-get install pandoc

如果apt-get安装的pandoc功能不齐全，可以如官网上一样先安装cable,再安装pandoc:

	sudo apt-get install cabal-install
	cabal update
	cabal install pandoc

然后就可以尝试着用一下了：
	
	pandoc demo.md -o demo.html

这样便可以简单的将demo的markdown文件转换成html文档了。另外还可以强制格式转换如下：

	pandoc demo.txt -o demo.html -f markdown -t html

上面的代码便是将demo.txt中的文档以markdown的格式转换成html并存入demo.html中了。

最关键的 **PDF文件** 到了，PDF文档能在不同平台保持一致的表现，是许多文档传输的首选。在转换PDF之前,还需要安装一个texlive的包：

	 sodu apt-get install texlive

然后便可以自如的转换PDF文件了：

	pandoc demo.md -o demo.pdf

英文文件转换状况良好，中文字体问题请参考[Pandoc 用命令行转换标记语言](http://www.openfoundry.org/tw/foss-programs/8814-pandoc-)

Markdown与Pandoc的用法也就说到这了，无疑它们搭配起来会让写作变得更加简单专注，这也就是我们的初衷。另外在写作中多结合Git,将文档推到GitHub上会是很好的尝试。

#####参考文档
+ [Markdown写作浅谈](http://www.yangzhiping.com/tech/r-markdown-knitr.html) , 阳志平
+ [黑魔法利器pandoc](http://yanping.me/cn/blog/2012/03/13/pandoc/) , 雁起平沙
+ [Pandoc 用命令行转换标记语言](http://www.openfoundry.org/tw/foss-programs/8814-pandoc-) , 林雪凡
+ [Pandoc 官网](http://johnmacfarlane.net/pandoc) , John MacFarlane
+ [Markdown 语法说明](http://wowubuntu.com/markdown/) , riku
