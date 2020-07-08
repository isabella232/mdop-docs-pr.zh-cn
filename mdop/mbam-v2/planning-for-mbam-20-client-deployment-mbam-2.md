---
title: 计划 MBAM 2.0 客户端部署
description: 计划 MBAM 2.0 客户端部署
author: dansimp
ms.assetid: 3a92cf29-092f-4cad-bdfa-d5f6aafe554b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c3a7383188d4064247d8e493c8e6125fc24a1d2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798091"
---
# 计划 MBAM 2.0 客户端部署


根据你部署 Microsoft BitLocker 管理和监视（MBAM）客户端的时间，你可以在你的组织中的计算机上启用 BitLocker 驱动器加密，方法是在最终用户收到计算机之前或之后。 对于 MBAM 独立版和 Configuration Manager 拓扑，你必须为 MBAM 配置组策略设置。

如果你使用的是 MBAM 独立拓扑，建议您使用企业软件部署系统将 MBAM 客户端软件部署到最终用户计算机。

如果使用 Configuration Manager 拓扑部署 MBAM，则可以使用 Configuration Manager 将 MBAM 客户端软件部署到最终用户计算机。 在配置管理器中，MBAM 安装将创建 MBAM 可管理的计算机的集合。 此集合包括的工作站和设备没有受信任的平台模块（TPM），但运行的是 Windows 8。

**注意** 如果你使用的是 Configuration Manager 2007，则不支持 MBAM 的集成 Configuration Manager 安装的 Windows To Go。

 

## 部署 MBAM 客户端以在将计算机分发给最终用户后启用 BitLocker 加密


配置组策略后，你可以使用企业软件部署系统产品（如 Microsoft System Center Configuration Manager 或 Active Directory 域服务（AD DS））将 MBAM 客户端安装的 Windows Installer 文件部署到目标计算机。 若要部署 MBAM 客户端，你可以使用32位或64位 MbamClientSetup.exe 文件或 MBAMClient.msi 文件，这些文件与 MBAM 软件一起提供。

在将计算机分配给客户端计算机之后部署 MBAM 客户端时，系统会提示最终用户对其计算机进行加密。 这使 MBAM 能够收集包含 PIN 和密码的数据，然后开始加密过程。

**注意** 在此方法中，如果尚未激活该芯片，则会提示拥有 TPM 芯片的计算机的用户激活并初始化 TPM 芯片。

 

## 在将计算机分发给最终用户之前使用 MBAM 客户端启用 BitLocker 加密


在同时接收和配置计算机的组织中，以及计算机具有兼容的 TPM 芯片的地方，你可以在向每台计算机上安装任何用户数据之前，安装 MBAM 客户端来管理该计算机上的 BitLocker 加密。 此过程的优点是，每台计算机都将与 BitLocker 加密兼容。 此方法不依赖于用户操作，因为管理员已加密计算机。 此方案的一个关键假设是，组织的策略在将计算机交付给用户之前安装企业的 Windows 映像。

如果你的组织希望使用 TPM 芯片加密计算机，管理员将添加 TPM 保护程序以加密计算机的操作系统卷。 如果你的组织希望使用 TPM 芯片和 PIN 保护器，则管理员使用 TPM 保护程序对操作系统卷进行加密，然后用户首次登录时选择 PIN。 如果您的组织决定仅使用引脚保护器，则管理员不必先加密卷。 当用户登录时，Microsoft BitLocker 管理和监视会提示他们提供 PIN 或 PIN 和密码，以便在以后的计算机重启时使用。

**注意** TPM 保护程序选项要求管理员在将计算机交付给用户之前接受激活和初始化 TPM 的 BIOS 提示。

 

## 相关主题


[计划部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[部署 MBAM 2.0 客户端](deploying-the-mbam-20-client-mbam-2.md)

 

 





