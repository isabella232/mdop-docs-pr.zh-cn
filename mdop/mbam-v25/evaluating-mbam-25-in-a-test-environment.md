---
title: 在测试环境中评估 MBAM 2.5
description: 在测试环境中评估 MBAM 2.5
author: dansimp
ms.assetid: 72959b7a-e55f-4797-91b3-5be23c8c2844
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d7ba8a62f5ddecf85fe56e04fc16a6bae374ba9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803311"
---
# 在测试环境中评估 MBAM 2.5


本主题介绍了如何设置测试环境以在独立或 System Center Configuration Manager 集成拓扑中评估 Microsoft BitLocker 管理和监视（MBAM）2.5。

## 使用独立拓扑评估 MBAM 2。5


若要使用独立拓扑评估 MBAM，请使用下表中的信息安装 MBAM 服务器软件，然后在测试环境中配置 MBAM 服务器功能。

**使用独立拓扑评估 MBAM 2。5**

1. 在安装 MBAM 之前，请执行下列操作：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">任务</th>
   <th align="left">获取说明的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>确保已安装所有必备软件。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>检查所需的硬件、RAM 和其他规范。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支持的配置</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>如果计划使用 cmdlet 配置 MBAM，请查看使用 Windows PowerShell 的先决条件。</p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</a></p></td>
   </tr>
   </tbody>
   </table>



2. 安装 MBAM Server 软件，然后配置所需的功能。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">任务</th>
   <th align="left">获取说明的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>在要配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</p></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>配置合规性和审核数据库以及恢复数据库。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何配置 MBAM 2.5 数据库</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>配置 "报表" 功能。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何配置 MBAM 2.5 报告</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>配置 web 应用程序。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何配置 MBAM 2.5 Web 应用程序</a></p></td>
   </tr>
   </tbody>
   </table>



3. 在客户端计算机上，执行以下操作：

   1.  在客户端计算机上安装 MBAM 客户端。

   2.  将 MBAM 组策略对象（Gpo）应用到计算机。

   3.  设置以下注册表项，强制 MBAM 客户端以更快的速度唤醒，并且按固定时间间隔：

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注意**  
       由于这些键每分钟唤醒 MBAM 客户端，因此我们建议你仅在测试环境中使用这些注册表项设置。



   4.  重新启动**BitLocker 管理客户端服务**。

## 使用 System Center 2012 Configuration Manager 集成拓扑评估 MBAM 2。5


若要使用 Configuration Manager 集成拓扑评估 MBAM，请使用下表中的信息安装 MBAM 服务器软件，然后在测试环境中配置 MBAM 服务器功能。 在客户端计算机上安装 MBAM 客户端之后，你将完成额外的步骤，强制 MBAM 客户端更快地向 MBAM 报告计算机的状态。

**使用 System Center 2012 Configuration Manager 集成拓扑评估 MBAM 2。5**

1. 在安装 MBAM 之前，请查看必备软件和支持的配置。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">任务</th>
   <th align="left">获取说明的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>确保已安装所有必备软件。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>检查所需的硬件、RAM 和其他规范。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支持的配置</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>如果计划使用 cmdlet 配置 MBAM，请查看使用 Windows PowerShell 的先决条件。</p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>创建或编辑该 mof 文件。</p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)">编辑 Configuration.mof 文件</a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)">创建或编辑 Sms_def.mof 文件</a></p></td>
   </tr>
   </tbody>
   </table>



2. 安装 MBAM Server 软件，然后配置所需的功能。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">任务</th>
   <th align="left">获取说明的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>在要配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>你可以使用 Windows PowerShell 或导出的数据层应用程序（DAC）程序包将数据库安装到远程 SQL Server 计算机。 有关 DAC 包的详细信息，请参阅 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 数据层应用程序 </a> 。</p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>配置合规性和审核数据库以及恢复数据库。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何配置 MBAM 2.5 数据库</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>配置 "报表" 功能。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何配置 MBAM 2.5 报告</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>配置 web 应用程序。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何配置 MBAM 2.5 Web 应用程序</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>将 System Center Configuration Manager 配置为安装 Configuration Manager 对象。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">如何配置 MBAM 2.5 System Center Configuration Manager 集成</a></p></td>
   </tr>
   </tbody>
   </table>



3. 在客户端计算机上，执行以下操作：

   1.  在客户端计算机上安装 MBAM 客户端和 Configuration Manager 客户端。

   2.  将 MBAM 组策略对象应用到计算机。

   3.  设置以下注册表项，强制 MBAM 客户端以更快的速度唤醒，并且按固定时间间隔：

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注意**  
       由于这些键每分钟唤醒 MBAM 客户端，因此我们建议你仅在测试环境中使用这些注册表项设置。



   4.  重新启动**BitLocker 管理客户端服务**。

   5.  在 "控制面板" 中，打开 "**配置管理器**"，然后单击 "**操作**" 选项卡。

   6.  选择 "**硬件清单周期**"，然后单击 "**立即运行**"。 此步骤通过使用您导入到的 mof 文件中的新类运行硬件清单，然后将数据发送到 Configuration Manager 服务器。

   7.  选择 "**计算机策略检索" & 评估周期**，然后单击 "**立即运行**" 以应用与该客户端计算机相关的组策略对象。



4. 在 Configuration Manager 控制台中，执行以下操作：

   1.  在导航窗格中，右键单击 " **MBAM 支持的计算机**"，单击 "**更新成员身份**"，然后单击 **"是"** 强制客户端计算机立即报告其成员身份。

   2.  在导航窗格中，单击 " **MBAM 支持的计算机**" 以验证客户端计算机是否显示在该集合中。

5. 在客户端计算机上的 "控制面板" 中，再次重新打开**Configuration Manager** ，然后执行下列操作：

   1.  单击 "**操作**" 选项卡，然后重新运行**计算机策略检索 & 评估周期**。

   2.  单击 "**配置**" 选项卡，选择 "BitLocker 基线"，然后单击 "**求值**"。

6. 在配置管理器控制台中，验证客户端计算机是否显示在企业合规性报告上：如下所示：

   1.  在导航窗格中，选择 "**监视**" 工作区。

   2.  在控制台树中，展开 "**概述** &gt; **报告** &gt; **报告** &gt; **MBAM**"。

   3.  选择表示要查看报表的语言的文件夹，然后在 "结果" 窗格中选择报表。

## 使用 System Center Configuration Manager 2007 集成拓扑评估 MBAM 2。5


若要使用 Configuration Manager 集成拓扑评估 MBAM，请按照与在生产环境中使用的相同步骤在测试环境中安装和配置 MBAM。 在客户端计算机上安装 MBAM 客户端后，请完成本主题中的其他步骤，以使 MBAM 客户端能够更快地开始将计算机的状态报告到 MBAM。

**使用 Configuration Manager 2007 集成拓扑评估 MBAM**

1. 在安装 MBAM 之前，请执行下列操作：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">任务</th>
   <th align="left">获取说明的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>确保已安装所有必备软件。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>检查所需的硬件、RAM 和其他规范。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支持的配置</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>创建或编辑该 mof 文件。</p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)">编辑 Configuration.mof 文件</a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)">创建或编辑 Sms_def.mof 文件</a></p></td>
   </tr>
   </tbody>
   </table>



2. 安装 MBAM Server 软件，然后配置所需的功能。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">任务</th>
   <th align="left">获取说明的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>在要配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>你可以使用 Windows PowerShell 或导出的数据层应用程序（DAC）程序包将数据库安装到远程 SQL Server 计算机。 有关 DAC 包的详细信息，请参阅 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 数据层应用程序 </a> 。</p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安装 MBAM 2.5 服务器软件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>配置合规性和审核数据库以及恢复数据库。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何配置 MBAM 2.5 数据库</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>配置 "报表" 功能。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何配置 MBAM 2.5 报告</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>配置 web 应用程序。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何配置 MBAM 2.5 Web 应用程序</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>将 System Center Configuration Manager 配置为安装 Configuration Manager 对象。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">如何配置 MBAM 2.5 System Center Configuration Manager 集成</a></p></td>
   </tr>
   </tbody>
   </table>



3. 在客户端计算机上，执行以下操作：

   1.  在客户端计算机上安装 MBAM 客户端。

   2.  将 MBAM 组策略对象应用到计算机。

   3.  设置以下注册表项以强制 MBAM 客户更快、更快地醒来：

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注意**  
       由于这些键每分钟唤醒 MBAM 客户端，因此我们建议你仅在评估环境中使用这些注册表项设置。



   4.  重新启动**BitLocker 管理客户端服务**。

   5.  在 "控制面板" 中，打开 "**配置管理器**"，然后单击 "**操作**" 选项卡。

   6.  选择 "**计算机策略检索" & 评估周期**，然后单击 "**立即运行**" 以应用与该客户端计算机相关的组策略对象。

   7.  选择 "**硬件清单周期**"，然后单击 "**立即运行**"。 此步骤通过使用您导入到的 mof 文件中的新类运行硬件清单，然后将数据发送到 Configuration Manager 服务器。

4. 在 Configuration Manager 控制台中，执行以下操作：

   1.  在导航窗格中，右键单击 " **MBAM 支持的计算机**"，单击 "**更新成员身份**"，然后单击 **"是"** 强制客户端计算机立即报告其成员身份。

   2.  在导航窗格中，单击 " **MBAM 支持的计算机**" 以验证客户端计算机是否显示在该集合中。

5. 在客户端计算机上的 "控制面板" 中，再次重新打开**Configuration Manager** ，然后执行下列操作：

   1.  单击 "**操作**" 选项卡，然后重新运行**计算机策略检索 & 评估周期**。

   2.  单击 "**配置**" 选项卡，选择 "BitLocker 基线"，然后单击 "**求值**"。

6. 在 Configuration Manager 控制台中，验证客户端计算机是否显示在 "企业合规性报告" 上，如下所示

   1.  在导航窗格中，展开 "**计算机管理** &gt; **报告** &gt; **服务**" &gt; ** &lt; 服务器名称 &gt; MBAM**。

   2.  在**MBAM**节点中，选择表示要查看报表的语言的文件夹，然后从 "结果" 窗格中选择报表。


## 相关主题


[MBAM 2.5 入门](getting-started-with-mbam-25.md)


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。





