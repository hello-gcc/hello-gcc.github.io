---
title: STM32学习笔记 之 STM32CubeIDE工程创建和编译
toc: true
date: 2020-05-31 22:35:37
categories:
- 技术
tags:
- STM32
- STM32CubeIDE
---

上篇文章简单介绍了一下STM32CubeIDE工具及其安装，也看了下它的类eclipse界面。本文将介绍如何创建一个STM32工程和基本的操作，以及如何编译出一个可执行文件。

<!--more-->

### STM32CubeIDE 工程创建
#### Type A：新建工程
* 打开 File-> New -> STM32 Project 
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/imgstm32cubeide_build_00.png)
* 在搜索框中输入主控芯片的型号，可以在右侧查找到指定的MCU，点击Next
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/imgstm32cubeide_build_01.png)
* 输入工程名，并且选择相应的编程语言、目标文件和使用的模板工程，点击Finish，这样就创建了一个STM32CubeMX文件
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/imgstm32cubeide_build_02.png)
* 配置完工程下的CubeMX文件之后，选择Project Manager选项卡，配置生成相应的工程文件
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/imgstm32cubeide_build_03.png)
* 配置时钟和相应的GPIO口
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_04.png)
* 此时保存.ioc文件，提示是否生成代码，点击Yes，则生成工程代码
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_05.png)
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_06.png)

#### Type B：通过CubeMX文件创建工程
* 如果已经有CubeMX生成的ioc文件，则可以打开 File -> New -> STM32 Project From STM32CubeMX .ioc File，相应的文件
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_07.png)
* 打开指定的ioc文件，点击Finish，然后就是配置文件生成代码，同上述Type A方法类似，不再赘诉
 ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_08.png)

### STM32CubeIDE 工程编译
#### 工程简介
* 工程创建后，生成了对应的代码，从上述的图片中可以看到工程中的主要几个文件夹：Includes、Core、Drivers已经ioc和ld文件

|  Folder | Description |
| --- | --- |
| Includes |  所有库的头文件 |
| Core     |  用户编码文件和头文件 |
| Drivers  |  CMSIS和HAL库文件和头文件 |


#### 编译环境配置和结果
* 右键点击工程，选择Properties，打开选项卡，C/C++ Build --> Settings进行编译相关配置
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_09.png)
* 在Tool Settings选项卡下：
  * 编译输出配置MCU Post build outputs，指定输出文件为hex和bin
  * 汇编配置MCU GCC Assembler
  * 编译配置MCU GCC Compiler，头文件，宏定义，优化等级等
  * 链接配置MCU GCC Linker，链接库等
    ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_10.png)
* 点击构建图标，编译当前工程
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_11.png)
* 编译成功后，在工程浏览栏中，将会出现工程名相同的二进制文件和Debug文件夹，即为需要download到stm32f103c8t6开发板中的文件
  ![](https://cdn.jsdelivr.net/gh/hello-gcc/blog_pic_bed/stm32cubeide_build_12.png)

### 后记
* 至此，STM32CubeIDE工程创建的基本步骤算完成了，我们生成了需要的可执行文件，接下来将会记录调试功能，以及非常棒的在线调试相关功能。