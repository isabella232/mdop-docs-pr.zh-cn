---
title: 如何设置或禁用数据库大小
description: 如何设置或禁用数据库大小
author: dansimp
ms.assetid: 4abaf349-132d-4186-8873-a0e515593b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cbb041920e2680d51b01926f144eba595fe28d05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801067"
---
# <span data-ttu-id="b73db-103">如何设置或禁用数据库大小</span><span class="sxs-lookup"><span data-stu-id="b73db-103">How to Set Up or Disable Database Size</span></span>


<span data-ttu-id="b73db-104">你可以使用应用程序虚拟化服务器管理控制台中的以下过程来指定要存储在数据库中的应用程序虚拟化系统使用的大小（以 MB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="b73db-104">You can use the following procedures in the Application Virtualization Server Management Console to specify the size (in MB) of Application Virtualization System usage that you want to store in the database.</span></span>

<span data-ttu-id="b73db-105">当所存储数据的大小达到指定限制的95% （高水位线）时，系统将删除10% 的使用率数据，从而导致85% 的数据。</span><span class="sxs-lookup"><span data-stu-id="b73db-105">When the size of the stored data reaches 95% (the high watermark) of the specified limit, the system will delete 10% of the usage data, leaving 85% of the data.</span></span> <span data-ttu-id="b73db-106">将删除程序包和应用程序使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="b73db-106">Package and application usage data will be deleted.</span></span> <span data-ttu-id="b73db-107">当数据库变得足够大并接近高水位线时，将向 SQL Server 日志发送一条警告消息，告知您已达到此限制。</span><span class="sxs-lookup"><span data-stu-id="b73db-107">When the database grows large enough and approaches the high watermark, a warning message is sent to the SQL Server log to inform you that this limit has been reached.</span></span> <span data-ttu-id="b73db-108">此警告是必需的，因为清理操作可能会影响报表的输出。</span><span class="sxs-lookup"><span data-stu-id="b73db-108">This warning is necessary because the cleanup action can affect the output of the reports.</span></span> <span data-ttu-id="b73db-109">它还将帮助你确定是否需要增加最大数据库大小、减少要保留的使用数据的月份数，或关闭日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="b73db-109">It will also help you decide whether you need to increase the maximum database size, reduce the number of months of usage data to be kept, or turn down the logging level.</span></span>

<span data-ttu-id="b73db-110">**注意** 将提供 "**无大小限制**" 和 "**保留所有使用情况**" 选项，以便您可以禁用使用情况报告和数据库清理。</span><span class="sxs-lookup"><span data-stu-id="b73db-110">**Note** The **No Size Limit** and **Keep All Usage** options are provided so that you can disable usage reporting and database cleanup.</span></span> <span data-ttu-id="b73db-111">选择这些项目也将清理数据库事务日志。</span><span class="sxs-lookup"><span data-stu-id="b73db-111">Selecting these items will clean up the database transaction log as well.</span></span> <span data-ttu-id="b73db-112">（所有提交的 Microsoft SQL Server 事务都将从数据库日志中删除。）</span><span class="sxs-lookup"><span data-stu-id="b73db-112">(All committed Microsoft SQL Server transactions will be removed from the database log.)</span></span>

 

**<span data-ttu-id="b73db-113">设置数据库大小</span><span class="sxs-lookup"><span data-stu-id="b73db-113">To set up database size</span></span>**

1.  <span data-ttu-id="b73db-114">右键单击左窗格中的 "应用程序虚拟化系统" 节点，然后选择 "**系统选项**"。</span><span class="sxs-lookup"><span data-stu-id="b73db-114">Right-click the Application Virtualization System node in the left pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="b73db-115">选择 "**数据库**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b73db-115">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="b73db-116">选择 "**最大数据库大小（MB）** " 或 "**无大小限制**" 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="b73db-116">Select the **Maximum Database Size (MB)** or **No Size Limit** radio button.</span></span>

4.  <span data-ttu-id="b73db-117">如果你选择指定数据库大小，最佳做法建议你输入一个介于512和 4096 MB 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="b73db-117">If you choose to specify a database size, best practices recommend that you enter a number between 512 and 4096 MB.</span></span> <span data-ttu-id="b73db-118">默认大小为 1024 MB，如果需要增加数据库大小，则可以输入的最大值为2147483647。</span><span class="sxs-lookup"><span data-stu-id="b73db-118">The default size is 1024 MB and if you need to increase the database size, the maximum value you can enter is 2,147,483,647.</span></span> <span data-ttu-id="b73db-119">如果选择 "**无大小限制**"，数据库将增长，直到达到磁盘大小限制。</span><span class="sxs-lookup"><span data-stu-id="b73db-119">If you select **No Size Limit**, the database will grow until it reaches the disk size limit.</span></span>

5.  <span data-ttu-id="b73db-120">单击**Apply** "应用 **" 或 "确定"**。</span><span class="sxs-lookup"><span data-stu-id="b73db-120">Click **Apply** or **OK**.</span></span>

**<span data-ttu-id="b73db-121">禁用数据库大小限制</span><span class="sxs-lookup"><span data-stu-id="b73db-121">To disable database size limits</span></span>**

1.  <span data-ttu-id="b73db-122">右键单击 "**范围**" 窗格中的 "应用程序虚拟化系统" 节点，然后选择 "**系统选项**"。</span><span class="sxs-lookup"><span data-stu-id="b73db-122">Right-click the Application Virtualization System node in the **Scope** pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="b73db-123">选择 "**数据库**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b73db-123">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="b73db-124">选择 "**无大小限制**" 并**保留 "所有使用情况**" 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="b73db-124">Select the **No Size Limit** and **Keep All Usage** radio buttons.</span></span>

4.  <span data-ttu-id="b73db-125">单击**Apply** "应用 **" 或 "确定"**。</span><span class="sxs-lookup"><span data-stu-id="b73db-125">Click **Apply** or **OK**.</span></span>

## <span data-ttu-id="b73db-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="b73db-126">Related topics</span></span>


[<span data-ttu-id="b73db-127">如何在 Server Management Console 中自定义 Application Virtualization System</span><span class="sxs-lookup"><span data-stu-id="b73db-127">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[<span data-ttu-id="b73db-128">如何设置或禁用使用情况报告</span><span class="sxs-lookup"><span data-stu-id="b73db-128">How to Set Up or Disable Usage Reporting</span></span>](how-to-set-up-or-disable-usage-reporting.md)

 

 





