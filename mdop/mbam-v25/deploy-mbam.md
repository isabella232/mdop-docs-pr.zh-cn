---
title: 在独立配置中部署 MBAM 2.5
description: 介绍了如何在独立配置中部署 MBAM 2.5。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 1ceccf3973bb131484f91917c2b80cd676d1c31b
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910467"
---
# <a name="deploying-mbam-25-in-a-standalone-configuration"></a>在独立配置中部署 MBAM 2.5

本文提供有关在独立配置中安装 Microsoft BitLocker 管理和监视 (MBAM) 2.5 的分步说明。 在本指南中，我们将使用双服务器配置。 这两台服务器之一将是在 2012 数据库服务器运行Microsoft SQL Server服务器。 此服务器将托管 MBAM 数据库和报告。 附加服务器将是承载"Windows Server 2012和监控服务器"和"自助式门户"的 Web 服务器。

## <a name="preparation-steps-before-installing-mbam-25-server-software"></a>安装 MBAM 2.5 服务器软件之前的准备步骤

### <a name="step-1-installation-and-configuration-of-servers"></a>步骤 1：安装和配置服务器

在开始配置 MBAM 2.5 之前，必须确保根据 MBAM 系统要求配置这两台服务器。 请参阅 [MBAM 最低系统要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)，然后选择满足这些要求的配置。 

#### <a name="step-11-deploying-prerequisites-for-database-and-reporting-server"></a>步骤 1.1：部署数据库和报告服务器的先决条件

1. 安装和配置运行 Windows Server 2008 R2 (或更高版本) 服务器。

2. 安装 Windows PowerShell 3.0。

3. 安装 Microsoft SQL Server 2008 R2 或更高版本，其中包含最新的 Service Pack。 如果要为 MBAM 安装新的 SQL Server 实例，请确保SQL Server包括 SQL_Latin1_General_CP1_CI_AS 排序规则。 必须安装以下SQL Server功能：

    * 数据库引擎
    * Reporting Services
    * 客户端工具连接
    * 管理工具 – 完成

    > [!Note]
    > （可选）还可以在 SQL Server[中透明数据加密 (TDE) 功能](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)。

    SQL Server Reporting Services必须以"本机"模式安装并配置，而不是在未配置或"SharePoint"模式下。

    ![必需的SQL Server功能。](images/deploying-MBAM-1.png)

4. 如果您计划将 SSL 用于管理和监控网站，请确保在配置管理和监控网站之前将 SQL Server Reporting Services (SSRS) 配置为使用安全套接字层 (SSL) 协议。 否则，报告功能将使用未加密 (HTTP) 数据传输，而不是使用 (HTTPS) 。

    你可以按照在 [本机模式](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017) 报表服务器上配置 SSL 连接在报表服务器上配置 SSL。
    
    > [!Note]
    > 你可以按照SQL Server版本安装指南安装SQL Server安装SQL Server。 链接如下所示：
        > * [SQL Server 2014 年](https://docs.microsoft.com/sql/sql-server/install/planning-a-sql-server-installation?view=sql-server-2014)
        > * [SQL Server 2012 年](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))
        > * [SQL Server 2008 R2](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))

5. 在安装 SQL Server 后，请确保在 SQL Server 中预配用户帐户，并将以下权限分配给将在 数据库服务器 上配置 MBAM 数据库和报告角色的用户。

    角色实例的角色SQL Server：
        
    * dbcreator
    * processadmin

    应用程序实例SQL Server Reporting Services：
    
    * 创建文件夹
    * 发布报告

你的数据库服务器已准备好配置 MBAM 2.5 角色。 让我们移到下一台服务器。

#### <a name="step-12-deploying-prerequisites-for-administration-and-monitoring-server"></a>步骤 1.2：部署管理和监控服务器的先决条件

选择符合硬件配置的服务器，如 [MBAM 系统要求文档 所说明](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)。 它必须在 Windows Server 2008 R2 或更高版本的操作系统以及最新的 Service Pack 和更新中运行。 服务器准备就绪后，安装以下角色和功能：

##### <a name="roles"></a>角色

* Web Server (IIS) 管理工具 (选择 IIS 管理脚本和工具。) 

* Web 服务器角色服务

    * 常用 HTTP 功能<br />
      静态内容<br />
      默认文档

    * 应用程序开发<br />
      ASP.NET<br />
      .NET 扩展性<br />
      ISAPI 扩展<br />
      ISAPI 筛选器<br />
      安全性<br />
      Windows 身份验证<br />
      请求筛选

    * Web 服务 IIS 管理工具

##### <a name="feature"></a>功能

* .NET Framework 4.5 功能
  
  * Microsoft .NET Framework 4.5
  
    对于 Windows Server 2012 或 Windows Server 2012 R2，.NET Framework这些版本的 Windows Server 已安装 4.5。 但是，必须启用它。
  
    对于 Windows Server 2008 R2，.NET Framework Server 2008 R2 中不包含 Windows 4.5。 因此，你必须下载 .NET Framework 4.5 并单独安装它。
  
  * WCF 激活<br />
    HTTP 激活<br />
    非 HTTP 激活
  
  * TCP 激活
  
  * Windows进程激活服务：<br />
    进程模型<br />
    .NET Framework环境<br />
    配置 API

若要使自助服务门户正常工作，还应下载并安装 ASP.NET [MVC 4.0。](https://go.microsoft.com/fwlink/?linkid=392271)

下一步是在 Active Directory 中创建所需的 MBAM 用户和组。

### <a name="step-2-creating-users-and-groups-in-active-directory-domain-services"></a>步骤 2：在 Active Directory 域服务中创建用户和组
 
作为先决条件的一部分，您必须定义 MBAM 中使用的某些角色和帐户，以提供对特定服务器和功能（如 SQL Server 实例上运行的数据库以及管理和监控服务器上运行的 Web 应用程序）的安全性和访问权限。

在 Active Directory 中创建以下组和用户。  (可以使用组和用户的任何名称。) 用户不需要拥有更高的用户权限。 域用户帐户已足够。 在配置 MBAM 2.5 期间，必须指定这些组的名称：

* **MBAMAppPool**  

  **类型**：域用户

  **说明**：对合规性和审核数据库和恢复数据库具有读取或写入权限以允许 Web 应用程序访问这些数据库中的数据和报表的域用户。 它还将被 Web 应用程序的 应用程序池使用。

  **在 MBAM (配置期间使用的帐户) ： **

  1. Web 服务应用程序池域帐户

  2. 合规性和审核数据库和恢复数据库报表的用户读/写

* **MBAMROUser**

  **类型**：域用户

  **说明**：将有权访问Read-Only和审核数据库的域用户，使报告能够访问此数据库中的合规性和审核数据。 它还将是本地数据库实例用于访问合规性SQL Server Reporting Services审核数据库的域用户帐户。

  **在 MBAM (配置期间使用的帐户) ： **

  1. 报告合规性和审核数据库只读用户

  2. 合规性和审核数据库域用户帐户

* **MBAMAdvHelpDsk**

  **类型**：域组

  **说明**：MBAM 高级支持人员用户访问组：其成员有权访问管理和监控网站所有领域的域用户组。 具有此角色的用户在帮助用户恢复驱动器时，只需输入恢复密钥，而不是用户的域和用户名。 如果用户是 MBAM 支持用户组和 MBAM 高级支持用户组的成员，MBAM 高级支持人员用户组权限将覆盖 MBAM 支持组权限。

  **在 MBAM (配置期间使用 **的帐户) ：MBAM 高级支持人员用户

* **MBAMHelpDsk**

  **类型**：域组

  **说明**：MBAM 支持人员用户访问组：其成员有权访问 MBAM 管理和监控网站的管理 TPM 和驱动器恢复领域的域用户组。 具有此角色的人必须在使用任一选项时填写所有字段。 这包括用户的域和帐户名称。

  **在 MBAM (配置期间使用的帐户) **：MBAM 支持人员用户

* **MBAMRUGrp**

  **类型**：域组

  **说明**：其成员对管理和监控网站的"报告"区域中的报告具有只读访问权限的域用户组。

  **在 MBAM (配置期间使用的帐户) ： **

  1. 报告只读域访问组

  2. MBAM 报告用户访问组

### <a name="step-3-optional-configure-and-install-ssl-certificate-on-administration-and-monitoring-server"></a>步骤 3 (可选) ：在管理和监控服务器上配置和安装 SSL 证书

尽管这是可选的，但我们强烈建议你使用证书来帮助保护 MBAM 客户端与管理和监控网站以及 Self-Service之间的通信。 由于明显的安全原因，建议不要使用自签名证书。 建议您使用来自受信任证书颁发机构的 Web 服务器类型证书。 为此，可以从 KB 或 2754259 中引用"使用证书颁发机构批准的 [证书"部分](https://support.microsoft.com/help/2754259)。

证书颁发后，您应将证书添加到管理和监控服务器的个人存储中。 若要添加证书，请在本地计算机上打开证书存储。 为此，请执行下列步骤：

1. 右选择"开始"，然后选择"运行"。

   ![选择。](images/deploying-MBAM-2.png)

2. 键入"MMC.EXE" (不带引号) ，然后选择"确定 **"。**

   ![运行框。](images/deploying-MBAM-3.png) 

3. 选择**打开**的新 MMC 中的"文件"，然后选择"**添加/删除管理单元"。**
   
   ![选择。](images/deploying-MBAM-4.png)

4. 突出显示"**证书"** 管理单元，然后选择"添加 **"。**

   !["添加或删除管理单元"窗口。](images/deploying-MBAM-5.png)

5. 选择计算机 **帐户选项** ，然后选择下一 **步**。
   
   ![证书管理单元窗口。](images/deploying-MBAM-6.png)

6. 选择**下一个**屏幕上的本地计算机，**然后选择完成。**
   
   ![选择计算机窗口。](images/deploying-MBAM-7.png)

7. 现在，你已添加"证书"管理单元。 这将使您能够使用计算机证书存储中任何证书。

   !["添加或删除管理单元"窗口。](images/deploying-MBAM-8.png)

8. 将 Web 服务器证书导入到计算机的证书存储中。

   现在，你有权访问证书管理单元，可以将 Web 服务器证书导入到计算机的证书存储中。 为此，请按照后续步骤操作。

9. 打开"本地 (证书) 管理单元，然后浏览到"个人"和"证书 **"。** ****
   
   ![证书 (本地计算机) 管理单元窗口。](images/deploying-MBAM-9.png)

   > [!Note]
   > "证书"管理单元可能未列出。 如果未安装，则不安装任何证书。

10. 右选择"**证书"，** 选择"**所有任务**"，然后选择"导入 **"。**

    ![证书 (本地计算机) 管理单元窗口。](images/deploying-MBAM-10.png)

11. 向导启动时，选择"下一**步"。** 浏览到您创建的包含服务器证书和私钥的文件，然后选择"下一步 **"。**

    ![证书导入向导窗口。](images/deploying-MBAM-11.png)

12. 如果在创建文件时为该文件指定了密码，请输入密码。

   ![输入密码窗口。](images/deploying-MBAM-12.png)

   > [!Note]
   > 如果希望再次 **从此计算机** 导出密钥对，请确保选中"将密钥标记为可导出"选项。 作为新增的安全措施，你可能希望清除此选项，以确保没有人可以备份你的私钥。
 
13. 选择 **"** 下一步"，**** 然后选择要保存证书的证书存储。

    ![证书导入向导窗口。](images/deploying-MBAM-13.png)

    > [!Note]
    > 应选择 **"个人"，** 因为它是 Web 服务器证书。 如果证书包含在证书层次结构中，也将添加到此存储中。
 
14. 选择 **"下一**步"，然后选择"完成 **"。**

    ![证书导入向导窗口。](images/deploying-MBAM-14.png)

现在，你将在"个人证书"列表中看到 Web 服务器的服务器证书。 它将用服务器的公用名表示。  (可以在证书的主题部分找到) 

进一步参考：

[MBAM 2.5 安全注意事项](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

[规划如何保护 MBAM 网站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

下一步是为帐户注册服务应用程序池名称。

### <a name="step-4-configuring-ssl-certificate-for-mbam-web-server"></a>步骤 4：为 MBAM Web 服务器配置 SSL 证书

如果使用客户端和服务器之间的 SSL 通信，应确保证书具有增强型密钥使用 OIDs (1.3.6.1.5.5.7.3.1) 和 (1.3.6.1.5.5.7.3.2) 。 也就是说，应确保已添加"服务器身份验证"和"客户端身份验证"。

如果您在尝试浏览服务 URL 时收到证书错误，您使用的是颁发给不同名称的证书，或者您使用的是不正确的 URL 进行浏览。

尽管浏览器可能会提示你显示证书错误消息，但你可以继续操作，但 MBAM Web 服务不会忽略证书错误，并且会阻止连接。 你将注意到 MBAM 客户端的 MBAM 管理员事件日志中出现与证书相关的错误。 如果使用别名连接到管理和监控服务器，应为别名颁发证书。 即，证书的主题名称应为别名，本地服务器的 DNS 名称应添加到证书的 **"Subject Alternative Name"** 字段中。

示例：

如果虚拟名称为"bitlocker.contoso.com"且 MBAM 管理和监控服务器名称为"adminserver.contoso.com"，则证书应颁发给 bitlocker.contoso.com (主题名称) ，并且 adminserver.contoso.com 应添加到证书的 Subject **Alternative Name** 字段中。

同样，如果安装了多台管理和监控服务器以使用负载平衡器平衡负载，则应该向虚拟名称颁发 SSL 证书。 即，证书的"主题名称"字段应具有虚拟名称，并且所有本地服务器的名称都应添加到证书的"Subject **Alternative Name"** 字段中。

示例：

如果虚拟名称为"bitlocker.contoso.com"且服务器为"adminserver1.contoso.com"和"adminiserver2.contoso.com"，则证书应颁发给 bitlocker.contoso.com (主题名称) 和 adminserver1.contoso.com，并且 adminiserver2.contoso.com 应添加到证书的"主题备用名称"字段中。 ****

以下知识库文章介绍了使用 MBAM 配置 SSL 通信的步骤[：KB 2754259。](https://support.microsoft.com/help/2754259)

### <a name="step-5-register-spns-for-the-application-pool-account-and-configure-constrained-delegation"></a>步骤 5：为 应用程序池 帐户注册 SNS 并配置约束委派

> [!Note]
> 约束委派仅适用于 2.5，2.5 Service Pack 1 及更高版本不需要约束委派。

若要使 MBAM 服务器对来自管理和监控网站以及 Self-Service 门户的通信进行身份验证，必须在用于 Web 应用程序池 的域帐户下为主机名注册服务主体名称 (SPN) 。 以下文章包含注册 SNS 的分步说明 [：规划如何保护 MBAM 网站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

配置 SPN 后，应在 SPN 上设置约束委派。 为此，请执行下列步骤：

1. 转到 Active Directory，并查找你在之前步骤中为 MBAM 网站配置的应用池凭据。

2. 右键单击凭据， **然后选择属性**。

3. 选择委派 **选项卡** 。

4. 选择"Kerberos 身份验证"选项。

5. 选择 **"** 浏览"，然后再次浏览应用程序池凭据。 然后，应看到在应用程序池 creds 帐户上设置的所有 SNS。  (SPN 应类似于"http/bitlocker.fqdn.com") 。 突出显示与在 MBAM 安装期间指定的主机名相同的 SPN。

6. 选择“确定”****。

现在，你已做好必备条件。 在以下步骤中，你将在服务器上安装 MBAM 软件并对其进行配置。

## <a name="installing-and-configuring-mbam-25-server-software"></a>安装和配置 MBAM 2.5 服务器软件

### <a name="step-6-install-mbam-25-server-software"></a>步骤 6：安装 MBAM 2.5 服务器软件 

若要使用 Microsoft BitLocker 管理和监视安装向导在数据库服务器以及管理和监控服务器上安装 MBAM 服务器软件，请按照以下步骤操作。

1. 在你要安装 MBAM 的服务器上，MBAMserversetup.exe启动 Microsoft BitLocker 管理和监视安装向导。

2. 在"欢迎"页上，选择"下一**步"。**

3. 阅读并接受 Microsoft 软件许可协议，然后选择"下一**** 步"继续安装。

4. 确定在检查更新时是否使用 Microsoft Update，然后选择"下一步 **"。**

5. 决定是否参加客户体验改善计划，然后选择"下一**步"。**

6. 若要开始安装，请选择"安装 **"。**

7. 若要在 MBAM 服务器软件完成安装后配置服务器功能，请选中向导关闭后运行 **MBAM 服务器** 配置复选框。 或者，稍后可以使用服务器安装在"开始"菜单上创建的 **MBAM 服务器** 配置快捷方式 **来配置** MBAM。

8. 选择"**完成"。**

有关详细信息，请参阅安装 [MBAM 2.5 服务器软件](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

### <a name="step-7-configure-mbam-25-database-and-reports-role"></a>步骤 7：配置 MBAM 2.5 数据库和报告角色

在此步骤中，我们将使用 MBAM 向导配置 MBAM 2.5 数据库和报告组件：

1. 使用向导配置合规性和审核数据库和恢复数据库：
   
   1. 在要配置数据库的服务器上，启动 **MBAM 服务器配置向导**。 可以在"开始"**菜单上选择 MBAM**服务器配置以打开向导。 ****

   2. 选择 **"添加新功能"，** 选择"**合规性和审核数据库****"，"恢复数据库和报告**"，然后选择"下一**步"。** 向导检查是否满足数据库的所有先决条件。

   3. 如果先决条件检查成功，请选择" **下一步"** 继续。 否则，请解决所有缺少的先决条件，然后再次选择 **"检查先决条件"。**
   
   4. 使用下列说明，在向导中输入字段值：

2. 合规性和审核数据库

   |字段   |描述|
   |-------|-------|
   |SQL Server名称 |要配置合规性和审核数据库的服务器的名称。 <br /> 您必须在合规性和审核数据库计算机上添加例外，才能在端口上启用SQL Server通信。 默认端口号为 1433。|
   |SQL Server数据库实例    |将存储合规性和审核数据的数据库实例的名称。 如果使用的是默认实例，则必须将此字段留空。 还必须指定数据库信息将位于的位置。|
   |数据库名称   |将存储合规性数据的数据库的名称。 您必须记下您在此处指定的数据库的名称，因为您必须在稍后的步骤中提供此信息。|
   |域用户或组的读/写权限  |指定在步骤 2 中配置的 MBAMAppPool 用户的名称。|
   |只读访问域用户或组   |指定步骤 2 中配置的 MBAMROUser 用户的名称。|

3. 恢复数据库。

   |字段   |描述|
   |-----|-----|
   |SQL Server名称 |要配置恢复数据库的服务器的名称。 必须在恢复数据库计算机上添加例外，才能在端口上启用SQL Server通信。 默认端口号为 1433。|
   |SQL Server数据库实例    |将存储恢复数据的数据库实例的名称。 如果使用的是默认实例，则必须将此字段留空。 还必须指定数据库信息将位于的位置。|
   |数据库名称   |将存储恢复数据的数据库的名称。|
   |域用户或组的读/写权限  |具有此数据库的读/写权限以允许 Web 应用程序访问此数据库中的数据和报表的域用户或组。 <br />如果在此字段中输入用户，则它必须与"配置 Web 应用程序"页上的 Web 服务应用程序池 **域帐户** 字段中 **的值** 相同。 <br />如果在此字段中输入组，则"配置 Web 应用程序 **"页上"Web**服务"应用程序池域帐户"**** 字段中的值必须是在此字段中输入的组的成员。|
   
   完成条目后，选择"下一**步"。** 向导检查是否满足数据库的所有先决条件。
   
   如果先决条件检查成功，请选择" **下一步"** 继续。 否则，请解决所有缺少的先决条件，然后再次选择"下 **一步** "。

4. 报告。

   |字段   |描述|
   |----|----|
   |SQL Server Reporting Services实例  |将SQL Server Reporting Services报告的实例。 如果使用的是默认实例，则必须将此字段留空。|
   |报告角色域组 |如步骤 2 所述指定 MBAMRUGrp 的名称。|
   |SQL Server名称 |配置合规性和审核数据库的服务器的名称。|
   |SQL Server数据库实例    |配置合规性和审核数据的数据库实例的名称。 如果使用的是默认实例，则必须将此字段留空。 <br />必须在"报告"计算机上添加例外，才能在报告服务器的端口上启用传入流量。  (默认端口为 80.) |
   |数据库名称|  合规性和审核数据库的名称。 默认情况下，数据库名称为 MBAM 合规性状态。|
   |合规性和审核数据库域帐户    |指定步骤 2 中配置的 MBAMROUser 用户的名称。|
   
   完成条目后，选择"下一**步"。** 向导检查是否满足报告功能的所有先决条件。 选择“下一步”以继续。 在 **"摘要"** 页上，查看将添加的功能。
   
   有关详细信息，请参阅以下文章：如何配置 [MBAM 2.5 数据库](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

### <a name="step-8-configure-the-mbam-25-web-applications-role"></a>步骤 8：配置 MBAM 2.5 Web 应用程序角色

1. 在要配置 Web 应用程序的服务器上，启动 MBAM 服务器配置向导。 可以在"开始"**菜单上选择 MBAM**服务器配置以打开向导。 ****

2. 选择 **"添加新功能"，** 选择 **"管理和监控网站**和**自助式门户**"，然后选择"下一**步"。** 向导检查是否满足数据库的所有先决条件。

3. 如果先决条件检查成功，请选择" **下一步"** 继续。 否则，请解决所有缺少的先决条件，然后再次选择 **"检查先决条件"。**

4. 使用以下说明在向导中输入字段值。

   |字段   |描述|
   |-----|-----|
   |安全证书    |选择步骤 3 中以前创建的证书，以选择性地加密 Web 服务与配置管理和监控网站的服务器之间的通信。 如果选择"不使用证书"，则 Web 通信可能不安全。|
   |主机名   |要配置管理和监控网站的主计算机的名称。 <br />它不一定就是计算机主机名，它可以是任何内容。 但是，如果主机名不同于计算机的 netbios 名称，您必须创建 A 记录并确保 SPN 使用自定义主机名，而不是 netbios 名称。 这一点在负载平衡方案中很常见。|
   |安装路径   |要安装管理和监控网站的路径。|
   |端口    |用于网站通信的端口号。 <br /> 必须设置防火墙例外才能通过指定端口启用通信。|
   |Web 服务应用程序池域帐户和密码    |指定 MBAMAppPool 用户的用户帐户和密码，如步骤 2 中配置。 <br /> 为了提高安全性，将凭据中指定的帐户设置为具有有限的用户权限。 此外，将帐户密码设置为永不过期。|

5. 验证内置帐户IIS_IUSRS或 应用程序池 帐户是否添加到"身份验证后模拟客户端"和"以批处理作业**** 本地安全设置登录"。 ****

   若要检查帐户是否已添加到本地安全设置，请打开本地安全策略编辑器，展开****"本地策略"节点，选择****"用户权限分配"节点，然后双击"身份验证后模拟客户端"，在右侧窗格中选择"作为**** 批处理作业策略登录"。 **** ****

6. 使用以下字段说明在向导中为合规性和审核数据库配置连接信息。
   |字段   |描述|
   |------|------|
   |SQL Server名称 |配置合规性和审核数据库的服务器的名称。|
   |SQL Server数据库实例    |数据库实例的名称SQL Server (例如，) 配置合规性和审核 \<Server Name\> 数据库的名称。 如果使用的是默认实例，则保留此为空白。|
   |数据库名称   |合规性和审核数据库的名称。 默认情况下，为"MBAM 合规性状态"。|

7. 使用以下字段说明在向导中为恢复数据库配置连接信息。
   |字段   |描述|
   |----|----|
   |SQL Server名称 |配置恢复数据库的服务器的名称。|
   |SQL Server数据库实例    |数据库实例的名称SQL Server (例如，) 配置了 \<Server Name\> 恢复数据库的实例的名称。 如果使用的是默认实例，则保留此为空白。|
   |数据库名称   |恢复数据库的名称。 默认情况下，它是"MBAM 恢复和硬件"。|

8. 使用以下说明在向导中输入字段值以配置管理和监控网站。
   |字段   |描述|
   |----|----|
   |高级支持人员角色域组 |指定步骤 2 中配置的 MBAMAdvHelpDsk 组的名称。|
   |支持人员角色域组  |指定在步骤 2 中配置的 MBAMHelpDsk 组的名称。|
   |使用System Center Configuration Manager集成 |选中以清除此复选框。     |
   |报告角色域组 |指定在步骤 2 中配置的 MBAMRUGrp 组的名称。    |
   |SQL Server Reporting ServicesURL   |为配置 MBAM 报表的 SSRS 服务器指定 Web 服务 URL。 可以通过登录到数据库服务器上 Reporting Services Configuration Manager 来查找此信息。 <br /> 完全限定域名的示例： https://MyReportServer.Contoso.com/ReportServer <br />自定义主机名的示例： https://MyReportServer/ReportServer|
   |虚拟目录   |管理和监控网站的虚拟目录。 此名称对应于服务器上网站的物理目录，并附加到网站的主机名。 例如： <br />http (s) ：// ： *\<host name\>* *\<port\>* /HelpDesk/ <br />如果不指定虚拟目录，则使用值 HelpDesk。     |

9. 使用以下说明在向导中输入字段值以配置Self-Service门户。

   |字段   |描述|
   |----|----|
   |虚拟目录   |Web 应用程序的虚拟目录。 此名称对应于服务器上网站的物理目录，并附加到网站的主机名。 例如：<br />http (s) ：// *\<host name\>* ： *\<port\>* /SelfService/<br /> 如果不指定虚拟目录，则使用值"SelfService"。|

10. 完成条目后，选择"下一**步"。** 向导检查是否满足 Web 应用程序的所有先决条件。

11. 选择 **"下一** 步"继续。

12. 在 **"摘要"** 页上，查看将添加的功能。

13. 选择 **"** 添加"将 Web 应用程序添加到服务器，然后选择"关闭 **"。**

## <a name="customizing-and-validating-steps-after-installing-mbam-25-server-software"></a>在安装 MBAM 2.5 服务器软件后自定义和验证步骤

### <a name="step-9-customizing-the-self-server-portal-for-your-organization"></a>步骤 9：为组织自定义自服务器门户

若要通过Self-Service通知文本、公司名称、指向更多信息的指针等来自定义 Self-Service 门户，请参阅自定义组织的 Self-Service [门户](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization)。
 
### <a name="step-10-configure-the-self-server-portal-if-client-computers-cannot-access-the-cdn"></a>步骤 10：配置自服务器门户（如果客户端计算机无法访问CDN 

确定客户端计算机是否有权访问 Microsoft AJAX 内容分发网络 (CDN) 。 The CDN gives the Self-Service Portal the access it requires to certain JavaScript files. 如果未在客户端计算机无法访问 Self-Service 时配置 CDN 门户，则只显示公司名称和用户登录时使用的帐户。 不会显示错误消息。

执行下列操作之一：

* 如果客户端计算机有权访问 CDN，则不执行任何操作。 完成Self-Service门户配置。

* 如果客户端计算机无法访问 CDN，请按照当客户端计算机无法访问 Microsoft 内容分发网络 时如何配置[Self-Service 门户中的步骤](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network)操作。

### <a name="step-11-validate-the-mbam-25-server-feature-configuration"></a>步骤 11：验证 MBAM 2.5 服务器功能配置 

若要验证 MBAM 服务器部署是否使用独立拓扑，请按照以下步骤操作。

1. 在部署了 MBAM 功能的每台服务器上，选择 **"控制面板**  >  **计划**  >  **程序和功能"。** 验证 **Microsoft BitLocker 管理和监控** 是否显示在 **"程序和功能"列表中** 。
   > [!Note]
   > 若要执行验证，必须使用在每个服务器上具有本地计算机管理凭据的域帐户。

2. 在配置了恢复数据库的服务器上，SQL Server Management Studio并验证**是否配置了 MBAM**恢复和硬件数据库。

3. 在配置了合规性和审核数据库的服务器 om 上，SQL Server Management Studio验证是否配置了 MBAM 合规性状态数据库。

4. 在配置了"报告"功能的服务器上，使用管理凭据打开 Web 浏览器，然后浏览到 SQL Server Reporting Services 主页。
   
   网站实例的默认主页位置SQL Server Reporting Services如下：http (s) ：// *\<MBAM Reports Server Name\>* ： *\<port\>* /Reports.aspx
   
   若要查找实际 URL，请使用 Reporting Services Configuration Manager 工具，并选择在安装过程中指定的实例。
   
5. 验证名为"Microsoft BitLocker 管理和监控"的"报告"文件夹是否包含名为"一些"的数据源。 此数据源包含具有表示语言区域设置的名称的文件夹 (例如，en-us) 。 报告在语言文件夹中。

   > [!Note]
   > 如果SQL Server Reporting Services (SSRS) 配置为命名实例，则 URL 应类似于以下内容：http (s) ：// \<MBAM Reports Server Name\> ： \<port\> /Reports_\<SSRS Instance Name\>
   >
   > 如果未将 SSRS 配置为使用安全套接字层 (SSL) ，则当您安装 MBAM 服务器时，报告 URL 将设置为"HTTP"而不是"HTTPS"。 如果您随后转到"管理和监控网站" (也称为支持人员) 并选择报告，您将收到以下消息："只显示安全内容"。 若要显示报告，请选择"**显示所有内容"。**

6. 在配置了管理和监控网站功能的服务器上，运行服务器管理器，浏览到"角色"，然后选择******"Web 服务器** (IIS) Internet Information Services ( >  **IIS) **管理器"。

7. 在 **"连接**"中，浏览 \<computer name\> 到 ，然后选择"**站点**  >  **""Microsoft BitLocker 管理和监视"。** 验证是否列出了以下内容：

   * MBAMAdministrationService
   * MBAMComplianceStatusService
   * MBAMRecoveryAndHardwareService

8. 在配置了管理和监控网站以及 Self-Service 门户的服务器上，使用管理凭据打开 Web 浏览器。

9. 浏览到以下网站以验证它们是否加载成功：
   * https () ：// \<MBAM Administration Server Name\> ： \<port\> /HelpDesk/ (确认每个链接用于导航和报告) 
   * http (s) ：// \<MBAM Administration Server Name\> ： \<port\> /SelfService/

   > [!Note]
   > 假定在默认端口上配置了服务器功能，而不进行网络加密。 如果在不同的端口或虚拟目录上配置了服务器功能，请更改 URL 以包括相应的端口。 例如：http (s) ：// \<host name\> ： \<port\> /HelpDesk/ http (s) ：// ： / 如果服务器功能配置为使用网络加密，http:// \<host name\> 更改为 \<port\> / \<virtualdirectory\> https://。
   
10. 浏览到以下 Web 服务以验证它们是否加载成功。 将打开一个页面，指示服务正在运行。 但是，该页面不会显示任何元数据。

    * http (s) ：// ： \<MBAM Administration Server Name> \<port> /MBAMAdministrationService/AdministrationService.svc
    * http (s) ：// ： \<MBAM Administration Server Name> \<port> /MBAMUserSupportService/UserSupportService.svc
    * http (s) ：// ： \<MBAM Administration Server Name> \<port> /MBAMComplianceStatusService/StatusReportingService.svc
    * http (s) ：// ： \<MBAM Administration Server Name> \<port> /MBAMRecoveryAndHardwareService/CoreService.svc

### <a name="step-12-configure-the-mbam-group-policy-templates"></a>步骤 12：配置 MBAM 组策略模板

若要部署 MBAM，必须设置用于定义 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置。 若要完成此任务，必须将 MBAM 组策略模板复制到可以运行组策略管理控制台 (GPMC) 或高级组策略管理 (AGPM) 的服务器或工作站，然后编辑设置。

> [!Important]
> 请勿更改 **BitLocker** 驱动器加密节点中的组策略设置，否则 MBAM 将无法正常工作。 当你在 **MDOP MBAM (BitLocker Management) ** 节点中配置组策略设置时，MBAM 会自动配置 **BitLocker 驱动器加密** 设置。
 
#### <a name="copying-the-mbam-25-group-policy-templates"></a>复制 MBAM 2.5 组策略模板

在安装 MBAM 客户端之前，你必须将特定于 MBAM 的组策略对象 (GPO) 管理工作站。 这些 GPO 定义 BitLocker 的 MBAM 实现设置。 可以将组策略模板复制到支持基于 Windows 的服务器或客户端计算机且可以运行组策略管理控制台 (GPMC) 或高级组策略管理 (AGPM) 的任何服务器或工作站。

有关详细信息，请参阅复制 [MBAM 2.5 组策略模板](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates)。
 
#### <a name="editing-mbam-25-gpo-settings"></a>编辑 MBAM 2.5 GPO 设置

创建必要的 GPO 后，必须将 MBAM 组策略设置部署到组织的客户端计算机。 若要查看和创建 GPO，必须安装组策略管理控制台 (GPMC) 或高级组策略 (AGPM) 。

有关详细信息，请参阅编辑[MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings)组策略设置和规划[MBAM 2.5 组策略要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)。
 
### <a name="step-13-deploying-the-mbam-25-client"></a>步骤 13：部署 MBAM 2.5 客户端

根据你部署 Microsoft BitLocker 管理和监控客户端软件时，你可以先在组织中的计算机上启用 BitLocker，然后再接收计算机，也可以先配置组策略，然后使用企业软件部署系统部署 MBAM 客户端软件。
 
#### <a name="deploy-the-mbam-client-to-desktop-or-portable-computers"></a>将 MBAM 客户端部署到台式计算机或便携计算机

配置组策略设置后，可以使用 Microsoft System Center 2012 Configuration Manager 或 Active Directory 域服务 (AD DS) 等企业软件部署系统产品将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。 可以使用 32 位或 64 位 MbamClientSetup.exe 文件，或使用 32 位或 64 位 MBAMClient.msi文件。 这些与 MBAM 客户端软件一起提供。

有关详细信息，请参阅如何将 [MBAM 客户端部署到台式机或笔记本电脑](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25)。
 
#### <a name="deploy-the-mbam-client-as-part-of-a-windows-deployment"></a>将 MBAM 客户端部署为 Windows部署的一部分

在集中接收和配置计算机的组织中，可以在将任何用户数据写入到每台计算机上安装 MBAM 客户端来管理 BitLocker 驱动器加密。 此过程的好处是每台计算机都符合 BitLocker。 此方法不依赖于用户操作，因为管理员已加密计算机。 此方案的一个关键假设是，组织的策略是在将计算机Windows安装企业映像。 如果组策略设置配置为需要 PIN，则系统会提示用户接收策略后设置 PIN。

有关详细信息，请参阅如何将 MBAM 客户端部署为 Windows[部署的一部分](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25)。
 
#### <a name="how-to-deploy-the-mbam-client-by-using-a-command-line"></a>如何使用命令行部署 MBAM 客户端

有关详细信息，请参阅 [如何使用命令行部署 MBAM 客户端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line)。

#### <a name="post-deployment-of-clients"></a>客户端部署后

现在，你已完成部署活动，你应该查看以下日志，并确定客户端是否成功报告给 MBAM 数据库。

## <a name="faq"></a>常见问题

### <a name="how-to-create-a-load-balanced-iis-servers"></a>如何创建负载平衡 IIS 服务器

* SPN 只能注册到友好名称 (例如：bitlocker.corp.net) ，并且不能注册到各个 IIS 服务器。

* 如果使用证书，则证书必须同时在负载平衡组中所有 IIS 服务器的"主题备用名称"**** 字段中输入 FQDN 和 NetBIOS 名称，并且必须同时作为"友好名称" (例如：bitlocker.corp.net) 。 否则，当您浏览负载平衡的地址时，该证书将被报告为不受信任的浏览器。

有关详细信息，请参阅 [IIS Network Load Balancing](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing) and [Registering SNS for the 应用程序池 account](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account)。

### <a name="how-to-configure-a-certificate"></a>如何配置证书

* 您必须具有两个证书。 一个证书用于SQL，另一个证书用于 IIS。 它们必须在启动 MBAM 安装之前安装。

* 建议使用安装程序将证书添加到 IIS 配置，而不是手动编辑web.config文件。

* 如果证书上的"颁发给"字段与服务器名称不匹配，MBAM 配置程序将不会接受该证书。 在这种情况下，请从 IIS 控制台临时创建自签名证书，并使用它在 Configurator 中。 这将确定为 SSL 和 HTTPS 安装了 Web 应用程序。 此后，你可以将证书从 MBAM 网站的 IIS 绑定更改为一个证书。

### <a name="the-sql-permissions-requirement-for-installation"></a>安装SQL权限要求

为 MBAM 应用程序池创建帐户，并仅授予 SecurityAdmin、Public 和 DBCreator 权限。

有关详细信息 [，请参阅 MBAM 数据库](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/) 配置 – 最低权限。

> [!Note]
> * 在某些情况下，初始安装和升级操作需要更多权限。
> * 使用具有临时 SA 的帐户进行安装。
> * 请勿在没有足够的权限对 SQL Server 进行更改的用户帐户 (Run As) 上下文中启动 Configurator，因为这将导致安装错误。
> * 必须使用对 SQL Server 具有权限的帐户登录。 仅SQL Server远程运行 MBAM 配置器创建或更新数据库。 对于 SSRS 服务器，必须安装 MBAM 并在本地运行 Configurator 以安装或更新 MBAM SSRS 报告。

### <a name="the-permission-required-for-spn-registration"></a>SPN 注册所需的权限

用于 IIS 门户安装的帐户必须具有 Write ServicePrincipalName 和 Write Validated SPN 权限。 如果没有这些权限，安装将返回一条警告消息，指出它无法注册 SPN。

> [!Note]
> 您将收到此警告消息两次。 这并不意味着 SPN 必须注册两个对象。

有关详细信息，请参阅 [MBAM 安装程序失败，显示"注册 SPN 延迟"错误消息](https://support.microsoft.com/help/2754138/)。

### <a name="did-i-have-to-update-the-admx-templates-to-the-latest-version"></a>我是否必须将 ADMX 模板更新到最新版本？

将 ADMX 模板更新到最新版本后，你将在 GPO 的 MBAM 根节点中看到多个操作系统选项。 例如，Windows 7、Windows 8.1 和 Windows 10 版本 1511 及更高版本。

若要详细了解如何更新 ADMX 模板，请参阅以下文章：
* [如何下载和部署 MDOP 组策略 (.admx) 模板](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)
* [规划 MBAM 2.5 组策略要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)
* [Microsoft 桌面优化包组策略管理模板](https://www.microsoft.com/en-us/download/details.aspx?id=55531)
