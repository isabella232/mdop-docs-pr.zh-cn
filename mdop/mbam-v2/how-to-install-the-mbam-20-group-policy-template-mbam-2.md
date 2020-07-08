---
title: 如何安装 MBAM 2.0 组策略模板
description: 如何安装 MBAM 2.0 组策略模板
author: dansimp
ms.assetid: bc193232-d060-4285-842e-d194a74dd3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6420fc4d499de05ed740b038b40aff6a9cd8a05f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803931"
---
# 如何安装 MBAM 2.0 组策略模板


除了服务器相关的 Microsoft BitLocker 管理和监视（MBAM）功能之外，服务器设置应用程序还包括 Microsoft BitLocker 管理和监视组策略模板。 此模板可安装在任何能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的计算机上。

以下步骤介绍了如何安装 MBAM 组策略模板。

**注意** 请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。

 

**安装 MBAM 组策略模板**

1.  在要安装 MBAM 的服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。

2.  在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。

3.  阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。

4.  默认情况下，将选择安装所有 Microsoft BitLocker 管理和监视功能。 清除 "**策略模板**" 之外的所有功能选项，然后单击 "**下一步**" 以继续安装。

    **注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 满足所有先决条件后，安装将继续。

     

5.  有关如何以及在何处安装模板的特定步骤，请参阅[如何下载和部署 MDOP 组策略（admx）模板](https://technet.microsoft.com/library/dn659707.aspx)。

6.  在 "Microsoft BitLocker 管理和监视设置向导" 显示所选功能的安装页面后，单击 "**完成**" 关闭 MBAM 设置。

## 相关主题


[部署 MBAM 2.0 组策略对象](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





