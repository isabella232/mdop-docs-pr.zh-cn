---
title: 在应用程序虚拟化应用程序中使用 UE-V 2. x
description: 在应用程序虚拟化应用程序中使用 UE-V 2. x
author: dansimp
ms.assetid: 4644b810-fc48-4fd0-96e4-2fc6cd64d8ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221d21c5815b36b57a04a0299352e5fe64f657c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804135"
---
# <span data-ttu-id="899f6-103">在应用程序虚拟化应用程序中使用 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="899f6-103">Using UE-V 2.x with Application Virtualization Applications</span></span>


<span data-ttu-id="899f6-104">Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 支持 Microsoft Application Virtualization （App-v）应用程序，而无需对 App-v 包或 UE-V 模板进行任何所需的修改。</span><span class="sxs-lookup"><span data-stu-id="899f6-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 support Microsoft Application Virtualization (App-V) applications without any required modifications to either the App-V package or the UE-V template.</span></span> <span data-ttu-id="899f6-105">但是，需要额外的步骤，因为不能直接在虚拟化 App-v 应用程序上运行 UE-V 生成器。</span><span class="sxs-lookup"><span data-stu-id="899f6-105">However, an additional step is required because you cannot run the UE-V Generator directly on a virtualized App-V application.</span></span> <span data-ttu-id="899f6-106">而必须在本地安装应用程序，生成模板，然后将该模板应用于虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="899f6-106">Instead, you must install the application locally, generate the template, and then apply the template to the virtualized application.</span></span> <span data-ttu-id="899f6-107">UE-V 支持 app-v 4.5、App V 4.6 和 App-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="899f6-107">UE-V supports App-V 4.5, App-V 4.6, and App-V 5.0 packages.</span></span>

## <span data-ttu-id="899f6-108">App-v 应用程序的 UE-V 设置同步</span><span class="sxs-lookup"><span data-stu-id="899f6-108">UE-V settings synchronization for App-V applications</span></span>


<span data-ttu-id="899f6-109">当应用程序按程序名称打开时，按文件版本号和产品版本号（可选）通过使用 App-v 安装应用程序时，UE-V 监视器。</span><span class="sxs-lookup"><span data-stu-id="899f6-109">UE-V monitors when an application opens by the program name and, optionally, by file version numbers and product version numbers, whether the application is installed locally or virtually by using App-V.</span></span> <span data-ttu-id="899f6-110">当应用程序启动时，UE-V 会监视 app-v 进程，应用存储在用户的设置存储路径中的任何设置，然后使应用程序可以正常启动。</span><span class="sxs-lookup"><span data-stu-id="899f6-110">When the application starts, UE-V monitors the App-V process, applies any settings that are stored in the user's settings storage path, and then enables the application to start normally.</span></span> <span data-ttu-id="899f6-111">UE-V 监视 app-v 应用程序，并自动将相关文件和注册表路径转换为虚拟化位置，而不是应用 V 计算环境之外的物理位置。</span><span class="sxs-lookup"><span data-stu-id="899f6-111">UE-V monitors App-V applications and automatically translates the relevant file and registry paths to the virtualized location as opposed to the physical location outside the App-V computing environment.</span></span>

 **<span data-ttu-id="899f6-112">实现虚拟化应用程序的设置同步</span><span class="sxs-lookup"><span data-stu-id="899f6-112">To implement settings synchronization for a virtualized application</span></span>**

1.  <span data-ttu-id="899f6-113">运行 UE-V 生成器以收集本地安装的应用程序的设置，该应用程序的设置要在计算机之间同步。</span><span class="sxs-lookup"><span data-stu-id="899f6-113">Run the UE-V Generator to collect the settings of the locally installed application whose settings you want to synchronize between computers.</span></span> <span data-ttu-id="899f6-114">此过程将创建一个设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="899f6-114">This process creates a settings location template.</span></span> <span data-ttu-id="899f6-115">如果您使用的是内置模板（如 Microsoft Office 2010 模板），请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="899f6-115">If you use a built-in template such as the Microsoft Office 2010 template, skip this step.</span></span> <span data-ttu-id="899f6-116">有关运行 UE-V 生成器的详细信息，请参阅[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates)</span><span class="sxs-lookup"><span data-stu-id="899f6-116">For more information about running the UE-V Generator, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates).</span></span>

2.  <span data-ttu-id="899f6-117">安装 app-v 应用程序包（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="899f6-117">Install the App-V application package if you have not already done so.</span></span>

3.  <span data-ttu-id="899f6-118">将模板发布到设置模板目录的位置，或使用 `Register-UEVTemplate` Windows PowerShell cmdlet 手动安装模板。</span><span class="sxs-lookup"><span data-stu-id="899f6-118">Publish the template to the location of your settings template catalog or manually install the template by using the `Register-UEVTemplate` Windows PowerShell cmdlet.</span></span>

    <span data-ttu-id="899f6-119">**注意** 如果将新创建的模板发布到设置模板目录，则在同步提供程序更新设置之前，客户端不会收到模板。</span><span class="sxs-lookup"><span data-stu-id="899f6-119">**Note** If you publish the newly created template to the settings template catalog, the client does not receive the template until the sync provider updates the settings.</span></span> <span data-ttu-id="899f6-120">若要手动启动此过程，请打开 "**任务计划程序**"，展开 "**任务计划程序库**"，展开 " **Microsoft**"，然后展开 " **ue-v**"。</span><span class="sxs-lookup"><span data-stu-id="899f6-120">To manually start this process, open **Task Scheduler**, expand **Task Scheduler Library**, expand **Microsoft**, and expand **UE-V**.</span></span> <span data-ttu-id="899f6-121">在 "结果" 窗格中，右键单击 "**模板自动更新**"，然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="899f6-121">In the results pane, right-click **Template Auto Update**, and then click **Run**.</span></span>

     

4.  <span data-ttu-id="899f6-122">启动 app-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="899f6-122">Start the App-V package.</span></span>






## <span data-ttu-id="899f6-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="899f6-123">Related topics</span></span>


[<span data-ttu-id="899f6-124">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="899f6-124">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

 

 





