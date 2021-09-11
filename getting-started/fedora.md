# Fedora
原文链接： https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/index.html

## 安装

> 注意：这是在已经安装了 Fedora 的系统上安装 `ZFS`，如果想将 `ZFS` 作为根文件系统，请参考底下的文章。

1. 如果安装了来自 Fedora 官方仓库的 `zfs-fuse`，请先将其删除。 它不受维护，不应在任何情况下使用：

   ```shell
   dnf remove -y zfs-fuse
   ```

2. 添加 ZFS 报告源:

   ```shell
   dnf install -y https://zfsonlinux.org/fedora/zfs-release$(rpm -E %dist).noarch.rpm
   ```

3. 安装 ZFS 软件包:

   ```
   dnf install -y kernel-devel zfs
   ```

4. 加载内核模块:

   ```
   modprobe zfs
   ```

   如果内核模块加载失败，你的内核版本可能是不被 OpenZFS 支持的，尝试安装一个 `长期支持版(LTS)` 的内核：

   ```
   dnf copr enable -y kwizart/kernel-longterm-5.4
   dnf install -y kernel-longterm kernel-longterm-devel
   ```

   重启，然后加载内核模块
   ```
   modprobe zfs
   ```

   这可能需要重新编译模块：
   ```
   ls -1 /lib/modules \
   | while read kernel_version; do
     dkms autoinstall -k $kernel_version
   done
   ```

5. 通常情况下， 只有在 ZFS 内核监测到储存池时才加载内核模块。可以设置开机时自动加载模块：

   ```
   echo zfs > /etc/modules-load.d/zfs.conf
   ```

## 测试源

你可以使用最新版本的测试 OpenZFS。但是这些包**不应该**用于生产系统。

```shell
dnf config-manager --enable zfs-testing
dnf install zfs
```

## 在根目录使用ZFS

ZFS 可以用作 Fedora 的根文件系统。 以下提供安装指南。

[Start here](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/0-overview.html).
- [Overview](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/0-overview.html)
- [Preparation](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/1-preparation.html)
- [System Installation](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/2-system-installation.html)
- [System Configuration](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/3-system-configuration.html)
- [Optional Configuration](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/4-optional-configuration.html)
- [Bootloader](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/5-bootloader.html)
- [Recovery](https://openzfs.github.io/openzfs-docs/Getting%20Started/Fedora/Root%20on%20ZFS/6-recovery.html)