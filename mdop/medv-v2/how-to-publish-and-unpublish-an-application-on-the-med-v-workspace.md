---
title: 如何在 MED-V 工作区上发布和取消发布应用程序
description: 如何在 MED-V 工作区上发布和取消发布应用程序
author: dansimp
ms.assetid: fd5a62e9-0577-44d2-ae17-61c0aef78ce8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc8f9579d800aa0e5da0d67e0cd71bcae5e912a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804065"
---
# <span data-ttu-id="2710d-103">如何在 MED-V 工作区上发布和取消发布应用程序</span><span class="sxs-lookup"><span data-stu-id="2710d-103">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>


<span data-ttu-id="2710d-104">即使在 MED-V 工作区中安装了应用程序，你也可能还需要先发布应用程序，然后才能向最终用户提供该应用程序。</span><span class="sxs-lookup"><span data-stu-id="2710d-104">Even though an application is installed in a MED-V workspace, you might also have to publish the application before it becomes available to the end user.</span></span> <span data-ttu-id="2710d-105">默认情况下，大多数应用程序在安装时发布，并且创建和启用快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2710d-105">By default, most applications are published at the time that they are installed and shortcuts are created and enabled.</span></span>

<span data-ttu-id="2710d-106">在某些情况下，你可能希望在 MED-V 工作区上安装应用程序，而不让最终用户（如病毒扫描软件）使用这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="2710d-106">In some cases, you might want to install applications on the MED-V workspace without making them available to the end user, for example, virus-scanning software.</span></span> <span data-ttu-id="2710d-107">同样，你希望在某些情况下发布安装在以前对最终用户不可用的 MED-V 工作区中安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2710d-107">Similarly, there are occasions in which you want to publish an application that is installed on the MED-V workspace that was previously unavailable to the end user.</span></span> <span data-ttu-id="2710d-108">例如，如果安装未在 "**开始**" 菜单上自动创建快捷方式，则可能必须发布已安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2710d-108">For example, you might have to publish an installed application if the installation did not automatically create a shortcut on the **Start** menu.</span></span>

<span data-ttu-id="2710d-109">**重要提示** 如果发布不支持 UNC 路径的应用程序，我们建议你将应用程序映射到驱动器。</span><span class="sxs-lookup"><span data-stu-id="2710d-109">**Important** If you publish an application that does not support UNC paths, we recommend that you map the application to a drive.</span></span>

 

<span data-ttu-id="2710d-110">你可以通过执行以下任务之一将应用程序发布或取消发布到已部署的 MED-V 工作区：</span><span class="sxs-lookup"><span data-stu-id="2710d-110">You can publish or unpublish applications to a deployed MED-V workspace by performing one of the following tasks:</span></span>

**<span data-ttu-id="2710d-111">发布或取消发布已安装的应用程序</span><span class="sxs-lookup"><span data-stu-id="2710d-111">To publish or unpublish an installed application</span></span>**

1.  <span data-ttu-id="2710d-112">若要在已部署的 MED-V 工作区上发布应用程序，请将该应用程序的快捷方式复制到虚拟机上的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="2710d-112">To publish an application on a deployed MED-V workspace, copy a shortcut for that application to the following folder on the virtual machine:</span></span>

    <span data-ttu-id="2710d-113">C:\\Documents 和 Settings\\All Users\\Start 菜单</span><span class="sxs-lookup"><span data-stu-id="2710d-113">C:\\Documents and Settings\\All Users\\Start Menu</span></span>

    <span data-ttu-id="2710d-114">如有必要，请使用组策略或 ESD 系统部署脚本，该脚本将该应用程序的快捷方式复制到 "所有 Users\\Start" 菜单文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-114">If it is necessary, use Group Policy or an ESD system to deploy a script that copies the shortcut for that application to the All Users\\Start Menu folder.</span></span>

2.  <span data-ttu-id="2710d-115">若要在已部署的 MED-V 工作区上取消发布应用程序，请从虚拟机上的以下文件夹中删除该应用程序的快捷方式：</span><span class="sxs-lookup"><span data-stu-id="2710d-115">To unpublish an application on a deployed MED-V workspace, delete the shortcut for that application from the following folder on the virtual machine:</span></span>

    <span data-ttu-id="2710d-116">C:\\Documents 和 Settings\\All Users\\Start 菜单</span><span class="sxs-lookup"><span data-stu-id="2710d-116">C:\\Documents and Settings\\All Users\\Start Menu</span></span>

    <span data-ttu-id="2710d-117">如有必要，请使用组策略或 ESD 系统部署脚本，该脚本从 "所有 Users\\Start" 菜单文件夹中删除该应用程序的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2710d-117">If it is necessary, use Group Policy or an ESD system to deploy a script that deletes the shortcut for that application from the All Users\\Start Menu folder.</span></span>

    <span data-ttu-id="2710d-118">**注意** 通常，卸载应用程序时，快捷方式会自动从主机 "**开始**" 菜单中删除。</span><span class="sxs-lookup"><span data-stu-id="2710d-118">**Note** Frequently, the shortcut is automatically deleted from the host computer **Start** menu when you uninstall the application.</span></span> <span data-ttu-id="2710d-119">但是，在某些情况下（例如对于为共享计算机的所有用户配置的 MED-V 工作区），可能需要在卸载应用程序后手动删除 "**开始**" 菜单上的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2710d-119">However, in some cases, such as for a MED-V workspace that is configured for all users of a shared computer, you might have to manually delete the shortcut on the **Start** menu after the application is uninstalled.</span></span> <span data-ttu-id="2710d-120">最终用户可以通过右键单击快捷方式并选择 "**删除**" 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2710d-120">The end-user can do this by right-clicking the shortcut and selecting **Delete**.</span></span>

     

<span data-ttu-id="2710d-121">若要测试应用程序是否已发布或未发布，请在 MED-V 工作区中验证是否有相应的快捷方式可用。</span><span class="sxs-lookup"><span data-stu-id="2710d-121">To test that the application was published or unpublished, verify on the MED-V workspace whether the corresponding shortcut is available or not.</span></span>

<span data-ttu-id="2710d-122">**注意** Windows XP SP3 中包含的应用程序和位于虚拟机 "开始" 菜单文件夹中的应用程序不会自动发布到主机。</span><span class="sxs-lookup"><span data-stu-id="2710d-122">**Note** Applications that are included in Windows XP SP3 and are located in the virtual machine Start Menu folder are not automatically published to the host.</span></span> <span data-ttu-id="2710d-123">它们由阻止自动发布的注册表设置控制。</span><span class="sxs-lookup"><span data-stu-id="2710d-123">They are controlled by registry settings that block automatic publishing.</span></span> <span data-ttu-id="2710d-124">有关详细信息，请参阅[Windows 虚拟 PC 应用程序排除列表](windows-virtual-pc-application-exclude-list.md)。</span><span class="sxs-lookup"><span data-stu-id="2710d-124">For more information, see [Windows Virtual PC Application Exclude List](windows-virtual-pc-application-exclude-list.md).</span></span>

 

**<span data-ttu-id="2710d-125">发布 "控制面板" 项目</span><span class="sxs-lookup"><span data-stu-id="2710d-125">To publish Control Panel items</span></span>**

1.  <span data-ttu-id="2710d-126">在目标是项目名称的虚拟机（如 C:\\WINDOWS\\system32\\appwiz.cpl）上创建快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2710d-126">Create a shortcut on the virtual machine where the target is the name of the item, such as C:\\WINDOWS\\system32\\appwiz.cpl.</span></span>

    <span data-ttu-id="2710d-127">快捷方式必须在 "%ALLUSERSPROFILE%\\Start Menu\\" 文件夹或其中一个子文件夹中创建或移动到其中一个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-127">The shortcut must be either created in or moved to the "%ALLUSERSPROFILE%\\Start Menu\\" folder or one of its subfolders.</span></span>

    <span data-ttu-id="2710d-128">项目将发布到主机 "开始" 菜单文件夹中相应位置的主计算机。</span><span class="sxs-lookup"><span data-stu-id="2710d-128">The item will be published to the host computer in the corresponding location in the host Start Menu folder.</span></span>

2.  <span data-ttu-id="2710d-129">启动主机中项目的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2710d-129">Start the shortcut for the item in the host.</span></span>

<span data-ttu-id="2710d-130">**小心** 创建快捷方式时，请不要指定% SystemRoot% \\control.exe。</span><span class="sxs-lookup"><span data-stu-id="2710d-130">**Caution** When you create the shortcut, do not specify %SystemRoot%\\control.exe.</span></span> <span data-ttu-id="2710d-131">此应用程序将不会发布，因为它包含在阻止自动发布的注册表设置中。</span><span class="sxs-lookup"><span data-stu-id="2710d-131">This application will not be published because it is contained in the registry settings that block automatic publishing.</span></span>

 

**<span data-ttu-id="2710d-132">MED-V 如何处理自动应用程序发布</span><span class="sxs-lookup"><span data-stu-id="2710d-132">How MED-V handles automatic application publishing</span></span>**

1.  <span data-ttu-id="2710d-133">在应用程序发布期间，MED-V 通过尝试匹配存在于来宾中的文件夹层次结构，将来宾虚拟机中的快捷方式复制到主机计算机。</span><span class="sxs-lookup"><span data-stu-id="2710d-133">During application publishing, MED-V copies the shortcuts from the guest virtual machine to the host computer by trying to match the folder hierarchy that exists in the guest.</span></span> <span data-ttu-id="2710d-134">通过执行此操作，MED-V 通过执行以下步骤将来自来宾的快捷方式复制到主机：</span><span class="sxs-lookup"><span data-stu-id="2710d-134">By doing this, MED-V copies shortcuts from the guest to the host by following these steps:</span></span>

    1.  <span data-ttu-id="2710d-135">MED-V 尝试在名为与快捷方式所在的来宾中的文件夹相同的主机上的 "开始 Menu\\Programs" 下找到某个文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-135">MED-V tries to locate a folder under Start Menu\\Programs in the host computer that is named the same as the folder in the guest where the shortcut resides.</span></span>

    2.  <span data-ttu-id="2710d-136">如果没有匹配的文件夹，则 MED-V 会尝试在主机 "开始" 菜单文件夹中查找与快捷方式所在的来宾中的文件夹同名的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-136">If there is no matching folder, MED-V then tries to locate a folder in the host Start Menu folder that is named the same as the folder in the guest where the shortcut resides.</span></span>

    3.  <span data-ttu-id="2710d-137">如果没有匹配的文件夹，则 MED-V 会将指向主机上默认文件夹的快捷方式复制到 "开始 Menu\\Programs" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-137">If there is no matching folder, MED-V copies the shortcut to the default folder on the host, the Start Menu\\Programs folder.</span></span>

2.  <span data-ttu-id="2710d-138">应用程序发布过程示例：</span><span class="sxs-lookup"><span data-stu-id="2710d-138">Example of application publishing process:</span></span>

    1.  <span data-ttu-id="2710d-139">如果将应用程序快捷方式发布到来宾中的 "开始 Menu\\Programs\\AppShortcuts" 文件夹，则 MED-V 将在主机中查找 "开始 Menu\\Programs\\ AppShortcuts" 文件夹，如果找到，则将快捷方式复制到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-139">If an application shortcut is published to the Start Menu\\Programs\\AppShortcuts folder in the guest, then MED-V looks in the host computer for a Start Menu\\Programs\\ AppShortcuts folder and if found, copies the shortcut to that folder.</span></span>

    2.  <span data-ttu-id="2710d-140">如果找不到文件夹，则 MED-V 在主机中查找开始 Menu\\AppShortcuts 文件夹，如果找到，则将快捷方式复制到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-140">If the folder is not found, then MED-V looks in the host computer for a Start Menu\\AppShortcuts folder and if found, copies the shortcut to that folder.</span></span>

    3.  <span data-ttu-id="2710d-141">如果找不到文件夹，则 MED-V 会将快捷方式复制到 "开始 Menu\\Programs" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-141">If the folder is not found, then MED-V copies the shortcut to the Start Menu\\Programs folder.</span></span>

<span data-ttu-id="2710d-142">**注意** 在 MED-V 的主机 "开始" 菜单文件夹中，文件夹必须已存在，才能复制快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2710d-142">**Note** A folder must already exist in the host computer Start Menu folder for MED-V to copy the shortcut there.</span></span> <span data-ttu-id="2710d-143">如果文件夹尚不存在，则 MED-V 不会创建该文件夹。</span><span class="sxs-lookup"><span data-stu-id="2710d-143">MED-V does not create the folder if it does not already exist.</span></span>

 

## <span data-ttu-id="2710d-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="2710d-144">Related topics</span></span>


[<span data-ttu-id="2710d-145">在 MED-V 工作区上安装和删除应用程序</span><span class="sxs-lookup"><span data-stu-id="2710d-145">Installing and Removing an Application on the MED-V Workspace</span></span>](installing-and-removing-an-application-on-the-med-v-workspace.md)

[<span data-ttu-id="2710d-146">管理 MED-V 工作区的软件更新</span><span class="sxs-lookup"><span data-stu-id="2710d-146">Managing Software Updates for MED-V Workspaces</span></span>](managing-software-updates-for-med-v-workspaces.md)

[<span data-ttu-id="2710d-147">Windows Virtual PC 应用程序排除列表</span><span class="sxs-lookup"><span data-stu-id="2710d-147">Windows Virtual PC Application Exclude List</span></span>](windows-virtual-pc-application-exclude-list.md)

 

 





