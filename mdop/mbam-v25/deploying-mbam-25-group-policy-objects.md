---
title: 部署 MBAM 2.5 组策略对象
description: 部署 MBAM 2.5 组策略对象
author: dansimp
ms.assetid: 4b835054-6846-463d-af58-8ac4639a1188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9624b94e9d4808a35e1199290f4cd90a8122f767
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803558"
---
# 部署 MBAM 2.5 组策略对象


若要部署 MBAM，你必须设置用于定义 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置。 若要完成此任务，必须将 MBAM 组策略模板复制到能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的服务器或工作站，然后编辑设置。

**重要提示** 请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。 在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。

 

## 复制 MBAM 2.5 组策略模板


在安装 MBAM 客户端之前，必须将 MBAM 特定的组策略对象（Gpo）复制到管理工作站。 这些 Gpo 定义了用于 BitLocker 驱动器加密的 MBAM 实现设置。 你可以将组策略模板复制到受支持的 Windows server 或客户端计算机的任何服务器或工作站，并且能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）。

[复制 MBAM 2.5 组策略模板](copying-the-mbam-25-group-policy-templates.md)

## 编辑 MBAM 2.0 GPO 设置


创建必要的 Gpo 后，必须将 MBAM 组策略设置部署到你的组织的客户端计算机。 若要查看和创建 Gpo，必须安装组策略管理控制台（GPMC）或高级组策略管理（AGPM）。

[编辑 MBAM 2.5 组策略设置](editing-the-mbam-25-group-policy-settings.md)

## 显示或隐藏 Windows "控制面板" 中的 "MBAM 控制面板"


由于 MBAM 提供了一个可替换默认 Windows BitLocker 控制面板的自定义 MBAM 控制面板，因此你也可以选择使用组策略设置显示或隐藏最终用户的默认 BitLocker 控制面板。

[在控制面板中隐藏默认的“BitLocker 驱动器加密”项目](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)

## 用于部署 MBAM 2.0 组策略对象的其他资源


[部署 MBAM 2.5](deploying-mbam-25.md)

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。

 

 





