---
title: Hexo 之 主题Maupassant侧边栏增加音乐Aplayer
toc: true
date: 2019-05-27 22:20:08
categories:
- 技术
tags:
- Hexo
---

在Hexo的Maupassant主题下，为了使博客的功能更加完善，增加音乐播放模块，看了Maupassant主题作者的ISSU，发现并没有该功能的实现，不过从部分网友的折腾过程来看，使用Aplayer实现的效果是最好的。
<!-- more -->

### 需求
网上查找了许多Hexo增加音乐播放的文章，大部分是在博客文章中添加音乐播放功能，而且接口封装非常便捷。自己就思考，可不可以将播放功能增加到侧边栏。

### 方案
主流的方案有以下几种：
1. 通过网易云的外链生成iframe代码或者flash代码，插入个人需要将音乐模块放置的地方
2. 通过Aplayer插入播放音乐功能
3. 通过Hexo-tag-aplayer引入Aplayer
4. 通过Aplayer和MetingJS接口，将class为aplayer的div插入相应的位置

### 分析
1. 方案一（网易云外链代码插入）
    - 优点：方便快捷，直接通过因为就可以生成代码
    - 缺点：有版权的歌曲无法无法播放，尺寸有限制
2. 方案二（Aplayer插入）
    - 优点：界面美观，尺寸自适应
    - 缺点：需要配置音乐的url，比较麻烦
3. 方案三（Hexo-tag-aplayer引入Aplayer）
    - 优点：非常便捷，直接根据id或者list id就可以播放
    - 缺点：目前只能在文章中引用
4. 方案四（MetingJS和Aplayer结合使用）
    - 优点：可以音乐播放添加到任何位置，自适应，根据音乐id或列表list id就可以播放音乐
    - 缺点：需要更改主题脚本文件
  
### 实战
由于个人的需求是侧边栏实现音乐播放功能，通过上述的对比，最终现在方案四，具体的修改方法如下：
- 在Maupassant主题路径增加文件
  themes/maupassant/layout/_widget/aplayer.pug ，文件内容如下
```js
.widget
  link(rel="stylesheet", type='text/css', href="https://cdn.jsdelivr.net/npm/aplayer@1.10/dist/APlayer.min.css")
  script(type='text/javascript', src="https://cdn.jsdelivr.net/npm/aplayer@1.10/dist/APlayer.min.js")
  script(type='text/javascript', src="https://cdn.jsdelivr.net/npm/meting@1.2/dist/Meting.min.js")
  
  div(class="aplayer", data-id="2578068117" ,data-server="netease" ,data-type="playlist" ,data-listmaxheight="98px",data-theme="#FF4081")
```
- 修改Maupassant主题下的配置文件
  themes/maupassant/_config.yml , 在widgets标签下增加aplaye ，修改如下：
```yml
widgets: ## Six widgets in sidebar provided: search, category, tag, recent_posts, rencent_comments and links.
  - aplayer 
  - search
  - category
  - tag
  - recent_posts
  - recent_comments
  - links
```
- 编译博客
  执行hexo g生成博客代码

- 本地部署
  执行hexo s部署本地localhost:4000

- 服务器部署
    执行hexo d部署到github page
    
- 效果
  ![Aplayer](/img/aplayer.png)
