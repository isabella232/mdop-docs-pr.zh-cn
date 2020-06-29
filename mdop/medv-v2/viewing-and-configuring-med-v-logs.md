---
title: 查看和配置 MED-V 日志
description: 查看和配置 MED-V 日志
author: dansimp
ms.assetid: a15537ce-981d-4f55-9c3c-e7fbf94b8fe5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7984cec072827136db9ea52a535c0ea44c6bc2c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803426"
---
# <span data-ttu-id="a7f0d-103">查看和配置 MED-V 日志</span><span class="sxs-lookup"><span data-stu-id="a7f0d-103">Viewing and Configuring MED-V Logs</span></span>


<span data-ttu-id="a7f0d-104">当您解决 MED-V 问题和问题时，您可能会发现访问 MED-V 事件日志有帮助或有必要。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-104">When you are troubleshooting MED-V issues and problems, you may find it helpful or necessary to access the MED-V event logs.</span></span> <span data-ttu-id="a7f0d-105">你可以使用 MED-V 管理工具包打开主计算机和来宾虚拟机的事件查看器。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-105">You can open Event Viewer for the host computer and the guest virtual machine by using the MED-V Administration Toolkit.</span></span> <span data-ttu-id="a7f0d-106">你还可以使用 MED-V 管理工具包设置 MED-V 事件日志报告 MED-V 事件的日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-106">You can also use the MED-V Administration Toolkit to set the logging level at which the MED-V event logs report MED-V events.</span></span>

<span data-ttu-id="a7f0d-107">有关如何打开 MED-V 管理工具包的信息，请参阅[使用管理工具包对 Med-v 进行故障排除](troubleshooting-med-v-by-using-the-administration-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-107">For information about how to open the MED-V Administration Toolkit, see [Troubleshooting MED-V by Using the Administration Toolkit](troubleshooting-med-v-by-using-the-administration-toolkit.md).</span></span>

## <span data-ttu-id="a7f0d-108">查看 MED-V 事件日志</span><span class="sxs-lookup"><span data-stu-id="a7f0d-108">Viewing MED-V Event Logs</span></span>


<span data-ttu-id="a7f0d-109">在 " **Med-v 管理工具包**" 窗口中，单击 "**主机事件**" 以打开主机的事件查看器。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-109">On the **MED-V Administration Toolkit** window, click **Host Events** to open the event viewer for the host computer.</span></span> <span data-ttu-id="a7f0d-110">或者，单击 "**来宾事件**" 以打开来宾虚拟机的事件查看器。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-110">Or, click **Guest Events** to open Event Viewer for the guest virtual machine.</span></span>

<span data-ttu-id="a7f0d-111">"事件查看器" 打开并显示相应的事件日志，可用于对部署或管理 MED-V 时可能遇到的问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-111">Event Viewer opens and displays the corresponding event logs that you can use to troubleshoot the issues that you might encounter when you deploy or manage MED-V.</span></span> <span data-ttu-id="a7f0d-112">默认情况下，仅显示错误和警告。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-112">By default, only errors and warnings are displayed.</span></span> <span data-ttu-id="a7f0d-113">有关特定事件 Id 和消息的详细信息，请参阅[Med-v 事件日志消息](med-v-event-log-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-113">For more information about specific event IDs and messages, see [MED-V Event Log Messages](med-v-event-log-messages.md).</span></span>

<span data-ttu-id="a7f0d-114">**注意** 最终用户在具有管理权限的情况中，只能将事件日志文件保存在来宾中。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-114">**Note** End users can only save event log files in the guest if they have administrative permissions.</span></span>

 

### <span data-ttu-id="a7f0d-115">在主计算机中手动打开事件查看器</span><span class="sxs-lookup"><span data-stu-id="a7f0d-115">To manually open the Event Viewer in the host computer</span></span>

1.  <span data-ttu-id="a7f0d-116">单击 "**开始**"，单击 "**控制面板**"，然后单击 "**管理工具**"。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-116">Click **Start**, click **Control Panel**, and then click **Administrative Tools**.</span></span>

2.  <span data-ttu-id="a7f0d-117">双击 "**事件查看器**"，然后单击 "**应用程序和服务日志**"。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-117">Double-click **Event Viewer**, and then click **Applications and Services Logs**.</span></span>

3.  <span data-ttu-id="a7f0d-118">双击 " **MEDV**"。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-118">Double-click **MEDV**.</span></span>

## <span data-ttu-id="a7f0d-119">配置 MED-V 事件日志</span><span class="sxs-lookup"><span data-stu-id="a7f0d-119">Configuring MED-V Event Logs</span></span>


<span data-ttu-id="a7f0d-120">你可以通过选择 MED-V 管理工具包上的相应选项按钮来指定 MED-V 事件日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-120">You can specify the MED-V event logging level by selecting the corresponding option button on the MED-V Administration Toolkit.</span></span> <span data-ttu-id="a7f0d-121">你可以决定事件日志是否仅包括错误、错误和警告，或者错误、警告和提示消息。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-121">You can decide whether event logging includes errors only, errors and warnings, or errors, warnings and informational messages.</span></span> <span data-ttu-id="a7f0d-122">为主计算机和来宾虚拟机设置指定的事件日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-122">The event logging level specified is set for both the host computer and the guest virtual machine.</span></span>

<span data-ttu-id="a7f0d-123">你还可以通过编辑 EventLogLevel 注册表值来指定事件日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-123">You can also specify the event logging level by editing the EventLogLevel registry value.</span></span> <span data-ttu-id="a7f0d-124">有关详细信息，请参阅[管理 Med-v 工作区配置设置](managing-med-v-workspace-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-124">For more information, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).</span></span>

<span data-ttu-id="a7f0d-125">**注意** 在 " **Med-v 管理工具包**" 窗口中指定的级别适用于未来的 med-v 事件日志记录。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-125">**Note** The level you specify on the **MED-V Administration Toolkit** window applies to future MED-V event logging.</span></span> <span data-ttu-id="a7f0d-126">如果将级别设置为捕获所有错误、警告和信息性消息，则会删除事件日志更快地填充和较旧的事件。</span><span class="sxs-lookup"><span data-stu-id="a7f0d-126">If you set the level to capture all errors, warnings, and informational messages, then the event logs fill more quickly and older events are removed.</span></span>

 

## <span data-ttu-id="a7f0d-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="a7f0d-127">Related topics</span></span>


[<span data-ttu-id="a7f0d-128">重启和重置 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a7f0d-128">Restarting and Resetting a MED-V Workspace</span></span>](restarting-and-resetting-a-med-v-workspace.md)

[<span data-ttu-id="a7f0d-129">查看 MED-V 工作区配置</span><span class="sxs-lookup"><span data-stu-id="a7f0d-129">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)

 

 





