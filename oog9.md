---
title: "trans"
id: oog9
lang: zh-CN
tags: [commands, ]
os: 
date: 2026-08-01
---

# trans
translate-shell是一款命令行下翻译软件

## 安装
```shell
# arch
& sudo pacman -S translate-shell
```

## 命令
```shell
# 将目标语言翻译为默认语言
# 默认语言可以在 ~/.config/translate-shell/init.trans中加入:
# set target zh-CN
# -b 省略读音标注,只输出翻译文本
trans -b "世界你好"
# 将目标语言从中文翻译为英文
trans -b zh:en "这是中文"
# 将目标语言翻译为中文
trans -b -t zh "hello world"
# 使用google引擎翻译目标语言为中文
trans -b -e google -t zh "hello world"
# 同上,用bing引擎
trans -b -e bing -t zh "hello world"
```
