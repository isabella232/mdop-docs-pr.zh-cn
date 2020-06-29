---
title: 如何从桌面通知区域加载虚拟应用程序
description: 如何从桌面通知区域加载虚拟应用程序
author: dansimp
ms.assetid: f52758eb-8b81-4b3c-9bc3-adcf7c00c238
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7004f9e0031dfeeedc8b6a916e2f3488f1d31e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801328"
---
# <span data-ttu-id="62c38-103">如何从桌面通知区域加载虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="62c38-103">How to Load Virtual Applications from the Desktop Notification Area</span></span>


<span data-ttu-id="62c38-104">如果你是移动用户，你可能希望将应用程序中的应用程序完全加载到缓存中，以便在断开连接操作或脱机模式下使用它们。</span><span class="sxs-lookup"><span data-stu-id="62c38-104">If you are a mobile user, you might want to fully load your applications in the cache to use them during disconnected operation or offline mode.</span></span> <span data-ttu-id="62c38-105">若要流式处理应用程序虚拟化（app-v）服务器或应用程序虚拟化（app-v）流服务器中的应用程序，必须连接到服务器才能加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c38-105">To stream applications from the Application Virtualization (App-V) Server or the Application Virtualization (App-V) Streaming Server, you must be connected to a server to load applications.</span></span> <span data-ttu-id="62c38-106">如果尝试加载应用程序时未连接到服务器，系统将生成相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="62c38-106">If you are not connected to the server when you attempt to load applications, your system will generate an appropriate error message.</span></span> <span data-ttu-id="62c38-107">你还可以从文件或磁盘将应用程序流式传输到客户端。</span><span class="sxs-lookup"><span data-stu-id="62c38-107">You can also stream applications to the client from a file or disk.</span></span>

<span data-ttu-id="62c38-108">应用程序一次加载一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c38-108">The applications are loaded one application at a time.</span></span> <span data-ttu-id="62c38-109">进度条显示应用程序名称、加载的应用程序百分比以及已处理的应用程序数与排队的应用程序总数。</span><span class="sxs-lookup"><span data-stu-id="62c38-109">The progress bar shows you the application name, the percentage of application loaded, and the number of applications already processed compared to the total number of the applications queued.</span></span> <span data-ttu-id="62c38-110">你可以跳过在100% 加载前正在进行的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c38-110">You can skip any application in progress before it is 100% loaded.</span></span> <span data-ttu-id="62c38-111">您也可以跳过所有剩余应用程序的加载。</span><span class="sxs-lookup"><span data-stu-id="62c38-111">You can skip the loading of all remaining applications as well.</span></span>

<span data-ttu-id="62c38-112">**注意** 如果你的系统在加载应用程序时遇到错误，它会向你报告错误。</span><span class="sxs-lookup"><span data-stu-id="62c38-112">**Note** If your system encounters an error while loading an application, it reports the error to you.</span></span> <span data-ttu-id="62c38-113">必须先取消错误对话框，然后它才会加载下一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c38-113">You must dismiss the error dialog before it will load the next application.</span></span>

 

**<span data-ttu-id="62c38-114">加载所有应用程序</span><span class="sxs-lookup"><span data-stu-id="62c38-114">To load all applications</span></span>**

1.  <span data-ttu-id="62c38-115">右键单击通知区域中的 "应用程序虚拟化系统" 图标。</span><span class="sxs-lookup"><span data-stu-id="62c38-115">Right-click the Application Virtualization System icon in the notification area.</span></span>

2.  <span data-ttu-id="62c38-116">从弹出菜单中选择 "**加载应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="62c38-116">Select **Load Applications** from the pop-up menu.</span></span>

**<span data-ttu-id="62c38-117">跳过应用程序</span><span class="sxs-lookup"><span data-stu-id="62c38-117">To skip applications</span></span>**

1.  <span data-ttu-id="62c38-118">单击进度栏以显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="62c38-118">Click the progress bar to display the dialog box.</span></span>

2.  <span data-ttu-id="62c38-119">选择以下按钮之一以获得所需的结果：</span><span class="sxs-lookup"><span data-stu-id="62c38-119">Select one of the following buttons to achieve the desired results:</span></span>

    1.  <span data-ttu-id="62c38-120">**跳过**-跳过当前加载的应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c38-120">**Skip**—To skip the currently loading application.</span></span>

    2.  <span data-ttu-id="62c38-121">**全部跳过**-跳过所有剩余的应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c38-121">**Skip All**—To skip all remaining applications.</span></span>

    3.  <span data-ttu-id="62c38-122">**继续**-取消对话框并继续加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c38-122">**Continue**—To cancel the dialog box and continue loading applications.</span></span>

## <span data-ttu-id="62c38-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="62c38-123">Related topics</span></span>


[<span data-ttu-id="62c38-124">如何为 Application Virtualization Client Management 使用桌面通知区域</span><span class="sxs-lookup"><span data-stu-id="62c38-124">How to Use the Desktop Notification Area for Application Virtualization Client Management</span></span>](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





