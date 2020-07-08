---
title: 如何安装 MBAM 1.0 组策略模板
description: 如何安装 MBAM 1.0 组策略模板
author: dansimp
ms.assetid: 451a50b0-939c-47ad-9248-a138deade550
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a055c84fb6b1645592b53d957daf157a6055880
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803748"
---
# 如何安装 MBAM 1.0 组策略模板


除了 Microsoft BitLocker 管理和监视（MBAM）的服务器相关功能之外，服务器设置应用程序还包含一个 MBAM 组策略模板。 你可以在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的任何计算机上安装此模板。

以下步骤介绍了如何安装 MBAM 组策略模板。

**注意** 请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。

 

**安装 MBAM 组策略模板**

1.  启动 MBAM 安装向导;然后，单击 "欢迎" 页面上的 "**安装**"。

2.  阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。

3.  默认情况下，将选择所有 MBAM 功能进行安装。 清除 "**策略模板**" 之外的所有功能选项，然后单击 "**下一步**" 以继续安装。

    **注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 满足所有先决条件后，安装将继续。

     

4.  MBAM 安装向导显示所选功能的安装页面后，单击 "**完成**" 关闭 MBAM 设置。

## 相关主题


[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)

 

 





