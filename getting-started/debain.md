# Debian
原文链接：https://openzfs.github.io/openzfs-docs/Getting%20Started/Debian/index.html

## 安装
>提示： 如果你想将 ZFS 作为你的根文件系统，请参考[Root on ZFS](https://openzfs.github.io/openzfs-docs/Getting%20Started/Debian/index.html#root-on-zfs)

ZFS 包储存在 [contrib repository](https://packages.debian.org/source/zfs-linux)。 但是 [backports repository](https://backports.debian.org/Instructions/) 通常提供更新的版本，你可以按此方式使用他们：

### Add the backports repository:

编辑 `/etc/apt/sources.list.d/buster-backports.list`  
```shell
vi /etc/apt/sources.list.d/buster-backports.list
```

添加如下内容：  
```shell
deb http://deb.debian.org/debian buster-backports main contrib
deb-src http://deb.debian.org/debian buster-backports main contrib
```

编辑 `/etc/apt/preferences.d/90_zfs`  
```shell
vi /etc/apt/preferences.d/90_zfs
``` 

添加如下内容:  
```shell
Package: libnvpair1linux libuutil1linux libzfs2linux libzpool2linux spl-dkms zfs-dkms zfs-test zfsutils-linux zfsutils-linux-dev zfs-zed
Pin: release n=buster-backports
Pin-Priority: 990
```

### 安装软件包

```shell
apt update
apt install dpkg-dev linux-headers-$(uname -r) linux-image-amd64
apt install zfs-dkms zfsutils-linux
```

## 将ZFS作为安装根目录
- [Debian Buster Root on ZFS](https://openzfs.github.io/openzfs-docs/Getting%20Started/Debian/Debian%20Buster%20Root%20on%20ZFS.html)
- [Debian Stretch Root on ZFS](https://openzfs.github.io/openzfs-docs/Getting%20Started/Debian/Debian%20Stretch%20Root%20on%20ZFS.html)

## Related topics
- [Debian GNU Linux initrd documentation](https://openzfs.github.io/openzfs-docs/Getting%20Started/Debian/Debian%20GNU%20Linux%20initrd%20documentation.html)