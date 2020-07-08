---
title: 规划 MBAM 2.5 客户端部署
description: 规划 MBAM 2.5 客户端部署
author: dansimp
ms.assetid: 23c89976-af24-4753-9412-ce0ea42d1964
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ff03b58da0985b2f57308c99a9bc15f4a0554623
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803879"
---
# 规划 MBAM 2.5 客户端部署


根据你部署 Microsoft BitLocker 管理和监视（MBAM）客户端软件的时间，你可以在最终用户收到计算机之前或之后在组织中的计算机上启用 BitLocker 驱动器加密。 对于 MBAM 单机版和 System Center Configuration Manager 集成拓扑，你必须为 MBAM 配置组策略设置。

如果你使用的是 MBAM 独立拓扑，我们建议你使用企业软件部署系统将 MBAM 客户端软件部署到最终用户计算机。

如果使用 Configuration Manager 集成拓扑部署 MBAM，则可以使用 Configuration Manager 将 MBAM 客户端软件部署到最终用户计算机。 在配置管理器中，MBAM 安装将创建 MBAM 可管理的计算机的集合。 此集合包括的工作站和设备没有受信任的平台模块（TPM），但运行的是 Windows 8、Windows 8.1 或 Windows 10。

**注意** 使用 Configuration Manager 2007 时，Configuration Manager 集成拓扑安装不支持 Windows To Go。

 

## 部署 MBAM 客户端以在将计算机分发给最终用户之后启用 BitLocker 驱动器加密


配置组策略后，你可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 或 Active Directory 域服务（AD DS））将 MBAM 客户端安装的 Windows Installer 文件部署到目标计算机。 若要部署 MBAM 客户端，你可以使用32位或64位 MbamClientSetup.exe 文件或 MBAMClient.msi 文件，这些文件或 MBAM 客户端软件附带的文件。

**注意** 从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。 但是，你可以从产品附带的可执行文件（.exe）中提取 MSI。

 

在将计算机分配给客户端计算机之后部署 MBAM 客户端时，系统会提示最终用户对其计算机进行加密。 此操作使 MBAM 能够收集数据，其中包括 PIN 和密码（如果策略要求），然后开始加密过程。

**注意** 在此方法中，如果尚未激活该芯片，则系统将提示拥有 TPM 芯片的计算机的最终用户激活并初始化 TPM 芯片。

 

## 在计算机分发给最终用户之前使用 MBAM 客户端启用 BitLocker 驱动器加密


在同时接收和配置计算机的组织中，以及计算机具有兼容的 TPM 芯片的地方，你可以在向每台计算机上使用 MBAM 客户端管理 BitLocker 驱动器加密，然后再向其写入任何用户数据。 此过程的好处是，每台计算机都合规。 此方法不依赖于最终用户操作，因为管理员已加密计算机。 此方案的一个关键假设是，在将计算机交付给最终用户之前，组织的策略会安装企业的 Windows 映像。

如果你的组织希望使用 TPM 芯片加密计算机，管理员将添加 TPM 保护程序以加密计算机的操作系统卷。 如果你的组织希望使用 TPM 芯片和 PIN 保护器，则管理员使用 TPM 保护程序对操作系统卷进行加密，然后最终用户首次登录时选择 PIN。 如果您的组织决定仅使用引脚保护器，则管理员不必先加密卷。 当最终用户登录时，Microsoft BitLocker 管理和监视会提示他们提供 PIN 或 PIN 和密码，以便在以后的计算机重启时使用。

**注意** TPM 保护程序选项要求管理员在将计算机交付给最终用户之前接受激活和初始化 TPM 的 BIOS 提示。

 

## MBAM 客户端对加密硬驱的支持


MBAM 支持在满足 Opal 的 TCG 规范要求和 IEEE 1667 标准的加密硬盘上支持 BitLocker。 在这些设备上启用 BitLocker 时，它将在已加密的驱动器上生成密钥并执行管理功能。 有关详细信息，请参阅[加密的硬驱](https://technet.microsoft.com/library/hh831627.aspx)。


## 相关主题


[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[部署 MBAM 2.5 客户端](deploying-the-mbam-25-client.md)

 

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




