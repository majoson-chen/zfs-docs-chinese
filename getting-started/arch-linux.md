# Arch Linux
本文原文链接：https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/index.html


## 概述
由于许可证不兼容，`ZFS` 在 `Arch-Linux` 官方存储库中不可用。

`ZFS` 的支持将存在于第三方储存库中 [archzfs-repo](https://github.com/archzfs/archzfs).

## 安装

> 注意：这是在已经安装了 Arch-Linux 的系统上安装 `ZFS`，如果想将 `ZFS` 作为根文件系统，请参考底下的文章。

1. 添加 `archzfs repo` 到 `pacman` 中, [原文](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/0-archzfs-repo.html)
   1. 导入 `archzfs` 存储库的密钥  
      ```shell
      curl -L https://archzfs.com/archzfs.gpg |  pacman-key -a -
      curl -L https://git.io/JsfVS | xargs -i{} pacman-key --lsign-key {}
      curl -L https://git.io/Jsfw2 > /etc/pacman.d/mirrorlist-archzfs
      ```

   2. 添加 archzfs 储存库  
      ```shell
      tee -a /etc/pacman.conf <<- 'EOF'
      
      #[archzfs-testing]
      #Include = /etc/pacman.d/mirrorlist-archzfs
      
      [archzfs]
      Include = /etc/pacman.d/mirrorlist-archzfs
      EOF
      ```

   3. 更新 `pacman` 数据库  
      ```shell
      pacman -Sy
      ```

2. 根据你的需要安装 [zfs-linux*](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/1-zfs-linux.html) 或者 [zfs-dkms](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/2-zfs-dkms.html)， 有关详细信息，请参阅相应页面。

## 实时镜像
最新实时映像附带的内核包可能与 `ZFS` 不兼容，用户应按照[此处](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/3-live.html)的说明检查内核版本。

## 使用 ZFS 作为根目录

ZFS 可以用作 `Arch-Linux` 的根文件系统。 以下提供了安装指南。

- [Start here](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/0-overview.html).
  - [Overview](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/0-overview.html)
  - [Preparation](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/1-preparation.html)
  - [System Installation](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/2-system-installation.html)
  - [System Configuration](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/3-system-configuration.html)
  - [Optional Configuration](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/4-optional-configuration.html)
  - [Bootloader](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/5-bootloader.html)
  - [Recovery](https://openzfs.github.io/openzfs-docs/Getting%20Started/Arch%20Linux/Root%20on%20ZFS/6-recovery.html)
