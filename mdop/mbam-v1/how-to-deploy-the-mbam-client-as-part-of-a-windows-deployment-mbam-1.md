---
title: 如何在 Windows 部署过程中部署 MBAM 客户端
description: 如何在 Windows 部署过程中部署 MBAM 客户端
author: dansimp
ms.assetid: 8704bf33-535d-41da-b9b2-45b60754367e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a63311bcc93d84472ceff5c80c9222fefd5445c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803663"
---
# 如何在 Windows 部署过程中部署 MBAM 客户端


Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。 通过在计算机映像和 Windows 部署过程中启用客户端计算机上的 BitLocker 管理和加密，可将 BitLocker 客户端集成到组织中。

**注意**  
若要查看 MBAM 客户端系统要求，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。



在 Windows 部署的初始映像阶段，使用 BitLocker 加密客户端计算机可以降低 MBAM 实现的管理开销。 此方法还可确保已部署的每台计算机都已运行 BitLocker 且配置正确。

**警告**  
本主题介绍如何使用注册表编辑器更改 Windows 注册表。 如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。 在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。 Microsoft 无法保证更改注册表时可能出现的问题可以解决。 更改注册表的风险由您自己承担。



**将计算机加密为 Windows 部署的一部分**

1.  如果你的组织计划在 BitLocker 中使用受信任的平台模块（TPM）保护器选项或 TPM + PIN 保护程序选项，则必须在 MBAM 的初始部署之前激活 TPM 芯片。 当你激活 TPM 芯片时，你可以在该过程的稍后部分避免重新启动，并确保根据你的组织的要求正确配置 TPM 芯片。 必须在计算机的 BIOS 中手动激活 TPM 芯片。 有关如何配置 TPM 芯片的更多详细信息，请参阅制造商文档。

2.  安装 MBAM 客户端代理。

3.  我们建议你将计算机加入域 .。。

    -   如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。 默认情况下，除非可以存储恢复密钥，否则 MBAM 不允许进行加密。

    -   如果在 MBAM 服务器上存储恢复密钥之前计算机在恢复模式下启动，则必须 reimaged 计算机。 没有可用的恢复方法。

4.  以管理员身份打开命令提示符，停止 MBAM 服务，然后将服务设置为 "**手动** **" 或 "按需**"。 然后运行下列命令：

    **net stop mbamagent**

    **sc config mbamagent start = demand**

5.  将 MBAM 代理的注册表设置设置为 "忽略组策略"，并运行**仅限操作系统**的 TPM 加密若要执行此操作，请运行**regedit**，然后从 c:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 导入注册表项模板。

6.  在 regedit 中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM 并配置下表中列出的设置。

    注册表项

    配置设置

    DeploymentTime

    0 = 关闭

    1 = 使用部署时间策略设置（默认值）

    UseKeyRecoveryService

    0 = 不使用密钥保管（这种情况下，不需要接下来的两个注册表项）。

    1 = 在密钥恢复系统中使用密钥托管（默认）

    建议：计算机必须能够与密钥恢复服务进行通信。 继续之前，请验证计算机是否可以与服务通信。

    KeyRecoveryOptions

    0 = 仅上载恢复密钥

    1 = 上载恢复密钥和密钥恢复包（默认值）

    KeyRecoveryServiceEndPoint

    将此值设置为密钥恢复 web 服务器的 URL。

    示例： http:// &lt; 计算机名 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。



~~~
**Note**  
MBAM policy or registry values can be set here to override the previously set values.
~~~



7. MBAM 代理在 MBAM 客户端部署期间重新启动系统。 当您准备好进行此重启时，请以管理员身份在命令提示符处运行以下命令：

   **net start mbamagent**

8. 当计算机重新启动并且 BIOS 提示您接受 TPM 更改时，请接受更改。

9. 在 Windows 客户端操作系统成像过程中，当你准备好开始加密时，请重新启动 MBAM 代理服务。 然后，若要将 "开始" 设置为 "**自动**"，请以管理员身份打开命令提示符，并运行以下命令：

   **sc config mbamagent start = auto**

   **net start mbamagent**

10. 删除旁路注册表值。 若要执行此操作，请运行 regedit，浏览到 HKLM\\SOFTWARE\\Microsoft 注册表项，右键单击**MBAM**节点，然后单击 "**删除**"。

## 相关主题


[部署 MBAM 1.0 客户端](deploying-the-mbam-10-client.md)









