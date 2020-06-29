---
title: 部署 MBAM 1.0 组策略对象
description: 部署 MBAM 1.0 组策略对象
author: dansimp
ms.assetid: 2129291e-d2b2-41ed-b643-1e311c49fee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d14123f1d5b197146e425cba063e8ce4c180641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802924"
---
# 部署 MBAM 1.0 组策略对象


若要成功部署 Microsoft BitLocker 管理和监视（MBAM），必须首先确定你将在 MBAM 实现中使用的组策略。 有关各种可用策略的详细信息，请参阅[规划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)。 确定要使用的策略后，必须使用 MBAM 1.0 组策略模板来创建和部署一个或多个包含 MBAM 策略设置的组策略对象（GPO）。

## 安装 MBAM 1.0 组策略模板


除了提供 MBAM 服务器相关的功能，服务器设置应用程序还包含一个 MBAM 组策略模板。 你可以在可运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的任何计算机上安装此模板。

[如何安装 MBAM 1.0 组策略模板](how-to-install-the-mbam-10-group-policy-template.md)

## 部署 MBAM 1.0 组策略设置


创建必要的 Gpo 后，必须将 MBAM 组策略设置部署到你的组织的客户端计算机。

[如何编辑 MBAM 1.0 GPO 设置](how-to-edit-mbam-10-gpo-settings.md)

## 在 Windows 中显示 "MBAM 控制面板"


由于 MBAM 提供了可替换默认 Windows BitLocker 控制面板的自定义 MBAM 控制面板，因此你也可以选择通过使用组策略隐藏最终用户的默认 BitLocker 控制面板。

[如何在 Windows 控制面板中隐藏默认的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)

## 用于部署 MBAM 1.0 组策略对象的其他资源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





