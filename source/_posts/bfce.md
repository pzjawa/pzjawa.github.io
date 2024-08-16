---
title: 为第三方系统接入HMS
tags:
  - 玩机
categories:
  - 技术
keywords: '华为,刷机,玩机,root,magisk,类原生,原生,hms,push,推送,鸿蒙,harmony,harmonyos'
abbrlink: bfce
date: 2023-07-14 00:00:00
cover: https://image.ifeng.asia:5243/files/2/66bdc50a5a14f.webp
description:
---

## 前言

国内安卓生态并未接入**GCM**/**FCM**统一推送体系，国内安卓应用大都采用自带推送服务或第三方推送服务体系，从而导致应用需要常驻后台。

在国内比较成功的系统级推送体系有**MIPush**和**HMS**等，接入后能够有效减少应用因消息推送的需要而频繁自启的行为，从而减少后台占用达到省电的效果。

HMS需要使用到**HMS Core**，可以在[华为应用市场](https://consumer.huawei.com/cn/support/appgallery/)和[酷安](https://www.coolapk.com/apk/com.huawei.hwid)下载到。如遇到点击通知无法打开目标应用，可以将HMS Core转为**系统应用**。

请将HMS Core**设置开机自启**，**加入电池优化白名单**，**锁定后台**。

## 已ROOT

在非华为设备上由于缺乏系统服务配合，只能唤醒目标应用让其自己弹出通知，同时大部分应用在非华为设备上不会主动启用HMS推送服务。为了能够更好接入HMS，我们需要伪装成华为机型，主要有两种方法：使用[HMSPush](https://github.com/fei-ke/HMSPush)或机型修改模块。

下载安装[HMSPush](https://github.com/fei-ke/HMSPush/releases/)，并在LSP勾选系统框架和HMS Core后重启。将支持HMS的应用勾选作用域，如果你使用了其他方法伪装华为机型则无需进行这一步。打开HMSPush即可看到应用支持列表和状态。

## 非ROOT

下载安装[LSPatch](https://github.com/LSPosed/LSPatch)，选择HMSPush列表里的应用进行修补，其中HMS Core为必须。

这里以HMS Core为例子：

新建修补，可以是安装包也可以是已安装的应用。选择便捷模式，点击嵌入模块，模块选择HMSPush。等待修补完成后安装，需要卸载原应用后再安装修补过的应用。完成后重启系统，回到HMSPus查看状态。

## HMS Core精简

由于我们只需要用到HMS的推送服务，所以我们可以对不必要的进程进行精简，从而进一步减少后台占用。

管理相关进程可以使用[爱玩机工具箱](https://www.coolapk.com/apk/com.byyoung.setting)，[Thanox](https://github.com/Tornaco/Thanox)和[MyAndroidTools](https://www.myandroidtools.com/)等软件。

请将下面列出的进程打开，其余进程全部关闭。

**服务**

 HMSCoreService

 HMSInnerService

 OpenDeviceIdentifierBindService

 OobeService

HMSStubKitUpdateJobService

 **广播**

 OobeOnBootBroadcastReceiver

 HMSOnBootBroadcastReceiver

 **活动**

 JumpActivity

PushEarthquakeActivity

 TileLongClickJumperActivity

 **内容提供者**

 HMSFrameworkProvider

 KitProcessAgentCoreProvider

 ModuleQueryProvider

 HmsSettingSearchProvider

 UpdateSettingProvider
