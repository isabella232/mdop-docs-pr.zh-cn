---
title: 如何为 App-V 配置 Microsoft SQL Server 镜像支持
description: 如何为 App-V 配置 Microsoft SQL Server 镜像支持
author: dansimp
ms.assetid: 6d069eb5-109f-460a-836a-de49473b7035
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fb572442cd12bb32fc9406de65f05a3bf061f946
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801615"
---
# 如何为 App-V 配置 Microsoft SQL Server 镜像支持


你可以使用以下过程将 Microsoft Application Virtualization （App-v）环境配置为使用 Microsoft SQL Server 数据库镜像。 配置数据库镜像有助于解决灾难恢复和故障转移情形。 App-v 4.5 SP2 支持当前可用于 Microsoft SQL Server 2005 和 SQL Server 2008 的所有数据库镜像模式。

**注意**  
此过程专为熟悉使用 Microsoft SQL Server 设置和配置 SQL Server 数据库和数据库镜像的管理员编写，因此仅涵盖 App-v 特有的特定配置设置。



**将 app-v 环境配置为使用 Microsoft SQL Server 数据库镜像**

1.  在数据库镜像的标准业务做法之后，设置 App-v 数据库的 SQL Server 数据库镜像。 对于有关实现 Microsoft SQL Server 数据库镜像的常规信息，请使用以下链接：

    -   **MICROSOFT SQL 2005**-[设置数据库镜像](https://go.microsoft.com/fwlink/?LinkId=187478)（https://go.microsoft.com/fwlink/?LinkId=187478)

    -   **MICROSOFT SQL 2008**-[设置数据库镜像](https://go.microsoft.com/fwlink/?LinkId=187477)（https://go.microsoft.com/fwlink/?LinkId=187477)

    此外，你可以在[数据库镜像最佳做法和性能注意事项](https://go.microsoft.com/fwlink/?LinkId=190270)（.）中找到最佳做法信息 https://go.microsoft.com/fwlink/?LinkId=190270) 。

2.  设置镜像后，请验证 App-v 数据库显示状态 **（主体、同步）**，并且镜像数据库显示状态 **"（镜像、已同步/正在还原）**"。 先解决所有镜像问题，然后再继续下一步。 有关监视状态的其他信息，请参阅[监视镜像状态](https://go.microsoft.com/fwlink/?LinkId=190279)（ https://go.microsoft.com/fwlink/?LinkId=190279) 。

3.  在承载 app-v 数据库镜像的 sql server 计算机上，通过使用帐户名称** &lt; domain &gt; \\ &lt; ManagementServerHostName &gt; $ **为 app-v 管理服务器的网络服务帐户创建 SQL Server 登录。

4.  在 App-v 管理服务器上安装 Microsoft SQL Server Native Client，在运行 App-v Management Web 服务的计算机上安装（如果安装在其他计算机上）。 如果你计划让其他 App-v 管理服务器连接到镜像 SQL 数据库以实现负载平衡，则你必须在这些计算机上安装 Microsoft SQL Server Native Client。 你可以从 Microsoft 下载中心（.）中的[MICROSOFT Sql server 2008 功能包](https://go.microsoft.com/fwlink/?LinkId=187479)页面下载 Microsoft Sql Server Native Client https://go.microsoft.com/fwlink/?LinkId=187479) 。

5.  检查注册表项 **_LOCAL HKEY \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlservername** ，确保它仅包含 SQL Server 的主机名。 如果它包括实例名称（例如*serverhostname\\instancename*），则必须删除实例名称。

    **重要提示**  
    应用程序-V 管理服务器在启用数据库镜像时使用 TCP/IP 网络库与 SQL Server 进行通信，因此不能使用实例名称。 必须在注册表项中指定端口号。



6.  检查注册表项 **_LOCAL HKEY \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlserverport** ，确保它包含在 sql Server 计算机上用于 sql 的端口号。 如果你使用的是命名实例，此密钥值必须设置为命名实例使用的端口。

7.  创建注册表项 **_LOCAL HKEY \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverservername** as REG \ _SZ 然后将值设置为托管镜像的 SQL Server 的主机名。

8.  创建注册表项**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverserverport**作为 DWORD，然后将值设置为运行 sql Server 以托管镜像的计算机上用于 SQL 的端口号。 如果你使用镜像的命名实例，此 key 值必须设置为命名实例使用的端口号。

9.  在运行 App-v 管理 Web 服务的计算机上，配置通用数据链接（UDL）文本文件。 在安装 App-v 的目录中，双击**SftMgmt**并指定以下值：

    -   在 "**提供程序**" 选项卡上，选择 OLE DB 访问接口**SQL Server Native Client 10.0**。

    -   单击 "**下一步**" 以选择 "**连接**" 选项卡。在 "**服务器名称**" 框中，输入 SQL Server 的服务器名称。 接下来，选择 "**使用 WINDOWS NT 集成安全性**"。 最后，单击列表**选择数据库**，然后选择 app-v 数据库名称。

    -   单击 "**全部**" 选项卡，然后选择 "条目**故障转移" 合作伙伴**。 单击 "**编辑值**"，然后输入故障转移 SQL server 的服务器名称。 单击“确定”****。

    **重要提示**  
    App-v 系统使用 Kerberos 身份验证。 因此，当你配置 SQL 镜像（其中在 SQL Server 上启用了 Kerberos 身份验证，SQL Server 服务在域用户帐户下运行），你必须手动配置 SPN。 有关详细信息，请参阅在[为分布式环境配置 App-v 管理](https://go.microsoft.com/fwlink/?LinkId=203186)（）一文中的 "SQL 服务使用基于域的帐户" https://go.microsoft.com/fwlink/?LinkId=203186) 。



10. 若要验证数据库镜像是否正常运行，请测试故障转移并确认 App-v 管理服务器继续正常工作。

    **重要提示**  
    继续保持警惕，并按照您的标准业务做法，确保系统操作在出现故障时不会中断。



~~~
After the failover has occurred successfully, as verified by using the SQL Server status monitoring information, right-click the **Applications** node in the App-V Management Console, and then select **Refresh**. The list of applications should display normally if the system is working correctly.
~~~

## 相关主题


[如何在 Application Virtualization Server Management Console 中执行管理任务](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)









