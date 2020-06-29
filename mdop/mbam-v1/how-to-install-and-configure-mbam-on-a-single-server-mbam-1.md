---
title: 如何在单个服务器上安装和配置 MBAM
description: 如何在单个服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 55841c63-bad9-44e7-b7fd-ea7037febbd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 225f66493ceafce5461df3fcc6f701e9a2922a5f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803500"
---
# 如何在单个服务器上安装和配置 MBAM


本主题中的过程介绍了单个服务器上的 Microsoft BitLocker 管理和监视（MBAM）功能的完整安装。

每个服务器功能都具有特定的先决条件。 若要验证你是否满足先决条件以及硬件和软件要求，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。 此外，某些功能还包含安装过程中必须提供的信息才能成功部署该功能。 在开始 MBAM 部署之前，还应查看[准备 MBAM 1.0 的环境](preparing-your-environment-for-mbam-10.md)。

**注意** 若要获取安装程序日志文件，必须通过使用**msiexec**程序包和 **/l** &lt; location 选项来安装 MBAM &gt; 。 将在您指定的位置创建日志文件。

在安装 MBAM 的用户的% temp% 文件夹中创建了其他安装日志文件。

 

## 在单个服务器上安装 MBAM 服务器功能


以下步骤介绍了如何安装常规 MBAM 功能。

**注意** 请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。

 

**启动 MBAM Server 功能安装**

1.  启动 MBAM 安装向导。 单击欢迎页面上的 "**安装**"。

2.  阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。

3.  默认情况下，将选择所有 MBAM 功能进行安装。 将在同一台计算机上安装的功能必须同时安装。 清除要在别处安装的功能。 必须按以下顺序安装 MBAM 功能：

    -   恢复和硬件数据库

    -   合规性和审核数据库

    -   合规性审核和报告

    -   管理和监视服务器

    -   MBAM 组策略模板

    **注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 满足所有先决条件后，安装将继续。

     

4.  系统将提示您配置网络通信安全。 MBAM 可以加密恢复和硬件数据库、管理和监视服务器以及客户端之间的通信。 如果你决定加密通信，系统将要求你选择要用于加密的授权机构预配的证书。

5.  单击**下一步**以继续。

6.  MBAM 安装向导将显示所选功能的安装页面。

**部署 MBAM 服务器功能**

1.  在 "**配置恢复和硬件数据库**" 窗口中，指定 SQL Server 实例以及将存储恢复和硬件数据的数据库的名称。 你还必须同时指定数据库文件位置和日志信息位置。

2.  单击**下一步**以继续。

3.  在 "**配置合规性和审核数据库**" 窗口中，指定 SQL Server 实例以及将存储合规性和审核数据的数据库的名称。 然后，指定数据库文件位置和日志信息位置。

4.  单击**下一步**以继续。

5.  在 "**合规性和审核报告**" 窗口中，指定将使用的报表服务实例，并提供用于访问数据库的域用户帐户。 这应该是专为此用途预配的用户帐户。 用户帐户应该能够访问 MBAM Reports Users 组中所有可用的数据。

6.  单击**下一步**以继续。

7.  在 "**配置管理和监视服务器**" 窗口中，输入**端口绑定**、**主机名**（可选）和 MBAM 管理和监视服务器的**安装路径**。

    **警告** 你指定的端口号必须是管理和监视服务器上未使用的端口号，除非指定了唯一的主机标题名称。

     

8.  单击**下一步**以继续。

9.  指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。 Microsoft Update 选项不会打开 Windows 中的自动更新。

10. 当安装向导收集了必要的功能信息时，MBAM 安装已准备好开始。 如果要查看或更改安装设置，请单击 "**返回**" 以在向导中向后移动。 单击 "**安装**" 以开始安装。 单击 "**取消**" 退出安装程序。 安装程序安装 MBAM 功能并通知您安装已完成。

11. 单击 "**完成**" 退出向导。

12. 安装 MBAM server 功能后，必须将用户添加到 MBAM 角色。 有关详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。

**执行安装后配置**

1.  安装完成后，你必须添加用户角色，以便你可以授予用户访问 MBAM 管理网站中的功能的权限。 在 "管理和监视" 服务器上，将用户添加到以下本地组：

    -   **MBAM 硬件用户**：此本地组的成员可以访问 MBAM 管理网站中的硬件功能。

    -   **MBAM 帮助台用户**：此本地组的成员可以访问 MBAM 管理网站中的驱动器恢复和管理 TPM 功能。 驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。

    -   **MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理网站中管理 TPM 功能。 对于高级帮助台用户，驱动器恢复中仅需要 "密钥 ID" 字段。 对于 "管理 TPM 用户"，仅需要 "计算机域字段" 和 "计算机名称" 字段。

2.  在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的计算机上，将用户添加到以下本地组以使其能够访问 MBAM 管理网站中的 "报告" 功能：

    -   **MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理网站中的报表功能。

    **注意** **MBAM 报表**的相同用户成员身份或组成员身份必须在已安装管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告的所有计算机上维护。

    若要在所有计算机上保持相同的成员身份，你应该创建一个域安全组，并将该域组添加到每个本地 MBAM Report Users 组。 执行此操作时，可以使用 "域" 组管理组成员身份。

     

## 验证 MBAM 服务器功能安装


MBAM 安装完成后，验证安装是否已成功设置 BitLocker 管理所需的所有必需 MBAM 功能。 使用以下过程确认 MBAM 服务是否正常运行：

**验证 MBAM 服务器功能安装**

1. 在部署 MBAM 功能的每台服务器上，打开 **"控制面板"**。 单击 "**程序**"，然后单击 "**程序和功能**"。 验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。

   **注意**  
   若要验证安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。

     

2. 在安装了恢复和硬件数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 恢复和硬件**数据库。

3. 在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 合规性和审核数据库**。

4. 在安装合规性和审核报告的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。

   SQL Server Reporting Services 网站实例的默认主位置位于 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。 若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。

   确认列出了名为 "**马耳他合规性报告**" 的文件夹，其中包含五个报表和一个数据源。

   **注意**  
   如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http：//* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *

     

5. 在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"，选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（iis）管理器**"

6. 在 "**连接**" 中，浏览到 " * &lt; computername &gt; *"，选择 "**网站**"，然后选择 " **Microsoft BitLocker 管理和监视**"。 验证 " **MBAMAdministrationService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。

7. 在安装了 "管理和监视" 功能的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 MBAM 网站中的以下位置以验证它们是否已成功加载：

   -   *http:// &lt; computername &gt; /default.aspx*和确认导航和报表的每个链接

   -   *http:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注意**  
   通常，服务安装在默认端口80上，而不进行网络加密。 如果服务安装在其他端口上，请将 Url 更改为包含相应的端口。 例如，http://* &lt; computername &gt; ： &lt; port &gt; */default.aspx 或 http:// <em> &lt; hostheadername &gt; / </em> 默认值 .aspx。

   如果服务是通过网络加密安装的，请将 http://更改为 https://。

     

## 相关主题


[部署 MBAM 1.0 服务器基础结构](deploying-the-mbam-10-server-infrastructure.md)

 

 





