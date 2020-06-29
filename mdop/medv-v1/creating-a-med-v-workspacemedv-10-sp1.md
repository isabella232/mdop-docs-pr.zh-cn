---
title: 创建 MED-V 工作区
description: 创建 MED-V 工作区
author: dansimp
ms.assetid: 9578bb99-8a09-44c1-b88f-538901f16ad3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 189da6b28515f0d234c8a258138a27be7a7375d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803653"
---
# <span data-ttu-id="be876-103">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="be876-103">Creating a MED-V Workspace</span></span>


<span data-ttu-id="be876-104">MED-V 工作区是最终用户与 MED-V 提供的虚拟机交互的桌面环境。</span><span class="sxs-lookup"><span data-stu-id="be876-104">A MED-V workspace is the desktop environment in which end users interact with the virtual machine provided by MED-V.</span></span> <span data-ttu-id="be876-105">由管理员创建和自定义 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="be876-105">The MED-V workspace is created and customized by the administrator.</span></span> <span data-ttu-id="be876-106">它包含一个图像和策略，后者定义了 MED-V 工作区的规则和功能。</span><span class="sxs-lookup"><span data-stu-id="be876-106">It consists of an image and the policy, which defines the rules and functionality of the MED-V workspace.</span></span> <span data-ttu-id="be876-107">可以创建多个 MED-V 工作区，每个都有其自己的配置、设置和规则进行自定义。</span><span class="sxs-lookup"><span data-stu-id="be876-107">Multiple MED-V workspaces can be created, each customized with its own configuration, settings, and rules.</span></span> <span data-ttu-id="be876-108">用户、组或多个用户或组可以与每个 MED-V 工作区相关联，从而使 MED-V 工作区仅适用于关联的用户或组的计算机。</span><span class="sxs-lookup"><span data-stu-id="be876-108">A user, group, or multiple users or groups can be associated with each MED-V workspace, thereby making the MED-V workspace available only for the associated user's or group's computers.</span></span>

## <span data-ttu-id="be876-109">如何添加 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="be876-109">How to Add a MED-V Workspace</span></span>


**<span data-ttu-id="be876-110">添加 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="be876-110">To add a MED-V workspace</span></span>**

1.  <span data-ttu-id="be876-111">单击 "**策略**管理" 按钮以打开 "**策略**" 模块。</span><span class="sxs-lookup"><span data-stu-id="be876-111">Click the **Policy** management button to open the **Policy** module.</span></span>

    <span data-ttu-id="be876-112">**策略**模块由左侧的**工作区**菜单以及**常规**、**虚拟机**、**部署**、**应用程序**、 **Web**、 **VM 设置**、**网络**和**性能**选项卡组成。</span><span class="sxs-lookup"><span data-stu-id="be876-112">The **Policy** module consists of the **Workspaces** menu on the left and the **General**, **Virtual Machine**, **Deployment**, **Applications**, **Web**, **VM Setup**, **Network**, and **Performance** tabs.</span></span>

2.  <span data-ttu-id="be876-113">在 "**策略**" 菜单上，选择 "**新建工作区**"，或单击 "**添加**" 以创建新的 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="be876-113">On the **Policy** menu, select **New Workspace**, or click **Add** to create a new MED-V workspace.</span></span>

3.  <span data-ttu-id="be876-114">在 "**常规**" 选项卡上的 "**名称**" 字段中，输入 med-v 工作区的名称。</span><span class="sxs-lookup"><span data-stu-id="be876-114">On the **General** tab, in the **Name** field, enter the name of the MED-V workspace.</span></span>

4.  <span data-ttu-id="be876-115">在 "**说明**" 字段中，输入 med-v 工作区的说明。</span><span class="sxs-lookup"><span data-stu-id="be876-115">In the **Description** field, enter a description for the MED-V workspace.</span></span>

5.  <span data-ttu-id="be876-116">在 "**支持联系人信息**" 字段中，输入技术支持的联系信息。</span><span class="sxs-lookup"><span data-stu-id="be876-116">In the **Support contact info** field, enter the contact information for technical support.</span></span>

    <span data-ttu-id="be876-117">有关配置 MED-V 工作区的详细信息，请参阅[配置 Med-v 工作区策略](configuring-med-v-workspace-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="be876-117">For more information about configuring a MED-V workspace, see [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

## <span data-ttu-id="be876-118">如何克隆 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="be876-118">How to Clone a MED-V Workspace</span></span>


<span data-ttu-id="be876-119">可以克隆 MED-V 工作区，以便你可以创建与现有 MED-V 工作区相同的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="be876-119">A MED-V workspace can be cloned so that you can create a MED-V workspace identical to an existing MED-V workspace.</span></span>

**<span data-ttu-id="be876-120">克隆 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="be876-120">To clone a MED-V workspace</span></span>**

1.  <span data-ttu-id="be876-121">单击要克隆的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="be876-121">Click the MED-V workspace to clone.</span></span>

2.  <span data-ttu-id="be876-122">在 "**策略**" 菜单上，选择 "**复制工作区**"。</span><span class="sxs-lookup"><span data-stu-id="be876-122">On the **Policy** menu, select **Clone Workspace**.</span></span>

    <span data-ttu-id="be876-123">将创建一个新的 MED-V 工作区，其名称为 &lt; 原始的 med-v 工作区名称 &gt; -2。</span><span class="sxs-lookup"><span data-stu-id="be876-123">A new MED-V workspace is created with the name &lt;Original MED-V workspace name&gt; - 2.</span></span>

## <span data-ttu-id="be876-124">如何删除 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="be876-124">How to Delete a MED-V Workspace</span></span>


**<span data-ttu-id="be876-125">删除 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="be876-125">To delete a MED-V workspace</span></span>**

-   <span data-ttu-id="be876-126">在 "**策略**" 模块中，当工作区窗格处于焦点时，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="be876-126">In the **Policy** module, while the workspace pane is in focus, click **Remove**.</span></span>

## <span data-ttu-id="be876-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="be876-127">Related topics</span></span>


[<span data-ttu-id="be876-128">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="be876-128">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





