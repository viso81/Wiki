---
title: "linux 常用命令"
id: swj6
lang: zh-CN
tags: [commands, linux, bash]
os: linux
shell: bash
date: 2026-07-25
---

# linux 常用命令


## xdg-settings
```bash
# 查看能用的浏览器
ls /usr/share/applications/ | grep -i browser
# 设置默认浏览器为qutebrowser
xdg-settings set default-web-browser qutebrowser.desktop
# 确认你的的默认浏览器
xdg-settings get default-web-browser
# 用默认浏览器打开链接
xdg-open https://github.com

```

## wl-copy
从命令哈复制字符到系统剪切板,必须是Wayland环境
```bash
cat 文件 | wl-copy
# 安装
sudo pacman -S wl-clipboard
```
