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
# <span data-ttu-id="95369-103">如何为 App-V 配置 Microsoft SQL Server 镜像支持</span><span class="sxs-lookup"><span data-stu-id="95369-103">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span>


<span data-ttu-id="95369-104">你可以使用以下过程将 Microsoft Application Virtualization （App-v）环境配置为使用 Microsoft SQL Server 数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="95369-104">You can use the following procedure to configure your Microsoft Application Virtualization (App-V) environment to use Microsoft SQL Server database mirroring.</span></span> <span data-ttu-id="95369-105">配置数据库镜像有助于解决灾难恢复和故障转移情形。</span><span class="sxs-lookup"><span data-stu-id="95369-105">Configuring database mirroring can help with disaster recovery and failover scenarios.</span></span> <span data-ttu-id="95369-106">App-v 4.5 SP2 支持当前可用于 Microsoft SQL Server 2005 和 SQL Server 2008 的所有数据库镜像模式。</span><span class="sxs-lookup"><span data-stu-id="95369-106">App-V 4.5 SP2 supports all modes of database mirroring currently available for Microsoft SQL Server 2005 and SQL Server 2008.</span></span>

**<span data-ttu-id="95369-107">注意</span><span class="sxs-lookup"><span data-stu-id="95369-107">Note</span></span>**  
<span data-ttu-id="95369-108">此过程专为熟悉使用 Microsoft SQL Server 设置和配置 SQL Server 数据库和数据库镜像的管理员编写，因此仅涵盖 App-v 特有的特定配置设置。</span><span class="sxs-lookup"><span data-stu-id="95369-108">This procedure is written for administrators who are familiar with setting up and configuring SQL Server databases and database mirroring with Microsoft SQL Server, and therefore covers only the specific configuration settings that are unique to App-V.</span></span>



**<span data-ttu-id="95369-109">将 app-v 环境配置为使用 Microsoft SQL Server 数据库镜像</span><span class="sxs-lookup"><span data-stu-id="95369-109">To configure your App-V environment to use Microsoft SQL Server database mirroring</span></span>**

1.  <span data-ttu-id="95369-110">在数据库镜像的标准业务做法之后，设置 App-v 数据库的 SQL Server 数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="95369-110">Set up SQL Server database mirroring of the App-V database following your standard business practices for database mirroring.</span></span> <span data-ttu-id="95369-111">对于有关实现 Microsoft SQL Server 数据库镜像的常规信息，请使用以下链接：</span><span class="sxs-lookup"><span data-stu-id="95369-111">Use the following links for general information about implementing Microsoft SQL Server database mirroring:</span></span>

    -   <span data-ttu-id="95369-112">**MICROSOFT SQL 2005**-[设置数据库镜像](https://go.microsoft.com/fwlink/?LinkId=187478)（https://go.microsoft.com/fwlink/?LinkId=187478)</span><span class="sxs-lookup"><span data-stu-id="95369-112">**Microsoft SQL 2005**—[Setting Up Database Mirroring](https://go.microsoft.com/fwlink/?LinkId=187478) (https://go.microsoft.com/fwlink/?LinkId=187478)</span></span>

    -   <span data-ttu-id="95369-113">**MICROSOFT SQL 2008**-[设置数据库镜像](https://go.microsoft.com/fwlink/?LinkId=187477)（https://go.microsoft.com/fwlink/?LinkId=187477)</span><span class="sxs-lookup"><span data-stu-id="95369-113">**Microsoft SQL 2008**—[Setting Up Database Mirroring](https://go.microsoft.com/fwlink/?LinkId=187477) (https://go.microsoft.com/fwlink/?LinkId=187477)</span></span>

    <span data-ttu-id="95369-114">此外，你可以在[数据库镜像最佳做法和性能注意事项](https://go.microsoft.com/fwlink/?LinkId=190270)（.）中找到最佳做法信息 https://go.microsoft.com/fwlink/?LinkId=190270) 。</span><span class="sxs-lookup"><span data-stu-id="95369-114">In addition, you can find Best Practices information in [Database Mirroring Best Practices and Performance Considerations](https://go.microsoft.com/fwlink/?LinkId=190270) (https://go.microsoft.com/fwlink/?LinkId=190270).</span></span>

2.  <span data-ttu-id="95369-115">设置镜像后，请验证 App-v 数据库显示状态 **（主体、同步）**，并且镜像数据库显示状态 **"（镜像、已同步/正在还原）**"。</span><span class="sxs-lookup"><span data-stu-id="95369-115">After mirroring has been set up, verify that the App-V database shows a status of **(Principal, Synchronized)**, and the mirrored database shows a status of **(Mirror, Synchronized / Restoring)**.</span></span> <span data-ttu-id="95369-116">先解决所有镜像问题，然后再继续下一步。</span><span class="sxs-lookup"><span data-stu-id="95369-116">Resolve any mirroring issues before proceeding to the next step.</span></span> <span data-ttu-id="95369-117">有关监视状态的其他信息，请参阅[监视镜像状态](https://go.microsoft.com/fwlink/?LinkId=190279)（ https://go.microsoft.com/fwlink/?LinkId=190279) 。</span><span class="sxs-lookup"><span data-stu-id="95369-117">For additional information about monitoring the status, see [Monitoring Mirroring Status](https://go.microsoft.com/fwlink/?LinkId=190279) (https://go.microsoft.com/fwlink/?LinkId=190279).</span></span>

3.  <span data-ttu-id="95369-118">在承载 app-v 数据库镜像的 sql server 计算机上，通过使用帐户名称\*\* &lt; domain &gt; \\ &lt; ManagementServerHostName &gt; $ \*\*为 app-v 管理服务器的网络服务帐户创建 SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="95369-118">On the SQL Server computer that hosts the mirror of the App-V database, create the SQL Server Login for the network service account of the App-V Management Server by using the account name **&lt;domain&gt;\\&lt;ManagementServerHostName&gt;$**.</span></span>

4.  <span data-ttu-id="95369-119">在 App-v 管理服务器上安装 Microsoft SQL Server Native Client，在运行 App-v Management Web 服务的计算机上安装（如果安装在其他计算机上）。</span><span class="sxs-lookup"><span data-stu-id="95369-119">Install the Microsoft SQL Server Native Client on the App-V Management Server, and on the computer running the App-V Management Web Service if installed on a different computer.</span></span> <span data-ttu-id="95369-120">如果你计划让其他 App-v 管理服务器连接到镜像 SQL 数据库以实现负载平衡，则你必须在这些计算机上安装 Microsoft SQL Server Native Client。</span><span class="sxs-lookup"><span data-stu-id="95369-120">If you plan to have additional App-V Management Servers connect to the mirrored SQL database for load balancing, you must install the Microsoft SQL Server Native Client on those computers as well.</span></span> <span data-ttu-id="95369-121">你可以从 Microsoft 下载中心（.）中的[MICROSOFT Sql server 2008 功能包](https://go.microsoft.com/fwlink/?LinkId=187479)页面下载 Microsoft Sql Server Native Client https://go.microsoft.com/fwlink/?LinkId=187479) 。</span><span class="sxs-lookup"><span data-stu-id="95369-121">You can download the Microsoft SQL Server Native Client from the [Microsoft SQL Server 2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=187479) page in the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=187479).</span></span>

5.  <span data-ttu-id="95369-122">检查注册表项 **_LOCAL HKEY \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlservername** ，确保它仅包含 SQL Server 的主机名。</span><span class="sxs-lookup"><span data-stu-id="95369-122">Check the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLServerName** and make sure that it contains only the host name of the SQL Server.</span></span> <span data-ttu-id="95369-123">如果它包括实例名称（例如*serverhostname\\instancename*），则必须删除实例名称。</span><span class="sxs-lookup"><span data-stu-id="95369-123">If it includes an instance name, for example *serverhostname\\instancename*, the instance name must be removed.</span></span>

    **<span data-ttu-id="95369-124">重要提示</span><span class="sxs-lookup"><span data-stu-id="95369-124">Important</span></span>**  
    <span data-ttu-id="95369-125">应用程序-V 管理服务器在启用数据库镜像时使用 TCP/IP 网络库与 SQL Server 进行通信，因此不能使用实例名称。</span><span class="sxs-lookup"><span data-stu-id="95369-125">The App-V Management Server uses the TCP/IP networking library to communicate with the SQL Server when database mirroring is enabled, and therefore instance names cannot be used.</span></span> <span data-ttu-id="95369-126">必须在注册表项中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="95369-126">The port numbers must be specified in the registry keys instead.</span></span>



6.  <span data-ttu-id="95369-127">检查注册表项 **_LOCAL HKEY \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlserverport** ，确保它包含在 sql Server 计算机上用于 sql 的端口号。</span><span class="sxs-lookup"><span data-stu-id="95369-127">Check the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLServerPort** and make sure that it contains the port number that is used for SQL on the SQL Server computer.</span></span> <span data-ttu-id="95369-128">如果你使用的是命名实例，此密钥值必须设置为命名实例使用的端口。</span><span class="sxs-lookup"><span data-stu-id="95369-128">If you are using a named instance this key value must be set to the port that is used for the named instance.</span></span>

7.  <span data-ttu-id="95369-129">创建注册表项 **_LOCAL HKEY \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverservername** as REG \ _SZ 然后将值设置为托管镜像的 SQL Server 的主机名。</span><span class="sxs-lookup"><span data-stu-id="95369-129">Create the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLFailoverServerName** as REG\_SZ and then set the value to the host name of the SQL Server that hosts the mirror.</span></span>

8.  <span data-ttu-id="95369-130">创建注册表项**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverserverport**作为 DWORD，然后将值设置为运行 sql Server 以托管镜像的计算机上用于 SQL 的端口号。</span><span class="sxs-lookup"><span data-stu-id="95369-130">Create the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLFailoverServerPort** as DWORD and then set the value to the port number that is used for SQL on the computer that is running SQL Server to host the mirror.</span></span> <span data-ttu-id="95369-131">如果你使用镜像的命名实例，此 key 值必须设置为命名实例使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="95369-131">If you are using a named instance for the mirror this key value must be set to the port number that is used for the named instance.</span></span>

9.  <span data-ttu-id="95369-132">在运行 App-v 管理 Web 服务的计算机上，配置通用数据链接（UDL）文本文件。</span><span class="sxs-lookup"><span data-stu-id="95369-132">On the computer that is running the App-V Management Web Service, configure the Universal Data Link (UDL) text file.</span></span> <span data-ttu-id="95369-133">在安装 App-v 的目录中，双击**SftMgmt**并指定以下值：</span><span class="sxs-lookup"><span data-stu-id="95369-133">In the directory where App-V is installed, double-click **SftMgmt.udl** and specify the following values:</span></span>

    -   <span data-ttu-id="95369-134">在 "**提供程序**" 选项卡上，选择 OLE DB 访问接口**SQL Server Native Client 10.0**。</span><span class="sxs-lookup"><span data-stu-id="95369-134">On the **Provider** tab, select the OLE DB provider **SQL Server Native Client 10.0**.</span></span>

    -   <span data-ttu-id="95369-135">单击 "**下一步**" 以选择 "**连接**" 选项卡。在 "**服务器名称**" 框中，输入 SQL Server 的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="95369-135">Click **Next** to select the **Connection** tab. In the **Server Name** box, enter the server name of the SQL Server.</span></span> <span data-ttu-id="95369-136">接下来，选择 "**使用 WINDOWS NT 集成安全性**"。</span><span class="sxs-lookup"><span data-stu-id="95369-136">Next, select **Use Windows NT Integrated Security**.</span></span> <span data-ttu-id="95369-137">最后，单击列表**选择数据库**，然后选择 app-v 数据库名称。</span><span class="sxs-lookup"><span data-stu-id="95369-137">Finally, click the list **Select the database**, and then select the App-V database name.</span></span>

    -   <span data-ttu-id="95369-138">单击 "**全部**" 选项卡，然后选择 "条目**故障转移" 合作伙伴**。</span><span class="sxs-lookup"><span data-stu-id="95369-138">Click the **All** tab, and then select the entry **Failover Partner**.</span></span> <span data-ttu-id="95369-139">单击 "**编辑值**"，然后输入故障转移 SQL server 的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="95369-139">Click **Edit Value**, and then enter the server name of the failover SQL Server.</span></span> <span data-ttu-id="95369-140">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="95369-140">Click **OK**.</span></span>

    **<span data-ttu-id="95369-141">重要提示</span><span class="sxs-lookup"><span data-stu-id="95369-141">Important</span></span>**  
    <span data-ttu-id="95369-142">App-v 系统使用 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="95369-142">The App-V system uses Kerberos authentication.</span></span> <span data-ttu-id="95369-143">因此，当你配置 SQL 镜像（其中在 SQL Server 上启用了 Kerberos 身份验证，SQL Server 服务在域用户帐户下运行），你必须手动配置 SPN。</span><span class="sxs-lookup"><span data-stu-id="95369-143">Therefore, when you configure SQL mirroring where Kerberos Authentication is enabled on the SQL Server and the SQL Server service runs under a domain user account, you must manually configure an SPN.</span></span> <span data-ttu-id="95369-144">有关详细信息，请参阅在[为分布式环境配置 App-v 管理](https://go.microsoft.com/fwlink/?LinkId=203186)（）一文中的 "SQL 服务使用基于域的帐户" https://go.microsoft.com/fwlink/?LinkId=203186) 。</span><span class="sxs-lookup"><span data-stu-id="95369-144">For more information, see “When SQL Service Uses Domain-Based Account” in the article [Configuring App-V Administration for a Distributed Environment](https://go.microsoft.com/fwlink/?LinkId=203186) (https://go.microsoft.com/fwlink/?LinkId=203186).</span></span>



10. <span data-ttu-id="95369-145">若要验证数据库镜像是否正常运行，请测试故障转移并确认 App-v 管理服务器继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="95369-145">To verify that database mirroring is running correctly, test the failover and confirm that the App-V Management Server continues to function correctly.</span></span>

    **<span data-ttu-id="95369-146">重要提示</span><span class="sxs-lookup"><span data-stu-id="95369-146">Important</span></span>**  
    <span data-ttu-id="95369-147">继续保持警惕，并按照您的标准业务做法，确保系统操作在出现故障时不会中断。</span><span class="sxs-lookup"><span data-stu-id="95369-147">Proceed with care, and follow your standard business practices to ensure that system operations are not disrupted in the event of a failure.</span></span>



~~~
After the failover has occurred successfully, as verified by using the SQL Server status monitoring information, right-click the **Applications** node in the App-V Management Console, and then select **Refresh**. The list of applications should display normally if the system is working correctly.
~~~

## <span data-ttu-id="95369-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="95369-148">Related topics</span></span>


[<span data-ttu-id="95369-149">如何在 Application Virtualization Server Management Console 中执行管理任务</span><span class="sxs-lookup"><span data-stu-id="95369-149">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)









