---
title: "windows使用注册表在右键菜单加入helix编辑"
id: iosq
lang: zh-CN
date: 2026-08-17
tags: [windows, reg, helix]
---

# windows使用注册表在右键菜单加入helix编辑

- 找到`HKEY_CLASSES_ROOT\*\shell\`
- 新建一项:`用helix编辑`
- 在用helix编辑项中新建项:`command`
- 在command项中双击默认项并写入值: `conhost.exe "C:\User\<用户名>\scoop\shims\hx.exe" "%1"`
