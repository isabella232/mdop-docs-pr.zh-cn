---
title: 如何将 MBAM 客户端部署到台式机或笔记本电脑
description: 如何将 MBAM 客户端部署到台式机或笔记本电脑
author: dansimp
ms.assetid: 3a7639e0-468e-4496-8be2-ed29b8e07c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b67533a555da4dabec6654ed3f95f91ad8d37bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803576"
---
# 如何将 MBAM 客户端部署到台式机或笔记本电脑


本主题介绍如何将 MBAM 客户端部署到最终用户的计算机。 你可以通过电子软件分发系统（如 Active Directory 域服务或 MicrosoftSystemCenterConfiguration 管理器）部署 MBAM 客户端。

若要将 MBAM 客户端部署为 Windows 部署的一部分，请参阅[如何通过将 MBAM 用作 Windows 部署的一部分来启用 BitLocker](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)。

在开始 MBAM 客户端部署之前，请查看[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。

**将 MBAM 客户端部署到台式计算机或膝上型计算机**

1.  找到 MBAM 软件附带的 MBAM 客户端安装文件。

2.  使用 Active Directory 域服务或企业软件部署工具（如 MicrosoftSystemCenterConfiguration Manager）将 Windows Installer 程序包部署到目标计算机。

3.  配置分发设置或组策略设置以运行 MBAM 客户端安装文件。

    成功安装后，MBAM 客户端将应用从域控制器收到的组策略设置以开始 BitLocker 驱动器加密和管理功能。

    **重要提示** 如果远程桌面协议连接处于活动状态，MBAM 客户端不会启动 BitLocker 驱动器加密操作。 必须关闭所有远程控制台连接，并且用户必须在 BitLocker 驱动器加密开始之前登录到物理控制台会话。

     


## 相关主题
[部署 MBAM 2.5 客户端](deploying-the-mbam-25-client.md)

[规划 MBAM 2.5 客户端部署](planning-for-mbam-25-client-deployment.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





