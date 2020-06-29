---
title: 在 MED-V 工作区上安装和删除应用程序
description: 在 MED-V 工作区上安装和删除应用程序
author: dansimp
ms.assetid: 24f32720-51ab-4385-adfe-4f5a65e45fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 22cb98c167b53b1b206b8b5be2ba18fc0fba4f06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804124"
---
# <span data-ttu-id="bb8eb-103">在 MED-V 工作区上安装和删除应用程序</span><span class="sxs-lookup"><span data-stu-id="bb8eb-103">Installing and Removing an Application on the MED-V Workspace</span></span>


<span data-ttu-id="bb8eb-104">与主机操作系统不兼容的应用程序可以在 MED-V 工作区中运行，并在 MED-V 工作区中打开，其方式与从主机打开的方式相同，在 "**开始**" 菜单上或使用本地主机快捷方式。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-104">Applications that are incompatible with the host operating system can be run in the MED-V workspace and opened in the MED-V workspace in the same manner in which they are opened from the host computer, on the **Start** menu or by using a localhost shortcut.</span></span>

<span data-ttu-id="bb8eb-105">部署 MED-V 工作区后，你可以使用多种不同的选项在 MED-V 工作区中安装和删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-105">After you have deployed a MED-V workspace, you have several different options available to you for installing and removing applications in the MED-V workspace.</span></span> <span data-ttu-id="bb8eb-106">这些选项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="bb8eb-106">These options include the following:</span></span>

-   [<span data-ttu-id="bb8eb-107">使用组策略</span><span class="sxs-lookup"><span data-stu-id="bb8eb-107">Using Group Policy</span></span>](#bkmk-grouppolicy)

-   [<span data-ttu-id="bb8eb-108">使用电子软件分发系统</span><span class="sxs-lookup"><span data-stu-id="bb8eb-108">Using an Electronic Software Distribution System</span></span>](#bkmk-esd)

-   [<span data-ttu-id="bb8eb-109">使用应用程序虚拟化（app-v）</span><span class="sxs-lookup"><span data-stu-id="bb8eb-109">Using Application Virtualization (APP-V)</span></span>](#bkmk-appv)

-   [<span data-ttu-id="bb8eb-110">更新核心图像</span><span class="sxs-lookup"><span data-stu-id="bb8eb-110">Updating the Core Image</span></span>](#bkmk-coreimage)

<span data-ttu-id="bb8eb-111">**重要提示** 若要确保已安装的应用程序自动发布到主机，请在虚拟机上为**所有用户**安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-111">**Important** To make sure that an installed application is automatically published to the host, install the application on the virtual machine for **All Users**.</span></span> <span data-ttu-id="bb8eb-112">有关应用程序发布的详细信息，请参阅[如何在 Med-v 工作区发布和取消发布应用程序](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-112">For more information about application publishing, see [How to Publish and Unpublish an Application on the MED-V Workspace](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md).</span></span>

 

<span data-ttu-id="bb8eb-113">**提示** MED-V 不支持用于内容处理的来宾到主机重定向，例如，在 Internet Explorer 的 MED-V 工作区中双击 Microsoft Word 文档。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-113">**Tip** MED-V does not support guest-to-host redirection for content handling, such as double-clicking a Microsoft Word document in Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="bb8eb-114">因此，必须在 MED-V 工作区中安装所需的应用程序（如 Microsoft Word），以便提供最终用户可能期望的默认内容处理功能。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-114">Therefore, the required applications, such as Microsoft Word, must be installed in MED-V workspace to provide the default content handling functionality that an end user might expect.</span></span>

 

## <a href="" id="bkmk-grouppolicy"></a> <span data-ttu-id="bb8eb-115">使用组策略添加和删除应用程序</span><span class="sxs-lookup"><span data-stu-id="bb8eb-115">Adding and Removing Applications by Using Group Policy</span></span>


<span data-ttu-id="bb8eb-116">你可以使用组策略和组策略对象向你的企业中的所有或某些 MED-V 工作区分配或发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-116">You can use Group Policy and Group Policy objects to assign or publish applications to all or some MED-V workspaces in your enterprise.</span></span> <span data-ttu-id="bb8eb-117">对于分配的应用程序，当最终用户登录到其计算机时，应用程序将显示在 "**开始**" 菜单上。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-117">For assigned applications, when an end user logs on to their computer, the application appears on the **Start** menu.</span></span> <span data-ttu-id="bb8eb-118">当用户首次选择新应用程序时，应用程序将安装并已准备好使用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-118">When they select the new application for the first time, the application installs and is ready for use.</span></span> <span data-ttu-id="bb8eb-119">对于已发布的应用程序，应用程序不会显示在 "**开始**" 菜单上。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-119">For published applications, the application does not appear on the **Start** menu.</span></span> <span data-ttu-id="bb8eb-120">只有最终用户可以使用**控制面板**中的 "**添加或删除程序**" 或打开与应用程序关联的文件来安装。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-120">It is only available for the end user to install by using **Add or Remove Programs** in **Control Panel** or by opening a file that is associated with the application.</span></span>

<span data-ttu-id="bb8eb-121">你还可以使用组策略和组策略对象，方法与从 MED-V 工作区中删除应用程序相同。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-121">You can also use Group Policy and Group Policy objects in the same manner to remove applications from the MED-V workspace.</span></span>

<span data-ttu-id="bb8eb-122">有关如何使用组策略添加和删除应用程序的详细信息，请参阅[组策略软件安装](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-122">For more information about how to add and remove applications by using Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

## <a href="" id="bkmk-esd"></a> <span data-ttu-id="bb8eb-123">使用 ESD 系统添加和删除应用程序</span><span class="sxs-lookup"><span data-stu-id="bb8eb-123">Adding and Removing Applications by Using an ESD System</span></span>


<span data-ttu-id="bb8eb-124">电子软件分发（ESD）系统旨在通过网络连接将软件和其他信息高效部署到许多不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-124">An electronic software distribution (ESD) system is designed to efficiently deploy software and other information to many different computers over network connections.</span></span> <span data-ttu-id="bb8eb-125">如果你的组织使用 ESD 系统部署软件，则可以使用它在 MED-V 工作区上添加和删除应用程序，就像在物理计算机上添加和删除应用程序一样。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-125">If your organization uses an ESD system to deploy software, you can use it to add and remove applications on MED-V workspaces just as you add and remove applications on physical computers.</span></span>

## <a href="" id="bkmk-appv"></a> <span data-ttu-id="bb8eb-126">使用 APP-V 添加和删除应用程序</span><span class="sxs-lookup"><span data-stu-id="bb8eb-126">Adding and Removing Applications by Using APP-V</span></span>


<span data-ttu-id="bb8eb-127">Microsoft Application Virtualization （App-v）提供管理功能，使应用程序可用于最终用户计算机，而无需直接在这些计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-127">Microsoft Application Virtualization (App-V) provides the administrative capability to make applications available to end-user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="bb8eb-128">如果你的组织具有你使用 Windows XP 中的 App-v 进行排序的应用程序，并对其重新排序将延迟迁移到 Windows 7，你可能需要将 MED-V 和 app-v 结合使用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-128">You might want to use MED-V and App-V together if, for example, your organization has applications that you sequenced with App-V in Windows XP, and re-sequencing them would delay your migration to Windows 7.</span></span>

<span data-ttu-id="bb8eb-129">你可以将 MED-V 与 App-v 结合使用，在已部署的 MED-V 工作区上添加和删除虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-129">You can use MED-V together with App-V to add and remove virtual applications on a deployed MED-V workspace.</span></span> <span data-ttu-id="bb8eb-130">若要以这种方式管理应用程序，必须首先在 MED-V 来宾操作系统上安装 app-v 代理。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-130">To manage applications in this manner, you must first install the App-V agent on the MED-V guest operating system.</span></span> <span data-ttu-id="bb8eb-131">然后，你可以在 MED-V 工作区中使用 app-v 添加和删除虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-131">You can then use App-V in the MED-V workspace to add and remove the virtual applications.</span></span>

<span data-ttu-id="bb8eb-132">有关如何安装和使用 app-v 的信息，请参阅[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-132">For information about how to install and use App-V, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939).</span></span>

<span data-ttu-id="bb8eb-133">**重要提示** 发布到 MED-V 工作区的 app-v 应用程序具有无法从主计算机重定向到来宾虚拟机的文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-133">**Important** App-V applications that you publish to the MED-V workspace have file-type associations that cannot redirect from the host computer to the guest virtual machine.</span></span> <span data-ttu-id="bb8eb-134">但是，最终用户仍可以通过单击 "**文件**"，然后单击已发布的 app-v 应用程序上的 "**打开**" 来访问这些文件类型。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-134">However, the end user can still access these file types by clicking **File**, and then by clicking **Open** on the published App-V application.</span></span>

<span data-ttu-id="bb8eb-135">若要强制重定向这些文件类型关联，请通过在来宾虚拟机中的命令提示符处键入以下内容来对映射的文件类型关联进行查询 app-v： **sftmime/QUERY OBJ： type**。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-135">To force redirection of those file-type associations, query App-V for mapped file type associations by typing the following at a command prompt in the guest virtual machine: **sftmime /QUERY OBJ:TYPE**.</span></span> <span data-ttu-id="bb8eb-136">然后，在主计算机中映射这些文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-136">Then, map those file type associations in the host computer.</span></span>

 

## <a href="" id="bkmk-coreimage"></a> <span data-ttu-id="bb8eb-137">在核心映像上添加和删除应用程序</span><span class="sxs-lookup"><span data-stu-id="bb8eb-137">Adding and Removing Applications on the Core Image</span></span>


<span data-ttu-id="bb8eb-138">尽管不会被视为 MED-V 最佳做法，但你可以直接在核心映像上添加和删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-138">Although not considered a MED-V best practice, you can add and remove applications directly on the core image.</span></span> <span data-ttu-id="bb8eb-139">添加或删除应用程序后，你可以将 MED-V 工作区重新部署到你的企业，就像最初部署它一样。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-139">After you have added or removed an application, you can redeploy the MED-V workspace back out to your enterprise just as you deployed it originally.</span></span>

<span data-ttu-id="bb8eb-140">有关如何在核心映像上添加或删除应用程序的详细信息，请参阅[在 Windows 虚拟 PC 映像上安装应用程序](installing-applications-on-a-windows-virtual-pc-image.md)。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-140">For more information about how to add or remove applications on the core image, see [Installing Applications on a Windows Virtual PC Image](installing-applications-on-a-windows-virtual-pc-image.md).</span></span>

<span data-ttu-id="bb8eb-141">**重要提示** 我们不推荐这种管理应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-141">**Important** We do not recommend this method of managing applications.</span></span> <span data-ttu-id="bb8eb-142">如果你在核心映像上添加或删除应用程序，并将 MED-V 工作区重新部署到你的企业，首次必须再次运行安装程序，并且虚拟机上保存的所有数据都将丢失。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-142">If you add or remove applications on the core image and redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved on the virtual machine is lost.</span></span>

 

<span data-ttu-id="bb8eb-143">**注意** 即使应用程序已安装到 MED-V 工作区中，你可能还需要先发布该应用程序，然后才能向最终用户提供该应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-143">**Note** Even though an application is installed into a MED-V workspace, you might also have to publish the application before it becomes available to the end user.</span></span> <span data-ttu-id="bb8eb-144">例如，如果安装未在 "**开始**" 菜单上自动创建快捷方式，则可能必须发布已安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-144">For example, you might have to publish an installed application if the installation did not automatically create a shortcut on the **Start** menu.</span></span> <span data-ttu-id="bb8eb-145">同样，若要取消发布应用程序，您可能需要手动从 "**开始**" 菜单中删除快捷方式。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-145">Likewise, to unpublish an application, you might have to manually remove a shortcut from the **Start** menu.</span></span>

<span data-ttu-id="bb8eb-146">默认情况下，当自动创建和启用快捷方式时，大部分应用程序会在安装时发布。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-146">By default, most applications are published at the time that they are installed, when shortcuts are automatically created and enabled.</span></span>

 

## <span data-ttu-id="bb8eb-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="bb8eb-147">Related topics</span></span>


[<span data-ttu-id="bb8eb-148">如何测试应用程序发布</span><span class="sxs-lookup"><span data-stu-id="bb8eb-148">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="bb8eb-149">如何在 MED-V 工作区上发布和取消发布应用程序</span><span class="sxs-lookup"><span data-stu-id="bb8eb-149">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





