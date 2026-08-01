---
title: "Arch + chezmoi 系统迁移清单"
---
# Arch + chezmoi 系统迁移清单

> 用途：换新机器 / 重装系统时，按顺序迁移 Arch Linux + chezmoi 管理的配置

## 0. 迁移前准备（旧系统）

- [ ] 导出显式安装的包列表
  ```bash
  pacman -Qqe > pkglist.txt
  ```
- [ ] 导出 AUR 包列表
  ```bash
  pacman -Qqem > aurlist.txt
  ```
- [ ] 把 `pkglist.txt`、`aurlist.txt` 纳入 chezmoi 管理或单独备份到云端/U盘
- [ ] 确认 chezmoi source 目录无未提交改动，并推送到远程
  ```bash
  chezmoi cd
  git status
  git push
  ```
- [ ] 备份加密密钥（如果 chezmoi 用了 age/gpg 加密敏感文件）
- [ ] 备份 SSH key、GPG key（如果没有走 chezmoi 加密方案）
- [ ] 记录当前显卡驱动、多显示器布局、输入法等硬件相关配置（截图或写备注）

## 1. 新机器：安装基础系统

- [ ] 完成 Arch 基础安装（archinstall 或手动分区、引导、网络）
- [ ] 确认能联网、能用终端

## 2. 批量恢复软件包

- [ ] 官方仓库包
  ```bash
  sudo pacman -S --needed - < pkglist.txt
  ```
- [ ] AUR 包（视你用的 helper，如 yay/paru）
  ```bash
  yay -S --needed - < aurlist.txt
  ```

## 3. 安装 chezmoi 并拉取配置

- [ ] 安装并初始化
  ```bash
  sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply <your-github-username>
  ```
- [ ] 如有加密文件，提前放好私钥，否则 apply 会报错

## 4. chezmoi 管不到的部分（手动检查）

- [ ] systemd 服务：`systemctl enable` 需要的服务
- [ ] 显卡驱动是否装对（NVIDIA/AMD/Intel）
- [ ] 多显示器 / 分辨率配置
- [ ] 输入法（fcitx5 / ibus 等）
- [ ] 字体安装
- [ ] 音频（PipeWire/PulseAudio）是否正常出声
- [ ] SSH key、GPG key 权限是否正确（`chmod 600`）

## 5. 收尾验证

- [ ] 打开常用软件，逐一确认能正常启动
- [ ] 跑一遍常用开发环境（编译、运行项目）
- [ ] 对照旧机器的工作流，检查有没有遗漏的配置或习惯性快捷键

---

*最后更新：迁移完成后可以把这份清单标记为「已完成 YYYY-MM-DD」，方便下次复用*
