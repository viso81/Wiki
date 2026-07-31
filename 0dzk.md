---
title: "qemu安装"
id: 0dzk
lang: zh-CN
date: 2026-07-31
tags: []
---

# qemu安装

## arch

- **建立镜像**

'''shell

& fsutil file createnew D:\vm\qemu\vars.fd 3653632
& copy "C:\Program Files\qemu\share\edk2-x86_64-code.fd" D:\vm\qemu\code.fd

& qemu-img create -f qcow2 arch.qcow2 60G

& qemu-system-x86_64 -m 8192 -smp 4 -accel whpx `
  -drive if=pflash,format=raw,readonly=on,file=code.fd `
  -drive if=pflash,format=raw,file=vars.fd `
  -cdrom d:\downloads\archlinux-2026.07.01-x86_64.iso -boot d `
  -hda arch.qcow2 `
  -vga std -display sdl,grab-mod=rctrl,gl=off `
  -audiodev dsound,id=snd0 `
  -device intel-hda -device hda-duplex,audiodev=snd0 `
  -netdev user,id=net0 -device e1000,netdev=net0

'''

- **安装arch后**

```shell

# 测试能不能联通网络
ping -c 3 archlinux.org
# 启动
timedatectl set-ntp true
# 查看分区
lsblk

# 分区
# cfdisk /dev/sda
# 简单分区就是512M的EFI分区,其他全部分为root分区
# 格式化
mkfs.fat -F32 /dev/sda1
mkfs.ext4 /dev/sda2

# 挂载
mount /dev/sda2 /mnt
mount --mkdir /dev/sda1 /mnt/boot

# 换源
reflector --country China --latest 10 --sort rate --save /etc/pacman.d/mirrorlist
# 安装基础系统
pacstrap -K /mnt base base-devel linux linux-firmware grub efibootmgr networkmanager sudo vim git fish
# 生成fstab
genfstab -U /mnt >> /mnt/etc/fstab
# 
cat /mnt/etc/fstab
# chroot
arch-chroot /mnt

```

- **arch-chroot**
```shell

# 时区
ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
hwclock --systohc


```
