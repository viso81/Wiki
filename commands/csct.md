---
title: "wmux"
id: csct
lang: zh-CN
tags: [commands, wmux, windows]
os: 
date: 2026-08-01
---

# command: wmux


## 安装
```console
cargo install wmux
```

## 命令
```shell
wmux new          # 创建持久会话，脚本放里面跑
Ctrl+B 然后 d     # detach 脱离会话（进程后台继续跑，窗口关掉也不死）
wmux ls           # 查看所有后台会话（等价 jobs）
wmux attach       # 重新拉回前台（等价 fg）
wmux attach -t xxx # 指定会话恢复
```
