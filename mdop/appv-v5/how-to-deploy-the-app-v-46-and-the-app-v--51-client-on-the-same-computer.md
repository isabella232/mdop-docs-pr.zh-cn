---
title: 如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端
description: 如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端
ms.assetid: 498d50c7-f13d-4fbb-8ea1-b959ade26fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 354db96223e623a7cd0416cb49ad67eb4d8f7162
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798479"
---
# <span data-ttu-id="5fa15-103">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="5fa15-103">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>

<span data-ttu-id="5fa15-104">**注意：** App-v 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="5fa15-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="5fa15-105">使用以下信息在同一台计算机上安装 Microsoft Application Virtualization （App-v）5.1 客户端（最好是使用最新的服务包和修补程序）和 app-v 4.6 S3 客户端或应用程序 V 4.6 S3 客户端。</span><span class="sxs-lookup"><span data-stu-id="5fa15-105">Use the following information to install the Microsoft Application Virtualization (App-V) 5.1 client (preferably, with the latest Service Packs and hotfixes) and the App-V 4.6SP2 client or the App-V 4.6S3 client on the same computer.</span></span> <span data-ttu-id="5fa15-106">有关受支持的版本、要求和其他计划信息，请参阅[规划从早期版本的 App-v 迁移](planning-for-migrating-from-a-previous-version-of-app-v51.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa15-106">For supported versions, requirements, and other planning information, see [Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v51.md).</span></span>

**<span data-ttu-id="5fa15-107">在同一台计算机上部署 app-v 5.1 客户端和 App-v 4.6 客户端</span><span class="sxs-lookup"><span data-stu-id="5fa15-107">To deploy the App-V 5.1 client and App-V 4.6 client on the same computer</span></span>**

1.  <span data-ttu-id="5fa15-108">在运行 app-v 4.6 的计算机上安装以下版本的 App-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="5fa15-108">Install the following version of the App-V client on the computer that is running App-V 4.6.</span></span>

    -   [<span data-ttu-id="5fa15-109">Microsoft Application Virtualization 4.6 Service Pack 3</span><span class="sxs-lookup"><span data-stu-id="5fa15-109">Microsoft Application Virtualization 4.6 Service Pack 3</span></span>](https://www.microsoft.com/download/details.aspx?id=41187)

2.  <span data-ttu-id="5fa15-110">在运行应用的 app-v 4.6 SP3 版本的计算机上安装 App-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="5fa15-110">Install the App-V 5.1 client on the computer that is running the App-V 4.6 SP3 version of the client.</span></span> <span data-ttu-id="5fa15-111">为获得最佳结果，建议你将所有可用更新安装到 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="5fa15-111">For best results, we recommend that you install all available updates to the App-V 5.1 client.</span></span>

3.  <span data-ttu-id="5fa15-112">逐步转换或重新序列化程序包。</span><span class="sxs-lookup"><span data-stu-id="5fa15-112">Convert or re-sequence the packages gradually.</span></span>

    -   <span data-ttu-id="5fa15-113">若要转换程序包，请使用 app-v 5.1 程序包转换器，并将所需的程序包转换为 App-v 5.1 （**appv**）文件格式。</span><span class="sxs-lookup"><span data-stu-id="5fa15-113">To convert the packages, use the App-V 5.1 package converter and convert the required packages to the App-V 5.1 (**.appv**) file format.</span></span>

    -   <span data-ttu-id="5fa15-114">若要对程序包进行重新排序，请考虑使用最新版本的 Sequencer 来获得最佳结果。</span><span class="sxs-lookup"><span data-stu-id="5fa15-114">To re-sequence the packages, consider using the latest version of the Sequencer for best results.</span></span>

    <span data-ttu-id="5fa15-115">有关发布程序包的详细信息，请参阅[如何使用管理控制台发布程序包](how-to-publish-a-package-by-using-the-management-console-51.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa15-115">For more information about publishing packages, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md).</span></span>

4.  <span data-ttu-id="5fa15-116">将程序包部署到客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="5fa15-116">Deploy packages to the client computers.</span></span>

5.  <span data-ttu-id="5fa15-117">根据需要转换扩展点。</span><span class="sxs-lookup"><span data-stu-id="5fa15-117">Convert extension points, as needed.</span></span> <span data-ttu-id="5fa15-118">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="5fa15-118">For more information, see the following resources:</span></span>

    -   [<span data-ttu-id="5fa15-119">如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="5fa15-119">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

    -   [<span data-ttu-id="5fa15-120">如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="5fa15-120">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

    -   [<span data-ttu-id="5fa15-121">如何转换在以前版本的 App-V 中创建的程序包</span><span class="sxs-lookup"><span data-stu-id="5fa15-121">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

6.  <span data-ttu-id="5fa15-122">测试 app-v 5.1 程序包是否成功，然后删除4.6 程序包。</span><span class="sxs-lookup"><span data-stu-id="5fa15-122">Test that your App-V 5.1 packages are successful, and then remove the 4.6 packages.</span></span> <span data-ttu-id="5fa15-123">若要检查客户端计算机的用户状态，我们建议你使用[用户体验虚拟化](https://technet.microsoft.com/library/dn458947.aspx)或其他用户环境管理工具。</span><span class="sxs-lookup"><span data-stu-id="5fa15-123">To check the user state of your client computers, we recommend that you use [User Experience Virtualization](https://technet.microsoft.com/library/dn458947.aspx) or another user environment management tool.</span></span>

    <span data-ttu-id="5fa15-124">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="5fa15-124">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="5fa15-125">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="5fa15-125">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="5fa15-126">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="5fa15-126">Got an App-V issue?</span></span>** <span data-ttu-id="5fa15-127">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="5fa15-127">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="5fa15-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="5fa15-128">Related topics</span></span>


[<span data-ttu-id="5fa15-129">计划从以前版本的 App-V 迁移</span><span class="sxs-lookup"><span data-stu-id="5fa15-129">Planning for Migrating from a Previous Version of App-V</span></span>](planning-for-migrating-from-a-previous-version-of-app-v51.md)

[<span data-ttu-id="5fa15-130">部署 App-V 5.1 Sequencer 和 Client</span><span class="sxs-lookup"><span data-stu-id="5fa15-130">Deploying the App-V 5.1 Sequencer and Client</span></span>](deploying-the-app-v-51-sequencer-and-client.md)

 

 





