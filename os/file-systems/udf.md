# UDF

## 概念

- 英文全称 Universal Disk Format (UDF)，通用碟片格式
- 一种由 OSTA 组织制定的文件规格
- 目的是取代光盘（CD，DVD等）上面使用的ISO9660文件系统

## 历史版本

| 版本 | 日期    | 主要特征                       |
| ---- | ------- | ------------------------------ |
| 1.02 | 08/1996 | 第一个版本，适合用于只读媒体上 |
| 1.50 | 02/1997 | 支持一次写入媒体，支持失效管理 |
| 2.00 | 04/1998 | 支持名字流                     |
| 2.01 | 03/2000 | 修改一些小问题                 |
| 2.50 | 04/2003 | 支持元数据分区获得更高性能     |
| 2.60 | 03/2005 | 支持虚拟可重写分区             |

- UDF 1.02：第一个UDF版本，被 DVD 电影使用的标准，适合于只读和硬驱动之类的介质。
- UDF 1.50：增加了**虚拟分区**（virtual partition）和**可备份分区**（sparable partition）。**虚拟分区**使一次性的介质（CD-R, DVD-R 和 DVD+R）表现的像一个可复写的介质，但是剩余的空间会不断的减小。**可备份分区**使得一张有很多失效区块的碟片逻辑上看起来是完整而且连续的。
- UDF 2.00 & UDF 2.01：对文件和目录增加的**命名流**（named streams），以及对卷增加**系统流**（system streams）。**命名流**可以用来实现其他文件系统中的扩展属性，比如 NTFS 中的 ACL。UDF 2.01修正了2.00的一些小错误，并没有引入主要功能。
- UDF 2.50：
- UDF 2.60：

## UDF标准的结构

UDF标准包含2套规范，ECMA-167 和 OSTA-UDF。

- ECMA([European Computer Manufacturer's Association](http://www.ecma-international.org/)) ， ECMA-167 是一个卷和文件结构标准，ECMA 被定义为一个总体框架。它留下了足够的选择和未决定的细节，需要由其他标准来填补。ECMA-167 有第二版（ECMA-167/2）和第三版（ECMA-167/3）。ECMA-167/3增加了命名流。所以 UDF 的 1.x 版本是基于 ECMA-167/2，而 UDF 的 2.x 版本是基于 ECMA-167/3。ECMA-167/3 除了命名流的支持、更高的修订号和其他一些小地方外，几乎与 ECMA-167/2 完全相同。
- OSTA([Optical Storage Technology Association](http://www.osta.org/))，OSTA-UDF 基于 ECMA-167 的框架，在其基础上填充所有必需的细节，明确化那些有歧义的地方

也就是说，UDF 的实现是依据 ECMA－167 和 OSTA 制定的 UDF 标准来进行实现的，需要同时把2个标准拿在手上进行阅读。

## UDF 规范简介



## 参考资料

- [翻译Wenguang's Introduction to Universal Disk Format (UDF)](https://blog.csdn.net/johnny_nass_hu/article/details/48065895)