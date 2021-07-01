---
title: 如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用
description: 如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用
author: dansimp
ms.assetid: 7609ad7a-bb06-47be-b186-0a2db787c8a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: cd4086ca6bb2ea8d253ea3b743f4efe7efbbb6c1
ms.sourcegitcommit: 325c4b77f9a9df0f3de268457fed06184623bb94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "11626179"
---
# <a name="how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deployment"></a>如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用

> [!IMPORTANT]
> 这些说明与 Configuration Manager BitLocker 管理不相关。 不支持 `Invoke-MbamClientDeployment.ps1` 将 PowerShell 脚本与 Configuration Manager 中的 BitLocker 管理一同使用。 这包括在 Configuration Manager 任务序列期间托管 BitLocker 恢复密钥。 此外，从 Configuration Manager Current Branch 2103 开始，Configuration Manager BitLocker Management 不再使用 MBAM 密钥恢复服务站点托管密钥。 尝试将 PowerShell 脚本与 Configuration Manager Current Branch 2103 或更高版本一同使用可能会导致 `Invoke-MbamClientDeployment.ps1` Configuration Manager 站点出现严重问题。 已知问题包括创建大量面向所有设备的策略，这可能会导致策略风暴。 这将主要在配置管理器中和管理点SQL性能严重下降。

本主题介绍如何在最终用户的计算机上将 MBAM 用作映像和部署过程的一Windows BitLocker。 如果在安装阶段结束) 后重启 (时看到黑屏，指示无法解锁驱动器，请参阅早期版本的 Windows 版本在"安装程序 Windows 和配置管理器"步骤后不启动（如果预预配 BitLocker 与 Windows 10 版本[1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)一起使用）。

**先决条件：**

-   必须Windows映像部署过程（Microsoft Deployment Toolkit (MDT) 、Microsoft System Center Configuration Manager 或其他一些映像工具或进程）

-   必须在 BIOS 中启用 TPM，并且对操作系统可见

-   MBAM 服务器基础结构必须就位且可访问

-   必须创建 BitLocker 所需的系统分区

-   在 MBAM 完全启用 BitLocker 之前，计算机必须在映像期间加入域

**在部署中启用使用 MBAM 2.5 SP1 Windows BitLocker**

1. 在 MBAM 2.5 SP1 中，建议在部署期间启用 BitLocker Windows方法是使用 `Invoke-MbamClientDeployment.ps1` PowerShell 脚本。

   -   该 `Invoke-MbamClientDeployment.ps1` 脚本在映像过程中会安装 BitLocker。 当 BitLocker 策略要求时，MBAM 代理在域用户首次登录映像后立即提示域用户创建 PIN 或密码。

   -   易于与 MDT、System Center Configuration Manager或独立映像过程一同使用

   -   与 PowerShell 2.0 或更高版本兼容

   -   使用 TPM 密钥保护程序加密操作系统卷

   -   完全支持 BitLocker 预预配

   -   （可选）加密 FD

   -   托管 TPM OwnerAuth 对于 Windows 7，MBAM 必须拥有 TPM，托管发生。
   对于 Windows 8.1、Windows 10 RTM Windows 10版本 1511，支持托管 TPM OwnerAuth。
   对于Windows 10版本 1607 或更高版本，Windows可以取得 TPM 的所有权。 在 addiiton 中，Windows TPM 时不会保留 TPM 所有者密码。 有关 [更多详细信息，请参阅 TPM](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 所有者密码。

   -   托管恢复密钥和恢复密钥包

   -   立即报告加密状态

   -   新的 WMI 提供程序

   -   详细日志记录

   -   可靠的错误处理

   可以从下载 `Invoke-MbamClientDeployment.ps1` 中心下载 [Microsoft.com 脚本](https://www.microsoft.com/download/details.aspx?id=54439)。 这是部署系统调用的主要脚本，用于配置 BitLocker 驱动器加密，以及使用 MBAM 服务器记录恢复密钥。

   **MBAM 的 WMI 部署方法：** MBAM 2.5 SP1 中添加了以下 WMI 方法，以支持使用 PowerShell 脚本启用 `Invoke-MbamClientDeployment.ps1` BitLocker。

   <a href="" id="mbam-machine-wmi-class"></a>**MBAM\_Machine WMI 类** 
   **PrepareTpmAndEscrowOwnerAuth：** 读取 TPM OwnerAuth，然后使用 MBAM 恢复服务将其发送到 MBAM 恢复数据库。 如果 TPM 不归所有，并且自动预配未打开，它将生成 TPM OwnerAuth 并取得所有权。 如果失败，将返回错误代码进行疑难解答。

   **注意**对于Windows 10版本 1607 或更高版本，Windows可以取得 TPM 的所有权。 在 addiiton 中，Windows TPM 时不会保留 TPM 所有者密码。 有关 [更多详细信息，请参阅 TPM](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 所有者密码。

| 参数 | 描述 |
| -------- | ----------- |
| RecoveryServiceEndPoint | 指定 MBAM 恢复服务终结点的字符串。 |

以下是常见错误消息的列表：

| 常见返回值 | 错误消息 |
| -------------------- | ------------- |
|  **S_OK**<br />0 (0x0)  | 方法成功。 |
| **MBAM_E_TPM_NOT_PRESENT**<br />2147746304 (0x80040200)  | TPM 不在计算机中，或在 BIOS 配置中处于禁用状态。 |
| **MBAM_E_TPM_INCORRECT_STATE**<br />2147746305 (0x80040201)  | TPM 未处于正确的状态， (启用、激活和所有者安装) 。 |
| **MBAM_E_TPM_AUTO_PROVISIONING_PENDING**<br />2147746306 (0x80040202)  | MBAM 无法获得 TPM 的所有权，因为自动预配挂起。 请在完成自动设置后重试。 |
| **MBAM_E_TPM_OWNERAUTH_READFAIL**<br />2147746307 (0x80040203)  | MBAM 无法读取 TPM 所有者授权值。 成功托管后，该值可能已删除。 在 Windows 7 上，如果 TPM 归其他人所有，MBAM 将无法读取该值。 |
| **MBAM_E_REBOOT_REQUIRED**<br />2147746308 (0x80040204)  | 必须重新启动计算机才能将 TPM 设置为正确的状态。 您可能需要手动重新启动计算机。 |
| **MBAM_E_SHUTDOWN_REQUIRED**<br />2147746309 (0x80040205)  | 计算机必须关闭并再次打开，以将 TPM 设置为正确的状态。 您可能需要手动重新启动计算机。 |
| **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005)  | 远程终结点拒绝访问。 |
| **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D)  | 远程终结点不存在或无法定位。 |
| **WS_E_ENDPOINT_FAILURE<br />2151481357 (0x803D000F)  | 远程终结点无法处理请求。 |
| **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010)  | 远程终结点不可访问。 |
| **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013)  | 从远程终结点收到包含错误的消息。 确保连接到正确的服务终结点。 |
| **WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)  | 终结点地址 URL 无效。 URL 必须以"http"或"https"开始。 |

   **ReportStatus：** 读取卷的合规性状态，然后使用 MBAM 状态报告服务将其发送到 MBAM 合规性状态数据库。 状态包括加密强度、保护程序类型、保护程序状态和加密状态。 如果失败，将返回错误代码进行疑难解答。

   | 参数 | 描述 |
   | --------- | ----------- |
   | ReportingServiceEndPoint | 指定 MBAM 状态报告服务终结点的字符串。 |

   以下是常见错误消息的列表：

   | 常见返回值 | 错误消息 |
   | -------------------- | ------------- |
   | **S_OK**<br /> 0 (0x0)  | 方法成功 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005)  | 远程终结点拒绝访问。|
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D)  | 远程终结点不存在或无法定位。 |
   | **WS_E_ENDPOINT_FAILURE**<br /> 2151481357 (0x803D000F)  | 远程终结点无法处理请求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010)  | 远程终结点不可访问。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013)  | 从远程终结点收到包含错误的消息。 确保连接到正确的服务终结点。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020)  | 终结点地址 URL 无效。 URL 必须以"http"或"https"开始。 |

   <a href="" id="mbam-volume-wmi-class"></a>**MBAM\_Volume WMI Class** **EscrowRecoveryKey：** 读取卷的恢复数字密码和密钥包，然后使用 MBAM 恢复服务将它们发送到 MBAM 恢复数据库。 如果失败，将返回错误代码进行疑难解答。

   | 参数 | 描述 |
   | --------- | ----------- |
   | RecoveryServiceEndPoint | 指定 MBAM 恢复服务终结点的字符串。 |

   以下是常见错误消息的列表：

   | 常见返回值 | 错误消息 |
   | -------------------- | ------------- |
   | **S_OK**<br />0 (0x0)  | 方法成功 |
   | **FVE_E_LOCKED_VOLUME**<br />2150694912 (0x80310000)  | 卷已锁定。 |
   | **FVE_E_PROTECTOR_NOT_FOUND**<br />2150694963 (0x80310033)  | 未找到卷的数字密码保护程序。 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005)  | 远程终结点拒绝访问。 |
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D)  | 远程终结点不存在或无法定位。 |
   | **WS_E_ENDPOINT_FAILURE**<br />2151481357 (0x803D000F)  | 远程终结点无法处理请求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010)  | 远程终结点不可访问。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013)  | 从远程终结点收到包含错误的消息。 确保连接到正确的服务终结点。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020)  | 终结点地址 URL 无效。 URL 必须以"http"或"https"开始。 |
     

2. **使用 Microsoft Deployment Toolkit (MDT) 和 PowerShell 部署 MBAM**

   1.  在 MDT 中，创建新的部署共享或打开现有部署共享。

       **注意**  
       `Invoke-MbamClientDeployment.ps1`PowerShell 脚本可用于任何映像过程或工具。 本部分演示如何使用 MDT 集成它，但步骤类似于将其与任何其他进程或工具集成。

       **注意**  
       如果你使用的是 BitLocker 预预配 (WinPE) 并且想要保留 TPM 所有者授权值，则必须在安装重新启动到完整操作系统之前，立即在 WinPE 中添加脚本。 `SaveWinPETpmOwnerAuth.wsf` **如果不使用此脚本，将在重新启动时丢失 TPM 所有者授权值。**

   2.  复制到 `Invoke-MbamClientDeployment.ps1` ** &lt; DeploymentShare &gt; \\Scripts**。 如果你使用的是预预配，将文件 `SaveWinPETpmOwnerAuth.wsf` 复制到** &lt; DeploymentShare &gt; \\Scripts**中。

   3.  将 MBAM 2.5 SP1 客户端应用程序添加到部署共享中的 Applications 节点。

       1.  在"**应用程序"节点**下，单击"**新建应用程序"。**

       2.  选择 **"使用源文件的应用程序"。** 单击“下一步”****。

       3.  在 **"应用程序名称"** 中，键入"MBAM 2.5 SP1 客户端"。 单击“下一步”****。

       4.  浏览到包含 的目录 `MBAMClientSetup-<Version>.msi` 。 单击“下一步”****。

       5.  键入"MBAM 2.5 SP1 客户端"作为要创建的目录。 单击“下一步”****。

       6.  在 `msiexec /i MBAMClientSetup-<Version>.msi /quiet` 命令行中输入 。 单击“下一步”****。

       7.  接受其余默认值以完成"新建应用程序"向导。

   4.  在 MDT 中，右键单击部署共享的名称，然后单击 **属性**。 单击" **规则"** 选项卡。添加以下行：

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       单击"确定"关闭窗口。

   5.  在"任务序列"节点下，编辑用于部署Windows序列。 如果需要，可以通过右键单击"任务序列"节点，选择"新建任务**** 序列"并完成向导**** 来创建一个新任务序列。

       在所选 **任务序列** 的"任务序列"选项卡上，执行以下步骤：

       1.  在 **"预安装** "文件夹下，启用可选任务"启用 **BitLocker ** (脱机) "（如果你希望 BitLocker 在 WinPE 中启用，这将仅加密已用空间）。

       2.  若要在使用预预配时保留 TPM OwnerAuth，允许 MBAM 稍后托管它，请执行下列操作：

           1.  查找 **安装操作系统** 步骤

           2.  在命令行 **后添加新的"运行命令行** "步骤

           3.  将步骤命名 **为 Persist TPM OwnerAuth**

           4.  将命令行设置为"注意 `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **："Windows 10**版本 1607 或更高版本，Windows TPM 的所有权。 在 addiiton 中，Windows TPM 时不会保留 TPM 所有者密码。 有关 [更多详细信息，请参阅 TPM](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 所有者密码。

       3.  在状态 **还原文件夹中** ，删除启用 **BitLocker** 任务。

       4.  在"**状态还原"** 文件夹中的"自定义任务"**下**，创建新的"**安装应用程序"** 任务，并将其命名为 **"安装 MBAM 代理"。** 单击" **安装单个应用程序"** 单选按钮并浏览到之前创建的 MBAM 2.5 SP1 客户端应用程序。

       5.  在"**** 自定义任务"下的****"状态还原"文件夹中，在 MBAM 2.5 SP1 客户端应用程序步骤 () 后创建新的"运行**PowerShell**脚本"任务) 并 (根据你的环境环境) ：

           -   名称：为 MBAM 配置 BitLocker

           -   PowerShell 脚本： `Invoke-MbamClientDeployment.ps1`

           -   参数：

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p>-RecoveryServiceEndpoint</p></td>
               <td align="left"><p>必需</p></td>
               <td align="left"><p>MBAM 恢复服务终结点</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-StatusReportingServiceEndpoint</p></td>
               <td align="left"><p>可选</p></td>
               <td align="left"><p>MBAM 状态报告服务终结点</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-EncryptionMethod</p></td>
               <td align="left"><p>可选</p></td>
               <td align="left"><p>加密方法 (默认值：AES 128) </p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-EncryptAndEscrowDataVolume</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定对数据卷 (加密) 和托管数据卷恢复密钥 () </p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-WaitForEncryptionToComplete</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定等待加密完成</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-DoNotResumeSuspendedEncryption</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定部署脚本将不会恢复挂起的加密</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreEscrowOwnerAuthFailure</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定以忽略 TPM 所有者-身份验证托管失败。 它应在 MBAM 无法读取 TPM 所有者身份验证的情况下使用，例如，如果启用了 TPM 自动预配</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-IgnoreEscrowRecoveryKeyFailure</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定忽略卷恢复密钥托管失败</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreReportStatusFailure</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定忽略状态报告失败</p></td>
               </tr>
               </tbody>
               </table>

                 

**在部署中启用使用 MBAM 2.5 或更早版本Windows BitLocker**

1.  安装 MBAM 客户端。 有关说明，请参阅 [如何使用命令行部署 MBAM 客户端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。

2.  将计算机加入推荐 (域) 。

    -   如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。 默认情况下，MBAM 不允许加密，除非可以存储恢复密钥。

    -   如果计算机在恢复密钥存储在 MBAM 服务器上之前以恢复模式启动，则没有可用的恢复方法，并且计算机必须重新进行想象。

3.  以管理员角色打开命令提示符，并停止 MBAM 服务。

4.  通过**键入以下命令**，将**** 服务设置为手动或按需：

    **net stop mbamagent**

    **sc config mbamagent start= demand**

5.  设置注册表值，以便 MBAM 客户端忽略组策略设置，改为设置加密以启动Windows部署到该客户端计算机的时间。

    **注意**  
    此步骤介绍如何修改Windows注册表。 不正确地使用注册表编辑器可能会导致严重问题，可能需要重新安装Windows。 我们无法保证由于不正确地使用注册表编辑器而导致的问题能够得到解决。 使用注册表编辑器的风险由你自己承担。

    1.  为仅操作系统加密设置**** TPM，运行 Regedit.exe，然后从 C：\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg 导入注册表项模板。

    2.  在Regedit.exe中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM，然后配置下表中列出的设置。

        **注意**  
        你可以在此处设置与 MBAM 相关的组策略设置或注册表值。 这些设置将替代之前设置的值。

        注册表项 配置设置

        DeploymentTime

        0 = 关闭

        1 = 将部署时间策略 (默认设置) – 使用此设置在将 Windows部署到客户端计算机时启用加密。

        UseKeyRecoveryService

        0 = 请勿使用 (两个注册表项，在这种情况下，无需使用) 

        1 = 使用密钥恢复系统中的密钥托管 (默认) 

        这是推荐设置，它使 MBAM 能够存储恢复密钥。 计算机必须能够与 MBAM 密钥恢复服务通信。 在继续之前，请验证计算机能否与该服务通信。

        KeyRecoveryOptions

        0 = 仅上载恢复密钥

        1 = 将恢复密钥和密钥恢复包 (默认) 

        KeyRecoveryServiceEndPoint

        将此值设置为运行密钥恢复服务的服务器的 URL，例如，http:// 计算机名称 &lt; &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。


6.  MBAM 客户端将在 MBAM 客户端部署期间重新启动系统。 准备好执行此重启后，以管理员角色在命令提示符下运行以下命令：

    **net start mbamagent**

7.  当计算机重新启动，并且 BIOS 提示您时，接受 TPM 更改。

8.  在 Windows 客户端操作系统映像过程中，当你准备好开始加密时，以管理员角色打开命令提示符，并键入以下命令以将开始设置为自动并重新启动 MBAM**** 客户端代理：

    **sc config mbamagent start= auto**

    **net start mbamagent**

9.  若要删除绕过注册表值，请运行 Regedit.exe，然后转到 HKLM\\SOFTWARE\\Microsoft 注册表项。 右键单击**MBAM**节点，然后单击"删除 **"。**

## <a name="related-topics"></a>相关主题

[部署 MBAM 2.5 客户端](deploying-the-mbam-25-client.md)

[规划 MBAM 2.5 客户端部署](planning-for-mbam-25-client-deployment.md)

## <a name="got-a-suggestion-for-mbam"></a>有关于 MBAM 的建议吗？
- 在此处添加建议或对建议 [投票](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。
- 对于 MBAM 问题，请使用 [MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
