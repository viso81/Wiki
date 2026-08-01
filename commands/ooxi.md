---
title: "scoop"
id: ooxi
lang: zh-CN
tags: [commands, windows, scoop, 包管理器]
os: windows
date: 2026-08-01
---

# scoop


## 安装
```console

```

## 命令
```shell
# 安装
& scoop install <软件名>
# 卸载
& scoop uninstall <软件名>
# 强制删除残留目录+注册表链接
# 注意--purge连同用户数据,配置文件一并删除
& scoop uninstall <软件名> --purge
# 清理旧版本Shims快捷方式
& scoop reset *
# 列表
& scoop list
# 清理卸载后的孤儿依赖
& scoop cleanup *
# 强制清理所有就版本软件
& gsudo scoop cleanup * --global
# 查看下载缓存包占用
& scoop cache
# 清除所有缓存包
& scoop cache rm *
# 更新所有bucket索引,修复损坏记录
& scoop bucket update
# 检查已安装应用的完整性,列出以常列表
& scoop checkup

```
