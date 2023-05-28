---
title: 在不受支持的Mac上安装macOS Ventura
tags: [macOS]
category: [系统安装]
date: 2023-05-28 11:45:02
---

### 使用[OpenCore-Legacy-Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher)在MacBookPro2016安装macOS Ventura

OpenCore 是一个复杂的引导加载程序，可以用来做黑苹果的启动引导。也可以使用它在旧Mac上安装新系统。更多信息请查看[官方文档](https://dortania.github.io/OpenCore-Legacy-Patcher/)

### 系统安装盘制作
![](image1.png)
如图所示，选择 Create macOS Installer 然后按照引导选择制作macOS安装盘。

### 安装系统
安装盘制作完成后会引导你重新启动。重启后按Option键，选择从U盘启动。然后就可以安装macOS Ventura了。在安装过程中会重新启动多次，请耐心等待。注意系统安装完成前不要拔掉U盘。

### 安装补丁
到这一步已经进入系统了。只是还有些驱动不太正常。比如说闪屏，睡眠无法唤醒等。我们需要安装补丁，按下图选择完成操作。
![](image2.png)

### 安装引导
我们还需要最后一步，安装引导。这样拔掉U盘后也能正常进入系统。选择下边的选项完成安装。
![](image3.png)

自定义设置，如果想要无感知的进入系统。可以把 Show OpenCore Boot Picker 这个选项关掉。然后再重新安装引导。上边的Target Model可以根据自己的机型选择。如不知道该选哪个可以查看[这个文档](https://dortania.github.io/OpenCore-Legacy-Patcher/VENTURA-DROP.html)
![](image4.png)
