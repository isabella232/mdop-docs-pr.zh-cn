---
title: 如何在 Server Management Console 中管理应用程序许可证
description: 如何在 Server Management Console 中管理应用程序许可证
author: dansimp
ms.assetid: 48503b04-0de7-48de-98ee-4623a712a341
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ca9ab54c8b4cee06e0b17d8b5dee3d3ca7ce69c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801331"
---
# <span data-ttu-id="c4013-103">如何在 Server Management Console 中管理应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="c4013-103">How to Manage Application Licenses in the Server Management Console</span></span>


<span data-ttu-id="c4013-104">应用程序虚拟化服务器管理控制台是用于管理应用程序虚拟化平台的界面。</span><span class="sxs-lookup"><span data-stu-id="c4013-104">The Application Virtualization Server Management Console is the interface you use to manage the Application Virtualization platform.</span></span> <span data-ttu-id="c4013-105">从该应用程序中，你可以添加、删除、配置和控制应用程序许可证组。</span><span class="sxs-lookup"><span data-stu-id="c4013-105">From it, you can add, remove, configure, and control application license groups.</span></span>

<span data-ttu-id="c4013-106">**重要提示** 如果将 app-v client Application Source Root （ASR）设置配置为使用除管理服务器之外的任何流源（例如，流式服务器、IIS 服务器或文件服务器），则管理服务器无法强制实施其授权策略。</span><span class="sxs-lookup"><span data-stu-id="c4013-106">**Important** If the App-V client Application Source Root (ASR) setting is configured to use any type of streaming source other than the Management Server, for example a Streaming Server, an IIS server, or a File server, then the Management Server is unable to enforce its licensing policy.</span></span>

 

## <span data-ttu-id="c4013-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c4013-107">In This Section</span></span>


<a href="" id="how-to-create-an-application-license-group"></a>[<span data-ttu-id="c4013-108">如何创建应用程序许可证组</span><span class="sxs-lookup"><span data-stu-id="c4013-108">How to Create an Application License Group</span></span>](how-to-create-an-application-license-group.md)  
<span data-ttu-id="c4013-109">提供在许可证组中创建新应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="c4013-109">Provides a procedure for creating a new application in a license group.</span></span>

<a href="" id="how-to-associate-an-application-with-a-license-group"></a>[<span data-ttu-id="c4013-110">如何将应用程序与许可证组关联</span><span class="sxs-lookup"><span data-stu-id="c4013-110">How to Associate an Application with a License Group</span></span>](how-to-associate-an-application-with-a-license-group.md)  
<span data-ttu-id="c4013-111">提供将应用程序添加到许可证组的过程。</span><span class="sxs-lookup"><span data-stu-id="c4013-111">Provides a procedure for adding an application to a license group.</span></span>

<a href="" id="how-to-remove-an-application-from-a-license-group"></a>[<span data-ttu-id="c4013-112">如何从许可证组中删除应用程序</span><span class="sxs-lookup"><span data-stu-id="c4013-112">How to Remove an Application from a License Group</span></span>](how-to-remove-an-application-from-a-license-group.md)  
<span data-ttu-id="c4013-113">提供从许可证组中删除应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="c4013-113">Provides a procedure for removing an application from a license group.</span></span>

<a href="" id="how-to-remove-an-application-license-group"></a>[<span data-ttu-id="c4013-114">如何删除应用程序许可证组</span><span class="sxs-lookup"><span data-stu-id="c4013-114">How to Remove an Application License Group</span></span>](how-to-remove-an-application-license-group.md)  
<span data-ttu-id="c4013-115">本部分包括删除应用程序许可证组所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="c4013-115">This section includes the steps necessary to delete an application license group.</span></span>

<a href="" id="how-to-set-up-an-unlimited-license-group"></a>[<span data-ttu-id="c4013-116">如何设置无限制的许可证组</span><span class="sxs-lookup"><span data-stu-id="c4013-116">How to Set Up an Unlimited License Group</span></span>](how-to-set-up-an-unlimited-license-group.md)  
<span data-ttu-id="c4013-117">提供创建新的无限许可证组的过程，允许不限数量的用户访问该组中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4013-117">Provides a procedure for creating a new unlimited license group, allowing an unlimited number of users to access the applications in the group.</span></span>

<a href="" id="how-to-set-up-a-concurrent-license-group"></a>[<span data-ttu-id="c4013-118">如何设置并发许可证组</span><span class="sxs-lookup"><span data-stu-id="c4013-118">How to Set Up a Concurrent License Group</span></span>](how-to-set-up-a-concurrent-license-group.md)  
<span data-ttu-id="c4013-119">提供创建新的并发许可证组的过程，允许特定数量的并发用户访问该组中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4013-119">Provides a procedure for creating a new concurrent license group, allowing a specific number of concurrent users to access the applications in the group.</span></span>

<a href="" id="how-to-set-up-a-named-license-group"></a>[<span data-ttu-id="c4013-120">如何设置命名的许可证组</span><span class="sxs-lookup"><span data-stu-id="c4013-120">How to Set Up a Named License Group</span></span>](how-to-set-up-a-named-license-group.md)  
<span data-ttu-id="c4013-121">提供创建新的无限许可证组的过程，允许特定用户访问组中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4013-121">Provides a procedure for creating a new unlimited license group, allowing specific users to access the applications in the group.</span></span>

## <span data-ttu-id="c4013-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="c4013-122">Related topics</span></span>


[<span data-ttu-id="c4013-123">如何在 Application Virtualization Server Management Console 中执行管理任务</span><span class="sxs-lookup"><span data-stu-id="c4013-123">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





