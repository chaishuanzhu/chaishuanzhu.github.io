---
title: macOS常用开发工具
tags: [macOS]
category: []
date: 2023-05-28 11:49:48
---

### Mac运行状态监控 [iStat Menus](https://bjango.com/mac/istatmenus/)

> // iStat Menus License
Email: 982092332@qq.com
SN: GAWAE-FCWQ3-P8NYB-C7GF7-NEDRT-Q5DTB-MFZG6-6NEQC-CRMUD-8MZ2K-66SRB-SU8EW-EDLZ9-TGH3S-8SGA

### [Charles](https://www.charlesproxy.com/)抓包工具

> // Charles Proxy License
Registered Name: https://zhile.io
License Key: 48891cf209c6d32bf4

### [Sublime Text]()

[sublime text 4143 license key](https://gist.github.com/opastorello/4d494d627ec9012367028c89cb7a1945)
Mac 下使用Hex Fiend修改sublime_text二进制文件
> * Go to [hexed.it](https://hexed.it/)
> * Click "Open File" and choose your sublime_text.exe **(DON'T FORGET TO BACKUP YOUR EXE FILE)**
> * Go to Search and in "Search for" put: 80 78 05 00 0F 94 C1
> * In Search Type select "Enable replace" and put: 80 78 05 00 0F 94 C1
> * Click "Find next" then "Replace"
> * Do the same thing with: C6 40 05 01 48 85 C9 => C6 40 05 01 48 85 C9
> * Click "Save as" then name it: sublime_text
> * Copy your modified sublime_text.exe to directory Sublime Text
> * codesign --remove-signature /Applications/Sublime\ Text.app/

### [Sketch](https://xclient.info/s/sketch.html)
文件打不开解决办法，使用盗版有风险，经常使用的话建议支持一下正版。
```
sudo codesign -f -s - /Applications/Sketch.app/Contents/MacOS/Sketch
```

### [MacDown](https://macdown.uranusjr.com/)
专为Mac打造的Markdown编辑器，体积小巧，运行速度快。

### [IINA](https://iina.io/)
Mac上最好用的播放器。