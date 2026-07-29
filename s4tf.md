---
title: "windows下修改默认输入法为hx"
id: s4tf
lang: zh-CN
date: 2026-07-29
tags: [windows, regedit, 注册表]
---

# windows下修改默认输入法为hx

## - 右键添加"用Helix编辑"
在HKEY_CLASSES_ROOt/*/Shell/里新建项,名为:用Helix编辑,建好之后shell下有个默认的字段双击,在数值数据里中输入
`conhost.exe "C:\Users\<你的用户名>\scoop\shims\hx.exe" "%1"`

## - 修改文件默认编辑器
比如修改bat的默认编辑器,搜索"batfile"
在batfile/shell/edit/command/的默认字符串内输入
`conhost.exe "C:\Users\<你的用户名>\scoop\shims\hx.exe" "%1"`
