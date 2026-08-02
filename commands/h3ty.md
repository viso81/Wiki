---
title: "git"
id: h3ty
lang: zh-CN
tags: [commands, linux, windows, git]
os: linux
shell: bash
date: 2026-07-25
---

# command: git
版本控制,团队协作的软件


## 冲突处理
```shell
# 罗列冲突
git diff --name-only --diff-filter=U

# <<<<<<<< HEAD
# (本机内容)
# ============
# (远程内容)
# >>>>>>>> .
git diff <冲突文件名>
# 保留本地
git checkout --ours <冲突文件名>
git add <冲突文件名>
# 保留远程
git chechout --theirs <冲突文件名>
git add <冲突文件名>
```


## 本地分支改名
```shell
git branch -m master main # 本地masteer分支改名为main
git branch --set-upstream-to=origin/main main # 让本地main分支跟踪远程main分支
git pull
# 分支追踪
git branch --set-upstream-to=<远程分支> <本地分支>
git pull
```


## - 查看及修改配置
```shell
# 查看代理
git config --global --get http.proxy
git config --global --get https.proxy
# 设置代理
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890
# 个人项目一键提交执行该命令后可以用`git up`一键提交
git config --global alias.up '!git add -A && git commit -m "update $(date +%Y-%m-%d)" && git push'
# 全局
git config --global --list
git config --global --edit  
# 本地
git config --local --list
git config --local --edit
# 查看具体字段来源
git config --show-origin --get user.name
# 查看所有生效配置及来源
git config --list --show-origin
```


## 创建项目
```bash
# 创建项目目录
mkdir project
# 进入目录
cd project
# 初始化项目
git init
# 添加该项目下所有文件
git add -A
# 第一次提交
git commit -m "init project"
# 设置远程仓库
git remote add origin https://github.com/你的用户名/project.git
# 检查远程仓库
git remote -v
# 指向分支
git branch -M main
# 推送至远程仓库
gir push -u origin main
# 修改本地分支名
git branch -m <原名> <改名>
```


## git换ssh连接
国内用http和https不稳，换成ssh后使用起来方便很多
- 建立
```bash
ssh-keygen -t ed25519 -C "你的邮箱"
cat ~/.ssh/id_ed25519.pub
```
把输出内容复制，去 GitHub → Settings → SSH and GPG keys → New SSH key，粘贴保存。然后远程地址要用 SSH 格式，不是 https：
```bash
ssh -T git@github.com
git remote set-url origin git@github.com:viso81/项目.git
git push -u origin main
```
- 克隆
```bash
# SCP风格
git clone git@github.com:你的用户名/项目.git
# ssh://URL风格
git clone ssh://git@github.com/你的用户名/项目.git
```
- 指定远程项目
```bash
git remote set-url origin git@github.com:你的用户名/你的项目.git
```
