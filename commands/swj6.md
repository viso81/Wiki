---
title: "xdg-settings, xdg-open"
id: swj6
lang: zh-CN
tags: [commands, linux, xdg-settings, xdg-open]
os: linux
shell: bash
date: 2026-07-25
---

# xdg-settings, xdg-open


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
