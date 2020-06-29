---
title: 如何使用管理控制台注册和注销发布服务器
description: 如何使用管理控制台注册和注销发布服务器
author: dansimp
ms.assetid: c24f3b43-4888-41a9-9a39-973657f2b917
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5241af748029b7976c49b6474e5ef7c050699dd7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798377"
---
# <span data-ttu-id="48ae9-103">如何使用管理控制台注册和注销发布服务器</span><span class="sxs-lookup"><span data-stu-id="48ae9-103">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>


<span data-ttu-id="48ae9-104">你可以注册和注销将与 App-v 5.0 管理服务器同步的发布服务器。</span><span class="sxs-lookup"><span data-stu-id="48ae9-104">You can register and unregister publishing servers that will synchronize with the App-V 5.0 management server.</span></span> <span data-ttu-id="48ae9-105">您还可以查看发布服务器与管理服务器同步信息所进行的最后一次尝试。</span><span class="sxs-lookup"><span data-stu-id="48ae9-105">You can also see the last attempt that the publishing server made to synchronize the information with the management server.</span></span>

<span data-ttu-id="48ae9-106">使用以下过程注册或注销发布服务器。</span><span class="sxs-lookup"><span data-stu-id="48ae9-106">Use the following procedure to register or unregister a publishing server.</span></span>

**<span data-ttu-id="48ae9-107">使用管理控制台注册发布服务器</span><span class="sxs-lookup"><span data-stu-id="48ae9-107">To register a publishing server using the Management Console</span></span>**

1.  <span data-ttu-id="48ae9-108">连接到管理控制台，然后选择 "**服务器**"。</span><span class="sxs-lookup"><span data-stu-id="48ae9-108">Connect to the Management Console and select **Servers**.</span></span> <span data-ttu-id="48ae9-109">有关如何连接到管理控制台的详细信息，请参阅[如何连接到管理控制台](how-to-connect-to-the-management-console-beta.md)。</span><span class="sxs-lookup"><span data-stu-id="48ae9-109">For more information about how to connect to the Management Console, see [How to Connect to the Management Console](how-to-connect-to-the-management-console-beta.md).</span></span>

2.  <span data-ttu-id="48ae9-110">将显示已与管理服务器同步的发布服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="48ae9-110">A list of publishing servers that already synchronize with the management server is displayed.</span></span> <span data-ttu-id="48ae9-111">单击 "注册新服务器" 以注册新服务器。</span><span class="sxs-lookup"><span data-stu-id="48ae9-111">Click Register New Server to register a new server.</span></span>

3.  <span data-ttu-id="48ae9-112">键入 "**服务器名称**" 行上已加入域的计算机名称，以指定服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="48ae9-112">Type a computer name of a domain joined computer on the **Server Name** line, to specify a name for the server.</span></span> <span data-ttu-id="48ae9-113">您还应包括一个域名，例如**MyDomain\\TestServer**。</span><span class="sxs-lookup"><span data-stu-id="48ae9-113">You should also include a domain name, for example, **MyDomain\\TestServer**.</span></span> <span data-ttu-id="48ae9-114">单击 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="48ae9-114">Click **Check**.</span></span>

4.  <span data-ttu-id="48ae9-115">选择计算机，然后单击 "**添加**" 以将计算机添加到服务器列表。</span><span class="sxs-lookup"><span data-stu-id="48ae9-115">Select the computer and click **Add** to add the computer to the list of servers.</span></span> <span data-ttu-id="48ae9-116">新服务器将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="48ae9-116">The new server will be displayed in the list.</span></span>

**<span data-ttu-id="48ae9-117">使用管理控制台注销发布服务器</span><span class="sxs-lookup"><span data-stu-id="48ae9-117">To unregister a publishing server using the Management Console</span></span>**

1.  <span data-ttu-id="48ae9-118">连接到管理控制台，然后选择 "**服务器**"。</span><span class="sxs-lookup"><span data-stu-id="48ae9-118">Connect to the Management Console and select **Servers**.</span></span> <span data-ttu-id="48ae9-119">有关如何连接到管理控制台的详细信息，请参阅[如何连接到管理控制台](how-to-connect-to-the-management-console-beta.md)。</span><span class="sxs-lookup"><span data-stu-id="48ae9-119">For more information about how to connect to the Management Console, see [How to Connect to the Management Console](how-to-connect-to-the-management-console-beta.md).</span></span>

2.  <span data-ttu-id="48ae9-120">将显示与管理服务器同步的发布服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="48ae9-120">A list of publishing servers that synchronize with the management server is displayed.</span></span>

3.  <span data-ttu-id="48ae9-121">若要注销服务器，请右键单击计算机名称，然后选择计算机名称，然后选择 "**注销服务器**"。</span><span class="sxs-lookup"><span data-stu-id="48ae9-121">To unregister the server, right-click the computer name and select the computer name and select **unregister server**.</span></span>

    <span data-ttu-id="48ae9-122">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="48ae9-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="48ae9-123">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="48ae9-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="48ae9-124">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="48ae9-124">Got an App-V issue?</span></span>** <span data-ttu-id="48ae9-125">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="48ae9-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="48ae9-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="48ae9-126">Related topics</span></span>


[<span data-ttu-id="48ae9-127">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="48ae9-127">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





