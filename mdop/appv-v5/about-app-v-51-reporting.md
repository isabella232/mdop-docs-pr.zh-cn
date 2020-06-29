---
title: 关于 App-V 5.1 报告
description: 关于 App-V 5.1 报告
author: dansimp
ms.assetid: 385dca00-7178-4e35-8d86-c58867ebd65c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 827343d538238ca638b57a74ae5d2d74bc6c5968
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798674"
---
# <span data-ttu-id="ec2c1-103">关于 App-V 5.1 报告</span><span class="sxs-lookup"><span data-stu-id="ec2c1-103">About App-V 5.1 Reporting</span></span>

<span data-ttu-id="ec2c1-104">Microsoft Application Virtualization （App-v）5.1 包括一个内置的报告功能，可帮助你收集有关运行 app-v 5.1 客户端的计算机的信息以及有关虚拟应用程序包使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-104">Microsoft Application Virtualization (App-V) 5.1 includes a built-in reporting feature that helps you collect information about computers running the App-V 5.1 client as well as information about virtual application package usage.</span></span> <span data-ttu-id="ec2c1-105">你可以使用此信息从集中式数据库生成报表。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-105">You can use this information to generate reports from a centralized database.</span></span>

## <a href="" id="---------app-v-5-1-reporting-overview"></a> <span data-ttu-id="ec2c1-106">App-v 5.1 报告概述</span><span class="sxs-lookup"><span data-stu-id="ec2c1-106">App-V 5.1 Reporting Overview</span></span>

<span data-ttu-id="ec2c1-107">以下列表显示了 app-v 5.1 中用于报告的端到端高级别工作流。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-107">The following list displays the end–to-end high-level workflow for reporting in App-V 5.1.</span></span>

1. <span data-ttu-id="ec2c1-108">App-v 5.1 报告服务器具有下列先决条件：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-108">The App-V 5.1 Reporting server has the following prerequisites:</span></span>

    - <span data-ttu-id="ec2c1-109">Internet information Services （IIS） web 服务器角色</span><span class="sxs-lookup"><span data-stu-id="ec2c1-109">Internet Information Service (IIS) web server role</span></span>

    - <span data-ttu-id="ec2c1-110">Windows 身份验证角色（在 " **IIS/安全**" 下）</span><span class="sxs-lookup"><span data-stu-id="ec2c1-110">Windows Authentication role (under **IIS / Security**)</span></span>

    - <span data-ttu-id="ec2c1-111">安装和运行 sql Server Reporting Services （SSRS）的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec2c1-111">SQL Server installed and running with SQL Server Reporting Services (SSRS)</span></span>

    <span data-ttu-id="ec2c1-112">若要确认 SQL Server Reporting Services 正在运行，请 `http://localhost/Reports` 在 web 浏览器中以管理员身份查看将承载 app-v 5.1 报告的服务器。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-112">To confirm SQL Server Reporting Services is running, view `http://localhost/Reports` in a web browser as administrator on the server that will host App-V 5.1 Reporting.</span></span> <span data-ttu-id="ec2c1-113">将显示 SQL Server Reporting Services 主页。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-113">The SQL Server Reporting Services Home page should display.</span></span>

2. <span data-ttu-id="ec2c1-114">安装 app-v 5.1 报告服务器和关联的数据库。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-114">Install the App-V 5.1 reporting server and associated database.</span></span> <span data-ttu-id="ec2c1-115">有关安装报告服务器的详细信息，请参阅[如何在独立计算机上安装报告服务器并将其连接到数据库](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-115">For more information about installing the reporting server see [How to install the Reporting Server on a Standalone Computer and Connect it to the Database](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md).</span></span> <span data-ttu-id="ec2c1-116">配置运行 App-v 5.1 客户端的计算机应将数据发送到报告服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-116">Configure the time when the computer running the App-V 5.1 client should send data to the reporting server.</span></span>

3. <span data-ttu-id="ec2c1-117">如果您未使用电子软件分发系统（如 Configuration Manager 查看报告），则可以在 SQL Server Reporting Services 中定义报表。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-117">If you are not using an electronic software distribution system such as Configuration Manager to view reports then you can define reports in SQL Server Reporting Service.</span></span> <span data-ttu-id="ec2c1-118">从[下载中心](https://go.microsoft.com/fwlink/?LinkId=397255)下载预定义的 SSRS 报告。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-118">Download predefined SSRS Reports from the [Download Center](https://go.microsoft.com/fwlink/?LinkId=397255).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2c1-119">如果你将 Configuration Manager 与 app-v 5.1 结合使用，则大多数报表都是从 Configuration Manager 生成的，而不是从 App-v 5.1 生成的。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-119">If you are using the Configuration Manager integration with App-V 5.1, most reports are generated from Configuration Manager rather than from App-V 5.1.</span></span>

4. <span data-ttu-id="ec2c1-120">使用 as 管理员导入 app-v 5.1 PowerShell 模块后 `Import-Module AppvClient` ，启用 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-120">After importing the App-V 5.1 PowerShell module using `Import-Module AppvClient` as administrator, enable the App-V 5.1 client.</span></span> <span data-ttu-id="ec2c1-121">此示例 PowerShell cmdlet 支持 app-v 5.1 报告：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-121">This sample PowerShell cmdlet enables App-V 5.1 reporting:</span></span>

    ```powershell
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    <span data-ttu-id="ec2c1-122">若要立即发送 app-v 5.1 报告数据，请 `Send-AppvClientReport` 在 app-v 5.1 客户端上运行。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-122">To immediately send App-V 5.1 report data, run `Send-AppvClientReport` on the App-V 5.1 client.</span></span>

    <span data-ttu-id="ec2c1-123">有关安装启用了报告的 app-v 5.1 客户端的详细信息，请参阅[关于客户端配置设置](about-client-configuration-settings51.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-123">For more information about installing the App-V 5.1 client with reporting enabled see [About Client Configuration Settings](about-client-configuration-settings51.md).</span></span> <span data-ttu-id="ec2c1-124">若要使用 Windows PowerShell 管理 app-v 5.1 报告，请参阅[如何使用 PowerShell 启用 app-v 5.1 客户端上的报告](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-124">To administer App-V 5.1 Reporting with Windows PowerShell, see [How to Enable Reporting on the App-V 5.1 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md).</span></span>

5. <span data-ttu-id="ec2c1-125">在报表服务器从 App-v 5.1 客户端接收数据后，它会将数据发送到报告数据库。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-125">After the reporting server receives the data from the App-V 5.1 client it sends the data to the reporting database.</span></span> <span data-ttu-id="ec2c1-126">当数据库接收和处理客户端数据时，会将成功的答复发送到报告服务器，然后将通知发送到 App-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-126">When the database receives and processes the client data, a successful reply is sent to the reporting server and then a notification is sent to the App-V 5.1 client.</span></span>

6. <span data-ttu-id="ec2c1-127">当 App-v 5.1 客户端收到成功通知时，它将清空数据缓存以节省空间。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-127">When the App-V 5.1 client receives the success notification, it empties the data cache to conserve space.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2c1-128">默认情况下，在服务器确认数据接收后，缓存将被清除。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-128">By default the cache is cleared after the server confirms receipt of data.</span></span> <span data-ttu-id="ec2c1-129">你可以手动配置客户端以保存数据缓存。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-129">You can manually configure the client to save the data cache.</span></span>

<span data-ttu-id="ec2c1-130">如果 App-v 5.1 客户端设备未收到来自服务器的成功通知，它会将数据保留在缓存中，并尝试在下一个配置的时间间隔内重新发送数据。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-130">If the App-V 5.1 client device does not receive a success notification from the server, it retains data in the cache and tries to resend data at the next configured interval.</span></span> <span data-ttu-id="ec2c1-131">客户端继续收集数据并将其添加到缓存。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-131">Clients continue to collect data and add it to the cache.</span></span>

### <a href="" id="-------------app-v-5-1-reporting-server-frequently-asked-questions"></a> <span data-ttu-id="ec2c1-132">App-v 5.1 reporting server 常见问题</span><span class="sxs-lookup"><span data-stu-id="ec2c1-132">App-V 5.1 reporting server frequently asked questions</span></span>

<span data-ttu-id="ec2c1-133">下表显示了有关 App-v 5.1 报告的常见问题的答案</span><span class="sxs-lookup"><span data-stu-id="ec2c1-133">The following table displays answers to common questions about App-V 5.1 reporting</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec2c1-134">问题</span><span class="sxs-lookup"><span data-stu-id="ec2c1-134">Question</span></span></th>
<th align="left"><span data-ttu-id="ec2c1-135">详细信息</span><span class="sxs-lookup"><span data-stu-id="ec2c1-135">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec2c1-136">报告信息发送到报告数据库的频率是多少？</span><span class="sxs-lookup"><span data-stu-id="ec2c1-136">What is the frequency that reporting information is sent to the reporting database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec2c1-137">该频率取决于运行 App-v 5.1 客户端的计算机上配置报告任务的方式。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-137">The frequency depends on how the reporting task is configured on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="ec2c1-138">您必须配置发送报告数据的频率/间隔。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-138">You must configure the frequency / interval for sending the reporting data.</span></span> <span data-ttu-id="ec2c1-139">默认情况下，不启用 app-v 5.1 报告。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-139">App-V 5.1 Reporting is not enabled by default.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec2c1-140">报表服务器数据库中存储哪些信息？</span><span class="sxs-lookup"><span data-stu-id="ec2c1-140">What information is stored in the reporting server database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec2c1-141">以下列表显示了报告数据库中存储的内容：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-141">The following list displays what is stored in the reporting database:</span></span></p>
<ul>
<li><p><span data-ttu-id="ec2c1-142">运行 App-v 5.1 客户端的计算机上运行的操作系统：主机名、版本、service pack、type-客户端/服务器、处理器架构。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-142">The operating system running on the computer running the App-V 5.1 client: host name, version, service pack, type - client/server, processor architecture.</span></span></p></li>
<li><p><span data-ttu-id="ec2c1-143">App-v 5.1 客户端信息：版本。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-143">App-V 5.1 Client information: version.</span></span></p></li>
<li><p><span data-ttu-id="ec2c1-144">已发布程序包列表： GUID、版本 GUID、名称。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-144">Published package list: GUID, version GUID, name.</span></span></p></li>
<li><p><span data-ttu-id="ec2c1-145">应用程序使用信息：名称、版本、流式处理服务器、用户（domain\alias）、程序包版本 GUID、启动状态和时间、关闭时间。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-145">Application usage information: name, version, streaming server, user (domain\alias), package version GUID, launch status and time, shutdown time.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec2c1-146">发送到报告服务器的信息量的平均数量是多少？</span><span class="sxs-lookup"><span data-stu-id="ec2c1-146">What is the average volume of information that is sent to the reporting server?</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec2c1-147">这取决于。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-147">It depends.</span></span> <span data-ttu-id="ec2c1-148">以下列表显示发送到报告服务器的三组数据：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-148">The following list displays the three sets of the data sent to the reporting server:</span></span></p>
<ol>
<li><p><span data-ttu-id="ec2c1-149">操作系统和 App-v 5.1 客户端信息。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-149">Operating system, and App-V 5.1 client information.</span></span> <span data-ttu-id="ec2c1-150">每次发送此数据时约150字节。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-150">~150 Bytes, every time this data is sent.</span></span></p></li>
<li><p><span data-ttu-id="ec2c1-151">已发布程序包列表。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-151">Published package list.</span></span> <span data-ttu-id="ec2c1-152">30个程序包大约 7 KB。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-152">~7 KB for 30 packages.</span></span> <span data-ttu-id="ec2c1-153">仅当程序包列表使用较少的发布刷新进行更新时，才会发送此内容;如果没有任何更改，则不会发送此信息。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-153">This is sent only when the package list is updated with a publishing refresh, which is done infrequently; if there is no change, this information is not sent.</span></span></p></li>
<li><p><span data-ttu-id="ec2c1-154">虚拟应用程序使用信息-每个事件大约 0.25 KB。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-154">Virtual application usage information – about 0.25KB per event.</span></span> <span data-ttu-id="ec2c1-155">如果两次都在发送信息之前发生，则打开和结束计数为一个事件。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-155">Opening and closing count as one event if both occur before sending the information.</span></span> <span data-ttu-id="ec2c1-156">使用计划任务发送时，仅将上次成功上载后的数据发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-156">When sending using a scheduled task, only the data since the last successful upload is sent to the server.</span></span> <span data-ttu-id="ec2c1-157">如果通过 PowerShell cmdlet 手动发送，则会有一个可选参数，用于控制是否需要在下一次（该参数为 DeleteOnSuccess）重新发送数据 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-157">If sending manually through the PowerShell cmdlet, there is an optional argument that controls if the data needs to be re-sent next time around – that argument is <strong>DeleteOnSuccess</strong>.</span></span></p>
<p></p>
<p><span data-ttu-id="ec2c1-158">例如，如果二十个应用程序已打开并已关闭，并且报告信息每天发送，则典型的每天流量应大约为 0.15 KB + 20 x 0.25 KB，或者大约 5KB/user</span><span class="sxs-lookup"><span data-stu-id="ec2c1-158">So for example, if twenty applications are opened and closed and reporting information is scheduled to be sent daily, the typical daily traffic should be about 0.15KB + 20 x 0.25KB, or about 5KB/user</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec2c1-159">是否可以计划报告？</span><span class="sxs-lookup"><span data-stu-id="ec2c1-159">Can reporting be scheduled?</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec2c1-160">是。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-160">Yes.</span></span> <span data-ttu-id="ec2c1-161">除了使用 PowerShell Cmdlet （ <strong> Send-AppvClientReport）手动发送报告外 </strong> ，还可以计划任务，以便它会自动发生。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-161">Besides manually sending reporting using PowerShell Cmdlets (<strong>Send-AppvClientReport</strong>), the task can be scheduled so it will happen automatically.</span></span> <span data-ttu-id="ec2c1-162">可通过两种方式安排报告：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-162">There are two ways to schedule the reporting:</span></span></p>
<ol>
<li><p><span data-ttu-id="ec2c1-163">使用 PowerShell cmdlet- <strong> Set-AppvClientConfiguration </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-163">Using PowerShell cmdlets - <strong>Set-AppvClientConfiguration</strong>.</span></span> <span data-ttu-id="ec2c1-164">例如：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-164">For example:</span></span></p>
<p><span data-ttu-id="ec2c1-165">Set-AppvClientConfiguration-ReportingEnabled 1-ReportingServerURL<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span><span class="sxs-lookup"><span data-stu-id="ec2c1-165">Set-AppvClientConfiguration -ReportingEnabled 1 - ReportingServerURL <a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span></span></a></p>
<p></p>
<p><span data-ttu-id="ec2c1-166">有关客户端配置设置的完整列表，请参阅 <a href="about-client-configuration-settings51.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings51.md)"> 关于客户端配置设置 </a> 和查找以下条目： <strong> ReportingEnabled </strong> 、 <strong> ReportingServerURL </strong> 、 <strong> ReportingDataCacheLimit </strong> 、 <strong> ReportingDataBlockSize </strong> 、 <strong> ReportingStartTime </strong> 、 <strong> ReportingRandomDelay </strong> 、 <strong> ReportingInterval </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-166">For a complete list of client configuration settings see <a href="about-client-configuration-settings51.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings51.md)">About Client Configuration Settings</a> and look for the following entries: <strong>ReportingEnabled</strong>, <strong>ReportingServerURL</strong>, <strong>ReportingDataCacheLimit</strong>, <strong>ReportingDataBlockSize</strong>, <strong>ReportingStartTime</strong>, <strong>ReportingRandomDelay</strong>, <strong>ReportingInterval</strong>.</span></span></p>
<p></p></li>
<li><p><span data-ttu-id="ec2c1-167">使用组策略。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-167">By using Group Policy.</span></span> <span data-ttu-id="ec2c1-168">如果使用域控制器进行分发，则设置与前面列出的设置相同。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-168">If distributed using the domain controller, the settings are the same as previously listed.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ec2c1-169">注意</span><span class="sxs-lookup"><span data-stu-id="ec2c1-169">Note</span></span></strong><br/><p><span data-ttu-id="ec2c1-170">组策略设置替代使用 PowerShell 配置的本地设置。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-170">Group Policy settings override local settings configured using PowerShell.</span></span></p>
</div>
<div>
</div></li>
</ol></td>
</tr>
</tbody>
</table>

## <a href="" id="---------app-v-5-1-client-reporting"></a> <span data-ttu-id="ec2c1-171">App-v 5.1 客户端报告</span><span class="sxs-lookup"><span data-stu-id="ec2c1-171">App-V 5.1 Client Reporting</span></span>

<span data-ttu-id="ec2c1-172">若要使用 app-v 5.1 报告，您必须安装和配置 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-172">To use App-V 5.1 reporting you must install and configure the App-V 5.1 client.</span></span> <span data-ttu-id="ec2c1-173">安装客户端后，请使用**AppVClientConfiguration** PowerShell Cmdlet 或**ADMX 模板**来配置报告。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-173">After the client has been installed, use the **Set-AppVClientConfiguration** PowerShell cmdlet or the **ADMX Template** to configure reporting.</span></span> <span data-ttu-id="ec2c1-174">报告功能 cmdlet 可通过以下链接提供，并以**报告**开头。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-174">The reporting feature cmdlets are available by using the following link and are prefaced by **Reporting**.</span></span> <span data-ttu-id="ec2c1-175">有关客户端配置设置的完整列表，请参阅[关于客户端配置设置](about-client-configuration-settings51.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-175">For a complete list of client configuration settings see [About Client Configuration Settings](about-client-configuration-settings51.md).</span></span> <span data-ttu-id="ec2c1-176">以下部分提供了使用 PowerShell 的 app-v 5.1 客户端报告配置的示例。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-176">The following section provides examples of App-V 5.1 client reporting configuration using PowerShell.</span></span>

### <span data-ttu-id="ec2c1-177">使用 PowerShell 配置 App-v 客户端报告</span><span class="sxs-lookup"><span data-stu-id="ec2c1-177">Configuring App-V Client reporting using PowerShell</span></span>

<span data-ttu-id="ec2c1-178">以下示例显示 PowerShell 参数如何配置 app-v 5.1 客户端的报告功能。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-178">The following examples show how PowerShell parameters can configure the reporting features of the App-V 5.1 client.</span></span>

> [!NOTE]
> <span data-ttu-id="ec2c1-179">还可以使用 app-v 5.1 ADMX 模板中的组策略设置配置以下配置任务。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-179">The following configuration task can also be configured using Group Policy settings in the App-V 5.1 ADMX template.</span></span> <span data-ttu-id="ec2c1-180">有关使用 ADMX 模板的详细信息，请参阅[如何使用 Admx 模板和组策略修改 app-v 5.1 客户端配置](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-180">For more information about using the ADMX template, see [How to Modify App-V 5.1 Client Configuration Using the ADMX Template and Group Policy](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md).</span></span>

<span data-ttu-id="ec2c1-181">**若要在运行 app-v 5.1 客户端的计算机上启用报告和启动数据收集，** 请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-181">**To enable reporting and to initiate data collection on the computer running the App-V 5.1 client**:</span></span>

```powershell
Set-AppVClientConfiguration –ReportingEnabled 1
```

<span data-ttu-id="ec2c1-182">**若要将客户端配置为自动将数据发送到特定的报表服务器**，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-182">**To configure the client to automatically send data to a specific reporting server**:</span></span>

```powershell
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30 -ReportingInterval 1 -ReportingRandomDelay 30
```

<span data-ttu-id="ec2c1-183">此示例将客户端配置为自动将报告数据发送到报表服务器 URL **http://MyReportingServer:MyPort/** 。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-183">This example configures the client to automatically send the reporting data to the reporting server URL **http://MyReportingServer:MyPort/**.</span></span> <span data-ttu-id="ec2c1-184">此外，报告数据将在8:00 和 8:30 PM 之间每天发送，具体取决于为会话生成的随机延迟。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-184">Additionally, the reporting data will be sent daily between 8:00 and 8:30 PM, depending on the random delay generated for the session.</span></span>

<span data-ttu-id="ec2c1-185">**若要限制客户端上的数据缓存的大小**，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-185">**To limit the size of the data cache on the client**:</span></span>

```powershell
Set-AppvClientConfiguration –ReportingDataCacheLimit 100
```

<span data-ttu-id="ec2c1-186">将运行 App-v 5.1 客户端的计算机上的报告缓存的最大大小配置为 100 MB。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-186">Configures the maximum size of the reporting cache on the computer running the App-V 5.1 client to 100 MB.</span></span> <span data-ttu-id="ec2c1-187">如果在将数据发送到服务器之前已达到缓存限制，则日志将回滚，并且将根据需要覆盖数据。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-187">If the cache limit is reached before the data is sent to the server, then the log rolls over and data will be overwritten as necessary.</span></span>

<span data-ttu-id="ec2c1-188">**要配置客户端和服务器之间通过网络传输的数据块大小，** 请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-188">**To configure the data block size transmitted across the network between the client and the server**:</span></span>

```powershell
Set-AppvClientConfiguration –ReportingDataBlockSize 10240
```

<span data-ttu-id="ec2c1-189">指定客户端发送到 10240 MB 的最大数据块。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-189">Specifies the maximum data block that the client sends to 10240 MB.</span></span>

### <span data-ttu-id="ec2c1-190">收集的数据类型</span><span class="sxs-lookup"><span data-stu-id="ec2c1-190">Types of data collected</span></span>

<span data-ttu-id="ec2c1-191">下表显示了可使用 App-v 5.1 报告收集的信息类型。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-191">The following table displays the types of information you can collect by using App-V 5.1 reporting.</span></span>

|<span data-ttu-id="ec2c1-192">客户端信息</span><span class="sxs-lookup"><span data-stu-id="ec2c1-192">Client Information</span></span>  |<span data-ttu-id="ec2c1-193">程序包信息</span><span class="sxs-lookup"><span data-stu-id="ec2c1-193">Package Information</span></span>  |<span data-ttu-id="ec2c1-194">应用程序使用</span><span class="sxs-lookup"><span data-stu-id="ec2c1-194">Application Usage</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ec2c1-195">主机名</span><span class="sxs-lookup"><span data-stu-id="ec2c1-195">Host Name</span></span> |<span data-ttu-id="ec2c1-196">程序包名称</span><span class="sxs-lookup"><span data-stu-id="ec2c1-196">Package Name</span></span>|<span data-ttu-id="ec2c1-197">开始时间和结束时间</span><span class="sxs-lookup"><span data-stu-id="ec2c1-197">Start and End Times</span></span>|
|<span data-ttu-id="ec2c1-198">App-v 5.1 客户端版本</span><span class="sxs-lookup"><span data-stu-id="ec2c1-198">App-V 5.1 Client Version</span></span> |<span data-ttu-id="ec2c1-199">程序包版本</span><span class="sxs-lookup"><span data-stu-id="ec2c1-199">Package Version</span></span>|<span data-ttu-id="ec2c1-200">运行状态</span><span class="sxs-lookup"><span data-stu-id="ec2c1-200">Run Status</span></span>|
|<span data-ttu-id="ec2c1-201">处理器体系结构</span><span class="sxs-lookup"><span data-stu-id="ec2c1-201">Processor Architecture</span></span> |<span data-ttu-id="ec2c1-202">程序包源</span><span class="sxs-lookup"><span data-stu-id="ec2c1-202">Package Source</span></span>|<span data-ttu-id="ec2c1-203">关闭状态</span><span class="sxs-lookup"><span data-stu-id="ec2c1-203">Shutdown State</span></span>|
|<span data-ttu-id="ec2c1-204">操作系统版本</span><span class="sxs-lookup"><span data-stu-id="ec2c1-204">Operating System Version</span></span>|<span data-ttu-id="ec2c1-205">缓存百分比</span><span class="sxs-lookup"><span data-stu-id="ec2c1-205">Percent Cached</span></span>|<span data-ttu-id="ec2c1-206">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="ec2c1-206">Application Name</span></span>|
|<span data-ttu-id="ec2c1-207">Service Pack 级别</span><span class="sxs-lookup"><span data-stu-id="ec2c1-207">Service Pack Level</span></span>| |<span data-ttu-id="ec2c1-208">应用程序版本</span><span class="sxs-lookup"><span data-stu-id="ec2c1-208">Application Version</span></span>|
|<span data-ttu-id="ec2c1-209">操作系统类型</span><span class="sxs-lookup"><span data-stu-id="ec2c1-209">Operating System Type</span></span>| |<span data-ttu-id="ec2c1-210">用户名</span><span class="sxs-lookup"><span data-stu-id="ec2c1-210">Username</span></span>|
| | |<span data-ttu-id="ec2c1-211">连接组</span><span class="sxs-lookup"><span data-stu-id="ec2c1-211">Connection Group</span></span>|

<span data-ttu-id="ec2c1-212">客户端以 **.xml**格式收集和保存此数据。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-212">The client collects and saves this data in an **.xml** format.</span></span> <span data-ttu-id="ec2c1-213">默认情况下，数据缓存处于隐藏状态，需要管理员权限才能打开 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-213">The data cache is hidden by default and requires administrator rights to open the XML file.</span></span>

### <span data-ttu-id="ec2c1-214">将数据发送到服务器</span><span class="sxs-lookup"><span data-stu-id="ec2c1-214">Sending data to the server</span></span>

<span data-ttu-id="ec2c1-215">你可以配置运行 App-v 5.1 客户端的计算机以自动将数据发送到指定的报表服务器。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-215">You can configure the computer that is running the App-V 5.1 client to automatically send data to the specified reporting server.</span></span> <span data-ttu-id="ec2c1-216">若要指定服务器，请使用具有以下设置的**AppvClientConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-216">To specify the server use the **Set-AppvClientConfiguration** cmdlet with the following settings:</span></span>

- <span data-ttu-id="ec2c1-217">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="ec2c1-217">ReportingEnabled</span></span>
- <span data-ttu-id="ec2c1-218">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="ec2c1-218">ReportingServerURL</span></span>
- <span data-ttu-id="ec2c1-219">ReportingStartTime</span><span class="sxs-lookup"><span data-stu-id="ec2c1-219">ReportingStartTime</span></span>
- <span data-ttu-id="ec2c1-220">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="ec2c1-220">ReportingInterval</span></span>
- <span data-ttu-id="ec2c1-221">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="ec2c1-221">ReportingRandomDelay</span></span>

<span data-ttu-id="ec2c1-222">配置以前的设置后，必须创建计划任务。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-222">After you configure the previous settings, you must create a scheduled task.</span></span> <span data-ttu-id="ec2c1-223">计划任务将联系由**ReportingServerURL**设置指定的服务器，并将启动传输。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-223">The scheduled task will contact the server specified by the **ReportingServerURL** setting and will initiate the transfer.</span></span> <span data-ttu-id="ec2c1-224">如果你想要在计划的时间之外手动发送数据，请使用以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-224">If you want to manually send data outside of the scheduled times, use the following PowerShell cmdlet:</span></span>

```powershell
Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess
```

<span data-ttu-id="ec2c1-225">如果以前配置过报表服务器，则可以忽略 **– URL**参数。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-225">If the reporting server has been previously configured, then the **–URL** parameter can be omitted.</span></span> <span data-ttu-id="ec2c1-226">或者，如果应将数据发送到备用位置，请指定其他 URL 以替代此数据集的已配置**ReportingServerURL** 。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-226">Alternatively, if the data should be sent to an alternate location, specify a different URL to override the configured **ReportingServerURL** for this data collection.</span></span>

<span data-ttu-id="ec2c1-227">**-DeleteOnSuccess**参数指示如果传输成功，则清除数据缓存。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-227">The **-DeleteOnSuccess** parameter indicates that if the transfer is successful, then the data cache is cleared.</span></span> <span data-ttu-id="ec2c1-228">如果未指定此选项，则不会清除缓存。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-228">If this is not specified, then the cache will not be cleared.</span></span>

### <span data-ttu-id="ec2c1-229">手动数据收集</span><span class="sxs-lookup"><span data-stu-id="ec2c1-229">Manual Data Collection</span></span>

<span data-ttu-id="ec2c1-230">你还可以使用**AppVClientReport** cmdlet 手动收集数据。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-230">You can also use the **Send-AppVClientReport** cmdlet to manually collect data.</span></span> <span data-ttu-id="ec2c1-231">此解决方案对现有报告服务器或没有现有报告服务器很有帮助。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-231">This solution is helpful with or without an existing reporting server.</span></span> <span data-ttu-id="ec2c1-232">以下列表显示有关使用或不使用报表服务器收集数据的信息。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-232">The following list displays information about collecting data with or without a reporting server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec2c1-233">使用报表服务器</span><span class="sxs-lookup"><span data-stu-id="ec2c1-233">With a Reporting Server</span></span></th>
<th align="left"><span data-ttu-id="ec2c1-234">不带报表服务器</span><span class="sxs-lookup"><span data-stu-id="ec2c1-234">Without a Reporting Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec2c1-235">如果你有现有的 app-v 5.1 报表服务器，请创建自定义计划任务或脚本。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-235">If you have an existing App-V 5.1 reporting Server, create a customized scheduled task or script.</span></span> <span data-ttu-id="ec2c1-236">指定客户端将数据以所需的频率发送到指定位置。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-236">Specify that the client send the data to the specified location with the desired frequency.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec2c1-237">如果您没有现有的 app-v 5.1 报告服务器，请使用 <strong> – URL </strong> 参数将数据发送到指定的共享。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-237">If you do not have an existing App-V 5.1 reporting Server, use the <strong>–URL</strong> parameter to send the data to a specified share.</span></span> <span data-ttu-id="ec2c1-238">例如：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-238">For example:</span></span></p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p><span data-ttu-id="ec2c1-239">前面的示例将把报告数据发送到 <strong> &lt; &gt; 由 <strong> -URL 参数指示的 \MyShare\MyData/strong 位置 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-239">The previous example will send the reporting data to <strong>\MyShare\MyData&lt;/strong&gt; location indicated by the <strong>-URL</strong> parameter.</span></span> <span data-ttu-id="ec2c1-240">发送数据后，将清除缓存。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-240">After the data has been sent, the cache is cleared.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ec2c1-241">注意</span><span class="sxs-lookup"><span data-stu-id="ec2c1-241">Note</span></span></strong><br/><p><span data-ttu-id="ec2c1-242">如果指定了报告服务器之外的位置，则数据将使用 <strong> .xml 格式发送， </strong> 无需其他处理。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-242">If a location other than the Reporting Server is specified, the data is sent using <strong>.xml</strong> format with no additional processing.</span></span></p>
</div>
<div>
</div></td>
</tr>
</tbody>
</table>

### <span data-ttu-id="ec2c1-243">创建报表</span><span class="sxs-lookup"><span data-stu-id="ec2c1-243">Creating Reports</span></span>

<span data-ttu-id="ec2c1-244">若要使用 App-v 5.1 检索报表信息和创建报表，必须使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-244">To retrieve report information and create reports using App-V 5.1 you must use one of the following methods:</span></span>

- <span data-ttu-id="ec2c1-245">Microsoft **Sql Server Reporting services （SSRS）** -microsoft Sql Server reporting services 可通过 Microsoft sql server 使用。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-245">**Microsoft SQL Server Reporting Services (SSRS)** - Microsoft SQL Server Reporting Services is available with Microsoft SQL Server.</span></span> <span data-ttu-id="ec2c1-246">安装 app-v 5.1 报告服务器时，不会安装 SSRS。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-246">SSRS is not installed when you install the App-V 5.1 reporting server.</span></span> <span data-ttu-id="ec2c1-247">必须单独部署它才能生成相关联的报表。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-247">It must be deployed separately to generate the associated reports.</span></span>

    <span data-ttu-id="ec2c1-248">有关使用[MICROSOFT SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)的详细信息，请使用以下链接。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-248">Use the following link for more information about using [Microsoft SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596).</span></span>

- <span data-ttu-id="ec2c1-249">**脚本**-你可以通过直接通过脚本对 app-v 5.1 报告数据库生成报表。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-249">**Scripting** – You can generate reports by scripting directly against the App-V 5.1 reporting database.</span></span> <span data-ttu-id="ec2c1-250">例如：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-250">For example:</span></span>

    **<span data-ttu-id="ec2c1-251">存储过程：</span><span class="sxs-lookup"><span data-stu-id="ec2c1-251">Stored Procedure:</span></span>**

    <span data-ttu-id="ec2c1-252">**spProcessClientReport**计划在午夜或 12:00 AM 运行。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-252">**spProcessClientReport** is scheduled to run at midnight or 12:00 AM.</span></span>

    <span data-ttu-id="ec2c1-253">若要运行 Microsoft SQL Server 计划的存储过程，必须运行 Microsoft SQL Server 代理。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-253">To run the Microsoft SQL Server Scheduled Stored procedure, the Microsoft SQL Server Agent must be running.</span></span> <span data-ttu-id="ec2c1-254">应确保将 Microsoft SQL Server Agent 设置为**AutoStart**。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-254">You should ensure that the Microsoft SQL Server Agent is set to **AutoStart**.</span></span> <span data-ttu-id="ec2c1-255">有关详细信息，请参阅[AUTOSTART Sql Server 代理（Sql Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=287045)。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-255">For more information see [Autostart SQL Server Agent (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045).</span></span>

    <span data-ttu-id="ec2c1-256">还会在使用 app-v 5.1 数据库脚本时创建存储过程。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-256">The stored procedure is also created when using the App-V 5.1 database scripts.</span></span>

<span data-ttu-id="ec2c1-257">你还应确保将报表服务器 web 服务的**最大并发连接**设置为服务器能够管理的值，而不会影响可用性。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-257">You should also ensure that the reporting server web service's **Maximum Concurrent Connections** is set to a value that the server will be able to manage without impacting availability.</span></span> <span data-ttu-id="ec2c1-258">**报告 Web 服务**的**最大并发连接**数建议为**10000**。</span><span class="sxs-lookup"><span data-stu-id="ec2c1-258">The recommended number of **Maximum Concurrent Connections** for the **Reporting Web Service** is **10,000**.</span></span>

## <span data-ttu-id="ec2c1-259">相关主题</span><span class="sxs-lookup"><span data-stu-id="ec2c1-259">Related topics</span></span>

[<span data-ttu-id="ec2c1-260">部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="ec2c1-260">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)

[<span data-ttu-id="ec2c1-261">如何在独立计算机上安装报告服务器并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="ec2c1-261">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)
