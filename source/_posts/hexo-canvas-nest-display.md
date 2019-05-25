---
title: Hexo主题Maupassant动态背景canvas-nest显示问题
toc: true
date: 2019-05-25 11:56:20
categories: 
- 技术
tags:
- Hexo
---

为了让自己的个人博客不显得那么单调，发现Maupassant支持动态背景，但是在使用的过程中发现了一点小问题，导致无法使用。
<!-- more -->

### 问题
在使用Maupassant主题时，发现canvas-nest的enable设置为true后还是无法显示。

### 原因
在网上查找使用莫泊桑主题的网友博客发现，可以使用这个功能，然后分析了一下页面代码，发现我的博客没有canvas这个标签的代码。查看js源，发现路径不同。

```js
我的博客：
<script type="text/javascript" color="100,100,100" opacity="0.5" zindex="-2" count="50" src="//lib.baomitu.com/canvas-nest.js/2.0.4/canvas-nest.umd.jscanvas-nest.min.js"></script>

网友博客：
<script type="text/javascript" color="100,100,100" opacity="0.5" zindex="-2" count="50" src="//cdn.bootcss.com/canvas-nest.js/1.0.1/canvas-nest.min.js"></script>
```

### 更改方法
修改themes/maupassant/layout/_partial/after_footer.pug文件

```js
更改前：
script(type='text/javascript', color=color, opacity=opacity, zIndex=zIndex, count=count,src='//lib.baomitu.com/canvas-nest.js/2.0.4/canvas-nest.umd.js')

更改后：
script(type='text/javascript', color=color, opacity=opacity, zIndex=zIndex, count=count,src='//cdn.bootcss.com/canvas-nest.js/1.0.1/canvas-nest.min.js')
```
