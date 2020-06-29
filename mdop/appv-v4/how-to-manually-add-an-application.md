---
title: 如何手动添加应用程序
description: 如何手动添加应用程序
author: dansimp
ms.assetid: c635b07a-5c7f-4ab2-ba18-366457146cb9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 868939553fae6172ccca549ddc3f08aa76ee3c56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801280"
---
# <span data-ttu-id="03ff4-103">如何手动添加应用程序</span><span class="sxs-lookup"><span data-stu-id="03ff4-103">How to Manually Add an Application</span></span>


<span data-ttu-id="03ff4-104">将应用程序添加到应用程序虚拟化管理服务器时，建议将其导入。</span><span class="sxs-lookup"><span data-stu-id="03ff4-104">When adding an application to the Application Virtualization Management Server, it is recommended that you import it.</span></span> <span data-ttu-id="03ff4-105">你可以手动添加应用程序，但你必须提供本部分中所述的有关应用程序的确切详细信息。</span><span class="sxs-lookup"><span data-stu-id="03ff4-105">You can add an application manually, but you must provide the precise, detailed information about the application called for in this section.</span></span>

**<span data-ttu-id="03ff4-106">手动添加新的应用程序</span><span class="sxs-lookup"><span data-stu-id="03ff4-106">To manually add a new application</span></span>**

1.  <span data-ttu-id="03ff4-107">在左窗格中，右键单击 "**应用程序**" 节点，然后选择 "**新建应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="03ff4-107">In the left pane, right-click the **Applications** node and choose **New Application**.</span></span>

2.  <span data-ttu-id="03ff4-108">在 "**新建应用程序" 向导**中，完成 "**常规信息**" 对话框：</span><span class="sxs-lookup"><span data-stu-id="03ff4-108">In the **New Application Wizard**, complete the **General Information** dialog box:</span></span>

    1.  <span data-ttu-id="03ff4-109">"**应用程序名称**" —键入希望用户看到的名称。</span><span class="sxs-lookup"><span data-stu-id="03ff4-109">**Application Name**—Type the name you want the users to see.</span></span>

    2.  <span data-ttu-id="03ff4-110">**版本**-键入应用程序版本。</span><span class="sxs-lookup"><span data-stu-id="03ff4-110">**Version**—Type the application version.</span></span>

    3.  <span data-ttu-id="03ff4-111">**已启用**-在创建应用程序后，必须选中此框以流式传输应用程序。</span><span class="sxs-lookup"><span data-stu-id="03ff4-111">**Enabled**—This box must be selected to stream the application after you create it.</span></span>

    4.  <span data-ttu-id="03ff4-112">**说明**—键入管理使用的可选说明。</span><span class="sxs-lookup"><span data-stu-id="03ff4-112">**Description**—Type an optional description for administrative use.</span></span>

    5.  <span data-ttu-id="03ff4-113">**OSD 路径**-浏览网络到应用程序的开放式软件描述符（OSD）文件。</span><span class="sxs-lookup"><span data-stu-id="03ff4-113">**OSD Path**—Browse the network to the application's Open Software Descriptor (OSD) file.</span></span> <span data-ttu-id="03ff4-114">此文件必须位于共享网络文件夹中。</span><span class="sxs-lookup"><span data-stu-id="03ff4-114">This file must be in a shared network folder.</span></span>

    6.  <span data-ttu-id="03ff4-115">**图标路径**-浏览到应用程序的 .ico 文件。</span><span class="sxs-lookup"><span data-stu-id="03ff4-115">**Icon Path**—Browse to the application's ICO file.</span></span>

    7.  <span data-ttu-id="03ff4-116">**应用程序许可证组**-如果已设置许可证组，则可以通过在下拉列表中选择应用程序来将其分配给该应用程序。</span><span class="sxs-lookup"><span data-stu-id="03ff4-116">**Application License Group**—If you have set up license groups, you can assign the application to one by selecting it in the pull-down list.</span></span>

    8.  <span data-ttu-id="03ff4-117">**服务器组**-如果你有多个 Application Virtualization 服务器，则可以通过在下拉列表中选择应用程序来将其分配给一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="03ff4-117">**Server Group**—If you have multiple Application Virtualization Servers, you can assign the application to one by selecting it in the pull-down list.</span></span>

3.  <span data-ttu-id="03ff4-118">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="03ff4-118">Click **Next**.</span></span>

4.  <span data-ttu-id="03ff4-119">在 "**选择程序包**" 对话框中，选择相关程序包，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="03ff4-119">In the **Select Package** dialog box, select the related package and click **Next**.</span></span>

5.  <span data-ttu-id="03ff4-120">在 "**已发布的快捷方式**" 屏幕上，选择要在客户端计算机上显示应用程序快捷方式的位置的框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="03ff4-120">On the **Published Shortcuts** screen, select the boxes for the locations where you would like the application shortcuts to appear on the client computers and click **Next**.</span></span>

6.  <span data-ttu-id="03ff4-121">在 "**文件关联**" 屏幕中，可以向此应用程序添加新的类型文件关联。</span><span class="sxs-lookup"><span data-stu-id="03ff4-121">In the **File Associations** screen, you can add new type file associations to this application.</span></span> <span data-ttu-id="03ff4-122">若要执行此操作，请单击 "**添加**"，输入扩展名（不带上点），输入说明，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="03ff4-122">To do so, click **Add**, enter the extension (without a preceding dot), enter a description, and click **OK**.</span></span>

7.  <span data-ttu-id="03ff4-123">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="03ff4-123">Click **Next**.</span></span>

8.  <span data-ttu-id="03ff4-124">在 "**访问权限**" 对话框中，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="03ff4-124">In the **Access Permissions** dialog box, click **Add**.</span></span>

9.  <span data-ttu-id="03ff4-125">在 "**添加/编辑用户组**" 对话框中，导航到 "用户" 组。</span><span class="sxs-lookup"><span data-stu-id="03ff4-125">In the **Add/Edit User Group** dialog box, navigate to the user group.</span></span> <span data-ttu-id="03ff4-126">您也可以通过在相应字段中键入信息来输入域和组。</span><span class="sxs-lookup"><span data-stu-id="03ff4-126">You can also enter the domain and group by typing the information in the respective fields.</span></span> <span data-ttu-id="03ff4-127">完成后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="03ff4-127">When you finish, click **OK**.</span></span> <span data-ttu-id="03ff4-128">您可以添加具有相同页面的其他组。</span><span class="sxs-lookup"><span data-stu-id="03ff4-128">You can add other groups with the same pages.</span></span>

10. <span data-ttu-id="03ff4-129">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="03ff4-129">Click **Next**.</span></span>

11. <span data-ttu-id="03ff4-130">在 "**摘要**" 屏幕上，您可以查看导入设置。</span><span class="sxs-lookup"><span data-stu-id="03ff4-130">On the **Summary** screen, you can review the import settings.</span></span> <span data-ttu-id="03ff4-131">单击 "**完成**" 以添加应用程序，单击 "**返回**" 以更改信息，或单击 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="03ff4-131">Click **Finish** to add the application, click **Back** to change the information, or click **Cancel**.</span></span>

## <span data-ttu-id="03ff4-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="03ff4-132">Related topics</span></span>


[<span data-ttu-id="03ff4-133">如何在 Server Management Console 中管理应用程序</span><span class="sxs-lookup"><span data-stu-id="03ff4-133">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





