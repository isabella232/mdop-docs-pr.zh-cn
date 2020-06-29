---
title: Windows Virtual PC 应用程序排除列表
description: Windows Virtual PC 应用程序排除列表
author: dansimp
ms.assetid: 7715f198-f5ed-421e-8740-0cec2ca4ece3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/28/2017
ms.openlocfilehash: 190049ce99865ef237d8d26e14a8279def7da521
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803419"
---
# <span data-ttu-id="74fce-103">Windows Virtual PC 应用程序排除列表</span><span class="sxs-lookup"><span data-stu-id="74fce-103">Windows Virtual PC Application Exclude List</span></span>


<span data-ttu-id="74fce-104">在某些情况下，你可能不希望将 MED-V 工作区中安装的应用程序发布到主计算机的 "**开始**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="74fce-104">In some instances, you might not want applications that are installed in the MED-V workspace to be published to the host computer **Start** menu.</span></span> <span data-ttu-id="74fce-105">你可以按照有关[如何在 Med-v 工作区中发布和取消发布应用程序](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)的说明，取消发布这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="74fce-105">You can unpublish these applications by following the instructions at [How to Publish and Unpublish an Application on the MED-V Workspace](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md).</span></span> <span data-ttu-id="74fce-106">但是，如果程序自动更新，也可能会自动重新发布它。</span><span class="sxs-lookup"><span data-stu-id="74fce-106">However, if the program ever automatically updates, it might also be automatically republished.</span></span> <span data-ttu-id="74fce-107">这使你必须再次取消发布该应用程序。</span><span class="sxs-lookup"><span data-stu-id="74fce-107">This causes you to have to unpublish the application again.</span></span>

<span data-ttu-id="74fce-108">Windows 虚拟 PC 包含一个称为 "排除列表" 的功能，可用于指定不希望发布到主机 "**开始**" 菜单的某些已安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="74fce-108">Windows Virtual PC includes a feature known as the "Exclude List" that lets you specify certain installed applications that you do not want published to the host **Start** menu.</span></span> <span data-ttu-id="74fce-109">"排除列表" 位于 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 项的来宾注册表中，列出未发布到主机 "**开始**" 菜单的应用程序。</span><span class="sxs-lookup"><span data-stu-id="74fce-109">The "Exclude List" is located in the guest registry in the HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList key and lists those applications that are not published to the host **Start** menu.</span></span> <span data-ttu-id="74fce-110">你可以将 "排除列表" 视为永久取消发布指定的应用程序，因为列出的应用程序的任何自动更新将不会导致自动重新发布。</span><span class="sxs-lookup"><span data-stu-id="74fce-110">You can think of the “Exclude List” as permanently unpublishing the specified applications because any automatic updates to the applications that are listed will not cause them to be automatically republished.</span></span>

## <span data-ttu-id="74fce-111">使用 Windows 虚拟 PC 中的排除列表管理应用程序</span><span class="sxs-lookup"><span data-stu-id="74fce-111">Managing Applications by Using the Exclude List in Windows Virtual PC</span></span>


****

1.  <span data-ttu-id="74fce-112">以全屏打开 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="74fce-112">Open the MED-V workspace in full screen.</span></span>

    <span data-ttu-id="74fce-113">有关使用 MED-V 管理工具包以全屏模式打开 MED-V 工作区的信息，请参阅[查看 Med-v 工作区配置](viewing-med-v-workspace-configurations.md#bkmk-fullscreen)。</span><span class="sxs-lookup"><span data-stu-id="74fce-113">For information about opening the MED-V workspace in full-screen mode by using the MED-V Administration Toolkit, see [Viewing MED-V Workspace Configurations](viewing-med-v-workspace-configurations.md#bkmk-fullscreen).</span></span> <span data-ttu-id="74fce-114">或者，您可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 Pc**"，单击 " **windows 虚拟**pc"，然后双击 "med-v" 工作区，以在全屏方式手动打开它。</span><span class="sxs-lookup"><span data-stu-id="74fce-114">Or you can manually open it in full screen by clicking **Start**, click **All Programs**, click **Windows Virtual PC**, click **Windows Virtual PC**, and then double-click the MED-V workspace.</span></span>

2.  <span data-ttu-id="74fce-115">在 MED-V 工作区 Windows 虚拟 PC 窗口中，打开注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="74fce-115">In the MED-V workspace Windows Virtual PC window, open Registry Editor.</span></span>

    <span data-ttu-id="74fce-116">单击 "**开始**"，单击 "**运行**"，然后键入 regedit。</span><span class="sxs-lookup"><span data-stu-id="74fce-116">Click **Start**, click **Run**, and then type regedit.</span></span> <span data-ttu-id="74fce-117">然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="74fce-117">Then click **OK**.</span></span>

3.  <span data-ttu-id="74fce-118">在注册表编辑器中，找到 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 注册表项。</span><span class="sxs-lookup"><span data-stu-id="74fce-118">In Registry Editor, locate the HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList registry key.</span></span>

4.  <span data-ttu-id="74fce-119">为不希望发布到主机计算机 "**开始**" 菜单的已安装应用程序创建新的注册表值。</span><span class="sxs-lookup"><span data-stu-id="74fce-119">Create a new registry value for the installed application that you do not want published to the host computer **Start** menu.</span></span> <span data-ttu-id="74fce-120">例如，如果要取消发布自动发布的程序 Microsoft Silverlight，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="74fce-120">For example, if you want to unpublish the automatically published program Microsoft Silverlight, follow these steps:</span></span>

    1.  <span data-ttu-id="74fce-121">突出显示 VPCVAppExcludeList 注册表项，单击 "**编辑**"，单击 "**新建**"，然后单击 "**字符串值**"。</span><span class="sxs-lookup"><span data-stu-id="74fce-121">With the VPCVAppExcludeList registry key highlighted, click **Edit**, click **New**, and then click **String Value**.</span></span>

    2.  <span data-ttu-id="74fce-122">输入新注册表值的名称。</span><span class="sxs-lookup"><span data-stu-id="74fce-122">Enter the name for the new registry value.</span></span> <span data-ttu-id="74fce-123">例如，对于 Microsoft Silverlight，你可以输入 sllauncher.exe。</span><span class="sxs-lookup"><span data-stu-id="74fce-123">For example, for Microsoft Silverlight, you might enter sllauncher.exe.</span></span>

    3.  <span data-ttu-id="74fce-124">双击新的注册表值，然后输入值数据。</span><span class="sxs-lookup"><span data-stu-id="74fce-124">Double-click the new registry value and enter the value data.</span></span>

        <span data-ttu-id="74fce-125">"值数据" 是要取消发布的命令的完整路径。</span><span class="sxs-lookup"><span data-stu-id="74fce-125">The value data is the full path for the command that you want to unpublish.</span></span> <span data-ttu-id="74fce-126">你可以通过右键单击不希望发布的应用程序的 "**开始**" 菜单上的快捷方式，然后单击 "**属性**" 来查找完整路径。</span><span class="sxs-lookup"><span data-stu-id="74fce-126">You can find the full path by right-clicking on the shortcut on the **Start** menu for the application that you do not want published and then clicking **Properties**.</span></span> <span data-ttu-id="74fce-127">完整路径在 "**目标**" 下的 "**快捷方式**" 选项卡中列出。</span><span class="sxs-lookup"><span data-stu-id="74fce-127">The full path is listed in the **Shortcut** tab under **Target**.</span></span>

        <span data-ttu-id="74fce-128">例如，对于程序 Microsoft Silverlight，完整路径可能是 "C:\\program files Files\\Microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe"。</span><span class="sxs-lookup"><span data-stu-id="74fce-128">For example, for the program Microsoft Silverlight, the full path might be "C:\\Program Files\\Microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe."</span></span>

        <span data-ttu-id="74fce-129">**重要提示** 如果适用，在将完整路径输入到 "值数据" 字段中时，请删除完整路径中的引号。</span><span class="sxs-lookup"><span data-stu-id="74fce-129">**Important** If applicable, remove the quotation marks from the full path when you enter it into the value data field.</span></span>

         

5.  <span data-ttu-id="74fce-130">关闭注册表编辑器，然后重新启动 MED-V 工作区虚拟机。</span><span class="sxs-lookup"><span data-stu-id="74fce-130">Close Registry Editor and restart the MED-V workspace virtual machine.</span></span>

    <span data-ttu-id="74fce-131">应用程序仍安装在 MED-V 工作区中，但现在从主机 "**开始**" 菜单中被删除。</span><span class="sxs-lookup"><span data-stu-id="74fce-131">The application is still installed in the MED-V workspace but is now removed from the host computer **Start** menu.</span></span>

<span data-ttu-id="74fce-132">还可以通过从 VPCVAppExcludeList 键中删除相应的值来将排除的应用程序发布到主机 "**开始**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="74fce-132">You can also republish an excluded application to the host **Start** menu by deleting the corresponding value from the VPCVAppExcludeList key.</span></span> <span data-ttu-id="74fce-133">例如，若要重新发布 Microsoft Silverlight，请右键单击注册表值 sllauncher.exe 然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="74fce-133">For example, to republish Microsoft Silverlight, right-click the registry value sllauncher.exe and select **Delete**.</span></span>

## <span data-ttu-id="74fce-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="74fce-134">Related topics</span></span>


[<span data-ttu-id="74fce-135">MED-V 的技术参考</span><span class="sxs-lookup"><span data-stu-id="74fce-135">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

[<span data-ttu-id="74fce-136">如何在 MED-V 工作区上发布和取消发布应用程序</span><span class="sxs-lookup"><span data-stu-id="74fce-136">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





