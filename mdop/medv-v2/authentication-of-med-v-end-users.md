---
title: MED-V 最终用户的身份验证
description: MED-V 最终用户的身份验证
author: dansimp
ms.assetid: aaf96eb6-91d1-4f4d-9854-5fc73c7ae7ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14c1e95a94f2da76b6b6c5ebd9d4cf14dcf839a7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803658"
---
# MED-V 最终用户的身份验证


Microsoft 企业桌面虚拟化（MED-V）2.0 最终用户的身份验证是非常重要的安全问题。 在此上下文中，身份验证指验证 MED-V 最终用户的身份。

下一节提供了有关在 MED-V 中最终用户身份验证的信息和指南。

## MED-V 中的用户身份验证


MED-V 中的身份验证通常出现在两个级别上：当用户首次访问 MED-V 和每次更改其密码时。

根据你配置身份验证的 MED-V 设置的方式，通常会在某一点提示最终用户输入其密码，即启动 MED-V 时首次启动或首次尝试打开已发布的应用程序。

最终用户身份验证有多个方面可供你控制，包括以下内容：

最终用户输入的凭据是否存储在凭据管理器中

最终用户的显示方式，提供了输入和保存密码的选项

根据贵公司用于管理最终用户身份验证的首选过程，你可以指定特定的 MED-V 工作区是否进行凭据缓存。 缓存最终用户的凭据非常有用，因为它们只会提示一次用于其密码。 如果最终用户每次启动新的 MED-V 会话时都不允许保存其密码，则他们必须再次输入它。 例如，如果将 MED-V 配置为当最终用户登录到主机但禁用身份验证时启动，则仅在登录期间提示最终用户一次。 在这种情况下，凭据将有效，直到最终用户从主持人注销。

如果需要，您可以使用 "凭据管理器" 删除任何存储的最终用户凭据。

默认情况下，凭据存储已禁用，但你可以通过以下方法之一更改此设置：

**创建 med-v 工作区程序包时**。 有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。

**部署 med-v 工作区后**。 编辑 MED-V cmdlet 参数 UxCredentialCacheEnabled 以设置终端服务注册表项。 有关详细信息，请参阅 Windows PowerShell 帮助。

在 MED-V 工作区部署之后，你可以通过修改名为 DisablePasswordSaving 的终端服务策略来设置最终用户身份验证的首选项。 DisablePasswordSaving 控制是否在 RDP 客户端对话框窗口中显示 "密码保存" 复选框，以及是否显示 MED-V 凭据提示。

以下是名为 DisablePasswordSaving 的终端服务策略的策略路径。

**Regedit.exe**

HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Virtual Machine\\Policies\\DisablePasswordSaving

**注意**  
对 DisablePasswordSaving 所做的更改仅会影响到虚拟机的 RDP 提示。



下表列出了可用于配置凭据存储和不同配置的效果的不同方法：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">配置</th>
<th align="left">结果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DisablePasswordSaving</p></td>
<td align="left"><p><strong>禁用</strong></p></td>
<td align="left"><p>将显示 "MED-V" 提示，并清除 "接受" 复选框。 如果最终用户选中该复选框，则将缓存凭据以供以后使用。 最终用户还具有仅在密码过期时收到提示的好处。</p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>如果最终用户未选中此复选框，则会显示远程桌面连接（RDC）客户端提示，而不是 MED-V 提示，并且清除 "接受" 复选框。 如果最终用户选中该复选框，则将存储 RDC 客户端凭据以供以后使用。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>当最终用户输入凭据时，RDC 不会验证凭据。 如果最终用户通过 RDC 提示缓存凭据，则可能会有可能存储凭据错误的风险。 在这种情况下，必须在 Windows 凭据管理器中删除不正确的凭据。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>DisablePasswordSaving</p></td>
<td align="left"><p><strong>启用</strong></p></td>
<td align="left"><div class="alert">
<strong>注意</strong><br/><p>此配置更安全，因为它不允许缓存最终用户凭据。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



默认情况下，MED-V 安装会在来宾中设置一个注册表项，以取消 "密码过期" 提示。 最终用户仅提示在主机上更改密码。 在主机上更新的凭据将传递给来宾。

**注意**  
如果你在你的环境中使用组策略，请知道它可以替代注册表项，从而导致来自来宾的密码提示再次出现。



### 身份验证的安全问题

即使缓存最终用户的凭据可提供最佳用户体验，你也必须了解所涉及的风险。

启用凭据缓存后，最终用户的域凭据将以一种可还原的格式存储在 Windows 凭据管理器中。 因此，攻击者可以编写作为系统级进程或最终用户进程运行的工具，并检索最终用户的凭据。 您只能通过将 DisablePasswordSaving 设置为 "**启用**" 来减少此风险。

如果禁用了 MED-V 身份验证，但 "终端服务" 策略设置处于启用状态，则存在同样的问题。

## 相关主题


[MED-V 操作的安全最佳方案](security-best-practices-for-med-v-operations.md)









