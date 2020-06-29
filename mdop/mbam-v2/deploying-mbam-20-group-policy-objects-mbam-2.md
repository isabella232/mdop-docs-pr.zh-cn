---
title: 部署 MBAM 2.0 组策略对象
description: 部署 MBAM 2.0 组策略对象
author: dansimp
ms.assetid: f17f3897-73ab-431b-a6ec-5a6cff9f279a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1ce2c2a37631d9d678d6de7c1d66b7fdafb2ade9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803379"
---
# 部署 MBAM 2.0 组策略对象


若要成功部署 Microsoft BitLocker 管理和监视（MBAM），首先需要确定你将在 Microsoft BitLocker 管理和监视的实现中使用的组策略。 有关可用的不同策略的详细信息，请参阅[规划 MBAM 2.0 组策略要求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。 确定要使用的策略后，必须使用 MBAM 2.0 组策略模板创建和部署一个或多个组策略对象（GPO），其中包括 MBAM 的策略设置。

## 安装 MBAM 2.0 组策略模板


除了服务器相关的 Microsoft BitLocker 管理和监视功能之外，服务器设置应用程序还包含 MBAM 组策略模板。 此模板可以安装在可运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的任何计算机上。

[如何安装 MBAM 2.0 组策略模板](how-to-install-the-mbam-20-group-policy-template-mbam-2.md)

## 部署 MBAM 2.0 组策略设置


创建必要的 Gpo 后，必须将 MBAM 组策略设置部署到你的组织的客户端计算机。

[如何编辑 MBAM 2.0 GPO 设置](how-to-edit-mbam-20-gpo-settings-mbam-2.md)

## 在 Windows 中显示 "MBAM 控制面板"


由于 MBAM 提供了可替换默认 Windows BitLocker 控制面板的自定义 MBAM 控制面板，因此你也可以选择通过使用组策略隐藏最终用户的默认 BitLocker 控制面板。

[如何在 Windows 控制面板中隐藏默认的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)

## 用于部署 MBAM 2.0 组策略对象的其他资源


[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)

 

 





