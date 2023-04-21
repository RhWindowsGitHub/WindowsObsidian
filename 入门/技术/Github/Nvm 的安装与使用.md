

```ad-summary
title:概述
记录 Nvm 的安装与使用 （NVM） node version manager node 版本管理工具
```

# Nvm 的安装与使用

```ad-tip
title:INFO
作者：Cola

时间：2023-04-17 06:35 
```

```ad-todo
title:Features： 🐔
 - [x] Nvm 的安装
 - [x] 基本命令的使用
```

## 一、概述

### 1.1 Node Version  Manager

> nvm is a version manager for [node.js](https://nodejs.org/en/), designed to be installed per-user, and invoked per-shell. `nvm` works on any POSIX-compliant shell (sh, dash, ksh, zsh, bash), in particular on these platforms: unix, macOS, and [windows WSL](https://github.com/nvm-sh/nvm#important-notes).

Nvm  是一个用于 Node.js 的版本管理器，旨在用户自定义安装，并在每个 shell 中调用。nvm 可在任何符合 POSIX 标准的 shell（sh、dash、ksh、zsh、bash）上运行，尤其适用于这些平台：Unix、macOS 和 Windows WSL。

### 1.2 下载与安装

> 进入 [Node Version Manager](https://github.com/nvm-sh/nvm) 官方网站中的 Release 发布页面，选择对应版本下载即可

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417064635.png)

> 在 cmd 中使用 `nvm -v` 验证是否安装成功

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417065158.png)

## 二、使用

### 2.1 使用 nvm 安装 node

To download, compile, and install the latest release of node, do this:

```shell
nvm install node # "node" is an alias for the latest version
```

To install a specific version of node:

```shell
nvm install 14.7.0 # or 16.3.0, 12.22.1, etc
```

The first version installed becomes the default. New shells will start with the default version of node (e.g., `nvm alias default`).

You can list available versions using `ls-remote`:

```shell
nvm ls-remote
```

### 2.2 查看当前已经安装的 node

```shell
nvm list # 列出当前已经安装的 node
```

### 2.3 切换 node

```shell
nvm use <node 版本> # 使用 nvm use 加相应的版本号即可快速切换 node 版本
```


