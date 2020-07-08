---
title: 如何移动 MBAM 2.5 报告
description: 如何移动 MBAM 2.5 报告
author: dansimp
ms.assetid: c8223656-ca9d-41c8-94a3-64d07a6b99e9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1cdef260b4381671a1b9de66565ece0b70876200
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798034"
---
# 如何移动 MBAM 2.5 报告


使用这些过程将 "报告" 功能从一台计算机移动到另一台计算机，即将 "报告" 功能从服务器 A 移动到服务器 B。

移动 "报表" 功能的高级步骤如下：

1.  停止 MBAM 管理和监视网站的所有实例。

2.  在服务器 B 上安装 MBAM 2.5 服务器软件并在服务器 B 上配置 "报告" 功能。

3.  在 MBAM 管理和监视服务器上更新报表连接数据。

4.  恢复 MBAM 管理和监视网站的实例。

**注意** 若要运行本主题中的示例 Windows PowerShell 脚本，必须更新 Windows PowerShell 执行策略以允许运行脚本。 有关说明，请参阅[运行 Windows PowerShell 脚本](https://technet.microsoft.com/library/ee176949.aspx)。

 

**停止 MBAM 管理和监视网站**

-   在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台停止管理和监视网站。

    若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：

    ``` syntax
    PS C:\> Stop-Website "Microsoft BitLocker Administration and Monitoring"
    ```

**安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导**

1.  在服务器 B 上安装 MBAM Server 软件。有关说明，请参阅[安装 MBAM 2.5 Server 软件](installing-the-mbam-25-server-software.md)。

2.  在服务器 B 上，启动 "MBAM 服务器配置向导"，单击 "**添加新功能**"，然后仅选择 "**报表**" 功能。

    或者，你可以使用**Enable-MbamReport** Windows PowerShell cmdlet 来配置报告。

    有关如何配置报表的说明，请参阅[如何配置 MBAM 2.5 报表](how-to-configure-the-mbam-25-reports.md)。

**更新管理和监视服务器上的报表连接数据**

1.  在运行 "报表" 功能的服务器上，使用 "Internet 信息服务（IIS）管理器" 控制台更新报表 URL。

2.  展开 " **Microsoft BitLocker 管理和监视**"，然后选择 "**帮助台**" 节点。

3.  在 "**功能" 视图**的 "**管理**" 部分中，选择 "**配置编辑器**"。

4.  在 "**分区**" 字段中，选择 " **appSettings**"。

5.  选择 "**集合**" 行，然后单击窗格最右侧的 "省略号" 按钮 **（...）** 以打开**集合编辑器**。

6.  在**集合编辑器**中，选择包含**Mbam**的行，并更新**Mbam**的值，以反映服务器 B 的服务器名称的值的名称。

    如果以前在 SQL Server Reporting Services 的命名实例上配置了 "报表" 功能，请在 URL 中添加或更新实例的名称，例如：

    `http://$SERVERNAME$/ReportServer_$SQLSRSINSTANCENAME$/Pages....)`

7.  若要自动执行此过程，你可以使用 Windows PowerShell 在管理和监视服务器上运行与以下代码示例类似的命令。

    ``` syntax
    PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\\sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value "http://$SERVERNAME$/ReportServer[_$SRSINSTANCENAME$]/Pages/ReportViewer.aspx?/Microsoft+BitLocker+Administration+and+Monitoring/"
    ```

    使用下表中的说明，将代码示例中的值替换为与你的环境匹配的值。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>$SERVERNAME $</p></td>
    <td align="left"><p>报告已移动到的服务器的名称。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$SRSINSTANCENAME $</p></td>
    <td align="left"><p>报告已移动到的 SQL Server Reporting Services 实例的名称。</p></td>
    </tr>
    </tbody>
    </table>

     

**恢复管理和监视网站的实例**

1.  在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台启动 "管理和监视" 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：

    ``` syntax
    PS C:\> Start-Website "Microsoft BitLocker Administration and Monitoring"
    ```

    **注意** 若要运行此命令，必须将适用于 Windows PowerShell 的 IIS 模块添加到 Windows PowerShell 的当前实例。

     



## 相关主题


[如何配置 MBAM 2.5 报告](how-to-configure-the-mbam-25-reports.md)

[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[将 MBAM 2.5 功能移动到另一个服务器上](moving-mbam-25-features-to-another-server.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





