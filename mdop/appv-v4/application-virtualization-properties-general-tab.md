---
title: 应用程序虚拟化属性 "常规" 选项卡
description: 应用程序虚拟化属性 "常规" 选项卡
author: dansimp
ms.assetid: be7449d9-171a-4a11-9382-83b7008ccbdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ee00bfc7f70ee7b17da42aad61356540a7a0be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802316"
---
# <span data-ttu-id="554be-103">Application Virtualization 属性：“常规”选项卡</span><span class="sxs-lookup"><span data-stu-id="554be-103">Application Virtualization Properties: General Tab</span></span>


<span data-ttu-id="554be-104">使用 "**应用程序虚拟化属性**" 对话框的 "**常规**" 选项卡修改日志设置和数据位置。</span><span class="sxs-lookup"><span data-stu-id="554be-104">Use the **General** tab of the **Application Virtualization Properties** dialog box to modify log settings and data locations.</span></span>

<span data-ttu-id="554be-105">此选项卡包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="554be-105">This tab contains the following elements.</span></span>

<a href="" id="log-level"></a>**<span data-ttu-id="554be-106">日志级别</span><span class="sxs-lookup"><span data-stu-id="554be-106">Log Level</span></span>**  
<span data-ttu-id="554be-107">从下拉列表中选择级别。</span><span class="sxs-lookup"><span data-stu-id="554be-107">Select the level from the drop-down list.</span></span> <span data-ttu-id="554be-108">默认级别为 "**信息**"。</span><span class="sxs-lookup"><span data-stu-id="554be-108">The default level is **Information**.</span></span>

<a href="" id="reset-log"></a>**<span data-ttu-id="554be-109">重置日志</span><span class="sxs-lookup"><span data-stu-id="554be-109">Reset Log</span></span>**  
<span data-ttu-id="554be-110">单击此按钮备份当前日志文件，并立即开始新的日志文件。</span><span class="sxs-lookup"><span data-stu-id="554be-110">Click this button to back up the current log file and immediately start a new log file.</span></span>

<a href="" id="location"></a>**<span data-ttu-id="554be-111">位置</span><span class="sxs-lookup"><span data-stu-id="554be-111">Location</span></span>**  
<span data-ttu-id="554be-112">输入或浏览到要在其中保存日志文件 sftlog.txt 的位置。</span><span class="sxs-lookup"><span data-stu-id="554be-112">Enter or browse to the location where you want to save the log file sftlog.txt.</span></span> <span data-ttu-id="554be-113">默认位置如下所示：</span><span class="sxs-lookup"><span data-stu-id="554be-113">The default locations are as follows:</span></span>

-   <span data-ttu-id="554be-114">对于 WindowsXP、Windows Server2003-*C:\\Documents 和 Settings\\All Users\\Application Data\\Microsoft\\Application 虚拟化客户端*</span><span class="sxs-lookup"><span data-stu-id="554be-114">For WindowsXP, Windows Server2003—*C:\\Documents and Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization Client*</span></span>

-   <span data-ttu-id="554be-115">对于 Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application 虚拟化客户端*</span><span class="sxs-lookup"><span data-stu-id="554be-115">For Windows Vista, Windows 7, Windows Server2008—*C:\\ProgramData\\Microsoft\\Application Virtualization Client*</span></span>

<a href="" id="system-log-level"></a>**<span data-ttu-id="554be-116">系统日志级别</span><span class="sxs-lookup"><span data-stu-id="554be-116">System Log Level</span></span>**  
<span data-ttu-id="554be-117">从下拉列表中选择级别。</span><span class="sxs-lookup"><span data-stu-id="554be-117">Select the level from the drop-down list.</span></span> <span data-ttu-id="554be-118">默认级别为 "**警告**"。</span><span class="sxs-lookup"><span data-stu-id="554be-118">The default level is **Warning**.</span></span>

<span data-ttu-id="554be-119">**注意** "**系统日志级别**" 设置控制发送到系统事件日志的消息级别。</span><span class="sxs-lookup"><span data-stu-id="554be-119">**Note** The **System Log Level** setting controls the level of messages sent to the system event log.</span></span> <span data-ttu-id="554be-120">记录的消息与记录到客户端事件日志的消息相同，但它们存储在不具有客户端事件日志的空间限制的其他位置。</span><span class="sxs-lookup"><span data-stu-id="554be-120">The logged messages are identical to the messages that get logged to the client event log, but they are stored in a different location that does not have the space limitations of the client event log.</span></span> <span data-ttu-id="554be-121">由于系统事件日志没有空间限制，因此非常适合在需要详细日志记录的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="554be-121">Because the system event log does not have space limitations, it is ideally suited for situations where verbose logging is necessary.</span></span>

 

<a href="" id="global-data-directory"></a>**<span data-ttu-id="554be-122">全局数据目录</span><span class="sxs-lookup"><span data-stu-id="554be-122">Global Data Directory</span></span>**  
<span data-ttu-id="554be-123">输入或浏览到日志文件目录的位置。</span><span class="sxs-lookup"><span data-stu-id="554be-123">Enter or browse to the location of the directory of the log file.</span></span> <span data-ttu-id="554be-124">默认位置如下所示：</span><span class="sxs-lookup"><span data-stu-id="554be-124">The default locations are as follows:</span></span>

-   <span data-ttu-id="554be-125">对于 WindowsXP、Windows Server2003-*C:\\Documents 和 Settings\\All Users\\Application Data\\Microsoft\\Application 虚拟化客户端*</span><span class="sxs-lookup"><span data-stu-id="554be-125">For WindowsXP, Windows Server2003—*C:\\Documents and Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization Client*</span></span>

-   <span data-ttu-id="554be-126">对于 Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application 虚拟化客户端*</span><span class="sxs-lookup"><span data-stu-id="554be-126">For Windows Vista, Windows 7, Windows Server2008—*C:\\ProgramData\\Microsoft\\Application Virtualization Client*</span></span>

<a href="" id="user-data-directory"></a>**<span data-ttu-id="554be-127">用户数据目录</span><span class="sxs-lookup"><span data-stu-id="554be-127">User Data Directory</span></span>**  
<span data-ttu-id="554be-128">输入或浏览到存储特定于用户的数据的目录的位置。</span><span class="sxs-lookup"><span data-stu-id="554be-128">Enter or browse to the location of the directory where user-specific data is stored.</span></span> <span data-ttu-id="554be-129">默认值为% APPDATA%。</span><span class="sxs-lookup"><span data-stu-id="554be-129">The default is %APPDATA%.</span></span> <span data-ttu-id="554be-130">此路径必须是客户端计算机上的有效环境变量。</span><span class="sxs-lookup"><span data-stu-id="554be-130">This path must be a valid environment variable on the client computer.</span></span>

## <span data-ttu-id="554be-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="554be-131">Related topics</span></span>


[<span data-ttu-id="554be-132">Client Management Console：Application Virtualization 属性</span><span class="sxs-lookup"><span data-stu-id="554be-132">Client Management Console: Application Virtualization Properties</span></span>](client-management-console-application-virtualization-properties.md)

 

 





