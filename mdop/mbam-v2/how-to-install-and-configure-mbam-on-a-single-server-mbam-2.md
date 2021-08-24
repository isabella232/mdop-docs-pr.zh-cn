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
ms.openlocfilehash: 4dffe2e2dcb82866b86a3ac281aca8a0dcaab686
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910657"
---
# <a name="how-to-install-and-configure-mbam-on-a-single-server"></a>如何在单个服务器上安装和配置 MBAM


本主题中的过程介绍如何在单台服务器上的独立 (中安装 Microsoft BitLocker 管理和监视 (MBAM) 。 仅在测试环境中使用单服务器配置。 对于生产环境，请使用两台或多台服务器。 如果要使用 Configuration Manager 拓扑安装 Microsoft BitLocker 管理和监控，请参阅使用[Configuration Manager 部署 MBAM。](deploying-mbam-with-configuration-manager-mbam2.md)

下图显示了单服务器体系结构的示例。 有关数据库和功能的说明，请参阅 [MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md)的高级别体系结构。

![mbam 2 单服务器部署拓扑。](images/mbam2-1-server.gif)

每个服务器功能都有某些先决条件。 若要验证是否满足先决条件以及硬件和软件要求，请参阅[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 Supported Configurations。](mbam-20-supported-configurations-mbam-2.md) 此外，某些功能还有在安装过程中必须提供的信息，以成功部署该功能。 你还应该在开始 MBAM 部署之前查看准备 [MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md) 环境。

**注意**  
若要获取安装日志文件，请使用 Msiexec 程序包和 **/L** &lt; 位置 &gt; 选项安装 MBAM。 日志文件是在您指定的位置创建的。

其他安装程序日志文件是在安装 MBAM 的用户的服务器的 %temp% 文件夹中创建的。



## <a name="to-install-mbam-server-features-on-a-single-server"></a>在单台服务器上安装 MBAM 服务器功能


以下步骤介绍如何安装常规 MBAM 功能。

**启动 MBAM 服务器功能安装**

1.  在你想要安装 MBAM 的服务器上 ** ，MBAMSetup.exe** 启动 MBAM 安装向导。

2.  在"**欢迎**"页上，选择"**客户体验**改善计划"，然后单击"开始 **"。**

3.  阅读并接受 Microsoft 软件许可协议，然后单击"下一**** 步"继续安装。

4.  在"**拓扑选择"** 页上，选择"独立**拓扑**"，然后单击"下一步 **"。**

5.  在 **"选择要安装的功能"页上** ，选择要安装的功能。 默认情况下，选择所有 MBAM 功能进行安装。 必须同时安装要安装在同一台计算机中的功能。 清除要安装在其他位置的任何功能的复选框。 必须按以下顺序安装 MBAM 功能：

    -   恢复数据库

    -   合规性和审核数据库

    -   合规性和审核报告

    -   Self-Service 服务器

    -   管理和监控服务器

    -   MBAM 组策略模板

    **注意**  
    安装向导将检查安装的先决条件并显示缺少的先决条件。 如果满足所有先决条件，则继续安装。 如果检测到缺少的必备组件，必须解决缺少的先决条件，然后再次单击"**检查先决条件"。** 如果此时满足所有先决条件，则继续安装。



6.  在" **配置网络通信安全** "页上，选择是否加密管理和监控服务器上 Web 服务与客户端之间的通信。 如果决定加密通信，请选择证书颁发机构预配的证书以用于加密。 必须在此步骤之前创建证书，才能在此页面上选择它。

    **注意**  
    只有在选择"选择要安装的功能"页上Self-Service"门户"或"管理和监控服务器"功能时，才能 **显示** 此页面。



7.  单击 **"** 下一步"，然后继续下一组步骤以配置 MBAM 服务器功能。

**配置 MBAM 服务器功能**

1.  在 **"配置恢复数据库**"页上，SQL Server实例名称以及存储恢复数据的数据库的名称。 还必须同时指定数据库文件的位置和日志信息的位置。

2.  单击**下一步**以继续。

3.  在 **"配置合规性和**审核数据库"页上，SQL Server实例名称和将存储合规性和审核数据的数据库的名称。 还必须指定数据库文件的位置以及日志信息的位置。

4.  单击**下一步**以继续。

5.  在"**** 配置合规性和审核报告"页上，指定将安装合规性和审核报告SQL Server Reporting Services实例，并提供用于访问合规性和审核数据库的域用户帐户和密码。 配置此帐户的密码永不过期。 用户帐户应能够访问 MBAM 报告用户组的所有可用数据。

6.  单击**下一步**以继续。

7.  在" **配置 Self-Service** 门户"页上，输入 Self-Service 门户的端口号、主机名、虚拟目录名称和安装路径。

    **注意**  
    指定的端口号必须是管理和监控服务器上未使用的端口号，除非您指定了唯一的主机头名称。 如果使用防火墙Windows，将自动打开端口。



8.  单击**下一步**以继续。

9.  指定是否使用 Microsoft 更新来帮助保护计算机安全，然后单击下一 **步**。 这不会在更新中打开Windows。

10. 在" **配置管理和监控服务器** "页上，输入 Help Desk 网站的端口号、主机名、虚拟目录名称和安装路径。

    **注意**  
    指定的端口号必须是管理和监控服务器上未使用的端口号，除非您指定了唯一的主机头名称。 如果使用防火墙Windows，将自动打开端口。



11. 在 **"安装摘要"** 页上，查看将安装的功能列表，然后单击"安装"开始安装**** MBAM 功能。 如果需要 **查看** 或更改安装设置，请单击"上一步"以在向导中后退，或单击"取消 **"退出安装程序** 。 安装程序将安装 MBAM 功能，并通知你安装已完成。

12. 单击 **"完成** "退出向导。 安装 Microsoft BitLocker 管理和监控服务器功能后，继续下一部分并完成将用户添加到 Microsoft BitLocker 管理和监控角色的步骤。 有关角色详细信息，请参阅规划 [MBAM 2.0 管理员角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。

**执行安装后配置**

1.  在管理和监控服务器上，将用户添加到以下本地组，以授予他们访问 MBAM 技术支持网站功能的访问权限：

    -   **MBAM 支持人员用户**：此本地组的成员可以访问 MBAM 管理和监视网站上驱动器恢复和管理 TPM 功能。 驱动器恢复和管理 TPM 中所有字段都是支持人员用户的必填字段。

    -   **MBAM 高级支持人员用户**：此本地组的成员具有对 MBAM 管理和监控网站上驱动器恢复和管理 TPM 功能的高级访问权限。 对于高级支持人员用户，驱动器恢复中只需要密钥 **ID** 字段。 在"管理 TPM"中，只需要" **计算机域** "字段和 **"计算机名称** "字段。

2.  在管理和监控服务器上，将用户添加到以下本地组，以便他们可以访问 MBAM 管理和监控网站上的报告功能：

    -   **MBAM 报告用户**：此本地组的成员可以访问 MBAM 管理和监视网站上的报告功能。

    -   使用Self-Service名称、通知文本和其他公司特定信息为门户品牌。 有关说明，请参阅 [如何品牌化Self-Service门户](how-to-brand-the-self-service-portal.md)。

    **注意**  
    **MBAM**报告用户本地组的相同用户或组成员身份必须在安装了 MBAM 管理和监控服务器功能、合规性和审核数据库以及合规性和审核报告的所有计算机上进行维护。 为此，建议创建一个域安全组，并将其添加到每个本地 MBAM 报告用户组。 使用此过程时，请通过域组来管理组成员身份。



## <a name="validating-the-mbam-server-feature-installation"></a>验证 MBAM 服务器功能安装


完成 Microsoft BitLocker 管理和监控安装后，验证安装是否成功设置了 BitLocker 管理所需的全部 MBAM 功能。 使用以下过程确认 MBAM 服务是否正常工作。

**验证 MBAM 服务器功能安装**

1. 在部署了 MBAM 功能的每台服务器上，打开 **"控制面板"。** 选择 **"程序**"，然后选择"**程序和功能"。** 验证 **Microsoft BitLocker 管理和监控** 是否显示在 **"程序和功能"列表中** 。

   **注意**  
   若要验证安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。



2. 在安装了恢复数据库的服务器上，SQL Server Management Studio，并验证**是否安装了 MBAM 恢复和硬件**数据库。

3. 在安装了合规性和审核数据库的服务器上，SQL Server Management Studio验证是否安装了**MBAM**合规性状态数据库。

4. 在安装了合规性和审核报告的服务器中，使用管理凭据打开 Web 浏览器并浏览到 SQL Server Reporting Services 主页。

   网站实例的默认"主页"SQL Server Reporting Services位于 <em> &lt; Nameof HTTP:// MReportsServer &gt; </em> /Reports。 若要查找实际 URL，请使用 Reporting Services Configuration Manager 工具并选择在安装过程中指定的实例。

   确认名为"Microsoft BitLocker 管理和监控"的 Reports 文件夹包含一个名为 **"为"的数据源** ，以及 **"en-us"** 文件夹是否包含四个报告。

   **注意**  
   如果将 SQL Server Reporting Services配置为命名实例，则 URL 应类似于以下内容：http://* &lt; Nameof 是由 NAMEOF HTTP:// ReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 在安装了管理和监控功能的服务器中，运行 **服务器管理器** 并浏览到 **角色**。 选择 **"Web 服务器 (IIS) "，** 然后单击"IIS Internet Information Services (**管理器) " 。**

6. 在 **"连接"中**，浏览到* &lt; 计算机名 &gt; *，选择"**站点**"，然后选择 **"Microsoft BitLocker 管理和监控"。** 验证是否列出了 MBAMAdministrationService、MBAMUserSupportService、MBAMComplianceStatusService 和**MBAMRecoveryAndHardwareService。** **** **** ****

7. 在安装了管理和监控功能和 Self-Service 门户的服务器上，使用管理凭据打开 Web 浏览器并浏览到以下位置以验证它们是否成功加载：

   -   *http:// &lt; hostname &gt; /HelpDesk/default.aspx* 并确认导航和报告的每个链接

   -   *http:// &lt; hostname &gt; /SelfService&gt;/*

   -   *http:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *http:// &lt; 主机名 &gt; /MBAMUserSupportService/UserSupportService.svc*

   -   *http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *http:// &lt; 计算机名 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注意**  
   假定服务器功能安装在默认端口上，而不进行网络加密。 如果在不同的端口或虚拟目录中安装了服务器功能，请更改 URL 以包括相应的端口，例如 *，http:// 主机名 ： port &lt; &gt; &lt; &gt; /HelpDesk/default.asp*x 或 http://* &lt; hostname ： &gt; port &lt; &gt; / &lt; virtualdirectory &gt; /default.aspx*

   如果服务器功能是使用网络加密安装的，http:// 更改为 https://。



## <a name="related-topics"></a>相关主题


[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









