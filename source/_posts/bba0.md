---
title: ONPatch食用指南
tags:
  - LSPosed
  - LSPatch
  - ONPatch
categories:
  - 技术
abbrlink: bba0
date: 2024-02-25 00:00:00
cover: https://image.ifeng.asia:5243/files/2/66faa81062f7c.webp
description:
keywords: 'LSPatch,LSPosed,ONPatch,玩机,模块'
---

![](https://image.ifeng.asia:5243/files/2/66fa9142de9cd.webp)

2023年10月13日，[LSPatch]( https://github.com/LSPosed/LSPatch)被迫归档。[LSPosed](https://github.com/LSPosed/LSPosed)也紧随其后，在2024年1月8日归档不再更新，这一事件可以说是“**机圈大地震**”。

在[LSP](https://github.com/LSPosed/)停更后，出现了如[NPatch](https://t.me/NPatch),[OPatch](https://t.me/QToolC/268)等对[LSPatch]( https://github.com/LSPosed/LSPatch)的改版，最后我选择了在[OPatch](https://t.me/QToolC/268)基础上再魔改的`ONPatch`,使用`ONPatch`无需使用[Shizuku](https://shizuku.rikka.app/zh-hans/)和将`ONPatch`挂在后台保活。

## 修补

打开`ONPatch`的`管理`，点击右下角的加号后会弹出一个`注入模块`弹窗，你可以直接选择已安装的应用或下载好的安装包

考虑到兼容性，推荐选择`本地加载模式`而不是`内置模式`，此外`本地加载器模式`可以在不需要重新修补应用的情况下直接更新所使用的模块，缺点就是只能在本机运行，无法像内置那样分享给他人直接使用。

如果你需要对应用在`data`目录下的文件进行操作，可以将`注入文件提供者`给打开。

![](https://image.ifeng.asia:5243/files/2/66fa91421a029.webp)

点击`开始注入`等待修补注入完成后会在你指定的目录下生成新的安装包，如果你已经安装了原先未修补过的应用，请先卸载再安装修补后的应用。

![](https://image.ifeng.asia:5243/files/2/66fa914342da8.webp)

## 激活

安装好后不要直接打开，如果你已经打开，请先在该应用设置中结束运行该应用。

回到`ONPatch`的`管理`，可以看到你修补后的应用。点击应用后选择`模块作用域`，在`选择应用程序`中勾选你需要使用的模块。

将`ONPatch`挂在小窗确保在前台运行，然后打开激活后的应用，即可看到模块被成功激活。此后正常使用即可，无需让`ONPatch`挂在后台或前台保活。

## 更新

- 应用更新：重新执行一遍上述操作
- 模块更新：直接更新模块即可
- 模块新增：重新执行一遍[激活](https://blog.pzj.us.kg/posts/bba0.html#%E6%BF%80%E6%B4%BB)操作

## Tips

修补后会导致部分应用出现`非官方应用`的提示，在`设置`-`签名密钥库`中使用`LSPatch`的官方签名密钥库可一定程度上解决。
