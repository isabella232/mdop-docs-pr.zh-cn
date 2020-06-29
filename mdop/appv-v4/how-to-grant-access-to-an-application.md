---
title: 如何授予对应用程序的访问权限
description: 如何授予对应用程序的访问权限
author: dansimp
ms.assetid: e54d9e84-21f5-488f-b040-25f374d9289f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9cd3dfe4661f09bb7e7d3514a397955cb892be81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801415"
---
# <span data-ttu-id="bd848-103">如何授予对应用程序的访问权限</span><span class="sxs-lookup"><span data-stu-id="bd848-103">How to Grant Access to an Application</span></span>


<span data-ttu-id="bd848-104">作为管理员，你可以使用应用程序虚拟化服务器管理控制台确定哪些用户可以访问哪些应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd848-104">As the administrator, you can use the Application Virtualization Server Management Console to determine which users can access which applications.</span></span> <span data-ttu-id="bd848-105">你可以在导入 Sequencer 项目（SPRJ）或打开软件描述符（OSD）文件时或使用应用程序的 "**属性**" 对话框的任何时候执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bd848-105">You can do this when you import the Sequencer Project (SPRJ) or Open Software Descriptor (OSD) file or at anytime using the application's **Properties** dialog box.</span></span> <span data-ttu-id="bd848-106">对于这两种方法，请使用 "**访问权限**" 选项添加用户。</span><span class="sxs-lookup"><span data-stu-id="bd848-106">With both methods, use the **Access Permissions** options to add users.</span></span>

**<span data-ttu-id="bd848-107">向应用程序授予访问权限</span><span class="sxs-lookup"><span data-stu-id="bd848-107">To grant access to an application</span></span>**

1.  <span data-ttu-id="bd848-108">对于现有应用程序，请单击左窗格中的 "**应用程序**" 节点。</span><span class="sxs-lookup"><span data-stu-id="bd848-108">For an existing application, click the **Applications** node in the left pane.</span></span> <span data-ttu-id="bd848-109">右键单击右窗格中的应用程序，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="bd848-109">Right-click an application in the right pane, and choose **Properties**.</span></span>

2.  <span data-ttu-id="bd848-110">选择 "**访问权限**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bd848-110">Select the **Access Permissions** tab.</span></span>

3.  <span data-ttu-id="bd848-111">若要添加用户组，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="bd848-111">To add user groups, click **Add**.</span></span>

4.  <span data-ttu-id="bd848-112">在 "**添加/编辑用户组**" 对话框中，导航到 "用户" 组。</span><span class="sxs-lookup"><span data-stu-id="bd848-112">In the **Add/Edit User Group** dialog box, navigate to the user group.</span></span> <span data-ttu-id="bd848-113">您也可以通过在相应字段中键入信息来输入域和组。</span><span class="sxs-lookup"><span data-stu-id="bd848-113">You can also enter the domain and group by typing the information in the respective fields.</span></span>

5.  <span data-ttu-id="bd848-114">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd848-114">Click **OK**.</span></span> <span data-ttu-id="bd848-115">您可以添加具有相同页面的其他组。</span><span class="sxs-lookup"><span data-stu-id="bd848-115">You can add other groups with the same pages.</span></span>

6.  <span data-ttu-id="bd848-116">当向导再次出现时，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bd848-116">When the wizard reappears, click **OK**.</span></span>

    <span data-ttu-id="bd848-117">**注意** 在尝试授予对应用程序的访问权限之前，必须在 Active Directory 域服务中设置组。</span><span class="sxs-lookup"><span data-stu-id="bd848-117">**Note** You must set up your groups in Active Directory Domain Services before you attempt to grant access to applications.</span></span>

     

## <span data-ttu-id="bd848-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd848-118">Related topics</span></span>


[<span data-ttu-id="bd848-119">如何拒绝对应用程序的访问</span><span class="sxs-lookup"><span data-stu-id="bd848-119">How to Deny Access to an Application</span></span>](how-to-deny-access-to-an-application.md)

[<span data-ttu-id="bd848-120">如何在 Server Management Console 中管理应用程序组</span><span class="sxs-lookup"><span data-stu-id="bd848-120">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="bd848-121">如何在 Server Management Console 中管理应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="bd848-121">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="bd848-122">如何手动添加应用程序</span><span class="sxs-lookup"><span data-stu-id="bd848-122">How to Manually Add an Application</span></span>](how-to-manually-add-an-application.md)

 

 





