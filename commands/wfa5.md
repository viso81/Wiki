---
title: "chezmoi"
id: wfa5
lang: zh-CN
tags: [commands, linux, chezmoi]
date: 2026-07-26
---

# command: chezmoi
配置同步管理软件

## 命令
```bash
chezmoi add <文件>         # 把文件加入管理
chezmoi re-add <文件>      # 修改文件后重新同步到源
chezmoi add --force <文件> # 同上
chezmoi managed            # 查看管理的文件
chezmoi edit <文件>        # 编辑源文件
chezmoi diff               # 查看当前和源状态有什么差异
chezmoi status             # 简洁差异列表
chezmoi apply              # 把源状态应用到当前系统
chezmoi apply -v           # 详细显示应用过程
chezmoi apply -n -v        # 只看做什么，不真正做
chezmoi cd                 # 进入源目录
chezmoi doctor             # 查看健康状态
chezmoi source-path ~/.config/fish/config.fish # 查看某个文件在源目录的真实路径
chezmoi add --force ~/.local/bin/bat-smart     # 强制重新添加（覆盖源状态)
chezmoi forget ~/<文件>                        # 删除管理(但不会删除文件)
```

## 目录
```bash
chezmoi add -r <目录>         # 增加目录到管理
chezmoi add -r --exact <目录> # apply时会消除目录下多余的文件，强制跟源对齐
chezmoi managed | grep <目录> # 确认目录
chezmoi chattr exact <目录>   # 为已管理目录增加exact
chezmoi unmanaged <目录>      # 查看目录下哪些文件未被管理
```
