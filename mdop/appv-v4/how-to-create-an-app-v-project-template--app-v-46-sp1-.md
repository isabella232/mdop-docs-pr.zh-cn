---
title: 如何创建 App-V 项目模板 (App-V 4.6 SP1)
description: 如何创建 App-V 项目模板 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 7e87fba2-b72a-4bc9-92b8-220e25aae99a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e264d5c41b663bc9c450dc642e2b26297ee7ea1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801500"
---
# <span data-ttu-id="6dc96-103">如何创建 App-V 项目模板 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="6dc96-103">How to Create an App-V Project Template (App-V 4.6 SP1)</span></span>


<span data-ttu-id="6dc96-104">你可以使用 App-v 项目模板来保存与现有虚拟应用程序包关联的常用设置。</span><span class="sxs-lookup"><span data-stu-id="6dc96-104">You can use an App-V project template to save commonly applied settings associated with an existing virtual application package.</span></span> <span data-ttu-id="6dc96-105">然后，在你的环境中创建新的虚拟应用程序包时，可以应用这些设置，这有助于简化创建虚拟应用程序包的过程。</span><span class="sxs-lookup"><span data-stu-id="6dc96-105">These settings can then be applied when you create new virtual application packages in your environment which can help streamline the process of creating virtual application packages.</span></span>

<span data-ttu-id="6dc96-106">**注意** 仅当创建新的虚拟应用程序包时，才能应用 V 项目模板。</span><span class="sxs-lookup"><span data-stu-id="6dc96-106">**Note** You can only apply an App-V project template when you are creating a new virtual application package.</span></span> <span data-ttu-id="6dc96-107">不支持将项目模板应用于现有虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="6dc96-107">Applying project templates to existing virtual application packages is not supported.</span></span>

 

<span data-ttu-id="6dc96-108">有关应用-V 项目模板的详细信息，请参阅[如何应用 App-v 项目模板（app-v 4.6 SP1）](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="6dc96-108">For more information about applying an App-V project template, see [How to Apply an App-V Project Template (App-V 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md).</span></span>

<span data-ttu-id="6dc96-109">App-v 项目模板与 App-v 应用程序加速器不同，因为 app-v 应用程序加速器属于特定于应用程序，而 app-v 项目模板可应用于多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dc96-109">App-V project templates differ from App-V Application Accelerators because App-V Application Accelerators are application-specific, and App-V project templates can be applied to multiple applications.</span></span> <span data-ttu-id="6dc96-110">此外，使用包加速器创建虚拟应用程序包时，不能使用项目模板。</span><span class="sxs-lookup"><span data-stu-id="6dc96-110">Additionally, you cannot use a project template when you use a Package Accelerator to create a virtual application package.</span></span>

<span data-ttu-id="6dc96-111">使用 App-v 项目模板保存以下常规设置：</span><span class="sxs-lookup"><span data-stu-id="6dc96-111">The following general settings are saved with an App-V project template:</span></span>

-   <span data-ttu-id="6dc96-112">**高级监视选项**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-112">**Advanced Monitoring Options**.</span></span> <span data-ttu-id="6dc96-113">支持在监视期间、变基 **.dll**期间运行 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="6dc96-113">Enables Microsoft Update to run during monitoring, Rebase **.dll’s**.</span></span>

-   <span data-ttu-id="6dc96-114">**程序包部署设置**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-114">**Package Deployment Settings**.</span></span> <span data-ttu-id="6dc96-115">包含**协议**、**主机名**、**端口**、**路径**、**操作系统**、**强制执行安全描述符**、**创建 MSI**、**压缩程序包**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-115">Contains **Protocol**, **Host Name**, **Port**, **Path**, **Operating Systems**, **Enforce Security Descriptors**, **Create MSI**, **Compress Package**.</span></span>

-   <span data-ttu-id="6dc96-116">**常规选项**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-116">**General Options**.</span></span> <span data-ttu-id="6dc96-117">允许**生成 Microsoft Windows Installer （MSI）** 程序包、**允许虚拟化事件**、**允许虚拟化服务**、**将程序包版本附加到文件名**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-117">Allows you to **Generate Microsoft Windows Installer (MSI)** package, **Allow Virtualization of Events**, **Allow Virtualization of Services**, **Append Package Version to Filename**.</span></span>

-   <span data-ttu-id="6dc96-118">**排除项目**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-118">**Exclusion Items**.</span></span> <span data-ttu-id="6dc96-119">包含 "排除" 模式列表。</span><span class="sxs-lookup"><span data-stu-id="6dc96-119">Contains the Exclusion pattern list.</span></span>

**<span data-ttu-id="6dc96-120">创建项目模板</span><span class="sxs-lookup"><span data-stu-id="6dc96-120">To create a project template</span></span>**

1.  <span data-ttu-id="6dc96-121">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="6dc96-121">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="6dc96-122">如果虚拟应用程序包当前已在 App-v Sequencer 中打开，请跳到此过程的步骤3。</span><span class="sxs-lookup"><span data-stu-id="6dc96-122">If the virtual application package is currently open in the App-V Sequencer, skip to step 3 of this procedure.</span></span> <span data-ttu-id="6dc96-123">若要打开包含要用 app-v 项目模板保存的设置的现有虚拟应用程序包，请单击 "**文件**  /  **打开**"，然后单击 "**编辑\*\*\*\*包**"。</span><span class="sxs-lookup"><span data-stu-id="6dc96-123">To open the existing virtual application package that contains the settings you want to save with the App-V project template, click **File** / **Open** and click **Edit** **Package**.</span></span> <span data-ttu-id="6dc96-124">在 "**选择程序包**" 页面上，单击 "**浏览**" 并找到要打开的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="6dc96-124">On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open.</span></span> <span data-ttu-id="6dc96-125">单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-125">Click **Edit**.</span></span>

3.  <span data-ttu-id="6dc96-126">在 app-v Sequencer 控制台中，单击 "**文件**  /  **另存为模板**"。</span><span class="sxs-lookup"><span data-stu-id="6dc96-126">In the App-V Sequencer console, click **File** / **Save As Template**.</span></span> <span data-ttu-id="6dc96-127">查看将与新模板一起保存的设置后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-127">After you have reviewed the settings that will be saved with the new template, click **OK**.</span></span> <span data-ttu-id="6dc96-128">指定将与新的 App-v 项目模板关联的名称。</span><span class="sxs-lookup"><span data-stu-id="6dc96-128">Specify a name that will be associated with the new App-V project template.</span></span> <span data-ttu-id="6dc96-129">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="6dc96-129">Click **Save**.</span></span>

    <span data-ttu-id="6dc96-130">新的 App-v 项目模板保存在此过程的步骤3中指定的目录中。</span><span class="sxs-lookup"><span data-stu-id="6dc96-130">The new App-V project template is saved in the directory specified in step 3 of this procedure.</span></span>

## <span data-ttu-id="6dc96-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="6dc96-131">Related topics</span></span>


[<span data-ttu-id="6dc96-132">Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="6dc96-132">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="6dc96-133">如何应用 App-V 项目模板 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="6dc96-133">How to Apply an App-V Project Template (App-V 4.6 SP1)</span></span>](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)

 

 





