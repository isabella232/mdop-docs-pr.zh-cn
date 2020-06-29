---
title: 如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端
description: 如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.openlocfilehash: 38e77ce6ce6c0dba7c67f6c0dfa5c9e263e07e20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798481"
---
# <span data-ttu-id="8b66b-103">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端</span><span class="sxs-lookup"><span data-stu-id="8b66b-103">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</span></span>

<span data-ttu-id="8b66b-104">**注意：** App-v 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="8b66b-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="8b66b-105">以下示例假设已安装了 App-v 4.6 SP3 客户端。</span><span class="sxs-lookup"><span data-stu-id="8b66b-105">The following assumes that the App-V 4.6 SP3 client is already installed.</span></span>

<span data-ttu-id="8b66b-106">使用以下信息在同一台计算机上安装 app-v 5.0 客户端（最好是使用最新的服务包和修补程序）和 App-v 4.6 SP3 客户端。</span><span class="sxs-lookup"><span data-stu-id="8b66b-106">Use the following information to install the App-V 5.0 client (preferably, with the latest Service Packs and hotfixes) and the App-V 4.6SP3 client on the same computer.</span></span> <span data-ttu-id="8b66b-107">有关受支持的版本、要求和其他计划信息，请参阅[规划从早期版本的 App-v 迁移](planning-for-migrating-from-a-previous-version-of-app-v.md)。</span><span class="sxs-lookup"><span data-stu-id="8b66b-107">For supported versions, requirements, and other planning information, see [Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md).</span></span>

**<span data-ttu-id="8b66b-108">在同一台计算机上部署 app-v 5.0 客户端和 App-v 4.6 客户端</span><span class="sxs-lookup"><span data-stu-id="8b66b-108">To deploy the App-V 5.0 client and App-V 4.6 client on the same computer</span></span>**

1.  <span data-ttu-id="8b66b-109">在运行 app-v 4.6 版本的客户端的计算机上安装 app-v 5.0 SP3 客户端。</span><span class="sxs-lookup"><span data-stu-id="8b66b-109">Install the App-V 5.0 SP3 client on the computer that is running the App-V 4.6 version of the client.</span></span> <span data-ttu-id="8b66b-110">为获得最佳结果，建议你将所有可用更新安装到 app-v 5.0 SP3 客户端。</span><span class="sxs-lookup"><span data-stu-id="8b66b-110">For best results, we recommend that you install all available updates to the App-V 5.0 SP3 client.</span></span>

2.  <span data-ttu-id="8b66b-111">逐步转换或重新序列化程序包。</span><span class="sxs-lookup"><span data-stu-id="8b66b-111">Convert or re-sequence the packages gradually.</span></span>

    -   <span data-ttu-id="8b66b-112">若要转换程序包，请使用 app-v 5.0 程序包转换器，并将所需的程序包转换为 App-v 5.0 （**appv**）文件格式。</span><span class="sxs-lookup"><span data-stu-id="8b66b-112">To convert the packages, use the App-V 5.0 package converter and convert the required packages to the App-V 5.0 (**.appv**) file format.</span></span>

    -   <span data-ttu-id="8b66b-113">若要对程序包进行重新排序，请考虑使用最新版本的 Sequencer 来获得最佳结果。</span><span class="sxs-lookup"><span data-stu-id="8b66b-113">To re-sequence the packages, consider using the latest version of the Sequencer for best results.</span></span>

    <span data-ttu-id="8b66b-114">有关发布程序包的详细信息，请参阅[如何使用管理控制台发布程序包](how-to-publish-a-package-by-using-the-management-console-50.md)。</span><span class="sxs-lookup"><span data-stu-id="8b66b-114">For more information about publishing packages, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md).</span></span>

3.  <span data-ttu-id="8b66b-115">将程序包部署到客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="8b66b-115">Deploy packages to the client computers.</span></span>

4.  <span data-ttu-id="8b66b-116">根据需要转换扩展点。</span><span class="sxs-lookup"><span data-stu-id="8b66b-116">Convert extension points, as needed.</span></span> <span data-ttu-id="8b66b-117">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="8b66b-117">For more information, see the following resources:</span></span>

    -   [<span data-ttu-id="8b66b-118">如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="8b66b-118">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [<span data-ttu-id="8b66b-119">如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="8b66b-119">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [<span data-ttu-id="8b66b-120">如何转换在以前版本的 App-V 中创建的程序包</span><span class="sxs-lookup"><span data-stu-id="8b66b-120">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  <span data-ttu-id="8b66b-121">测试 app-v 5.0 程序包是否成功，然后删除4.6 程序包。</span><span class="sxs-lookup"><span data-stu-id="8b66b-121">Test that your App-V 5.0 packages are successful, and then remove the 4.6 packages.</span></span> <span data-ttu-id="8b66b-122">若要检查客户端计算机的用户状态，我们建议你使用[用户体验虚拟化](https://technet.microsoft.com/library/dn458947.aspx)或其他用户环境管理工具。</span><span class="sxs-lookup"><span data-stu-id="8b66b-122">To check the user state of your client computers, we recommend that you use [User Experience Virtualization](https://technet.microsoft.com/library/dn458947.aspx) or another user environment management tool.</span></span>

    <span data-ttu-id="8b66b-123">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="8b66b-123">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="8b66b-124">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="8b66b-124">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="8b66b-125">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="8b66b-125">Got an App-V issue?</span></span>** <span data-ttu-id="8b66b-126">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="8b66b-126">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="8b66b-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="8b66b-127">Related topics</span></span>


[<span data-ttu-id="8b66b-128">计划从以前版本的 App-V 迁移</span><span class="sxs-lookup"><span data-stu-id="8b66b-128">Planning for Migrating from a Previous Version of App-V</span></span>](planning-for-migrating-from-a-previous-version-of-app-v.md)

[<span data-ttu-id="8b66b-129">部署 App-V 5.0 Sequencer 和 Client</span><span class="sxs-lookup"><span data-stu-id="8b66b-129">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

 

 





