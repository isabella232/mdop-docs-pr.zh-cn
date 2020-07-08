---
title: 如何在分布式服务器上安装和配置 MBAM
description: 如何在分布式服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 67b91e6b-ae2e-4e47-9ef2-6819aba95976
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 841b894430d14604f0fd923703708d7a3f588c07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803492"
---
# 如何在分布式服务器上安装和配置 MBAM


本主题中的过程介绍了如何在分布式服务器上的独立拓扑中安装 Microsoft BitLocker 管理和监视（MBAM）2.0。 若要查看推荐的体系结构的图表以及数据库和功能的说明，请参阅[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)。 若要通过 Configuration Manager 拓扑安装 Microsoft BitLocker 管理和监视，请参阅[通过 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。

每个服务器功能都具有特定的先决条件。 若要验证你是否满足先决条件和硬件和软件要求，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。 此外，某些功能需要你在安装过程中提供特定信息才能成功部署该功能。 在开始 MBAM 部署之前，还应查看[规划 MBAM 2.0 服务器部署](planning-for-mbam-20-server-deployment-mbam-2.md)。

**注意**  
若要获取安装程序日志文件，必须使用 Msiexec 程序包和 **/l** &lt; location &gt; 选项来安装 MBAM。 将在您指定的位置创建日志文件。

其他安装日志文件在安装 MBAM 的用户服务器上的% temp% 文件夹中创建。



## <a href="" id="deploying-mbam-server-features-"></a>部署 MBAM 服务器功能


以下步骤介绍了如何安装常规 MBAM 功能。

**启动 MBAM 服务器安装向导**

1.  在要安装 Microsoft BitLocker 管理和监视的服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。

2.  在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。

3.  阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。

4.  在 "**拓扑选择**" 页面上，选择**独立**拓扑，然后单击 "**下一步**"。

    **注意**  
    如果要通过 Configuration Manager 集成拓扑安装 MBAM，请参阅[通过 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。



5.  选择要安装的功能。 默认情况下，将选择所有 MBAM 功能进行安装。 清除要在别处安装的功能。 将在同一台计算机上安装的功能必须同时安装。 必须按以下顺序安装 MBAM 功能：

    -   恢复数据库

    -   合规性和审核数据库

    -   合规性和审核报告

    -   自助服务门户

    -   管理和监视服务器

    -   MBAM 组策略模板

    **注意**  
    安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 如果此时间满足所有先决条件，安装将继续。



~~~
The MBAM Setup wizard displays installation pages for the features that you select. The following sections describe the installation procedures for each feature.

**Note**  
For the following instructions, it is assumed that each feature is to be installed on a separate server. If you install multiple features on a single server, you can change or eliminate some steps.
~~~



**安装恢复数据库**

1.  在 "**配置恢复数据库**" 页面上，指定将运行 "管理和监视服务器" 功能的计算机的名称。 部署 "管理和监视服务器" 功能后，它将使用其域帐户连接到数据库。

2.  单击**下一步**以继续。

3.  指定要存储恢复数据的 SQL Server 实例名称和数据库的名称。 还必须指定数据库将位于的位置以及日志信息所在的位置。

4.  单击 "**下一步**" 继续 MBAM 设置向导。

**安装合规性和审核数据库**

1.  在 "**配置合规性和审核数据库**" 页面上，指定将用于访问报表的数据库的用户帐户。

2.  指定将运行管理和监视服务器以及合规性和审核报告的计算机的计算机名称。 在部署管理和监视以及合规性和审核报告服务器之后，他们将使用其域帐户连接到数据库。

    **注意**  
    如果在没有合规性和审核报告功能的情况下安装合规性和审核数据库，则必须在合规性和审核数据库计算机上添加异常，才能在 Microsoft SQL Server 端口上启用入站流量。 默认端口号为1433。



3.  指定 SQL Server 实例名称以及将存储合规性和审核数据的数据库的名称。 你还必须指定数据库和日志信息的位置。

4.  单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。

**安装合规性和审核报告**

1.  在 "**配置合规性和审核报告**" 页面上，指定 &lt; &gt; 安装合规性和审核数据库的远程 SQL Server 实例名称（例如，服务器名）。

    **注意**  
    如果在没有管理和监视服务器的情况下安装合规性和审核报告，则必须在合规性和审核报告计算机上添加例外，以便在报告服务器端口上启用入站流量（默认端口为80）。



2.  指定合规性和审核数据库的名称。 默认情况下，数据库名称是 MBAM 合规性状态，但你可以在安装合规性和审核数据库时更改名称。

3.  单击**下一步**以继续。

4.  选择将安装合规性和审核报告的 SQL Server Reporting Services 实例。 提供用于访问合规性和审核数据库的域用户帐户和密码。 将此帐户的密码配置为永不过期。 用户帐户应该能够访问 MBAM Reports Users 组中可用的所有数据。

5.  单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。

**安装自助服务门户**

1.  在 "**配置自助服务门户**" 页面上，您可以选择加密自助服务门户和管理和监视服务器之间的通信。 如果你选择加密通信的选项，系统将提示你选择用于加密的证书颁发机构预配的证书。

2.  单击**下一步**以继续。

3.  指定安装合规性和审核数据库的 SQL Server 远程实例（例如， * &lt; 服务器名 &gt; *）。

4.  指定合规性和审核数据库的名称。 默认情况下，数据库名称为 MBAM 合规性状态。 但是，你可以在安装合规性和审核数据库时更改名称。

5.  单击**下一步**以继续。

6.  指定安装了恢复数据库的 SQL Server 远程实例（例如， * &lt; 服务器名 &gt; *）。

7.  指定恢复数据库的名称。 默认情况下，数据库名称是**MBAM 恢复和硬件**。 但是，你可以在安装恢复数据库功能时更改名称。

8.  单击**下一步**以继续。

9.  输入**端口号**、**主机名**（可选）和 MBAM 管理和监视服务器的**安装路径**。

    **注意**  
    你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。 如果您使用的是 Windows 防火墙，则该端口将自动打开。



10. 若要选择性地注册自助服务门户的服务主体名称（SPN），请选择 "**使用 Active Directory 注册此计算机的服务主体名称（spn）" （Windows 身份验证所需）**。 如果选中此复选框，MBAM 安装程序将不会尝试注册现有的 Spn，你可以在 MBAM 安装之前或之后手动注册 SPN。 有关手动注册 SPN 的说明，请参阅[手动 SPN 注册](https://go.microsoft.com/fwlink/?LinkId=286758)。

11. 单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。

12. 指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。

13. 在所选的 MBAM 功能信息完成后，即可使用设置向导启动 MBAM 安装。 如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中移动。 单击 "**安装**" 以开始安装。 单击 "**取消**" 退出向导。 安装程序安装你选择的 MBAM 功能并通知你安装已完成。

14. 单击 "**完成**" 退出向导。

    **注意**  
    若要在安装自助服务门户之后配置它，请向自助服务门户提供公司名称和其他公司特定的信息，请参阅如何为[自助服务门户](how-to-brand-the-self-service-portal.md)提供有关说明的品牌。



15. 如果客户端计算机有权访问 Microsoft 内容交付网络（CDN），从而使自助服务门户对某些 JavaScript 文件所需的访问权限，则你已完成自助服务门户安装。 如果客户端计算机没有 Microsoft CDN 的访问权限，请完成下一节中的步骤，将自助服务门户配置为从易于访问的源中引用 JavaScript 文件。

**在最终用户无法访问 Microsoft Content 传递网络时配置自助服务门户**

1. 如果客户端计算机有权访问 Microsoft 内容交付网络（CDN），从而使自助服务门户对某些 JavaScript 文件所需的访问权限完成，则自助服务门户安装已完成。 如果客户端计算机没有 Microsoft CDN 的访问权限，请完成本部分中的其余步骤，将自助服务门户配置为从可访问的源中引用 JavaScript 文件。

2. 从 Microsoft CDN 下载四个 JavaScript 文件：

   -   jQuery-1.7.2.min.js-[https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)

   -   MicrosoftAjax.js-[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)

   -   MicrosoftMvcAjax.js-[https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)

   -   MicrosoftMvcValidation.js- <https://go.microsoft.com/fwlink/p/?LinkId=272285>

3. 将 JavaScript 文件复制到自助服务门户的 "**脚本**" 目录中。 此目录位于 <em> &lt; MBAM 自助服务安装目录 &gt; \\ </em> 自助服务 Website\\Scripts。

4. 打开**Internet Information Services （IIS）管理器**。

5. 展开 "**网站** &gt; **Microsoft BitLocker 管理和监视**"，然后突出显示**SelfService**。

   **注意**  
   *SelfService*是默认的虚拟目录名称。 如果在安装过程中为此目录选择了其他名称，请记住将其余说明中的*SelfService*替换为您选择的名称。



6. 在中间窗格中，双击 "**应用程序设置**"。

7. 对于下表中的每一项，通过 &lt; &gt; 使用/SelfService/（或在安装过程中选择的名称）替换虚拟目录来编辑应用程序设置以引用新位置。 例如，虚拟目录路径将类似于/selfservice/scripts/jquery-1.7.2.min.js。

   -   jQueryPath：/ &lt; virtual directory &gt; /Scripts/jQuery-1.7.2.min.js

   -   MicrosoftAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftAjax.js

   -   MicrosoftMvcAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcAjax.js

   -   MicrosoftMvcValidationPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcValidation.js

**安装 "管理和监视服务器" 功能**

1. MBAM 可以加密 Web 服务与管理和监视服务器之间的通信。 如果你选择加密通信的选项，系统将提示你选择用于加密的证书颁发机构预配的证书。

2. 单击**下一步**以继续。

3. 指定安装合规性和审核数据库的 SQL Server 远程实例（例如： * &lt; ServerName &gt; *）。

4. 指定合规性和审核数据库的名称。 默认情况下，数据库名称为 MBAM 合规性状态。 但是，你可以在安装合规性和审核数据库时更改名称。

5. 单击**下一步**以继续。

6. 指定安装了恢复数据库的 SQL Server 远程实例（例如： * &lt; ServerName &gt; *）。

7. 指定恢复数据库的名称。 默认情况下，数据库名称是**MBAM 恢复和硬件**。 但是，你可以在安装恢复数据库功能时更改名称。

8. 单击**下一步**以继续。

9. 指定 SQL Server Reporting Services （SRS）网站的 "开始" URL。 SQL Server Reporting Services 网站实例的默认起始位置为：

   http:// <em> &lt; NameofMBAMReportsServer &gt; / </em> ReportServer

   **注意**  
   如果 SQL Server Reporting Services 配置为命名实例，则 URL 类似于以下内容： http://* &lt; NameofMBAMReportsServer &gt; */ReportServer\_* &lt; SRSInstanceName &gt; *。



10. 单击**下一步**以继续。

11. 输入**端口号**、**主机名**（可选）和 MBAM 管理和监视服务器的**安装路径**。

    **注意**  
    你指定的端口号必须是管理和监视服务器上未使用的端口号，除非你指定唯一的主机标题名称。 如果您使用的是 Windows 防火墙，则该端口将自动打开。



12. 若要选择性地注册自助服务门户的服务主体名称（SPN），请选择 "**使用 Active Directory 注册此计算机的服务主体名称（spn）" （Windows 身份验证所需）**。 如果选中此复选框，MBAM 安装程序将不会尝试注册现有的 Spn，你可以在 MBAM 安装之前或之后手动注册 SPN。 有关手动注册 SPN 的说明，请参阅[手动 SPN 注册](https://go.microsoft.com/fwlink/?LinkId=286758)。

13. 单击 "**下一步**" 以继续 "Microsoft BitLocker 管理和监视设置向导"。

14. 指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。

15. 在所选的 MBAM 功能信息完成后，即可使用设置向导启动 MBAM 安装。 如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中移动。 单击 "**安装**" 进行安装。 单击 "**取消**" 退出向导。 安装程序安装你选择的 MBAM 功能并通知你安装已完成。

16. 单击 "**完成**" 退出向导。

**执行安装后配置**

1.  在 "管理和监视" 服务器上，将用户添加到以下本地组，以使其可以访问 MBAM 管理和监视网站上的功能。

    -   **MBAM 帮助台用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的驱动器恢复和管理 TPM 功能。 驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。

    -   **MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理和监视网站上管理 TPM 功能。 对于高级帮助台用户，驱动器恢复中仅需要 "密钥 ID" 字段。 在 "**管理 TPM**" 中，仅需要 "**计算机域**字段" 和 "**计算机名称**" 字段。

2.  在托管管理和监视服务器以及合规性和审核数据库以及托管合规性和审核报告的服务器上的服务器上，将用户添加到以下本地组，以便他们可以访问 MBAM 管理和监视网站上的 "报告" 功能。

    -   **MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的报表。

    **注意**  
    **MBAM 报表**的相同用户或组成员身份必须在所有计算机上维护，这些用户本地组 MBAM 管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告已安装。



## 验证 MBAM 服务器功能安装


Microsoft BitLocker 管理和监视服务器功能安装完成后，建议你验证安装是否已成功设置 MBAM 的所有必要功能。 使用以下过程确认 Microsoft BitLocker 管理和监视服务正常运行。

**验证 MBAM 服务器安装**

1. 在部署 MBAM 功能的每台服务器上，打开 "**控制面板**"，选择 "**程序**"，然后选择 "**程序和功能**"。 验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。

   **注意**  
   若要验证 MBAM 安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。



2. 在安装了恢复数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 恢复和硬件**数据库。

3. 在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 合规性状态数据库**。

4. 在安装合规性和审核报告的服务器上，使用管理凭据打开 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。

   可以在 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 上找到 SQL Server Reporting Services 网站实例的默认起始位置 若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。

   确认名为**Microsoft BitLocker 管理和监视**的报告文件夹包含名为 " **MaltaDataSource** " 的数据源，并且 " **en-us** " 文件夹包含四个报表。

   **注意**  
   如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http：//* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"。 选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（Iis）管理器**"。

6. 在 "**连接**" 中，浏览到 " * &lt; computername &gt; *"，选择 "**网站**"，然后选择 " **Microsoft BitLocker 管理和监视**"。 验证 " **MBAMAdministrationService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。

7. 在安装了 "管理" 和 "监视" 功能和 "自助服务" 门户的服务器上，打开具有管理凭据的 web 浏览器，然后浏览到以下位置以验证它们是否成功加载。

   **注意**  
   以 ".svc" 结尾的 Url 不会显示网站。 成功由消息 "此服务的元数据发布当前已禁用" 或类似代码的信息指示。 如果您看到其他错误消息，或者如果找不到页面，则页面未成功加载。



~~~
-   *http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports

-   *http://&lt;hostname&gt;/SelfService&gt;/*

-   *http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc*

-   *http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc*

-   *http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc*

-   *http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc*

**Note**  
It is assumed that the server features were installed on the default port without network encryption. If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.aspx* or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*

If the server features were installed with network encryption, change http:// to https://.
~~~



8. 验证每个网页是否已成功加载。

## 相关主题


[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









