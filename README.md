# OpenZFS

本文是针对于 `OpenZFS` \(以下简称 `ZFS` \)官网内容进行的第三方翻译和补充, 遵循开源协议, 本文只提供参考, 不构成任何实际建议, 本人对由本文所造成的任何损失不承担责任.

OpenZFS官网wiki: [https://openzfs.org/wiki/Main\_Page](https://openzfs.org/wiki/Main_Page)

**注意:** 本文会对官网内容剔除一些不必要的内容以减少翻译工作量，同时，会在原文的基础上补充一些提示以助于读者阅读。

本人课余时间有限, 课业紧张, 欢迎前往 [GitHub](https://github.com/Li-Lian1069/zfs-docs-chinese) 提交 `Pull Request` 共同参与翻译.

## 简介

`OpenZFS` 是一个开源存储平台，在具有传统文件系统功能的基础上有更多先进的功能和特性。

包括：

* 防止数据损坏，支持数据和元数据的完整性检查。
* 持续的完整性验证和自动修复
  * 数据冗余与镜像，`RAID-Z1/2/3` \[和 `DRAID`\]
* 支持高存储容量——高达 256 万亿 yobibytes \(2^128 字节，大到足以装下世界上所有数据\)
* 使用 `LZ4`、`GZIP` 或 `ZSTD` 透明压缩节省空间
* 支持使用硬件加速的本机加密
* 具有 `快照(snapshots)` 和 `写时复制(copy-on-write)` 的高效存储
* 高效的本地或远程复制 — 使用 `ZFS` 发送和接收仅发送更改的块 

## OpenZFS 技术资源

* [如何安装ZFS](https://openzfs.github.io/openzfs-docs/Getting%20Started/index.html)
* [ZFS手册](https://openzfs.github.io/openzfs-docs/man/index.html)

## 捐赠

我们接受捐款以维持我们的开发。

OpenZFS 是 SPI 的关联项目 [Software in the Public Interest](https://www.spi-inc.org/projects/openzfs/)。 SPI 是一个 501\(c\)\(3\) 非营利组织，负责处理我们的捐赠、财务和合法资产。 您可以使用以下链接通过 `paypal` 捐款:

![](https://www.paypalobjects.com/en_US/i/scr/pixel.gif)

