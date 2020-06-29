---
title: 如何使用 PowerShell 在 App-V 5.0 Client 上启用报告
description: 如何使用 PowerShell 在 App-V 5.0 Client 上启用报告
author: dansimp
ms.assetid: a7aaf553-0f83-4cd0-8df8-93a5f1ebe497
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c004b4900a9814a11cb2706659a2edb99de6cc1b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798458"
---
# <span data-ttu-id="6d543-103">如何使用 PowerShell 在 App-V 5.0 Client 上启用报告</span><span class="sxs-lookup"><span data-stu-id="6d543-103">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span>


<span data-ttu-id="6d543-104">使用以下过程为报告配置 App-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="6d543-104">Use the following procedure to configure the App-V 5.0 for reporting.</span></span>

**<span data-ttu-id="6d543-105">配置运行 app-v 5.0 客户端以进行报告的计算机</span><span class="sxs-lookup"><span data-stu-id="6d543-105">To configure the computer running the App-V 5.0 client for reporting</span></span>**

1. <span data-ttu-id="6d543-106">安装 app-v 5.0 客户端。</span><span class="sxs-lookup"><span data-stu-id="6d543-106">Install the App-V 5.0 client.</span></span> <span data-ttu-id="6d543-107">有关安装客户端的详细信息，请参阅[如何部署 App-v 客户端](how-to-deploy-the-app-v-client-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="6d543-107">For more information about installing the client see [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md).</span></span>

2. <span data-ttu-id="6d543-108">在安装了 app-v 5.0 客户端之后，请使用 AppvClientConfiguration PowerShell 配置适当**的**报告配置设置：</span><span class="sxs-lookup"><span data-stu-id="6d543-108">After you have installed the App-V 5.0 client, use the **Set-AppvClientConfiguration** PowerShell to configure appropriate Reporting Configuration settings:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="6d543-109">设置</span><span class="sxs-lookup"><span data-stu-id="6d543-109">Setting</span></span></th>
   <th align="left"><span data-ttu-id="6d543-110">描述</span><span class="sxs-lookup"><span data-stu-id="6d543-110">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="6d543-111">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="6d543-111">ReportingEnabled</span></span></p></td>
   <td align="left"><p><span data-ttu-id="6d543-112">使客户端能够将信息返回到报表服务器。</span><span class="sxs-lookup"><span data-stu-id="6d543-112">Enables the client to return information to a reporting server.</span></span> <span data-ttu-id="6d543-113">客户端需要此设置才能收集客户端上的报告数据。</span><span class="sxs-lookup"><span data-stu-id="6d543-113">This setting is required for the client to collect the reporting data on the client.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="6d543-114">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="6d543-114">ReportingServerURL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="6d543-115">指定报表服务器上保存客户端信息的位置。</span><span class="sxs-lookup"><span data-stu-id="6d543-115">Specifies the location on the reporting server where client information is saved.</span></span> <span data-ttu-id="6d543-116">例如，http:// &lt; reportingservername &gt; ： &lt; reportingportnumber &gt; 。</span><span class="sxs-lookup"><span data-stu-id="6d543-116">For example, http://&lt;reportingservername&gt;:&lt;reportingportnumber&gt;.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="6d543-117">注意</span><span class="sxs-lookup"><span data-stu-id="6d543-117">Note</span></span></strong><br/><p><span data-ttu-id="6d543-118">这是在报表服务器安装期间分配的端口号</span><span class="sxs-lookup"><span data-stu-id="6d543-118">This is the port number that was assigned during the Reporting Server setup</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="6d543-119">报告开始时间</span><span class="sxs-lookup"><span data-stu-id="6d543-119">Reporting Start Time</span></span></p></td>
   <td align="left"><p><span data-ttu-id="6d543-120">此设置用于计划客户端自动将数据发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="6d543-120">This is set to schedule the client to automatically send the data to the server.</span></span> <span data-ttu-id="6d543-121">此设置将指示报告数据将开始发送的小时数。</span><span class="sxs-lookup"><span data-stu-id="6d543-121">This setting will indicate the hour at which the reporting data will start to send.</span></span> <span data-ttu-id="6d543-122">它采用24小时格式，并且将采用介于0-23 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="6d543-122">It is in the 24 hour format and will take a number between 0-23.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="6d543-123">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="6d543-123">ReportingRandomDelay</span></span></p></td>
   <td align="left"><p><span data-ttu-id="6d543-124">指定发送到报告服务器的数据的最大延迟（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="6d543-124">Specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="6d543-125">当计划任务启动时，客户端会在0和 ReportingRandomDelay 之间生成一个随机延迟，并在发送数据之前等待指定的持续时间。</span><span class="sxs-lookup"><span data-stu-id="6d543-125">When the scheduled task is started, the client generates a random delay between 0 and ReportingRandomDelay and will wait the specified duration before sending data.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="6d543-126">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="6d543-126">ReportingInterval</span></span></p></td>
   <td align="left"><p><span data-ttu-id="6d543-127">指定客户端将用于向报告服务器重新发送数据的重试间隔。</span><span class="sxs-lookup"><span data-stu-id="6d543-127">Specifies the retry interval that the client will use to resend data to the reporting server.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="6d543-128">ReportingDataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="6d543-128">ReportingDataCacheLimit</span></span></p></td>
   <td align="left"><p><span data-ttu-id="6d543-129">指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。</span><span class="sxs-lookup"><span data-stu-id="6d543-129">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="6d543-130">大小应用于内存中的缓存。</span><span class="sxs-lookup"><span data-stu-id="6d543-130">The size applies to the cache in memory.</span></span> <span data-ttu-id="6d543-131">达到限制时，日志文件将翻转。</span><span class="sxs-lookup"><span data-stu-id="6d543-131">When the limit is reached, the log file will roll over.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="6d543-132">ReportingDataBlockSize</span><span class="sxs-lookup"><span data-stu-id="6d543-132">ReportingDataBlockSize</span></span></p></td>
   <td align="left"><p><span data-ttu-id="6d543-133">指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。</span><span class="sxs-lookup"><span data-stu-id="6d543-133">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="6d543-134">大小应用于内存中的缓存。</span><span class="sxs-lookup"><span data-stu-id="6d543-134">The size applies to the cache in memory.</span></span> <span data-ttu-id="6d543-135">达到限制时，日志文件将翻转。</span><span class="sxs-lookup"><span data-stu-id="6d543-135">When the limit is reached, the log file will roll over.</span></span></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="6d543-136">配置相应的设置后，运行 App-v 5.0 客户端的计算机将自动收集数据并将数据发送回报表服务器。</span><span class="sxs-lookup"><span data-stu-id="6d543-136">After the appropriate settings have been configured, the computer running the App-V 5.0 client will automatically collect data and will send the data back to the reporting server.</span></span>

   <span data-ttu-id="6d543-137">此外，管理员还可以使用**send-AppvClientReport** PowerShell cmdlet 以按需方式向后手动发送数据。</span><span class="sxs-lookup"><span data-stu-id="6d543-137">Additionally, administrators can manually send the data back in an on-demand manner using the **Send-AppvClientReport** PowerShell cmdlet.</span></span>

   <span data-ttu-id="6d543-138">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="6d543-138">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="6d543-139">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="6d543-139">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="6d543-140">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="6d543-140">Got an App-V issue?</span></span>** <span data-ttu-id="6d543-141">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="6d543-141">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="6d543-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="6d543-142">Related topics</span></span>


[<span data-ttu-id="6d543-143">使用 PowerShell 管理 App-V</span><span class="sxs-lookup"><span data-stu-id="6d543-143">Administering App-V by Using PowerShell</span></span>](administering-app-v-by-using-powershell.md)









