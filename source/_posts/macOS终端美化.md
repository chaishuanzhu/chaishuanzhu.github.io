---
title: macOS终端美化
tags: [macOS]
category: []
date: 2023-05-28 11:48:22
---

随着官方版本的更新，在你看到这篇文章时，有些配置可能已经过时。请以官方文档为准。

### 安装 [Oh My ZSH](https://ohmyz.sh/)

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
禁用自动更新
```
zstyle ':omz:update' mode disabled 
```

### 安装插件

#### [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)

* 克隆插件到本地
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
* 修改 `~/.zshrc` 文件，添加插件
```
plugins=( [plugins...] zsh-syntax-highlighting)
```
* 使修改生效
```
source ~/.zshrc
```

#### [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md)

* 克隆插件到本地
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
* 修改 `~/.zshrc` 文件，添加插件
```
plugins=( 
    # other plugins...
    zsh-autosuggestions
)
```
* 使修改生效
```
source ~/.zshrc
```

#### [sublime](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/sublime)

* 修改 `~/.zshrc` 文件，添加插件
```
plugins=(... sublime)
```
* 使修改生效
```
source ~/.zshrc
```

### [powerlevel10k](https://github.com/romkatv/powerlevel10k)主题

* 克隆到本地
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
* 修改主题配置 `~/.zshrc`:
```
ZSH_THEME="powerlevel10k/powerlevel10k"
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(os_icon dir vcs) # 配置左侧图标
```

* 下载字体文件
[MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
[MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
[MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
[MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

* 双击下载好的文件完成安装
* 配置终端字体为`MesloLGS NF`

* 使主题修改生效, 在执行这个之前需要配置好字体。不然在`powerlevel10k`引导配置时，图标显示会乱码。
```
source ~/.zshrc
```

### 修改终端配色[iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)

* 克隆仓库到本地
```
git clone https://github.com/mbadolato/iTerm2-Color-Schemes.git
```
* 导入`iTerm2-Color-Schemes`主题文件, Mac 终端选择 `terminal` 文件夹下的文件。
![](image1.png)

### 参考
[ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)
[powerlevel10k](https://github.com/romkatv/powerlevel10k)
[iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)
[10 个 Terminal 主题，让你的 macOS 终端更好看](https://sspai.com/post/53008)

