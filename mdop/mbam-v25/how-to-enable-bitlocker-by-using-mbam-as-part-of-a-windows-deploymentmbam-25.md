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
ms.openlocfilehash: 4b2cbf333c705088d0a068521fb65e99551bb1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803926"
---
# 如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用


本主题介绍如何通过将 MBAM 用作 Windows 映像和部署过程的一部分，在最终用户的计算机上启用 BitLocker。 如果你在重启时看到黑屏（安装阶段结束后），指示无法解锁驱动器，请参阅[如果预配 BitLocker 与 Windows 10 版本1511一起使用，则不会在 "安装 windows 和配置管理器" 步骤之后开始使用较早的 Windows 版本](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)。

**先决条件：**

-   现有的 Windows 映像部署过程– Microsoft 部署工具包（MDT）、Microsoft System Center Configuration Manager 或其他映像工具或进程-必须放置

-   必须在 BIOS 中启用 TPM，并且操作系统可见

-   MBAM 服务器基础结构必须到位且易于访问

-   必须创建 BitLocker 所需的系统分区

-   在 MBAM 中，计算机必须加入域才能完全启用 BitLocker

**在 Windows 部署中使用 MBAM 2.5 SP1 启用 BitLocker**

1. 在 MBAM 2.5 SP1 中，建议用于在 Windows 部署期间启用 BitLocker 的方法是使用 `Invoke-MbamClientDeployment.ps1` PowerShell 脚本。

   -   `Invoke-MbamClientDeployment.ps1`脚本在映像过程中 Enacts BitLocker。 当 BitLocker 策略需要时，MBAM 代理会立即提示域用户在域用户第一次登录后进行映像时创建 PIN 或密码。

   -   易于与 MDT、System Center Configuration Manager 或独立成像进程一起使用

   -   与 PowerShell 2.0 或更高版本兼容

   -   用 TPM 密钥保护程序加密操作系统卷

   -   完全支持 BitLocker 预配

   -   （可选）加密 FDDs

   -   托管 TPM OwnerAuth For Windows 7，MBAM 必须拥有 TPM 才能进行保管。
   对于 Windows 8.1、Windows 10 RTM 和 Windows 10 版本1511，支持对 TPM OwnerAuth 进行托管。
   对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。 在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。 有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。

   -   托管恢复密钥和恢复密钥程序包

   -   立即报告加密状态

   -   新的 WMI 提供程序

   -   详细日志记录

   -   强健的错误处理

   你可以 `Invoke-MbamClientDeployment.ps1` 从[Microsoft.com 下载中心](https://www.microsoft.com/download/details.aspx?id=54439)下载脚本。 这是你的部署系统将调用以配置 BitLocker 驱动器加密的主脚本，并将恢复密钥与 MBAM 服务器一起记录。

   **MBAM 的 WMI 部署方法：** 在 MBAM 2.5 SP1 中添加了以下 WMI 方法以支持使用 `Invoke-MbamClientDeployment.ps1` PowerShell 脚本启用 BitLocker。

   <a href="" id="mbam-machine-wmi-class"></a>**MBAM \ _MACHINE WMI 类** 
   **PrepareTpmAndEscrowOwnerAuth：** 使用 MBAM 恢复服务读取 TPM OwnerAuth 并将其发送到 MBAM 恢复数据库。 如果 TPM 未拥有且自动预配未打开，它将生成一个 TPM OwnerAuth 并取得所有权。 如果失败，将返回错误代码进行故障排除。

   **注意**对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。 在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。 有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。

| 参数 | 描述 |
| -------- | ----------- |
| RecoveryServiceEndPoint | 指定 MBAM 恢复服务终结点的字符串。 |

下面是常见错误消息的列表：

| 常见返回值 | 错误消息 |
| -------------------- | ------------- |
|  **S_OK**<br />0（0x0） | 该方法成功。 |
| **MBAM_E_TPM_NOT_PRESENT**<br />2147746304（0x80040200） | 计算机中不存在 TPM，或者 BIOS 配置中已禁用 TPM。 |
| **MBAM_E_TPM_INCORRECT_STATE**<br />2147746305（0x80040201） | TPM 的状态不正确（启用、激活且允许所有者安装）。 |
| **MBAM_E_TPM_AUTO_PROVISIONING_PENDING**<br />2147746306（0x80040202） | MBAM 无法取得 TPM 的所有权，因为自动设置处于挂起状态。 自动预配完成后重试。 |
| **MBAM_E_TPM_OWNERAUTH_READFAIL**<br />2147746307（0x80040203） | MBAM 无法读取 TPM 所有者授权值。 此值可能已在成功托管后删除。 在 Windows 7 中，如果 TPM 归其他人所有，MBAM 无法读取该值。 |
| **MBAM_E_REBOOT_REQUIRED**<br />2147746308（0x80040204） | 必须重新启动计算机才能将 TPM 设置为正确状态。 您可能需要手动重启计算机。 |
| **MBAM_E_SHUTDOWN_REQUIRED**<br />2147746309（0x80040205） | 计算机必须关闭并重新打开，才能将 TPM 设置为正确状态。 您可能需要手动重启计算机。 |
| **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349（0x803D0005） | 远程终结点拒绝访问。 |
| **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357（0x803D000D） | 远程终结点不存在或无法定位。 |
| * * WS_E_ENDPOINT_FAILURE<br />2151481357（0x803D000F） | 远程终结点无法处理请求。 |
| **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360（0x803D0010） | 无法访问远程终结点。 |
| **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363（0x803D0013） | 从远程终结点收到包含错误的消息。 请确保连接到正确的服务终结点。 |
| **WS_E_INVALID_ENDPOINT_URL** 2151481376 （0x803D0020） | 终结点地址 URL 无效。 URL 必须以 "http" 或 "https" 开头。 |

   **ReportStatus：** 通过使用 MBAM 状态报告服务，读取卷的合规性状态并将其发送到 MBAM 合规性状态数据库。 状态包括密码强度、保护程序类型、保护程序状态和加密状态。 如果失败，将返回错误代码进行故障排除。

   | 参数 | 描述 |
   | --------- | ----------- |
   | ReportingServiceEndPoint | 指定 MBAM 状态报告服务终结点的字符串。 |

   下面是常见错误消息的列表：

   | 常见返回值 | 错误消息 |
   | -------------------- | ------------- |
   | **S_OK**<br /> 0（0x0） | 该方法成功 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349（0x803D0005） | 远程终结点拒绝访问。|
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357（0x803D000D） | 远程终结点不存在或无法定位。 |
   | **WS_E_ENDPOINT_FAILURE**<br /> 2151481357（0x803D000F） | 远程终结点无法处理请求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360（0x803D0010） | 无法访问远程终结点。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363（0x803D0013） | 从远程终结点收到包含错误的消息。 请确保连接到正确的服务终结点。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376（0x803D0020） | 终结点地址 URL 无效。 URL 必须以 "http" 或 "https" 开头。 |

   <a href="" id="mbam-volume-wmi-class"></a>**MBAM \ _VOLUME WMI Class** **EscrowRecoveryKey：** 读取卷的恢复数字密码和密钥包，并使用 MBAM 恢复服务将其发送到 MBAM 恢复数据库。 如果失败，将返回错误代码进行故障排除。

   | 参数 | 描述 |
   | --------- | ----------- |
   | RecoveryServiceEndPoint | 指定 MBAM 恢复服务终结点的字符串。 |

   下面是常见错误消息的列表：

   | 常见返回值 | 错误消息 |
   | -------------------- | ------------- |
   | **S_OK**<br />0（0x0） | 该方法成功 |
   | **FVE_E_LOCKED_VOLUME**<br />2150694912（0x80310000） | 卷已锁定。 |
   | **FVE_E_PROTECTOR_NOT_FOUND**<br />2150694963（0x80310033） | 找不到卷的数字密码保护器。 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349（0x803D0005） | 远程终结点拒绝访问。 |
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357（0x803D000D） | 远程终结点不存在或无法定位。 |
   | **WS_E_ENDPOINT_FAILURE**<br />2151481357（0x803D000F） | 远程终结点无法处理请求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360（0x803D0010） | 无法访问远程终结点。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363（0x803D0013） | 从远程终结点收到包含错误的消息。 请确保连接到正确的服务终结点。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376（0x803D0020） | 终结点地址 URL 无效。 URL 必须以 "http" 或 "https" 开头。 |
     

2. **使用 Microsoft 部署工具包（MDT）和 PowerShell 部署 MBAM**

   1.  在 MDT 中，创建新的部署共享或打开现有部署共享。

       **注意**  
       `Invoke-MbamClientDeployment.ps1`PowerShell 脚本可以与任何图像处理或工具一起使用。 本部分介绍如何使用 MDT 集成它，但步骤类似于将其与任何其他进程或工具进行集成。

       **注意**  
       如果您使用的是 BitLocker 预配（WinPE），并且想要维护 TPM 所有者授权值，则必须 `SaveWinPETpmOwnerAuth.wsf` 在安装重启到完整操作系统之前立即在 WinPE 中添加脚本。 **如果不使用此脚本，重新启动时将丢失 TPM 所有者授权值。**

   2.  复制 `Invoke-MbamClientDeployment.ps1` 到** &lt; DeploymentShare &gt; \\Scripts**。 如果使用预配，请将 `SaveWinPETpmOwnerAuth.wsf` 文件复制到** &lt; DeploymentShare &gt; \\Scripts**。

   3.  将 MBAM 2.5 SP1 客户端应用程序添加到部署共享中的 "应用程序" 节点。

       1.  在 "**应用程序**" 节点下，单击 "**新建应用程序**"。

       2.  选择 "**应用程序包含源文件**"。 单击“下一步”****。

       3.  在 "**应用程序名称**" 中，键入 "MBAM 2.5 SP1 Client"。 单击“下一步”****。

       4.  浏览到包含的目录 `MBAMClientSetup-<Version>.msi` 。 单击“下一步”****。

       5.  键入 "MBAM 2.5 SP1 Client" 作为要创建的目录。 单击“下一步”****。

       6.  `msiexec /i MBAMClientSetup-<Version>.msi /quiet`在命令行中输入。 单击“下一步”****。

       7.  接受剩余的默认设置以完成 "新建应用程序" 向导。

   4.  在 MDT 中，右键单击部署共享的名称，然后单击 "**属性**"。 单击 "**规则**" 选项卡。添加以下行：

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       单击 "确定" 关闭窗口。

   5.  在 "任务序列" 节点下，编辑用于 Windows 部署的现有任务序列。 如果需要，您可以通过右键单击**任务序列**节点、选择 "**新建任务序列**" 和 "完成向导" 来创建新任务序列。

       在所选任务序列的 "**任务序列**" 选项卡上，执行以下步骤：

       1.  在 "**预安装**" 文件夹下，如果希望在 WinPE 中启用 bitlocker，则启用可选任务 "**启用 bitlocker （脱机）** "，这将仅加密已使用的空间。

       2.  若要在使用预配时保留 TPM OwnerAuth，允许 MBAM 稍后进行保管，请执行以下操作：

           1.  查找**安装操作系统**步骤

           2.  在其后添加新的**运行命令行**步骤

           3.  对步骤**持久性 TPM OwnerAuth**命名

           4.  将命令行设置为 `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **注意：** 对于 windows 10 版本1607或更高版本，只有 WINDOWS 可以获得 TPM 的所有权。 在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。 有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。

       3.  在 "**状态还原**" 文件夹中，删除 "**启用 BitLocker** " 任务。

       4.  在 "**自定义任务**" 下的 "**状态还原**" 文件夹中，创建新的**安装应用程序**任务并将其命名为**Install MBAM 代理**。 单击 "**安装单个应用程序**" 单选按钮，然后浏览到以前创建的 MBAM 2.5 SP1 客户端应用程序。

       5.  在 "**自定义任务**" 下的 "**状态还原**" 文件夹中，使用以下设置创建新的**运行 POWERSHELL 脚本**任务（在 MBAM 2.5 SP1 客户端应用程序步骤之后）（根据你的环境更新参数）：

           -   名称：为 MBAM 配置 BitLocker

           -   PowerShell 脚本： `Invoke-MbamClientDeployment.ps1`

           -   实参

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
               <td align="left"><p>MBAM recovery 服务终结点</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-StatusReportingServiceEndpoint</p></td>
               <td align="left"><p>可选</p></td>
               <td align="left"><p>MBAM 状态报告服务终结点</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-EncryptionMethod</p></td>
               <td align="left"><p>可选</p></td>
               <td align="left"><p>加密方法（默认： AES 128）</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-EncryptAndEscrowDataVolume</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定加密数据卷和托管数据卷恢复密钥</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-WaitForEncryptionToComplete</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定等待加密完成</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-DoNotResumeSuspendedEncryption</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定部署脚本将不会恢复暂停的加密</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreEscrowOwnerAuthFailure</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定忽略 TPM 所有者-身份验证托管失败。 应在 MBAM 无法读取 TPM 所有者身份验证的情况下使用它，例如，如果启用了 TPM 自动预配</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-IgnoreEscrowRecoveryKeyFailure</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定忽略卷恢复密钥的托管失败</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreReportStatusFailure</p></td>
               <td align="left"><p>开关</p></td>
               <td align="left"><p>指定忽略状态报告失败</p></td>
               </tr>
               </tbody>
               </table>

                 

**在 Windows 部署中使用 MBAM 2.5 或更早版本启用 BitLocker**

1.  安装 MBAM 客户端。 有关说明，请参阅[如何使用命令行部署 MBAM 客户端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。

2.  将计算机加入域（推荐）。

    -   如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。 默认情况下，除非可以存储恢复密钥，否则 MBAM 不允许进行加密。

    -   如果在 MBAM 服务器上存储恢复密钥之前计算机在恢复模式下启动，则没有可用的恢复方法，并且必须 reimaged 计算机。

3.  以管理员身份打开命令提示符，并停止 MBAM 服务。

4.  通过键入以下命令将服务设置为**手动**或按**需**：

    **net stop mbamagent**

    **sc config mbamagent start = demand**

5.  设置注册表值，以便 MBAM 客户端忽略组策略设置，而设置加密以启动将 Windows 部署到该客户端计算机的时间。

    **小心** 此步骤介绍了如何修改 Windows 注册表。 注册表编辑器使用不当可导致严重问题，这些问题可能需要重新安装 Windows。 我们无法保证无法通过错误地使用注册表编辑器来解决所产生的问题。 使用注册表编辑器的风险由您自己承担。

    1.  设置仅适用于**操作系统**的 TPM 加密，运行 Regedit.exe，然后从 C:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 导入注册表项模板

    2.  在 Regedit.exe 中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM，并配置下表中列出的设置。

        **注意** 你可以在此处设置与 MBAM 相关的组策略设置或注册表值。 这些设置将替代以前设置的值。

        注册表项配置设置

        DeploymentTime

        0 = 关闭

        1 = 使用部署时间策略设置（默认值）-使用此设置可在将 Windows 部署到客户端计算机时启用加密。

        UseKeyRecoveryService

        0 = 不使用密钥保管（这种情况下，不需要接下来的两个注册表项）

        1 = 在密钥恢复系统中使用密钥托管（默认）

        这是推荐的设置，可使 MBAM 存储恢复密钥。 计算机必须能够与 MBAM 密钥恢复服务进行通信。 继续之前，请验证计算机是否可以与服务通信。

        KeyRecoveryOptions

        0 = 仅上载恢复密钥

        1 = 上载恢复密钥和密钥恢复包（默认）

        KeyRecoveryServiceEndPoint

        将此值设置为运行密钥恢复服务的服务器的 URL，例如，http:// &lt; 计算机名 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。


6.  MBAM 客户端将在 MBAM 客户端部署期间重新启动系统。 当您准备好进行此重启时，请以管理员身份在命令提示符处运行以下命令：

    **net start mbamagent**

7.  当计算机重新启动，并且 BIOS 提示您时，请接受 TPM 更改。

8.  在 Windows 客户端操作系统图像处理过程中，当你准备好开始加密时，请以管理员身份打开命令提示符，然后键入以下命令以将 "开始" 设置为 "**自动**"，然后重新启动 MBAM 客户端代理：

    **sc config mbamagent start = auto**

    **net start mbamagent**

9.  若要删除绕过的注册表值，请运行 Regedit.exe，然后转到 HKLM\\SOFTWARE\\Microsoft 注册表项。 右键单击**MBAM**节点，然后单击 "**删除**"。

## 相关主题

[部署 MBAM 2.5 客户端](deploying-the-mbam-25-client.md)

[规划 MBAM 2.5 客户端部署](planning-for-mbam-25-client-deployment.md)

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
