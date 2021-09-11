# NixOS

## Installation

Note: this is for installing ZFS on an existing NixOS installation. To use ZFS as root file system, see below.

默认情况下，`Live-image` 附带 ZFS 支持。

1. 为 ZFS 选项导入单独的配置文件：

   ```
   vim /etc/nixos/configuration.nix
   ##add './zfs.nix' to 'imports'
   # imports = [ ./zfs.nix ];
   ```

2. 配置 ZFS 选项：

   ```
   tee -a /etc/nixos/zfs.nix <<EOF
   { config, pkgs, ... }:
   
   { boot.supportedFilesystems = [ "zfs" ];
     networking.hostId = "$(head -c 8 /etc/machine-id)";
   }
   EOF
   ```

3. 应用配置更改：

   ```
   nixos-rebuild switch
   ```

## Root on ZFS

ZFS can be used as root file system for NixOS. An installation guide is available.

[Start here](https://openzfs.github.io/openzfs-docs/Getting%20Started/NixOS/Root%20on%20ZFS/0-overview.html)

