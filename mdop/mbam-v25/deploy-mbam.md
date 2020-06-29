---
title: 在独立配置中部署 MBAM 2.5
description: 介绍如何以独立的配置部署 MBAM 2.5。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 905eb7a40483a7a7b499d6dced8472331c87b838
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803967"
---
# 在独立配置中部署 MBAM 2。5

本文提供了在独立配置中安装 Microsoft BitLocker 管理和监视（MBAM）2.5 的分步说明。 在本指南中，我们将使用两个服务器的配置。 这两个服务器之一将是运行 Microsoft SQL Server 2012 的数据库服务器。 此服务器将托管 MBAM 数据库和报告。 其他服务器将是 Windows Server 2012 web 服务器托管的 "管理和监视服务器" 和 "自助服务门户"。

## 安装 MBAM 2.5 server 软件之前的准备步骤

### 步骤1：服务器的安装和配置

在开始配置 MBAM 2.5 之前，我们必须确保两台服务器都按 MBAM 的系统要求进行配置。 请参阅[MBAM 最低系统要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)，并选择满足这些要求的配置。 

#### 步骤1.1：部署数据库和报告服务器的先决条件

1. 安装和配置运行 Windows Server 2008 R2 （或更高版本）操作系统的服务器。

2. 安装 Windows PowerShell 3.0。

3. 安装 Microsoft SQL Server 2008 R2 或包含最新服务包的更高版本。 如果你要为 MBAM 安装新的 SQL Server 实例，请确保你安装的 SQL Server 包含 SQL_Latin1_General_CP1_CI_AS 的排序规则。 必须安装以下 SQL Server 功能：

    * 数据库引擎
    * Reporting Services
    * 客户端工具连接
    * 管理工具-完成

    > [!Note]
    > 或者，也可以[在 SQL Server 中安装透明数据加密（TDE）功能](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)。

    SQL Server Reporting Services 必须在 "本机" 模式下安装和配置，而不是在未配置或 "SharePoint" 模式下进行配置。

    ![所需的 SQL Server 功能](images/deploying-MBAM-1.png)

4. 如果你计划对管理和监视网站使用 SSL，请确保先将 SQL Server Reporting Services （SSRS）配置为使用安全套接字层（SSL）协议，然后再配置管理和监视网站。 否则，"报表" 功能将使用未加密（HTTP）数据传输，而不是加密（HTTPS）。

    你可以关注在本机模式报表服务器上[配置 Ssl 连接](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017)以在报表服务器上配置 ssl。
    
    > [!Note]
    > 你可以按照 sql server 各自版本的 SQL Server 安装指南安装 SQL Server。 这些链接如下所示：
        > * [SQL Server 2014](https://docs.microsoft.com/sql/sql-server/install/planning-a-sql-server-installation?view=sql-server-2014)
        > * [SQL Server 2012](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))
        > * [SQL Server 2008 R2](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))

5. 在 SQL Server 的安装后，请确保在 SQL Server 中预配用户帐户，并向将在数据库服务器上配置 MBAM 数据库和报告角色的用户分配以下权限。

    SQL Server 实例的角色：
        
    * dbcreator
    * processadmin

    SQL Server Reporting Services 实例的权限：
    
    * 创建文件夹
    * 发布报表

您的数据库服务器已准备好配置 MBAM 2.5 角色。 让我们移到下一台服务器。

#### 步骤1.2：部署管理和监视服务器的先决条件

选择满足[MBAM 系统要求文档](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)中所述硬件配置的服务器。 它必须运行 Windows Server 2008 R2 或更高版本的操作系统以及最新的 service pack 和更新。 在服务器准备就绪后，安装以下角色和功能：

##### 角色

* Web 服务器（IIS）管理工具（选择 "IIS 管理脚本和工具"。）

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

##### 功能

* .NET Framework 4.5 功能
  
  * Microsoft .NET Framework 4。5
  
    对于 Windows server 2012 或 Windows Server 2012 R2，已为这些版本的 Windows Server 安装了 .NET Framework 4.5。 但是，您必须启用它。
  
    对于 Windows server 2008 R2，Windows Server 2008 R2 中不包含 .NET Framework 4.5。 因此，你必须下载 .NET Framework 4.5 并单独安装它。
  
  * WCF 激活<br />
    HTTP 激活<br />
    非 HTTP 激活
  
  * TCP 激活
  
  * Windows 进程激活服务：<br />
    流程模型<br />
    .NET Framework 环境<br />
    配置 Api

若要使用自助服务门户，还应[下载并安装 ASP.NET MVC 4.0](https://go.microsoft.com/fwlink/?linkid=392271)。

下一步是在 Active Directory 中创建所需的 MBAM 用户和组。

### 步骤2：在 Active Directory 域服务中创建用户和组
 
作为先决条件的一部分，你必须定义在 MBAM 中使用的某些角色和帐户，以便为特定服务器和功能提供安全和访问权限，例如在 SQL Server 实例上运行的数据库和在管理和监视服务器上运行的 web 应用程序。

在 Active Directory 中创建以下组和用户。 （您可以为组和用户使用任何名称。）用户不必拥有更多的用户权限。 域用户帐户已足够。 在 MBAM 2.5 的配置期间，你必须指定这些组的名称：

* **MBAMAppPool**  

  **类型**：域用户

  **说明**：对合规性和审核数据库和恢复数据库具有读取或写入权限的域用户，使 web 应用程序能够访问这些数据库中的数据和报告。 它还将由 web 应用程序的应用程序池使用。

  **帐户角色（在 MBAM 配置期间）**：

  1. Web 服务应用程序池域帐户

  2. 合规性和审核数据库和恢复数据库对报表的读/写用户

* **MBAMROUser**

  **类型**：域用户

  **说明**：将对合规性和审核数据库具有只读访问权限的域用户，以使报表能够访问此数据库中的合规性和审核数据。 它还将是本地 SQL Server Reporting Services 实例用于访问合规性和审核数据库的域用户帐户。

  **帐户角色（在 MBAM 配置期间）**：

  1. 针对报表的合规性和审核数据库只读用户

  2. 合规性和审核数据库域用户帐户

* **MBAMAdvHelpDsk**

  **类型**：域组

  **说明**： MBAM 高级帮助台用户访问组：其成员有权访问管理和监视网站的所有区域的域用户组。 具有此角色的用户在帮助用户恢复其驱动器时，只需输入恢复密钥，而不是用户的域和用户名。 如果用户是 MBAM 支持人员组和 MBAM 高级帮助台用户组的成员，则 MBAM 高级帮助台用户组权限将替代 MBAM 帮助台组权限。

  **帐户角色（在 MBAM 配置期间）**： MBAM 高级帮助台用户

* **MBAMHelpDsk**

  **类型**：域组

  **说明**： MBAM 帮助台用户访问组：其成员有权访问 MBAM 管理和监视网站的 "管理 TPM" 和 "驱动器恢复" 区域的域用户组。 具有此角色的人员在使用任一选项时都必须填写所有字段。 这包括用户的域和帐户名称。

  **帐户角色（在 MBAM 配置期间）**： MBAM 帮助台用户

* **MBAMRUGrp**

  **类型**：域组

  **说明**：其成员对管理和监控网站的 "报告" 区域中的报表具有只读访问权限的域用户组。

  **帐户角色（在 MBAM 配置期间）**：

  1. 报告只读域访问组

  2. MBAM 报表用户访问组

### 步骤3（可选）：在管理和监视服务器上配置并安装 SSL 证书

尽管它是可选的，但我们强烈建议你使用证书来帮助保护 MBAM 客户端和管理和监视网站以及自助服务门户网站之间的通信。 我们不建议使用自签名证书，因为这是显而易见的安全理由。 我们建议你使用来自受信任的证书颁发机构的 Web 服务器类型证书。 若要执行此操作，您可以参考[知识库 2754259](https://support.microsoft.com/help/2754259)中的 "使用证书颁发机构批准的证书" 部分。

颁发证书后，应将证书添加到管理和监视服务器的个人存储区。 若要添加证书，请打开本地计算机上的 "证书" 存储。 为此，请执行下列步骤：

1. 右键选择 "开始"，然后选择 "运行"。

   ![选择 ](images/deploying-MBAM-2.png)

2. 键入 "MMC.EXE" （不带引号），然后选择 **"确定**"。

   !["运行" 框](images/deploying-MBAM-3.png) 

3. 在打开的新 MMC 中选择 "**文件**"，然后选择 "**添加/删除管理单元**"。
   
   ![选择](images/deploying-MBAM-4.png)

4. 突出显示 "**证书**" 管理单元，然后选择 "**添加**"。

   !["添加或删除管理单元" 窗口](images/deploying-MBAM-5.png)

5. 选择 "**计算机帐户**" 选项，然后选择 "**下一步**"。
   
   !["证书" 管理单元窗口](images/deploying-MBAM-6.png)

6. 在下一个屏幕上选择 "**本地计算机**"，然后选择 "**完成**"。
   
   ![选择计算机窗口](images/deploying-MBAM-7.png)

7. 您现在已添加 "证书" 管理单元。 这将使你能够使用计算机的证书存储中的任何证书。

   !["添加或删除管理单元" 窗口](images/deploying-MBAM-8.png)

8. 将 web 服务器证书导入到计算机的证书存储中。

   既然您有权访问 "证书" 管理单元，则可以将 web 服务器证书导入到计算机的证书存储中。 若要执行此操作，请执行后续步骤。

9. 打开 "证书（本地计算机）" 管理单元，然后通过浏览找到 "**个人**"，然后找到 "**证书**"。
   
   !["证书（本地计算机）" 管理单元窗口](images/deploying-MBAM-9.png)

   > [!Note]
   > 可能未列出 "证书" 管理单元。 如果不是，则没有安装证书。

10. 右键选择 "**证书**"，选择 "**所有任务**"，然后选择 "**导入**"。

    !["证书（本地计算机）" 管理单元窗口](images/deploying-MBAM-10.png)

11. 向导启动后，选择 "**下一步**"。 浏览到你创建的包含服务器证书和私钥的文件，然后选择 "**下一步**"。

    !["证书导入向导" 窗口](images/deploying-MBAM-11.png)

12. 如果在创建文件时为其指定了密码，请输入密码。

   ![输入密码窗口](images/deploying-MBAM-12.png)

   > [!Note]
   > 如果希望能够从该计算机再次导出密钥对，请确保选中 "将**密钥标记为可导出**" 选项。 作为添加的安全措施，您可能希望将此选项保留为 "已清除"，以确保没有人可以对您的私钥进行备份。
 
13. 选择 "**下一步**"，然后选择要将证书保存到的**证书存储**。

    !["证书导入向导" 窗口](images/deploying-MBAM-13.png)

    > [!Note]
    > 您应选择 "**个人**版"，因为它是 web 服务器证书。 如果你已在证书层次结构中包含证书，则该证书也将添加到此应用商店。
 
14. 选择 "**下一步**"，然后选择 "**完成**"。

    !["证书导入向导" 窗口](images/deploying-MBAM-14.png)

现在，你将在 "个人证书" 列表中看到 web 服务器的服务器证书。 它将由服务器的公用名称表示。 （您可以在证书的主题部分找到它。）

有关进一步参考：

[MBAM 2.5 安全注意事项](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

[规划如何保护 MBAM 网站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

下一步是为应用程序池帐户注册一个服务主体名称。

### 步骤4：为 MBAM Web 服务器配置 SSL 证书

如果在客户端和服务器之间使用 SSL 通信，则应确保证书具有增强的密钥用法 Oid （1.3.6.1.5.5.7.3.1）和（1.3.6.1.5.5.7.3.2）。 也就是说，应确保添加服务器身份验证和客户端身份验证。

如果你在尝试浏览服务 Url 时收到证书错误，则表示你使用的是颁发给其他名称的证书，或者你正在使用不正确的 URL 进行浏览。

尽管浏览器可能会提示你提供证书错误消息，但你继续操作，MBAM web 服务将不会忽略证书错误，并且将阻止连接。 在 MBAM 客户端的 MBAM 管理事件日志中，你将注意到与证书相关的错误。 如果使用别名连接到管理和监视服务器，则应将证书颁发给别名。 也就是说，证书的使用者名称应为别名，本地服务器的 DNS 名称应添加到证书的 "**主题备用名称**" 字段。

示例：

如果虚拟名称为 "bitlocker.contoso.com"，而 MBAM 管理和监视服务器名称为 "adminserver.contoso.com"，则应将证书颁发给 bitlocker.contoso.com （subject 名称），并且应将 adminserver.contoso.com 添加到证书的 "**主题备用名称**" 字段。

同样，如果你安装了多个管理和监视服务器以通过负载平衡器平衡负载，则应将 SSL 证书颁发给虚拟名称。 也就是说，证书的 "主题名称" 字段应具有虚拟名称，并且所有本地服务器的名称都应添加到证书的 "**主题备用名称**" 字段中。

示例：

如果虚拟名称为 "bitlocker.contoso.com"，并且服务器为 "adminserver1.contoso.com" 和 "adminiserver2.contoso.com"，则应将证书颁发给 bitlocker.contoso.com （subject 名称）和 adminserver1.contoso.com，并且应将 adminiserver2.contoso.com 添加到证书的 "**主题备用名称**" 字段。

以下知识库文章中介绍了使用 MBAM 配置 SSL 通信的步骤： [KB 2754259](https://support.microsoft.com/help/2754259)。

### 步骤5：注册应用程序池帐户的 SPN 并配置受限委派

> [!Note]
> 限制委派仅适用于2.5，对于 2.5 Service Pack 1 和更高版本不是必需的。

若要使 MBAM 服务器能够对来自管理和监视网站和自助服务门户的通信进行身份验证，你必须在用于 web 应用程序池的域帐户下注册主机名的服务主体名称（SPN）。 以下文章包含注册 Spn 的分步说明：[规划如何保护 MBAM 网站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

配置 SPN 后，应在 SPN 上设置受约束的委派。 为此，请执行下列步骤：

1. 转到 Active Directory，并查找您在前面的步骤中为 MBAM 网站配置的应用池凭据。

2. 右键单击凭据，然后选择 "**属性**"。

3. 选择 "**委派**" 选项卡。

4. 选择 Kerberos 身份验证的选项。

5. 选择 "**浏览**"，然后再次浏览你的应用池凭据。 然后，你应该看到在应用池凭据帐户上设置的所有 Spn。 （SPN 应类似于 "http/bitlocker fqdn .com"）。 突出显示与在 MBAM 安装期间指定的主机名相同的 SPN。

6. 选择“确定”****。

现在，你可以获得先决条件。 在接下来的步骤中，你将在服务器上安装 MBAM 软件并对其进行配置。

## 安装和配置 MBAM 2.5 服务器软件

### 步骤6：安装 MBAM 2.5 server 软件 

若要在数据库服务器和管理和监视服务器上使用 Microsoft BitLocker 管理和监视设置向导安装 MBAM 服务器软件，请按照以下步骤操作。

1. 在要在其上安装 MBAM 的服务器上，运行 MBAMserversetup.exe 以启动 Microsoft BitLocker 管理和监视设置向导。

2. 在 "欢迎" 页面上，选择 "**下一步**"。

3. 阅读并接受 Microsoft 软件许可协议，然后选择 "**下一步**" 继续安装。

4. 确定在检查更新时是否使用 Microsoft Update，然后选择 "**下一步**"。

5. 确定是否参与 "客户体验改善计划"，然后选择 "**下一步**"。

6. 若要开始安装，请选择 "**安装**"。

7. 若要在 MBAM 服务器软件完成安装后配置服务器功能，请选择 "在**向导关闭后运行 MBAM 服务器配置**" 复选框。 或者，你可以稍后通过使用服务器安装在 "**开始**" 菜单上创建的**MBAM 服务器配置**快捷方式来配置 MBAM。

8. 选择 "**完成**"。

有关详细信息，请参阅[安装 MBAM 2.5 Server 软件](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

### 步骤7：配置 MBAM 2.5 数据库和报表角色

在此步骤中，我们将使用 MBAM 向导配置 MBAM 2.5 数据库和报告组件：

1. 使用向导配置合规性和审核数据库和恢复数据库：
   
   1. 在要配置数据库的服务器上，启动 " **MBAM 服务器配置向导**"。 你可以选择 "**开始**" 菜单上的 " **MBAM 服务器配置**" 以打开该向导。

   2. 选择 "**添加新功能**"，选择 "**合规性和审核数据库**"、"**恢复数据库和报告**"，然后选择 "**下一步**"。 向导检查是否满足数据库的所有必备条件。

   3. 如果先决条件检查成功，请选择 "**下一步**" 以继续。 否则，请解决任何缺少的先决条件，然后**再次选择 "检查先决条件**"。
   
   4. 使用以下说明，在向导中输入字段值：

2. 合规性和审核数据库

   |字段   |描述|
   |-------|-------|
   |SQL Server 名称 |在其上配置合规性和审核数据库的服务器的名称。 <br /> 必须在合规性和审核数据库计算机上添加异常，才能在 SQL Server 端口上启用传入入站流量。 默认端口号为1433。|
   |SQL Server 数据库实例    |将存储合规性和审核数据的数据库实例的名称。 如果您使用的是默认实例，则必须将此字段保留为空。 还必须指定数据库信息的存放位置。|
   |数据库名称   |将存储合规性数据的数据库的名称。 你必须记下在此处指定的数据库的名称，因为你需要在后续步骤中提供此信息。|
   |读/写权限域用户或组  |指定在步骤2中配置的 MBAMAppPool 用户的名称。|
   |只读访问域用户或组   |指定在步骤2中配置的 MBAMROUser 用户的名称。|

3. 恢复数据库。

   |字段   |描述|
   |-----|-----|
   |SQL Server 名称 |在其上配置恢复数据库的服务器的名称。 必须在恢复数据库计算机上添加例外，才能在 SQL Server 端口上启用传入入站流量。 默认端口号为1433。|
   |SQL Server 数据库实例    |将存储恢复数据的数据库实例的名称。 如果您使用的是默认实例，则必须将此字段保留为空。 还必须指定数据库信息的存放位置。|
   |数据库名称   |将存储恢复数据的数据库的名称。|
   |读/写权限域用户或组  |对此数据库具有读/写权限的域用户或组，以使 web 应用程序能够访问此数据库中的数据和报表。 <br />如果在此字段中输入用户，它必须与 "**配置 Web 应用程序**" 页面上的 " **web 服务应用程序池域帐户**" 字段中的值相同。 <br />如果在此字段中输入组，则 "**配置 Web 应用程序**" 页面上的 " **Web 服务应用程序池域帐户**" 字段中的值必须是您在此字段中输入的组的成员。|
   
   完成输入后，选择 "**下一步**"。 向导检查是否满足数据库的所有必备条件。
   
   如果先决条件检查成功，请选择 "**下一步**" 以继续。 否则，请解决任何缺少的先决条件，然后再次选择 "**下一步**"。

4. 报告会.

   |字段   |描述|
   |----|----|
   |SQL Server Reporting Services 实例  |将配置报告的 SQL Server Reporting Services 的实例。 如果您使用的是默认实例，则必须将此字段保留为空。|
   |报告角色域组 |按照步骤2中所述，指定 MBAMRUGrp 的名称。|
   |SQL Server 名称 |配置合规性和审核数据库的服务器的名称。|
   |SQL Server 数据库实例    |配置合规性和审核数据的数据库实例的名称。 如果您使用的是默认实例，则必须将此字段保留为空。 <br />必须在报表计算机上添加异常，才能在报表服务器的端口上启用传入流量。 （默认端口为80。）|
   |数据库名称|  合规性和审核数据库的名称。 默认情况下，数据库名称为 MBAM 合规性状态。|
   |合规性和审核数据库域帐户    |指定在步骤2中配置的 MBAMROUser 用户的名称。|
   
   完成输入后，选择 "**下一步**"。 向导将检查是否满足 "报告" 功能的所有先决条件。 选择“下一步”以继续。 在 "**摘要**" 页面上，查看将添加的功能。
   
   有关详细信息，请参阅以下文章：[如何配置 MBAM 2.5 数据库](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

### 步骤8：配置 MBAM 2.5 Web 应用程序角色

1. 在要配置 web 应用程序的服务器上，启动 "MBAM 服务器配置向导"。 你可以选择 "**开始**" 菜单上的 " **MBAM 服务器配置**" 以打开该向导。

2. 选择 "**添加新功能**"，选择 "**管理和监视网站**和**自助服务门户**"，然后选择 "**下一步**"。 向导检查是否满足数据库的所有必备条件。

3. 如果先决条件检查成功，请选择 "**下一步**" 以继续。 否则，请解决任何缺少的先决条件，然后**再次选择 "检查先决条件**"。

4. 使用以下说明在向导中输入字段值。

   |字段   |描述|
   |-----|-----|
   |安全证书    |在步骤3中选择以前创建的证书，以选择性地加密 web 服务与要在其上配置管理和监视网站的服务器之间的通信。 如果您选择 "不使用证书"，则您的 web 通信可能不安全。|
   |主机名   |在其上配置管理和监视网站的主机的名称。 <br />它不必是计算机的主机名，它可以是任何内容。 但是，如果主机名与计算机的 netbios 名称不同，则必须创建 A 记录并确保 SPN 使用自定义主机名，而不是 netbios 名称。 这在负载平衡方案中很常见。|
   |安装路径   |要在其上安装管理和监视网站的路径。|
   |端口    |用于网站通信的端口号。 <br /> 必须设置防火墙例外以通过指定的端口启用通信。|
   |Web 服务应用程序池域帐户和密码    |根据步骤2中的配置，指定 MBAMAppPool 用户的用户帐户和密码。 <br /> 为了提高安全性，请将凭据中指定的帐户设置为具有受限的用户权限。 此外，将帐户的密码设置为永不过期。|

5. 验证内置 IIS_IUSRS 帐户或应用程序池帐户是否已添加到**身份验证后模拟客户端**，以及**作为批处理作业登录**的本地安全设置。

   若要检查帐户是否已添加到本地安全设置，请打开 "**本地安全策略编辑器**"，展开 "**本地策略**" 节点，选择 "**用户权限分配**" 节点，然后双击 "在**身份验证后模拟客户端**"，并在右侧窗格中**以批处理作业策略的形式登录**。

6. 使用以下字段说明为合规性和审核数据库配置向导中的连接信息。
   |字段   |描述|
   |------|------|
   |SQL Server 名称 |配置合规性和审核数据库的服务器的名称。|
   |SQL Server 数据库实例    |SQL Server 实例的名称（例如 \<Server Name\> ），以及配置合规性和审核数据库的名称。 如果您使用的是默认实例，请将其保留为空。|
   |数据库名称   |合规性和审核数据库的名称。 默认情况下，它是 "MBAM 合规性状态"。|

7. 使用以下字段说明为恢复数据库配置向导中的连接信息。
   |字段   |描述|
   |----|----|
   |SQL Server 名称 |在其上配置恢复数据库的服务器的名称。|
   |SQL Server 数据库实例    |在其上配置恢复数据库的 SQL Server 实例的名称（例如 \<Server Name\> ）。 如果您使用的是默认实例，请将其保留为空。|
   |数据库名称   |恢复数据库的名称。 默认情况下，它是 "MBAM 恢复和硬件"。|

8. 使用以下说明在向导中输入字段值以配置管理和监视网站。
   |字段   |描述|
   |----|----|
   |高级帮助台角色域组 |指定在步骤2中配置的 MBAMAdvHelpDsk 组的名称。|
   |帮助台角色域组  |指定在步骤2中配置的 MBAMHelpDsk 组的名称。|
   |使用 System Center Configuration Manager 集成 |选中以清除此复选框。     |
   |报告角色域组 |指定在步骤2中配置的 MBAMRUGrp 组的名称。    |
   |SQL Server Reporting Services URL   |为在其上配置了 MBAM 报表的 SSRS 服务器指定 Web 服务 URL。 你可以通过登录到数据库服务器上的 Reporting Services 配置管理器查找此信息。 <br /> 完全限定域名的示例：https://MyReportServer.Contoso.com/ReportServer <br />自定义主机名示例：https://MyReportServer/ReportServer|
   |虚拟目录   |管理和监视网站的虚拟目录。 此名称对应于服务器上网站的物理目录，并附加到网站的主机名。 例如： <br />http （s）：// *\<host name\>* ： *\<port\>* /HelpDesk/ <br />如果不指定虚拟目录，将使用值帮助台。     |

9. 使用以下说明在向导中输入字段值以配置自助服务门户。

   |字段   |描述|
   |----|----|
   |虚拟目录   |Web 应用程序的虚拟目录。 此名称对应于服务器上网站的物理目录，并附加到网站的主机名。 例如：<br />http （s）：// *\<host name\>* ： *\<port\>* /SelfService/<br /> 如果不指定虚拟目录，将使用值 "SelfService"。|

10. 完成输入后，选择 "**下一步**"。 向导检查是否满足 web 应用程序的所有先决条件。

11. 选择 "**下一步**" 继续。

12. 在 "**摘要**" 页面上，查看将添加的功能。

13. 选择 "**添加**" 以将 web 应用程序添加到服务器，然后选择 "**关闭**"。

## 在安装 MBAM 2.5 server 软件后自定义和验证步骤

### 步骤9：为你的组织自定义自服务器门户

若要通过添加自定义声明文本、公司名称、指向详细信息的指针自定义自助服务门户，请参阅[自定义组织的自助服务门户](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization)。
 
### 步骤10：在客户端计算机无法访问 CDN 时配置自助服务门户 

确定客户端计算机是否有权访问 Microsoft AJAX 内容交付网络（CDN）。 CDN 为自助服务门户提供对某些 JavaScript 文件所需的访问权限。 如果在客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和登录用户所使用的帐户。 将不会显示任何错误消息。

执行下列操作之一：

* 如果你的客户端计算机有权访问 CDN，请执行任何操作。 您的自助服务门户配置已完成。

* 如果客户端计算机不具有 CDN 的访问权限，请按照在[客户端计算机无法访问 Microsoft 内容传递网络时如何配置自助服务门户](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network)中的步骤进行操作。

### 步骤11：验证 MBAM 2.5 服务器功能配置 

若要验证 MBAM 服务器部署以使用独立拓扑，请执行以下步骤。

1. 在部署了 MBAM 功能的每台服务器上，选择 **"控制面板**  >  **程序**" 程序  >  **和功能**。 验证 "**程序和功能**" 列表中是否显示 " **Microsoft BitLocker 管理和监视**"。
   > [!Note]
   > 若要执行验证，你必须使用在每台服务器上具有本地计算机管理凭据的域帐户。

2. 在配置了恢复数据库的服务器上，打开 SQL Server Management Studio，并验证是否配置了**MBAM 恢复和硬件**数据库。

3. 在配置合规性和审核数据库的服务器 om 上，打开 SQL Server Management Studio，并验证是否配置了 MBAM 合规性状态数据库。

4. 在配置了 "报表" 功能的 "服务器 onm" 上，使用 "管理凭据" 打开 web 浏览器，然后浏览到 SQL Server Reporting Services 网站的主页。
   
   SQL Server Reporting Services 网站实例的默认主页位置如下所示： http （s）：// *\<MBAM Reports Server Name\>* ： *\<port\>* /Reports.aspx
   
   若要查找实际 URL，请使用 Reporting Services 配置管理器工具，然后选择在安装过程中指定的实例。
   
5. 验证名为 Microsoft BitLocker 管理和监视的报表文件夹是否包含名为 MaltaDataSource 的数据源。 此数据源包含具有表示语言区域设置的名称的文件夹（例如，en-us）。 报表位于 "语言" 文件夹中。

   > [!Note]
   > 如果 SQL Server Reporting Services （SSRS）配置为命名实例，则 URL 应类似于以下内容： http （s）：// \<MBAM Reports Server Name\> ： \<port\> /Reports_\<SSRS Instance Name\>
   >
   > 如果未将 SSRS 配置为使用安全套接字层（SSL），则在安装 MBAM 服务器时，报表的 URL 将设置为 "HTTP"，而不是 "HTTPS"。 如果您转到 "管理和监视" 网站（也称为 "帮助台"）并选择报表，则会收到以下消息： "仅显示安全内容"。 若要显示报表，请选择 "**显示所有内容**"。

6. 在配置了 "管理和监视网站" 功能的服务器上，运行 "服务器管理器"，浏览到 "**角色**"，然后选择 " **Web 服务器（iis）**  >  **Internet 信息服务（iis）** 管理器"。

7. 在 "**连接**" 中，浏览到 "网站"， \<computer name\> 然后选择 "**网站**  >  **Microsoft BitLocker 管理和监视**"。 验证是否列出以下内容：

   * MBAMAdministrationService
   * MBAMComplianceStatusService
   * MBAMRecoveryAndHardwareService

8. 在配置了管理和监视网站和自助服务门户的服务器上，通过使用管理凭据打开 web 浏览器。

9. 浏览到以下网站，验证它们是否成功加载：
   * https （s）：// \<MBAM Administration Server Name\> ： \<port\> /HelpDesk/（确认导航和报告的每个链接）
   * http （s）：// \<MBAM Administration Server Name\> ： \<port\> /SelfService/

   > [!Note]
   > 假设您在没有网络加密的情况下在默认端口上配置了服务器功能。 如果你在其他端口或虚拟目录上配置了服务器功能，请将 Url 更改为包含相应的端口。 例如： http （s）：// \<host name\> ： \<port\> /HelpDesk/http： \<host name\> //： \<port\> / \<virtualdirectory\> /如果服务器功能配置为使用网络加密，请将 http://更改为 https://。
   
10. 浏览到以下 web 服务以验证它们是否已成功加载。 将打开一个页面，指示该服务正在运行。 但是，该页面不显示元数据。

    * http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMAdministrationService/AdministrationService.svc
    * http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMUserSupportService/UserSupportService.svc
    * http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMComplianceStatusService/StatusReportingService.svc
    * http （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMRecoveryAndHardwareService/CoreService.svc

### 步骤12：配置 MBAM 组策略模板

若要部署 MBAM，你必须设置用于定义 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置。 若要完成此任务，必须将 MBAM 组策略模板复制到可以运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的服务器或工作站，然后编辑设置。

> [!Important]
> 不要更改 " **BitLocker 驱动器加密**" 节点中的组策略设置，否则 MBAM 将无法正常工作。 在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。
 
#### 复制 MBAM 2.5 组策略模板

在安装 MBAM 客户端之前，必须将 MBAM 特定的组策略对象（Gpo）复制到管理工作站。 这些 Gpo 定义了适用于 BitLocker 的 MBAM 实现设置。 你可以将组策略模板复制到属于受支持的基于 Windows 的服务器或客户端计算机的任何服务器或工作站，并且可以运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）。

有关详细信息，请参阅[复制 MBAM 2.5 组策略模板](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates)。
 
#### 编辑 MBAM 2.5 GPO 设置

创建必要的 Gpo 后，必须将 MBAM 组策略设置部署到你的组织的客户端计算机。 若要查看和创建 Gpo，必须安装组策略管理控制台（GPMC）或高级组策略管理（AGPM）。

有关详细信息，请参阅[编辑 MBAM 2.5 组策略设置](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings)和[规划 MBAM 2.5 组策略要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)。
 
### 步骤13：部署 MBAM 2.5 客户端

根据你部署 Microsoft BitLocker 管理和监视客户端软件的时间，你可以在用户接收计算机之前或者通过配置组策略并使用企业软件部署系统部署 MBAM 客户端软件，在你的组织中的计算机上启用 BitLocker。
 
#### 将 MBAM 客户端部署到台式计算机或便携式计算机

配置组策略设置后，你可以使用企业软件部署系统产品（如 Microsoft System Center 2012 Configuration Manager 或 Active Directory 域服务（AD DS））将 MBAM 客户端安装 Windows Installer 文件部署到目标计算机。 你可以使用32位或64位 MbamClientSetup.exe 文件或32位或64位 MBAMClient.msi 文件。 这些软件与 MBAM 客户端软件一起提供。

有关详细信息，请参阅[如何将 MBAM 客户端部署到台式计算机或膝上型计算机](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25)。
 
#### 将 MBAM 客户端部署为 Windows 部署的一部分

在要集中接收和配置计算机的组织中，可以安装 MBAM 客户端以在每台计算机上管理 BitLocker 驱动器加密，然后再向其中写入任何用户数据。 此过程的好处是，每台计算机都与 BitLocker 兼容。 此方法不依赖于用户操作，因为管理员已加密计算机。 此方案的一个关键假设是组织的策略是在计算机交付给用户之前安装企业 Windows 映像。 如果将组策略设置配置为需要 PIN 码，则会在用户收到策略后提示用户设置 PIN。

有关详细信息，请参阅[如何在 Windows 部署中部署 MBAM 客户端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25)。
 
#### 如何使用命令行部署 MBAM 客户端

有关详细信息，请参阅[如何使用命令行部署 MBAM 客户端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line)。

#### 客户端部署后

现在，你已完成部署活动，你应该查看以下日志并确定客户是否已成功报告到 MBAM 数据库。

## 常见问题

### 如何创建负载平衡 IIS 服务器

* SPN 必须仅注册为友好名称（例如： bitlocker.corp.net），并且不能注册到单独的 IIS 服务器。

* 如果使用了证书，则证书必须将 FQDN 和 NetBIOS 名称输入到 "负载平衡" 组中所有 IIS 服务器的 "**主题备用名称**" 字段中，也必须具有友好名称（例如： bitlocker.corp.net）。 否则，当你浏览负载平衡地址时，该证书将报告为浏览器不受信任。

有关详细信息，请参阅[IIS 网络负载平衡](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing)和[注册应用程序池帐户的 spn](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account)。

### 如何配置证书

* 您必须拥有两个证书。 一个证书用于 SQL server，另一个证书用于 IIS。 必须先安装它们，然后才能开始 MBAM 安装。

* 我们建议你使用安装程序将证书添加到 IIS 配置，而不是手动编辑 web.config 文件。

* 如果证书上的 "颁发给" 字段与服务器名称不匹配，则 MBAM 配置器将不接受该证书。 在这种情况下，从 IIS 控制台临时创建自签名证书，然后在配置器中使用它。 这将使 nsure 为 SSL 和 HTTPS 安装 Web 应用。 之后，你可以将证书从 MBAM 网站的 IIS 绑定更改为一个证书。

### 安装的 SQL 权限要求

为 MBAM 应用程序池创建一个帐户，并仅为其授予 SecurityAdmin、Public 和 DBCreator 权限。

有关详细信息，请参阅[MBAM 数据库配置-最低权限](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/)。

> [!Note]
> * 在某些情况下，初始安装和升级操作需要更多的权限。
> * 使用具有临时 SA 的帐户进行安装。
> * 不要在没有足够权限来更改 SQL Server 的用户帐户上下文中启动配置器，因为这将导致安装错误。
> * 您必须使用在 SQL Server 上拥有权限的帐户登录。 通过远程运行 MBAM 配置器，仅可创建或更新 SQL Server 数据库。 对于 SSRS 服务器，必须在本地安装 MBAM 并运行配置器以安装或更新 MBAM SSRS 报表。

### SPN 注册所需的权限

用于 IIS portal 安装的帐户必须具有写 ServicePrincipalName 并写入验证的 SPN 权限。 如果没有这些权限，安装将返回一条警告消息，指出它无法注册 SPN。

> [!Note]
> 此时将收到此警告消息两次。 这并不意味着 SPN 必须已注册两个对象。

有关详细信息，请参阅[MBAM 安装失败，并显示 "注册 SPN 延期" 错误消息](https://support.microsoft.com/help/2754138/)。

### 是否必须将 ADMX 模板更新到最新版本？

将 ADMX 模板更新到其最新版本之后，你将在 GPO 的 MBAM 根节点中看到多个 OS 选项。 例如，Windows 7、Windows 8.1 和 Windows 10 版本1511及更高版本。

有关如何更新 ADMX 模板的详细信息，请参阅以下文章：
* [如何下载和部署 MDOP 组策略 (.admx) 模板](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)
* [规划 MBAM 2.5 组策略要求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)
* [Microsoft 桌面优化包组策略管理模板](https://www.microsoft.com/en-us/download/details.aspx?id=55531)
