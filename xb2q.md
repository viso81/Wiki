---
title: "XDG 规范"
id: xb2q
lang: zh-CN
date: 2026-07-27
tags: [linux,XDG]
---

# XDG 规范
由freedesktop.org维护的开放标准,用以统一linux下跨发行版,跨桌面配置

# 核心环境变量和默认路径
|环境变量|默认路径(用户级)|系统路径(共享)|用途|
|:------:|:--------------|:------------|:--|
|XDG_DATA_HOME|~/.local/share/|/usr/share/,<br> /usr/local/share/|应用的数据,插件,主题等持久数据|
|XDG_CONFIG_HOME|~/.config/|/etc/xdg/,<br> /usr/share/config/|应用配置文件|
|XDG_STATE_HOME|~/.local/state/|/var/lib|日志,历史记录等非持久数据|
|XDG_CACHE_HOME|~/.cache/|/var/cache/|缓存|
|XDG_RUNTIME_DIR|/run/user/$UID/|-|运行时数据
