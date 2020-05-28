---
title: STM32学习笔记 之 STM32CubeIDE安装和基本功能介绍
toc: true
date: 2020-05-27 22:57:29
categories:
- 技术
tags: 
- STM32
---


> 凡事预则立，不预则废 ———— 《礼记·中庸》

离上篇文章发布已经很久没有更新了，其实“预”了很久，Flag也“立”了很多个，但是呢，没有付诸行动。说多了就是掩饰，啥都不多说，直接开篇。
<!--more-->

### STM32CubeIDE是个啥？
* 第一眼看到这个软件的名字，就马上想到了STM32CubeMX这个可视化的芯片参数配置工具，总感觉它俩之间有着千丝万缕的关系。其实，这俩还真有关系。
* 先来看看官方的解释：
  - STM32CubeIDE is an all-in-one multi-OS development tool, which is part of the STM32Cube software ecosystem
  - 这货属于STM32Cube软件生态中的一个多平台、高度集成的开发工具
* 再来看看官方的图片：
  ![](/img/stm32/stm32cubeide-install-01.jpg)
* 这下是不是看明白了？还不明白，再贴个图：
  ![](/img/stm32/stm32cubeide-install-02.png)
* 这一行工具栏，怎么这么眼熟，这个不就是它么？
  <img src="/img/stm32/stm32cubeide-install-03.png" width="50%" height="50%">
* 开始懂了

### STM32CubeIDE软件获取和安装
1. 下载
* 支持系统：Windows、Linux、MacOS
* 官方链接：[STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html#get-software)
2. 安装
* 这个就比较简单了，作为一个程序员，安装路径就不要用中文了吧...

### STM32CubeIDE界面简介
1. 工程路径选择：启动软件后，选择一个路径作为Workspcace，然后就Launch如下图所示：
   ![](/img/stm32/stm32cubeide-install-04.png)
2. 工具栏介绍：如果经常使用eclipse开发C/C++程序，这个界面就非常熟悉了，较eclipse工具增加一个CubeMX配置插件
   ![](/img/stm32/stm32cubeide-install-05.png) 
3. 暂时就先简单介绍这么多，下次再记录工程创建和编译调试相关内容