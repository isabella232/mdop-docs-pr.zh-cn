---
title: 删除 MBAM 服务器功能或软件
description: 删除 MBAM 服务器功能或软件
author: dansimp
ms.assetid: 5212ba3f-124d-43c5-824a-608e9a192e86
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e6e57c3d2a62a4e01242ade7a82a7bfa551da83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803676"
---
# 删除 MBAM 服务器功能或软件


这些说明介绍了如何从 Microsoft BitLocker 管理和监视（MBAM）中删除软件和功能。 如果您删除 MBAM 服务器功能，则只会从服务器中删除已配置的功能，而不是 MBAM 服务器软件。 如果您删除 MBAM 服务器软件，将删除该软件以及您在该服务器上配置的任何 MBAM 服务器功能。

**注意** 为了防止意外删除数据，MBAM 不提供用于删除数据库的机制;您必须手动执行此操作。

 

## <a href="" id="bkmk-removeserverfeatures"></a>删除 MBAM 服务器功能


你可以使用以下任一方法来删除已配置的 MBAM 服务器功能：

-   MBAM Server 配置向导

-   Windows PowerShell cmdlet

### 使用 MBAM 服务器配置向导删除功能

按照这些说明操作，使用 MBAM 服务器配置向导从服务器中删除配置的 MBAM 服务器功能。

**使用向导删除 MBAM 功能**

1.  在要删除功能的服务器上，选择 " **MBAM 服务器配置**" 以打开配置向导。

2.  单击 "**删除功能**"，选择要删除的功能，然后单击 "**下一步**"。 "**摘要**" 页面显示您选择要删除的功能。

3.  单击 "**删除**" 开始删除这些功能，然后单击 "**关闭**"。

### 使用 Windows PowerShell 删除功能

使用以下步骤作为一般指南，使用 Windows PowerShell cmdlet 删除 MBAM 服务器功能。

**使用 Windows PowerShell 删除 MBAM 功能**

1.  在删除任何功能之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。

2.  使用以下 cmdlet 删除 MBAM Server 功能：

    -   Disable-MbamReport

    -   Disable-MbamWebApplication

    -   Disable-MbamCMIntegration

    若要获取有关 windows powershell cmdlet 的帮助，请键入**get-help** &lt; *cmdlet* &gt; 或查看适用于 windows powershell cmdlet 的[windows powershell 页面的 Microsoft 桌面优化包自动化](https://go.microsoft.com/fwlink/?LinkId=393498)MBAM。

## 删除 MBAM Server 软件


使用以下步骤删除 MBAM Server 软件和你在该服务器上配置的任何 MBAM 服务器功能。

**删除 MBAM 服务器软件**

1.  在要卸载 MBAM Server 软件的服务器上，运行**MBAMserversetup.exe**以启动 Microsoft BitLocker 管理和监视设置向导。

2.  选择 "**卸载**"，然后按照其余提示完成卸载 MBAM Server 软件的过程。



## 相关主题


[部署 MBAM 2.5](deploying-mbam-25.md)

 

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。



