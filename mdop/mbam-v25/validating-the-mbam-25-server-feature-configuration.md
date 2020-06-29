---
title: 验证 MBAM 2.5 服务器功能配置
description: 验证 MBAM 2.5 服务器功能配置
author: dansimp
ms.assetid: f4983a33-ce18-4186-a471-dd6415940504
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f955e0b9ccb7952995574e4aa981674f7c7667fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804097"
---
# 验证 MBAM 2.5 服务器功能配置


完成 Microsoft BitLocker 管理和监视（MBAM）2.5 服务器功能部署时，建议你验证部署，以确保已成功配置所有功能。 使用与你部署的拓扑（独立或 System Center Configuration Manager 集成）匹配的过程。

## 使用独立拓扑验证 MBAM 服务器部署


使用以下步骤验证具有独立拓扑的 MBAM 服务器部署。

**验证独立的 MBAM 服务器部署**

1.  在部署 MBAM 功能的每台服务器上，单击 **"控制面板** &gt; **程序** &gt; **程序和功能**"。 验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。

    **注意**  
    若要进行验证，你必须使用在每台服务器上具有本地计算机管理凭据的域帐户。



2.  在配置了恢复数据库的服务器上，打开 SQL Server Management Studio 并验证是否配置了**MBAM 恢复和硬件**数据库。

3.  在配置合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否配置了**MBAM 合规性状态数据库**。

4.  在配置了 "报表" 功能的服务器上，打开具有管理凭据的 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。

    SQL Server Reporting Services 网站实例的默认起始位置为：

    http （s）：// &lt; *MBAMReportsServerName* &gt; ： &lt; *port* &gt; /Reports.aspx

    若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。

5.  确认名为**Microsoft BitLocker 管理和监视**的报告文件夹包含名为**MaltaDataSource**的数据源和语言文件夹。 数据源包含名称表示语言（例如，en-us）的文件夹。 报表位于 "语言" 文件夹中。

    **注意**  
    如果 SQL Server Reporting Services （SSRS）配置为命名实例，则 URL 应类似于以下内容： http （s）：// &lt; *MBAMReportsServerName* &gt; ： &lt; *port* &gt; /Reports\_ &lt; *SSRSInstanceName*&gt;



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring Website (also known as Help Desk) and select a report, the following message appears: "Only Secure Content is Displayed." To show the report, click **Show All Content**.
~~~



6. 在配置了 "管理和监视网站" 功能的服务器上，运行 "**服务器管理器**"，浏览到 "**角色**"，然后选择 " **Web 服务器（iis）** &gt; **Internet 信息服务（iis）管理器**"。

7. 在 "**连接**" 中，浏览到 " * &lt; 计算机名称 &gt; * "，然后选择 " **Sites** &gt; **Microsoft BitLocker 管理和监视**" 站点。 验证是否列出以下内容：

   -   **MBAMAdministrationService**

   -   **MBAMComplianceStatusService**

   -   **MBAMRecoveryAndHardwareService**

8. 在配置了管理和监视网站和自助服务门户的服务器上，使用管理凭据打开 web 浏览器。

9. 浏览到以下网站，验证它们是否成功加载：

   -   https （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /HelpDesk/-确认导航和报告的每个链接

   -   http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /SelfService/

   **注意**  
   假设您在没有网络加密的情况下在默认端口上配置了服务器功能。 如果你在其他端口或虚拟目录上配置了服务器功能，请将 Url 更改为包含相应的端口，例如：

   http （s）：// &lt; *主机名* &gt; ： &lt; *port* &gt; /HelpDesk/

   http （s）：// &lt; *主机名* &gt; ： &lt; *port* &gt; / &lt; *virtualdirectory*&gt;/

   如果服务器功能配置了网络加密，请将 http://更改为 https://。



10. 浏览到以下 web 服务以验证它们是否已成功加载。 将打开一个页面，指示该服务正在运行，但页面不显示任何元数据。

    -   http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMAdministrationService/AdministrationService.svc

    -   http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMUserSupportService/UserSupportService.svc

    -   http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMComplianceStatusService/StatusReportingService.svc

    -   http （s）：// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /MBAMRecoveryAndHardwareService/CoreService.svc

## 通过 Configuration Manager 集成拓扑验证 MBAM 服务器部署


使用以下步骤通过 Configuration Manager 集成拓扑验证 MBAM 部署。 完成与你正在使用的 Configuration Manager 版本相匹配的验证步骤。

### <a href="" id="validating-the-mbam-server-deployment-with-system-center-2012-configuration-manager-"></a>通过 System Center 2012 配置管理器验证 MBAM 服务器部署

将 MBAM 与 System Center 2012 Configuration Manager 配合使用时，请使用以下步骤验证 MBAM 服务器部署。

**验证 Configuration Manager 集成 MBAM Server 部署-System Center 2012 Configuration Manager**

1.  在部署 System Center 2012 配置管理器的服务器上，打开 **"控制面板**" 中的 "**程序和功能**"，然后验证是否显示 " **Microsoft BitLocker 管理和监视**"。

    **注意**  
    若要验证配置，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。



2.  在 Configuration Manager 控制台中，单击 "**资源" 和 "合规性**" 工作区 &gt; **设备集合**，并确认是否显示名为 " **MBAM 支持的计算机**" 的新集合。

3.  在 Configuration Manager 控制台中，单击 "**监视**工作区 &gt; **报告** &gt; **报告** &gt; **MBAM**"。

4.  验证**MBAM**文件夹是否包含具有表示不同语言的名称的子文件夹，以及每个语言子文件夹中列出了下列报表：

    -   BitLocker 计算机合规性

    -   BitLocker 企业合规性仪表板

    -   BitLocker 企业合规性详细信息

    -   BitLocker 企业合规性摘要

5.  在 Configuration Manager 控制台中，单击 "**资源和合规性**工作区 &gt; **合规性设置**" &gt; **配置基线**，并确认 "配置基线**BitLocker 保护**" 已列出。

6.  在 Configuration Manager 控制台中，单击 "**资源和合规性**工作区 &gt; **合规性设置**" &gt; **配置项目**，并确认显示以下新配置项目：

    -   BitLocker 固定数据驱动器保护

    -   BitLocker 操作系统驱动器保护

### 通过 Configuration Manager 2007 验证 MBAM 服务器部署

将 MBAM 与 Configuration Manager 2007 配合使用时，请使用以下步骤验证 MBAM 服务器部署。

**验证 Configuration Manager 集成 MBAM Server 部署-Configuration Manager 2007**

1.  在部署 Configuration Manager 2007 的服务器上，打开 "**控制面板**" 上的 "**程序和功能**"，然后验证是否显示 " **Microsoft BitLocker 管理和监视**"。

    **注意**  
    若要验证配置，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。



2.  在 Configuration Manager 控制台中，单击 "**网站数据库 &lt; SiteCode &gt;  -  &lt; 服务器名 &gt; ， &lt; SiteName" &gt; ，"计算机管理**"，确认显示名为 " **MBAM 支持的计算机**" 的新集合。

3.  在 Configuration Manager 控制台中，单击 "**报告** &gt; **服务** &gt; ** \\\\ &lt; 服务器 &gt; 名** &gt; **报告文件夹** &gt; **MBAM**"。

    验证**MBAM**文件夹是否包含具有表示不同语言的名称的子文件夹，以及每个语言子文件夹中列出了下列报表：

    -   BitLocker 计算机合规性

    -   BitLocker 企业合规性仪表板

    -   BitLocker 企业合规性详细信息

    -   BitLocker 企业合规性摘要

4.  在 Configuration Manager 控制台中，单击 "**所需配置管理** &gt; **配置基线**"，然后确认 "配置基线**BitLocker 保护**" 已列出。

5.  在 Configuration Manager 控制台中，单击**所需的配置管理** &gt; **配置项目**，并确认显示以下新配置项目：

    -   BitLocker 固定数据驱动器保护

    -   BitLocker 操作系统驱动器保护



## 相关主题


[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






