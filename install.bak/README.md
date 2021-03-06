# 3 安装部署ZStack

本章主要概述了ZStack企业版（ZStack）不同模式下的安装部署过程以及TUI的功能介绍。

|名词|意义|
|------|------|
|ZStack|一种开源的云计算IaaS软件|
|TUI|字符用户界面|
|UI|基于浏览器的用户界面|


### ZStack TUI

ZStack TUI是专为ZStack集群中物理服务器准备的一套用户界面，其意义包含两方面：

- **分流UI的部分功能**
- **降低管理员登录服务器的频率**

其中，分流UI功能是指将针对服务器的配置密码、配置网络、重启机器等操作从UI中剥离出来，集中显示在TUI中；降低管理员登录频率是为了在降低物理机维护难度的同时，保护物理机内部的配置不被损坏。

根据功能不同，ZStack TUI分管理节点TUI和计算节点TUI两种，下面以管理节点TUI为主介绍其功能和使用方法。