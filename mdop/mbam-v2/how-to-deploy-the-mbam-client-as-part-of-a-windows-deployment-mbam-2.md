---
title: 如何在 Windows 部署过程中部署 MBAM 客户端
description: 如何在 Windows 部署过程中部署 MBAM 客户端
author: dansimp
ms.assetid: 67387de7-8b02-4412-9850-3b8d8e5c18af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d75e5748167d2d4866f98e9d3611584067ecd418
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803605"
---
# 如何在 Windows 部署过程中部署 MBAM 客户端


Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。 如果具有受信任的平台模块（TPM）芯片的计算机，则可以通过在客户端计算机上启用 BitLocker 管理和加密作为映像和 Windows 部署过程的一部分，将 BitLocker 客户端集成到组织中。

**注意**  
若要查看 Microsoft BitLocker 管理和监视客户端系统要求，请参阅[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。



在 Windows 部署的初始映像阶段使用 BitLocker 加密客户端计算机可以降低在组织中实施 MBAM 所需的管理开销。 它还确保已部署的每台计算机都已运行 BitLocker 且配置正确。

**注意**  
本主题介绍修改 Windows 注册表的过程。 注册表编辑器使用不当可能导致严重问题，可能需要重新安装 Windows。 Microsoft 无法保证无法通过错误地使用注册表编辑器来解决所产生的问题。 使用注册表编辑器的风险由您自己承担。



**将计算机加密为 Windows 部署的一部分**

1.  如果你的组织计划在 BitLocker 中使用受信任的平台模块（TPM）保护器选项或 TPM + PIN 保护程序选项，则必须在 MBAM 的初始部署之前激活 TPM 芯片。 当你激活 TPM 芯片时，你可以在该过程的稍后部分避免重新启动，并确保根据你的组织的要求正确配置 TPM 芯片。 必须在计算机的 BIOS 中手动激活 TPM 芯片。

    **注意**  
    某些供应商提供的工具可在操作系统内打开和激活 BIOS 中的 TPM 芯片。 有关如何配置 TPM 芯片的更多详细信息，请参阅制造商文档。



2.  安装 Microsoft BitLocker 管理和监视客户端代理。

3.  将计算机加入域（推荐）。

    -   如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。 默认情况下，除非可以存储恢复密钥，否则 MBAM 不允许进行加密。

    -   如果在 MBAM 服务器上存储恢复密钥之前计算机在恢复模式下启动，则必须 reimaged 计算机。 没有可用的恢复方法。

4.  以管理员身份运行命令提示符，停止 MBAM 服务，然后将该服务设置为**手动**或**按需**，然后通过键入以下命令开始：

    **net stop mbamagent**

    **sc config mbamagent start = demand**

5.  将 MBAM 代理的注册表设置设置为 "忽略组策略"，并通过运行**Regedit**，然后从 C:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 导入注册表项模板来运行**仅限操作系统加密**的 TPM

6.  在 regedit 中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM，并配置下表中列出的设置。

    注册表项

    配置设置

    DeploymentTime

    0 = 关闭

    1 = 使用部署时间策略设置（默认值）

    UseKeyRecoveryService

    0 = 不使用密钥保管（这种情况下，不需要接下来的两个注册表项）

    1 = 在密钥恢复系统中使用密钥托管（默认）

    建议：计算机必须能够与密钥恢复服务进行通信。 继续之前，请验证计算机是否可以与服务通信。

    KeyRecoveryOptions

    0 = 仅上载恢复密钥

    1 = 上载恢复密钥和密钥恢复包（默认）

    KeyRecoveryServiceEndPoint

    将此值设置为密钥恢复 web 服务器的 URL，例如，http:// &lt; 计算机名 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。



~~~
**Note**  
MBAM policy or registry values can be set here to override previously set values.
~~~



7. MBAM 代理在 MBAM 客户端部署期间重新启动系统。 当您准备好进行此重启时，请以管理员身份在命令提示符处运行以下命令：

   **net start mbamagent**

8. 当计算机重新启动，并且 BIOS 提示您接受 TPM 更改时，请接受更改。

9. 在 Windows 客户端操作系统成像过程中，当你准备好开始加密时，请重新启动 MBAM 代理服务，并通过以管理员身份运行命令提示符并键入以下命令来将 "开始" 设置为 "**自动**"：

   **sc config mbamagent start = auto**

   **net start mbamagent**

10. 通过运行 Regedit 并转到 HKLM\\SOFTWARE\\Microsoft 注册表项来删除旁路注册表值。 若要删除**MBAM**节点，请右键单击该节点，然后单击 "**删除**"。

## 相关主题


[部署 MBAM 2.0 客户端](deploying-the-mbam-20-client-mbam-2.md)









