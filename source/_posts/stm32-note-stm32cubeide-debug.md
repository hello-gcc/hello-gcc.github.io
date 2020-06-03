---
title: STM32学习笔记 之 STM32CubeIDE调试
toc: true
date: 2020-06-03 21:53:50
categories:
- 技术
tags:
- STM32
- STM32CubeIDE
---

接上篇工程编译和构建，本文记录如何使用STM32CubeIDE的在线调试功能，以及调试过程中相关的工具使用。

<!--more-->
### 调试配置
* 点击debug配置工具，选择Debug Configuration
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_debug_00.png)
* 新建调试，STM32 Cortex-M C/C++ Application
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_debug_01.png)
* 调试配置文件路径
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_debug_02.png)
* 配置调试器
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_debug_03.png)

### 在线调试
* 点击Debug就可以开始调试了，此时，程序进入main函数，并且会停在入口的init函数```HAL_Init()```

### 调试工具
* 在调试过程中，有非常多的工具可以使用，为我们调试程序带来便捷，并且在出现异常退出或者段错误时，调试窗口可以给出出错前调用的函数，非常实用的功能
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_debug_04.png)