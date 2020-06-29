---
title: 如何将 Client 配置为从发布服务器接收程序包和连接组更新
description: 如何将 Client 配置为从发布服务器接收程序包和连接组更新
author: dansimp
ms.assetid: f5dfd96d-4b63-468c-8d93-9dfdf47c28fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e9df1f8b324430449d8d1dd3624d9f1157968a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798533"
---
# <span data-ttu-id="ad195-103">如何将 Client 配置为从发布服务器接收程序包和连接组更新</span><span class="sxs-lookup"><span data-stu-id="ad195-103">How to Configure the Client to Receive Package and Connection Groups Updates From the Publishing Server</span></span>


<span data-ttu-id="ad195-104">使用 App-v 5.0 发布服务器部署程序包和连接组非常有用，因为它提供了单点管理和高可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="ad195-104">Deploying packages and connection groups using the App-V 5.0 publishing server is helpful because it offers single-point management and high scalability.</span></span>

<span data-ttu-id="ad195-105">使用以下步骤将 App-v 5.0 客户端配置为接收来自发布服务器的更新。</span><span class="sxs-lookup"><span data-stu-id="ad195-105">Use the following steps to configure the App-V 5.0 client to receive updates from the publishing server.</span></span>

<span data-ttu-id="ad195-106">**注意** 对于以下过程，管理服务器安装在名为**MyMgmtSrv**的计算机上，并且发布服务器安装在名为**MyPubSrv**的计算机上。</span><span class="sxs-lookup"><span data-stu-id="ad195-106">**Note** For the following procedures the management server was installed on a computer named **MyMgmtSrv**, and the publishing server was installed on a computer named **MyPubSrv**.</span></span>

 

**<span data-ttu-id="ad195-107">将 App-v 5.0 客户端配置为接收来自发布服务器的更新</span><span class="sxs-lookup"><span data-stu-id="ad195-107">To configure the App-V 5.0 client to receive updates from the publishing server</span></span>**

1.  <span data-ttu-id="ad195-108">部署 app-v 5.0 管理和发布服务器，并添加所需的程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="ad195-108">Deploy the App-V 5.0 management and publishing servers, and add the required packages and connection groups.</span></span> <span data-ttu-id="ad195-109">有关添加程序包和连接组的详细信息，请参阅[如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)，以及[如何创建连接组](how-to-create-a-connection-group.md)。</span><span class="sxs-lookup"><span data-stu-id="ad195-109">For more information about adding packages and connection groups, see [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md) and [How to Create a Connection Group](how-to-create-a-connection-group.md).</span></span>

2.  <span data-ttu-id="ad195-110">若要打开管理控制台，请单击以下链接，打开浏览器并键入以下内容： http://MyMgmtSrv/AppvManagement/Console.html 在 web 浏览器中，然后导入、发布和 entitle 特定用户组所需的所有程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="ad195-110">To open the management console click the following link, open a browser and type the following: http://MyMgmtSrv/AppvManagement/Console.html in a web browser, and import, publish, and entitle all the packages and connection groups which will be necessary for a particular set of users.</span></span>

3.  <span data-ttu-id="ad195-111">在运行 App-v 5.0 客户端的计算机上，打开提升的 PowerShell 命令提示符，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad195-111">On the computer running the App-V 5.0 client, open an elevated PowerShell command prompt, run the following command:</span></span>

    **<span data-ttu-id="ad195-112">Add-AppvPublishingServer-Name ABC-URL http://MyPubSrv/AppvPublishing</span><span class="sxs-lookup"><span data-stu-id="ad195-112">Add-AppvPublishingServer -Name ABC -URL http:// MyPubSrv/AppvPublishing</span></span>**

    <span data-ttu-id="ad195-113">此命令将配置指定的发布服务器。</span><span class="sxs-lookup"><span data-stu-id="ad195-113">This command will configure the specified publishing server.</span></span> <span data-ttu-id="ad195-114">您应看到类似于以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="ad195-114">You should see output similar to the following:</span></span>

    <span data-ttu-id="ad195-115">Id：1</span><span class="sxs-lookup"><span data-stu-id="ad195-115">Id : 1</span></span>

    <span data-ttu-id="ad195-116">SetByGroupPolicy： False</span><span class="sxs-lookup"><span data-stu-id="ad195-116">SetByGroupPolicy : False</span></span>

    <span data-ttu-id="ad195-117">名称： ABC</span><span class="sxs-lookup"><span data-stu-id="ad195-117">Name : ABC</span></span>

    <span data-ttu-id="ad195-118">URL： http://MyPubSrv/AppvPublishing</span><span class="sxs-lookup"><span data-stu-id="ad195-118">URL : http:// MyPubSrv/AppvPublishing</span></span>

    <span data-ttu-id="ad195-119">GlobalRefreshEnabled： False</span><span class="sxs-lookup"><span data-stu-id="ad195-119">GlobalRefreshEnabled : False</span></span>

    <span data-ttu-id="ad195-120">GlobalRefreshOnLogon： False</span><span class="sxs-lookup"><span data-stu-id="ad195-120">GlobalRefreshOnLogon : False</span></span>

    <span data-ttu-id="ad195-121">GlobalRefreshInterval：0</span><span class="sxs-lookup"><span data-stu-id="ad195-121">GlobalRefreshInterval : 0</span></span>

    <span data-ttu-id="ad195-122">GlobalRefreshIntervalUnit： Day</span><span class="sxs-lookup"><span data-stu-id="ad195-122">GlobalRefreshIntervalUnit : Day</span></span>

    <span data-ttu-id="ad195-123">UserRefreshEnabled： True</span><span class="sxs-lookup"><span data-stu-id="ad195-123">UserRefreshEnabled : True</span></span>

    <span data-ttu-id="ad195-124">UserRefreshOnLogon： True</span><span class="sxs-lookup"><span data-stu-id="ad195-124">UserRefreshOnLogon : True</span></span>

    <span data-ttu-id="ad195-125">UserRefreshInterval：0</span><span class="sxs-lookup"><span data-stu-id="ad195-125">UserRefreshInterval : 0</span></span>

    <span data-ttu-id="ad195-126">UserRefreshIntervalUnit： Day</span><span class="sxs-lookup"><span data-stu-id="ad195-126">UserRefreshIntervalUnit : Day</span></span>

    <span data-ttu-id="ad195-127">返回的 Id-在本例中为1</span><span class="sxs-lookup"><span data-stu-id="ad195-127">The returned Id – in this case 1</span></span>

4.  <span data-ttu-id="ad195-128">在运行 App-v 5.0 客户端的计算机上，打开一个 PowerShell 命令提示符，然后键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad195-128">On the computer running the App-V 5.0 client, open a PowerShell command prompt, and type the following command:</span></span>

    **<span data-ttu-id="ad195-129">Sync-AppvPublishingServer-ServerId 1</span><span class="sxs-lookup"><span data-stu-id="ad195-129">Sync-AppvPublishingServer -ServerId 1</span></span>**

    <span data-ttu-id="ad195-130">该命令将根据管理服务器上配置的程序包和连接组的权利，为需要为此特定客户添加或删除的程序包和连接组查询发布服务器。</span><span class="sxs-lookup"><span data-stu-id="ad195-130">The command will query the publishing server for the packages and connection groups that need to be added or removed for this particular client based on the entitlements for the packages and connection groups as configured on the management server.</span></span>

    <span data-ttu-id="ad195-131">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="ad195-131">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ad195-132">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="ad195-132">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ad195-133">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="ad195-133">Got an App-V issue?</span></span>** <span data-ttu-id="ad195-134">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="ad195-134">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ad195-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="ad195-135">Related topics</span></span>


[<span data-ttu-id="ad195-136">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="ad195-136">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





