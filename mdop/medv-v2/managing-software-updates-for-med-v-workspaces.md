---
title: 管理 MED-V 工作区的软件更新
description: 管理 MED-V 工作区的软件更新
author: dansimp
ms.assetid: a28d6dcd-cb9f-46ba-8dac-1d990837a3a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 696238a2f5ad9b7e5120f75f6cd09d890d12519b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803643"
---
# <span data-ttu-id="5f138-103">管理 MED-V 工作区的软件更新</span><span class="sxs-lookup"><span data-stu-id="5f138-103">Managing Software Updates for MED-V Workspaces</span></span>


<span data-ttu-id="5f138-104">你可以使用多种不同的选项在已部署的 MED-V 工作区中提供应用程序的软件更新。</span><span class="sxs-lookup"><span data-stu-id="5f138-104">You have several different options available to you for providing software updates for the applications in the deployed MED-V workspace.</span></span>

<span data-ttu-id="5f138-105">**注意** 有关如何指定用于定义 MED-V 如何接收自动更新的配置设置的信息，请参阅[管理 Med-v 工作区的自动更新](managing-automatic-updates-for-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="5f138-105">**Note** For information about how to specify the configuration settings that define how MED-V receives automatic updates, see [Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md).</span></span>

 

**<span data-ttu-id="5f138-106">在 MED-V 工作区中更新软件</span><span class="sxs-lookup"><span data-stu-id="5f138-106">Updating Software in a MED-V Workspace</span></span>**

1.  **<span data-ttu-id="5f138-107">使用电子软件分发系统</span><span class="sxs-lookup"><span data-stu-id="5f138-107">Using an Electronic Software Distribution System</span></span>**

    <span data-ttu-id="5f138-108">如果你的组织使用电子软件分发系统（ESD）系统部署软件，则可以使用它来提供 MED-V 工作区上的应用程序的软件更新，就像在物理计算机上提供应用程序更新一样。</span><span class="sxs-lookup"><span data-stu-id="5f138-108">If your organization uses an Electronic Software Distribution System (ESD) system to deploy software, you can use it to provide software updates for applications on MED-V workspaces just as you provide updates for applications on physical computers.</span></span>

2.  **<span data-ttu-id="5f138-109">使用组策略</span><span class="sxs-lookup"><span data-stu-id="5f138-109">Using Group Policy</span></span>**

    <span data-ttu-id="5f138-110">如果你的组织使用组策略部署软件，则可以使用它为 MED-V 工作区上的应用程序提供软件更新，就像在物理计算机上提供应用程序更新一样。</span><span class="sxs-lookup"><span data-stu-id="5f138-110">If your organization deploys software by using Group Policy, you can use it to provide software updates for applications on MED-V workspaces just as you provide updates for applications on physical computers.</span></span>

3.  **<span data-ttu-id="5f138-111">使用应用程序虚拟化（app-v）</span><span class="sxs-lookup"><span data-stu-id="5f138-111">Using Application Virtualization (APP-V)</span></span>**

    <span data-ttu-id="5f138-112">如果使用 MED-V 与 App-v 结合使用，则可以按照 App-v 工作区中的应用程序更新软件更新，以执行更新软件所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="5f138-112">If you use MED-V together with App-V, you can provide software updates to applications in the MED-V workspace by following the steps that are required by App-V for updating software.</span></span> <span data-ttu-id="5f138-113">有关详细信息，请参阅[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。</span><span class="sxs-lookup"><span data-stu-id="5f138-113">For more information, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939).</span></span>

4.  **<span data-ttu-id="5f138-114">更新核心映像中的软件</span><span class="sxs-lookup"><span data-stu-id="5f138-114">Updating Software in the Core Image</span></span>**

    <span data-ttu-id="5f138-115">尽管不会被视为 MED-V 最佳做法，但你可以将软件更新安装到核心映像上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5f138-115">Although not considered a MED-V best practice, you can install software updates to applications on the core image.</span></span> <span data-ttu-id="5f138-116">安装更新后，你可以将 MED-V 工作区重新部署到你的企业，就像最初部署它一样。</span><span class="sxs-lookup"><span data-stu-id="5f138-116">After you have installed the updates, you can then redeploy the MED-V workspace back out to your enterprise just as you deployed it originally.</span></span>

    <span data-ttu-id="5f138-117">**重要提示** 我们不推荐这种管理软件更新的方法。</span><span class="sxs-lookup"><span data-stu-id="5f138-117">**Important** We do not recommend this method of managing software updates.</span></span> <span data-ttu-id="5f138-118">此外，如果你更新核心映像中的软件并将 MED-V 工作区重新部署到你的企业，首次必须再次运行安装程序，并且虚拟机中保存的所有数据都将丢失。</span><span class="sxs-lookup"><span data-stu-id="5f138-118">In addition, if you update software in the core image and redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved in the virtual machine is lost.</span></span>

     

## <span data-ttu-id="5f138-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="5f138-119">Related topics</span></span>


[<span data-ttu-id="5f138-120">管理 MED-V 工作区的自动更新</span><span class="sxs-lookup"><span data-stu-id="5f138-120">Managing Automatic Updates for MED-V Workspaces</span></span>](managing-automatic-updates-for-med-v-workspaces.md)

[<span data-ttu-id="5f138-121">如何测试应用程序发布</span><span class="sxs-lookup"><span data-stu-id="5f138-121">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="5f138-122">如何在 MED-V 工作区上发布和取消发布应用程序</span><span class="sxs-lookup"><span data-stu-id="5f138-122">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





