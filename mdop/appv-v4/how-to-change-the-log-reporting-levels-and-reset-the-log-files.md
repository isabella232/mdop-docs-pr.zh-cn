---
title: 如何更改日志报告级别和重置日志文件
description: 如何更改日志报告级别和重置日志文件
author: dansimp
ms.assetid: 9561d6fb-b35c-491b-a355-000064583194
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7307dee0030d9c03a8107d9d0ceef2086a94df07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801660"
---
# <span data-ttu-id="0a2b7-103">如何更改日志报告级别和重置日志文件</span><span class="sxs-lookup"><span data-stu-id="0a2b7-103">How to Change the Log Reporting Levels and Reset the Log Files</span></span>


<span data-ttu-id="0a2b7-104">你可以使用以下过程在应用程序虚拟化管理控制台中更改**应用程序虚拟化**节点中的日志报告级别。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-104">You can use the following procedure to change the log reporting level from the **Application Virtualization** node in the Application Virtualization Management Console.</span></span> <span data-ttu-id="0a2b7-105">当日志文件达到最大大小（默认值为 256 MB）时，将在下次写入日志时会强制重置。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-105">When the log file reaches the maximum size (default is 256 MB), a reset is forced when the next write to the log occurs.</span></span> <span data-ttu-id="0a2b7-106">重置导致创建新的日志文件，并且旧文件被重命名为备份。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-106">A reset causes a new log file to be created, and the old file is renamed as a backup.</span></span>

**<span data-ttu-id="0a2b7-107">更改日志报告级别</span><span class="sxs-lookup"><span data-stu-id="0a2b7-107">To change the log reporting level</span></span>**

1.  <span data-ttu-id="0a2b7-108">右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-108">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="0a2b7-109">在 "**属性**" 对话框中的 "**常规**" 选项卡上，从 "**日志级别**" 下拉列表中选择所需的日志级别。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-109">On the **General** tab in the **Properties** dialog box, from the **Log Level** drop-down list, select the desired log level.</span></span>

    <span data-ttu-id="0a2b7-110">**注意** 如果选择 "**详细**" 作为日志记录级别，日志文件将很快变得很快。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-110">**Note** If you choose **Verbose** as the logging level, the log files will grow large very quickly.</span></span> <span data-ttu-id="0a2b7-111">这可能会阻止客户端性能，因此最佳做法是仅使用此日志级别来诊断特定问题。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-111">This might inhibit client performance, so best practice is to use this log level only for diagnosing specific problems.</span></span>

     

3.  <span data-ttu-id="0a2b7-112">在 "**属性**" 对话框中的 "**常规**" 选项卡上，从 "**系统日志级别**" 下拉列表中选择所需的日志级别。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-112">On the **General** tab in the **Properties** dialog box, from the **System Log Level** drop-down list, select the desired log level.</span></span>

    <span data-ttu-id="0a2b7-113">**注意** "**系统日志级别**" 设置控制发送到系统事件日志的消息级别。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-113">**Note** The **System Log Level** setting controls the level of messages sent to the system event log.</span></span> <span data-ttu-id="0a2b7-114">记录的消息与记录到客户端事件日志的消息相同，但它们存储在其他位置。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-114">The logged messages are identical to the messages that get logged to the client event log, but they are stored in a different location.</span></span>

     

4.  <span data-ttu-id="0a2b7-115">单击 **"确定" 或 "** **应用**" 更改设置。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-115">Click **OK** or **Apply** to change the setting.</span></span>

**<span data-ttu-id="0a2b7-116">重置日志文件</span><span class="sxs-lookup"><span data-stu-id="0a2b7-116">To reset the log file</span></span>**

1.  <span data-ttu-id="0a2b7-117">右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-117">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="0a2b7-118">在 "**属性**" 对话框中的 "**常规**" 选项卡上，单击 "**重置日志**" 以备份当前日志文件，并立即启动新的日志文件。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-118">On the **General** tab in the **Properties** dialog box, click **Reset Log** to back up the current log file and immediately start a new log file.</span></span> <span data-ttu-id="0a2b7-119">备份日志文件存储在同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-119">The backup log files are stored in the same folder.</span></span>

3.  <span data-ttu-id="0a2b7-120">单击 **"确定" 或 "** **应用**" 更改设置。</span><span class="sxs-lookup"><span data-stu-id="0a2b7-120">Click **OK** or **Apply** to change the setting.</span></span>

## <span data-ttu-id="0a2b7-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="0a2b7-121">Related topics</span></span>


[<span data-ttu-id="0a2b7-122">如何在 Application Virtualization Client Management Console 中配置客户端</span><span class="sxs-lookup"><span data-stu-id="0a2b7-122">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

[<span data-ttu-id="0a2b7-123">Application Virtualization Client 中的用户访问权限</span><span class="sxs-lookup"><span data-stu-id="0a2b7-123">User Access Permissions in Application Virtualization Client</span></span>](user-access-permissions-in-application-virtualization-client.md)

 

 





