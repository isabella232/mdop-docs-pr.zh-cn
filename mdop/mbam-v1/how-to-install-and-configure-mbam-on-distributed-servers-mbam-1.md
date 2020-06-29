---
title: 如何在分布式服务器上安装和配置 MBAM
description: 如何在分布式服务器上安装和配置 MBAM
author: dansimp
ms.assetid: 9ee766aa-6339-422a-8d00-4f58e4646a5e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51f56a12d4e59226f834c7e474af0f1e96c1e8e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803812"
---
# 如何在分布式服务器上安装和配置 MBAM


本主题中的过程介绍了分布式服务器上的 Microsoft BitLocker 管理和监视（MBAM）功能的完整安装。

每个服务器功能都具有特定的先决条件。 若要验证你是否满足先决条件和硬件和软件要求，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。 此外，某些功能需要你在安装过程中提供特定信息才能成功部署该功能。

**注意**  
若要获取安装程序日志文件，必须通过使用**msiexec**程序包和 **/l &lt; LOCATION &gt; **选项来安装 MBAM。 将在您指定的位置创建日志文件。

其他安装日志文件将在运行 MBAM 安装的用户的% temp% 文件夹中创建。



## <a href="" id="deploy-the-mbam-server-features-"></a>部署 MBAM 服务器功能


以下步骤介绍了如何安装常规 MBAM 功能。

**注意**  
请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。



**部署 MBAM 服务器功能**

1.  启动 MBAM 安装向导，然后单击 "欢迎" 页面上的 "**安装**"。

2.  阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。

3.  默认情况下，将选择所有 MBAM 功能进行安装。 清除要在别处安装的功能。 要在同一台计算机上安装的功能必须同时安装。 MBAM 功能必须按以下顺序安装：

    -   恢复和硬件数据库

    -   合规性和审核数据库

    -   合规性审核和报告

    -   管理和监视服务器

    -   MBAM 组策略模板

    **注意**  
    安装向导将检查安装的先决条件，并显示缺少的必备条件。 如果满足所有先决条件，安装将继续。 如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。 如果此时间满足所有先决条件，安装将继续。



4.  MBAM 安装向导将显示所选功能的安装页面。 以下部分介绍了每个功能的安装过程。

    **注意**  
    通常情况下，每个功能都安装在单独的服务器上。 如果要在一台服务器上安装多个功能，您可以更改或删除以下某些步骤。



~~~
**To install the Recovery and Hardware Database**

1.  Choose an option for MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the names of the computers that will be running the Administration and Monitoring Server feature, to configure access to the Recovery and Hardware Database.. Once the Administration and Monitoring Server feature is deployed, it connects to the database by using its domain account.

4.  Click **Next** to continue.

5.  Specify the **Database Configuration** for the SQL Server instance that stores the recovery and hardware data. You must also specify where the database will be located and where the log information will be located.

6.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Database**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Compliance and Audit Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that will be used for encryption.

2.  Click **Next** to continue.

3.  Specify the user account that will be used to access the database for reports.

4.  Click **Next** to continue.

5.  Specify the computer names of the computers that you want to run the Administration and Monitoring Server and the Compliance and Audit Reports, to configure the access to the Compliance and Audit Database.. After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they will connect to the databases by using their domain accounts.

6.  Specify the **Database Configuration** for the SQL Server instance that will store the compliance and audit data. You must also specify where the database will be located and where the log information will be located.

7.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Reports**

1.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Compliance and Audit Database are installed.

2.  Specify the name of the Compliance and Audit Database. By default, the database name is “MBAM Compliance Status”, but you can change the name when you install the Compliance and Audit Database.

3.  Click **Next** to continue.

4.  Select the SQL Server Reporting Services instance where the Compliance and Audit Reports will be installed. Provide the username and password used to access the compliance database.

5.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Administration and Monitoring Server feature**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the remote SQL Server instance, For example, *&lt;ServerName&gt;*, where the Compliance and Audit Database are installed.

4.  Specify the name of the Compliance and Audit Database. By default, the database name is MBAM Compliance Status, but, you can change the name when you install the Compliance and Audit Database.

5.  Click **Next** to continue.

6.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Recovery and Hardware Database are installed.

7.  Specify the name of the Recovery and Hardware Database. By default, the database name is **MBAM Recovery and Hardware**, but you can change the name when you install the Recovery and Hardware Database feature.

8.  Click **Next** to continue.

9.  Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site. The default Home location of a SQL Server Reporting Services site instance is at:

    http://*&lt;NameofMBAMReportsServer&gt;/*ReportServer

    **Note**  
    If you configured the SQL Server Reporting Services as a named instance, the URL resembles the following:http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*



10. Click **Next** to continue.

11. Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server

    **Warning**  
    The port number that you specify must be an unused port number on the Administration and Monitoring server, unless you specify a unique host header name.



12. Click **Next** to continue with the MBAM Setup wizard.
~~~

5. 

   指定是否使用 Microsoft 更新来帮助保护您的计算机安全，然后单击 "**下一步**"。

6. 所选的 MBAM 功能信息完成后，即可使用设置向导启动 MBAM 安装。 如果必须查看或更改安装设置，请单击 "**返回**" 以在向导中移动。 单击 "**安装**" 以开始安装。 单击 "**取消**" 退出向导。 安装程序安装你选择的 MBAM 功能并通知你安装已完成。

7. 单击 "**完成**" 退出向导。

8. 在安装 MBAM 服务器功能后，将用户添加到相应的 MBAM 角色。 有关详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。

**安装后配置**

1.  在 MBAM 设置完成后，你必须添加用户角色，然后用户才能访问 MBAM 管理网站中的功能。 在 "管理和监视" 服务器上，将用户添加到以下本地组。

    -   **MBAM 硬件用户**：此本地组的成员可以访问 MBAM 管理网站中的硬件功能。

    -   **MBAM 支持人员用户**：此本地组的成员可以在 MBAM 管理网站中访问驱动器恢复和管理受信任的平台模块（TPM）功能。 驱动器恢复和管理 TPM 中的所有字段是支持人员用户的必填字段。

    -   **MBAM 高级帮助台用户**：此本地组的成员对驱动器恢复具有高级访问权限，并在 MBAM 管理网站中管理 TPM 功能。 对于高级帮助台用户，驱动器恢复中仅需要 "密钥 ID" 字段。 在 "管理 TPM" 中，仅需要 "计算机域字段" 和 "计算机名称" 字段。

2.  在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的服务器上，将用户添加到以下本地组，以便他们可以访问 MBAM 管理网站中的 "报告" 功能。

    -   **MBAM 报表用户**：此本地组的成员可以访问 MBAM 管理网站中的报表。

    **注意**  
    **MBAM 报表**的相同用户或组成员身份必须在所有计算机上维护，这些用户本地组 MBAM 管理和监视服务器功能、合规性和审核数据库以及合规性和审核报告已安装。



## 验证 MBAM 服务器功能安装


MBAM 服务器功能安装完成后，应验证安装是否已成功设置 MBAM 的所有必要功能。 使用以下过程确认 MBAM 服务是否正常工作。

**验证 MBAM 安装**

1. 在每台已部署 MBAM 功能的服务器上，打开 "**控制面板**"，单击 "**程序**"，然后单击 "**程序和功能**"。 验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。

   **注意**  
   若要验证 MBAM 安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。



2. 在安装了恢复和硬件数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 恢复和硬件**数据库。

3. 在安装合规性和审核数据库的服务器上，打开 SQL Server Management Studio 并验证是否已安装**MBAM 合规性状态**数据库。

4. 在安装合规性和审核报告的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的 "开始"。

   SQL Server Reporting Services 网站实例的默认起始位置可在 http:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 中找到 若要查找实际 URL，请使用 Reporting Services 配置管理器工具，并选择在安装过程中指定的实例。

   确认列出了名为 "**马耳他合规性报告**" 的文件夹，其中包含五个报表和一个数据源。

   **注意**  
   如果 SQL Server Reporting Services 配置为命名实例，则 URL 应类似于以下内容： http：//* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



5. 在安装了 "管理和监视" 功能的服务器上，运行 "**服务器管理器**" 并浏览到 "**角色**"，选择 " **Web 服务器（iis）**"，然后单击 " **Internet 信息服务（iis）管理器**"。 在 "**连接**" 中，浏览到* &lt; Computername &gt; *，单击 "**网站**"，然后单击 " **Microsoft BitLocker 管理和监视**"。 验证 " **MBAMAdministrationService**"、" **MBAMComplianceStatusService**" 和 " **MBAMRecoveryAndHardwareService** " 是否已列出。

6. 在安装了 "管理和监视" 功能的服务器上，打开具有管理权限的 web 浏览器，然后浏览到 MBAM 网站中的以下位置，验证它们是否已成功加载：

   -   *http:// &lt; computername &gt; /default.aspx*和确认导航和报表的每个链接

   -   *http:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注意**  
   通常情况下，服务安装在默认端口80上，而不进行网络加密。 如果服务安装在其他端口上，请将 Url 更改为包含相应的端口。 例如，http://* &lt; computername &gt; ： &lt; port &gt; */default.aspx 或 http:// <em> &lt; hostheadername &gt; / </em> 默认值 .aspx

   如果服务是通过网络加密安装的，请将 http://更改为 https://。



~~~
Verify that each web page loads successfully.
~~~

## 相关主题


[部署 MBAM 1.0 服务器基础结构](deploying-the-mbam-10-server-infrastructure.md)









