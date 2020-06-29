---
title: 如何导入应用程序
description: 如何导入应用程序
author: dansimp
ms.assetid: ab40acad-1025-478d-8e13-0e1ff1bd37e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d9cd6d065ca28b5d856acdae7d10a1280105e9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801403"
---
# <span data-ttu-id="04af8-103">如何导入应用程序</span><span class="sxs-lookup"><span data-stu-id="04af8-103">How to Import an Application</span></span>


<span data-ttu-id="04af8-104">通常，你可以导入应用程序以使其可从应用程序虚拟化管理服务器流出。</span><span class="sxs-lookup"><span data-stu-id="04af8-104">Typically, you import applications to make them available to stream from an Application Virtualization Management Server.</span></span> <span data-ttu-id="04af8-105">你还可以手动添加应用程序，但必须提供有关应用程序的精确的详细信息来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="04af8-105">You can also add an application manually, but you must provide precise, detailed information about the application to do so.</span></span> <span data-ttu-id="04af8-106">有关详细信息，请参阅[如何手动添加应用程序](how-to-manually-add-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="04af8-106">For more information, see [How to Manually Add an Application](how-to-manually-add-an-application.md).</span></span>

<span data-ttu-id="04af8-107">**注意** 若要导入应用程序，你必须在服务器上具有已排序的开放式软件描述符（OSD）文件或其 Sequencer 项目（SPRJ）文件。</span><span class="sxs-lookup"><span data-stu-id="04af8-107">**Note** To import an application, you must have its sequenced Open Software Descriptor (OSD) file or its Sequencer Project (SPRJ) file available on the server.</span></span>

 

<span data-ttu-id="04af8-108">导入应用程序时，应确保服务器在 "**系统选项**" 对话框的 "**常规**" 选项卡上的 "**默认内容路径**" 字段中配置了一个值（可通过右键单击 App-v Server 控制台中的 "**应用程序虚拟化系统**" 节点进行访问）。</span><span class="sxs-lookup"><span data-stu-id="04af8-108">When importing an application, you should make sure the server is configured with a value in the **Default Content Path** field on the **General** tab of the **System Options** dialog (accessible by right-clicking the **Application Virtualization System** node in the App-V Server Console).</span></span> <span data-ttu-id="04af8-109">默认内容路径值定义将在何处导入应用程序，在导入过程中，此值用于修改在 OSD 文件中为 SFT 文件和图标快捷方式定义的路径。</span><span class="sxs-lookup"><span data-stu-id="04af8-109">The default content path value defines where the applications will be imported, and during the import process, this value is used to modify the paths defined in the OSD file for the SFT file and for the icon shortcuts.</span></span> <span data-ttu-id="04af8-110">在 OSD 文件中，SFT 文件的路径在基本代码 HREF 条目中指定，图标的路径在快捷方式条目中指定。</span><span class="sxs-lookup"><span data-stu-id="04af8-110">In the OSD file, the path for the SFT file is specified in the CODEBASE HREF entry and the path for the icons is specified in the SHORTCUTS entry.</span></span>

<span data-ttu-id="04af8-111">在导入过程中，在 "协议"、"服务器" 和 "（如果存在）" 中，在 OSD 文件的这两个路径中指定的端口将替换为默认内容路径中的值。</span><span class="sxs-lookup"><span data-stu-id="04af8-111">During the import process, the protocol, server, and, if present, port specified in these two paths in the OSD file will be replaced with the value from the default content path.</span></span> <span data-ttu-id="04af8-112">下表提供了导入路径将受到影响的示例。</span><span class="sxs-lookup"><span data-stu-id="04af8-112">The following table provides an example of how the import path will be affected.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="04af8-113">默认内容路径</span><span class="sxs-lookup"><span data-stu-id="04af8-113">Default Content Path</span></span></th>
<th align="left"><span data-ttu-id="04af8-114">OSD 文件基本代码 HREF</span><span class="sxs-lookup"><span data-stu-id="04af8-114">OSD File CODEBASE HREF</span></span></th>
<th align="left"><span data-ttu-id="04af8-115">结果值</span><span class="sxs-lookup"><span data-stu-id="04af8-115">Resulting Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04af8-116">\server\content &lt; /p&gt;</span><span class="sxs-lookup"><span data-stu-id="04af8-116">\server\content&lt;/p&gt;</span></span></td>
<td align="left"><p><a href="http://WebServer/myFolder/package.sft" data-raw-source="http://WebServer/myFolder/package.sft">http://WebServer/myFolder/package.sft</a></p></td>
<td align="left"><p><span data-ttu-id="04af8-117">\server\content\myFolder\package.sft</span><span class="sxs-lookup"><span data-stu-id="04af8-117">\server\content\myFolder\package.sft</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="04af8-118">导入应用程序</span><span class="sxs-lookup"><span data-stu-id="04af8-118">To import an application</span></span>**

1.  <span data-ttu-id="04af8-119">右键单击左窗格中的 "**应用程序**" 节点，然后选择 "**导入应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="04af8-119">Right-click the **Applications** node in the left pane, and choose **Import Applications**.</span></span>

2.  <span data-ttu-id="04af8-120">在 "**打开**" 对话框中，导航到应用程序的 SPRJ 或 OSD 文件。</span><span class="sxs-lookup"><span data-stu-id="04af8-120">In the **Open** dialog box, navigate to the application's SPRJ or OSD file.</span></span> <span data-ttu-id="04af8-121">突出显示该文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="04af8-121">Highlight the file and click **Open**.</span></span>

3.  <span data-ttu-id="04af8-122">在 "**新建应用程序" 向导**中，确保已选中要传输的应用程序的 "**启用**" 框。</span><span class="sxs-lookup"><span data-stu-id="04af8-122">In the **New Application Wizard**, be sure the **Enabled** box is selected for applications you want to stream.</span></span> <span data-ttu-id="04af8-123">您也可以输入说明并验证服务器和文件路径。</span><span class="sxs-lookup"><span data-stu-id="04af8-123">There you can also enter a description and verify the server and file paths.</span></span> <span data-ttu-id="04af8-124">此外，如果你已设置许可证和服务器组，你可以选择这些组。</span><span class="sxs-lookup"><span data-stu-id="04af8-124">Also, if you have set up license and server groups, you can select those.</span></span>

4.  <span data-ttu-id="04af8-125">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04af8-125">Click **Next**.</span></span>

5.  <span data-ttu-id="04af8-126">在 "**已发布的快捷方式**" 屏幕上，选择要在客户端计算机上显示应用程序快捷方式的位置的框。</span><span class="sxs-lookup"><span data-stu-id="04af8-126">On the **Published Shortcuts** screen, select the boxes for the locations where you would like the application shortcuts to appear on the client computers.</span></span>

6.  <span data-ttu-id="04af8-127">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04af8-127">Click **Next**.</span></span>

7.  <span data-ttu-id="04af8-128">在 "**文件关联**" 屏幕中，你可以向此应用程序添加新的文件关联。</span><span class="sxs-lookup"><span data-stu-id="04af8-128">In the **File Associations** screen, you can add new file associations to this application.</span></span> <span data-ttu-id="04af8-129">若要执行此操作，请单击 "**添加**"，输入扩展名（不带上点），输入说明，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="04af8-129">To do so, click **Add**, enter the extension (without a preceding dot), enter a description, and click **OK**.</span></span>

    <span data-ttu-id="04af8-130">**注意** 使用 Sequencer 4.0 排序的应用程序在通过管理控制台导入或创建文件时，将填充 "**文件关联**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="04af8-130">**Note** Applications sequenced with Sequencer 4.0 populate the **File Associations** dialog box when you import or create them through the management console.</span></span> <span data-ttu-id="04af8-131">以前的 Sequencer 版本程序包的应用程序不是。</span><span class="sxs-lookup"><span data-stu-id="04af8-131">Applications with previous Sequencer version packages do not.</span></span>

     

8.  <span data-ttu-id="04af8-132">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04af8-132">Click **Next**.</span></span>

9.  <span data-ttu-id="04af8-133">在 "**访问权限**" 屏幕中，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="04af8-133">In the **Access Permissions** screen, click **Add**.</span></span>

10. <span data-ttu-id="04af8-134">完成 "**选择组**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="04af8-134">Complete the **Select Groups** dialog box.</span></span> <span data-ttu-id="04af8-135">完成后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="04af8-135">When you finish, click **OK**.</span></span>

11. <span data-ttu-id="04af8-136">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04af8-136">Click **Next**.</span></span>

12. <span data-ttu-id="04af8-137">在 "**摘要**" 屏幕上，您可以查看导入设置。</span><span class="sxs-lookup"><span data-stu-id="04af8-137">On the **Summary** screen, you can review the import settings.</span></span> <span data-ttu-id="04af8-138">单击 "**完成**"，或单击 "**返回**" 以更改导入，或单击 "**取消**" 以取消导入。</span><span class="sxs-lookup"><span data-stu-id="04af8-138">Click **Finish**, or click **Back** to change the import or click **Cancel** to cancel the import.</span></span>

## <span data-ttu-id="04af8-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="04af8-139">Related topics</span></span>


[<span data-ttu-id="04af8-140">如何在 Server Management Console 中管理应用程序组</span><span class="sxs-lookup"><span data-stu-id="04af8-140">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="04af8-141">如何在 Server Management Console 中管理应用程序</span><span class="sxs-lookup"><span data-stu-id="04af8-141">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

[<span data-ttu-id="04af8-142">如何手动添加应用程序</span><span class="sxs-lookup"><span data-stu-id="04af8-142">How to Manually Add an Application</span></span>](how-to-manually-add-an-application.md)

 

 





