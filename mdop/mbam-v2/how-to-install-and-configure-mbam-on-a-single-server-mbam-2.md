---
title: 如何在单个服务器上安装和配置 MBAM
description: 如何在单个服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 45e6a012-6c8c-4d90-902c-d09de9a0cbea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 53e170f421bdce8dd6f771af3902af627a15a085
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803494"
---
# 如何在单个服务器上安装和配置 MBAM


本主题中的过程介绍了如何在单个服务器上的独立拓扑中安装 Microsoft BitLocker 管理和监视（MBAM）。 仅在测试环境中使用单服务器配置。 对于生产环境，使用两个或多个服务器。 如果你正在使用 Configuration Manager 拓扑安装 Microsoft BitLocker 管理和监视，请参阅使用[Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。

下图显示了单服务器体系结构的示例。 有关数据库和功能的说明，请参阅[MBAM 2.0 的高级别体系结构](high-level-architecture-for-mbam-20-mbam-2.md)。

![mbam 2 单服务器部署拓扑](images/mbam2-1-server.gif)

每个服务器功能都具有特定的先决条件。 若要验证你是否满足先决条件和硬件和软件要求，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。 此外，某些功能还包含安装过程中必须提供的信息才能成功部署该功能。 在开始 MBAM 部署之前，还应查看[准备 MBAM 2.0 的环境](preparing-your-environment-for-mbam-20-mbam-2.md)。

**注意**  
若要获取安装程序日志文件，你可以使用 Msiexec 程序包和 **/l** &lt; location &gt; 选项来安装 MBAM。 将在您指定的位置创建日志文件。

其他安装日志文件在安装 MBAM 的用户服务器上的% temp% 文件夹中创建。



## 在单个服务器上安装 MBAM 服务器功能


以下步骤介绍了如何安装常规 MBAM 功能。

**启动 MBAM Server 功能安装**

1.  在要安装 MBAM 的服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。

2.  在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。

3.  阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。

4.  在 "**拓扑选择**" 页面上，选择**独立**拓扑，然后单击 "**下一步**"。

5.  在 "**选择要安装的功能**" 页面上，选择要安装的功能。 默认情况下，将选择所有 MBAM 功能进行安装。 要在同一台计算机上安装的功能必须同时安装在一起。 清除要在其他位置安装的任何功能的复选框。 必须按以下顺序安装 MBAM 功能：

    -   恢复数据库

    -   合规性和审核数据库

    -   合规性和审核报告

    -   自助服务服务器

    -   管理和监视服务器

    -   MBAM 组策略模板

    **注意**  
    安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 如果此时间满足所有先决条件，安装将继续。



6.  在 "**配置网络通信安全**" 页面上，选择是否加密管理和监视服务器和客户端上的 Web 服务之间的通信。 如果您决定加密通信，请选择用于加密的证书颁发机构预配的证书。 在此步骤之前，必须创建证书，以使你能够在此页面上选择它。

    **注意**  
    仅当在 "**选择要安装的功能**" 页面上选择了 "自助式门户" 或 "管理和监视服务器" 功能时，才会显示此页面。



7.  单击 "**下一步**"，然后继续执行下一组步骤来配置 MBAM 服务器功能。

**配置 MBAM 服务器功能**

1.  在 "**配置恢复数据库**" 页面上，指定要存储恢复数据的数据库的 SQL Server 实例名称和数据库名称。 你还必须指定数据库文件所在的位置以及日志信息将位于何处。

2.  单击**下一步**以继续。

3.  在 "**配置合规性和审核数据库**" 页面上，指定要存储合规性和审核数据的数据库的 SQL Server 实例名称和名称。 你还必须指定数据库文件的位置和日志信息将位于何处。

4.  单击**下一步**以继续。

5.  在 "**配置合规性和审核报告**" 页面上，指定将安装合规性和审核报告的 SQL Server Reporting Services 实例，并提供用于访问合规性和审核数据库的域用户帐户和密码。 将此帐户的密码配置为永不过期。 用户帐户应该能够访问 MBAM Reports Users 组中所有可用的数据。

6.  单击**下一步**以继续。

7.  在 "**配置自助服务门户**" 页面上，输入自助服务门户的端口号、主机名、虚拟目录名称和安装路径。

    **注意**  
    你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。 如果您使用的是 Windows 防火墙，则该端口将自动打开。



8.  单击**下一步**以继续。

9.  指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。 此操作不会在 Windows 中启用自动更新。

10. 在 "**配置管理和监视服务器**" 页面上，输入技术支持网站的端口号、主机名、虚拟目录名称和安装路径。

    **注意**  
    你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。 如果您使用的是 Windows 防火墙，则该端口将自动打开。



11. 在 "**安装摘要**" 页面上，查看将安装的功能列表，然后单击 "**安装**" 以开始安装 MBAM 功能。 如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中向后移动，或者单击 "**取消**" 退出安装程序。 安装程序安装 MBAM 功能并通知您安装已完成。

12. 单击 "**完成**" 退出向导。 安装 Microsoft BitLocker 管理和监视服务器功能后，继续下一节，完成步骤必须将用户添加到 Microsoft BitLocker 管理和监视角色。 有关角色的详细信息，请参阅[规划 MBAM 2.0 管理员角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。

**执行安装后配置**

1.  在 "管理和监视" 服务器上，将用户添加到以下本地组，让他们可以访问 MBAM 技术支持网站功能：

    -   **MBAM 帮助台用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的驱动器恢复和管理 TPM 功能。 驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。

    -   **MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理和监视网站上管理 TPM 功能。 对于高级帮助台用户，驱动器恢复中仅需要 "**密钥 ID** " 字段。 在 "管理 TPM" 中，仅需要 "**计算机域**字段" 和 "**计算机名称**" 字段。

2.  在 "管理和监视" 服务器上，将用户添加到以下本地组，以使其能够访问 MBAM 管理和监视网站上的 "报告" 功能：

    -   **MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的报表功能。

    -   通过您的公司名称、通知文本和其他特定于公司的信息，为自助服务门户提供品牌。 有关说明，请参阅[如何为自助服务门户提供品牌](how-to-brand-the-self-service-portal.md)。

    **注意**  
    **MBAM 报表**的相同用户或组成员身份必须在已安装 MBAM 管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告的所有计算机上维护。 执行此操作的推荐方法是创建域安全组，并将该域组添加到每个本地 MBAM Report Users 组。 使用此过程时，按域组的方式管理组成员身份。



## 验证 MBAM 服务器功能安装


当 Microsoft BitLocker 管理和监视安装完成后，请验证安装是否已成功设置 BitLocker 管理所需的所有必需的 MBAM 功能。 使用以下过程确认 MBAM 服务是否正常工作。

**验证 MBAM 服务器功能安装**

1. 在部署 MBAM 功能的每台服务器上，打开 **"控制面板"**。 选择 "**程序**"，然后选择 "**程序和功能**"。 验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。

   **注意**  
   若要验证安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。



2. 在安装了恢复数据库的服务器上，打开 SQL Server Management Studio，并验证是否已安装**MBAM 恢复和硬件**数据库。

3. 在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio，并验证是否安装了**MBAM 合规性状态数据库**。

4. 在安装合规性和审核报告的服务器上，使用管理凭据打开 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。

   SQL Server Reporting Services 网站实例的默认主位置位于 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。 若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。

   确认名为 Microsoft BitLocker 管理和监视的报告文件夹包含名为 " **MaltaDataSource** " 的数据源，并且 " **en-us** " 文件夹包含四个报表。

   **注意**  
   如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http://* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"。 选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（Iis）管理器"。**

6. 在 **"连接" 中，** 浏览到 " * &lt; computername &gt; *"，选择 "**网站**"，然后选择 " **Microsoft BitLocker 管理和监视**"。 验证 " **MBAMAdministrationService**"、" **MBAMUserSupportService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。

7. 在安装了 "管理" 和 "监视" 功能和 "自助服务" 门户的服务器上，打开具有管理凭据的 web 浏览器，然后浏览到以下位置以验证它们是否成功加载：

   -   *http:// &lt; 主机名 &gt; /HelpDesk/default.aspx*并确认导航和报表的每个链接

   -   *http:// &lt; hostname &gt; /SelfService&gt;/*

   -   *http:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *http:// &lt; hostname &gt; /MBAMUserSupportService/UserSupportService.svc*

   -   *http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注意**  
   假设服务器功能安装在默认端口上，而不进行网络加密。 如果你在其他端口或虚拟目录上安装了服务器功能，请将 url 更改为包含相应的端口，例如*http:// &lt; 主机名 &gt; ： &lt; port &gt; /HelpDesk/default.asp*x 或*http:// &lt; 主机名 &gt; ： &lt; port &gt; / &lt; virtualdirectory &gt; /default.aspx*

   如果服务器功能是通过网络加密安装的，请将 http://更改为 https://。



## 相关主题


[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









