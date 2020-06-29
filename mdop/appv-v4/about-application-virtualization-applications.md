---
title: 关于 Application Virtualization 应用程序
description: 关于 Application Virtualization 应用程序
author: dansimp
ms.assetid: 3bf833b7-d172-4eef-a9e8-4b4f0c7eb15b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4eeea7a0ec4454aefcdde5196ae15ed029da45b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802476"
---
# <span data-ttu-id="b01fa-103">关于 Application Virtualization 应用程序</span><span class="sxs-lookup"><span data-stu-id="b01fa-103">About Application Virtualization Applications</span></span>


<span data-ttu-id="b01fa-104">在应用程序虚拟化中，*应用程序*是从应用程序虚拟化管理服务器流入到应用程序虚拟化桌面客户端或远程桌面服务（以前称为终端服务）的客户端的可执行程序（如 Microsoft Visio）。</span><span class="sxs-lookup"><span data-stu-id="b01fa-104">In Application Virtualization, an *application* is an executable program, such as Microsoft Visio, that is streamed to the Application Virtualization Desktop Client or Client for Remote Desktop Services (formerly Terminal Services) from an Application Virtualization Management Server.</span></span> <span data-ttu-id="b01fa-105">必须先通过使用 Application Virtualization Sequencer 处理应用程序，才能将该应用程序流式传输到客户端。</span><span class="sxs-lookup"><span data-stu-id="b01fa-105">Before an application can be streamed to a client, the application must be prepared for streaming by processing it with the Application Virtualization Sequencer.</span></span>

## <span data-ttu-id="b01fa-106">管理应用程序</span><span class="sxs-lookup"><span data-stu-id="b01fa-106">Managing Applications</span></span>


<span data-ttu-id="b01fa-107">必须先将应用程序添加到系统，然后才能使应用程序可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="b01fa-107">You must add applications to the system before you can make the applications available to users.</span></span> <span data-ttu-id="b01fa-108">将应用程序添加到系统的最常见方法是导入这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="b01fa-108">The most common method for adding applications to the system is to import them.</span></span> <span data-ttu-id="b01fa-109">若要访问此功能，请右键单击应用程序虚拟化服务器管理控制台中的 "**应用程序**" 节点，然后选择 "**导入应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="b01fa-109">To access this feature, right-click the **Applications** node in the Application Virtualization Server Management Console and choose **Import Applications**.</span></span>

<span data-ttu-id="b01fa-110">你可以同时导入多个开放软件描述符（OSD）文件，也可以导入一个可以包含多个 OSD 文件的 Sequencer 项目文件（SPRJ）。</span><span class="sxs-lookup"><span data-stu-id="b01fa-110">You can import more than one Open Software Descriptor (OSD) file at the same time, or you can import a Sequencer Project file (SPRJ) that can contain multiple OSD files.</span></span> <span data-ttu-id="b01fa-111">此功能使你能够以同样的方式配置相关的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b01fa-111">This functionality enables you to configure related applications similarly.</span></span>

<span data-ttu-id="b01fa-112">你还可以使用以下功能来帮助你管理应用程序：</span><span class="sxs-lookup"><span data-stu-id="b01fa-112">You can also use the following features to help you manage your applications:</span></span>

-   <span data-ttu-id="b01fa-113">**应用程序组**-使你能够创建应用程序的逻辑组以简化管理。</span><span class="sxs-lookup"><span data-stu-id="b01fa-113">**Application Groups**—Enables you to create logical groups of applications for simplified management.</span></span> <span data-ttu-id="b01fa-114">对组进行更改（例如，访问权限）时，所做的更改将应用到组中的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="b01fa-114">When changes are made to a group (for example, access permissions), the changes are applied to all applications in the group.</span></span> <span data-ttu-id="b01fa-115">组中的应用程序可以来自不同的程序包。</span><span class="sxs-lookup"><span data-stu-id="b01fa-115">Applications in a group can come from different packages.</span></span>

-   <span data-ttu-id="b01fa-116">**多重选择**-允许你在单击应用程序以修改应用程序属性时按住 CTRL 键，同时选择多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b01fa-116">**Multi Select**—Enables you to select multiple applications at once by holding the CTRL key when you click an application to modify the application properties.</span></span> <span data-ttu-id="b01fa-117">但是，如果你想要维护应用程序之间的关系，你应该创建一个应用程序组来保存应用程序。</span><span class="sxs-lookup"><span data-stu-id="b01fa-117">However, if you want to maintain a relationship between the applications, you should create an application group to hold the applications.</span></span>

-   <span data-ttu-id="b01fa-118">**跨系统副本**-使你能够在一个步骤中将应用程序从一个环境复制到另一个运行相同版本 app-v 的环境中。</span><span class="sxs-lookup"><span data-stu-id="b01fa-118">**Cross System Copy**—Enables you to copy applications from one environment to another environment that is running the same version of App-V in one step.</span></span> <span data-ttu-id="b01fa-119">例如，你可能有一个用户验收测试环境，你可以在其中开始部署和配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="b01fa-119">For example, you might have a user acceptance test environment where you initially deploy and configure applications.</span></span> <span data-ttu-id="b01fa-120">完成测试阶段后，您可能希望将同一组应用程序（包括权限）复制到生产环境。</span><span class="sxs-lookup"><span data-stu-id="b01fa-120">After you finish your testing phase, you might want to replicate the same set of applications (including permissions) to the production environment.</span></span>

## <span data-ttu-id="b01fa-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="b01fa-121">Related topics</span></span>


[<span data-ttu-id="b01fa-122">关于 Application Virtualization 程序包</span><span class="sxs-lookup"><span data-stu-id="b01fa-122">About Application Virtualization Packages</span></span>](about-application-virtualization-packages.md)

[<span data-ttu-id="b01fa-123">关于 Application Virtualization Server Management Console</span><span class="sxs-lookup"><span data-stu-id="b01fa-123">About the Application Virtualization Server Management Console</span></span>](about-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="b01fa-124">如何在 Server Management Console 中管理应用程序组</span><span class="sxs-lookup"><span data-stu-id="b01fa-124">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="b01fa-125">如何在 Server Management Console 中管理应用程序</span><span class="sxs-lookup"><span data-stu-id="b01fa-125">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





