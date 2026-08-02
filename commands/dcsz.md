---
title: "fzf"
tags: [linux, commands, fzf]
os: linux
shell: bash
date: 2026-07-25
---

# command: fzf
从标准输入接收一份列表（文件名、命令历史、任何文本行都行），你输入几个字符做模糊匹配，实时过滤出结果，用方向键选、回车确认。本质是一个"交互式过滤器"

## 命令
```bash
ls -al | fzf
# 用zk输出所有文档路径传送给fzf，之后用glow打开选择的文档
zk list --format "{{abs-path}}" --no-pager | fzf --preview 'glow -s dark {}'
```
