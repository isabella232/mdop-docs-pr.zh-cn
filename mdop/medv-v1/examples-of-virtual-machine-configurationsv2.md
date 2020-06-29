---
title: 虚拟机配置示例
description: 虚拟机配置示例
author: dansimp
ms.assetid: 5937601e-41ab-4ca2-8fa1-3c9154710cd6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b9fc7b1f88b2b30ea149fe73a387826fdbb2a66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803598"
---
# <span data-ttu-id="d9080-103">虚拟机配置示例</span><span class="sxs-lookup"><span data-stu-id="d9080-103">Examples of Virtual Machine Configurations</span></span>


<span data-ttu-id="d9080-104">下面是典型的虚拟机配置的示例：一个在永久性的 MED-V 工作区中，另一个位于 revertible MED-V 工作区中。</span><span class="sxs-lookup"><span data-stu-id="d9080-104">The following are examples of typical virtual machine configurations: one in a persistent MED-V workspace and one in a revertible MED-V workspace.</span></span>

<span data-ttu-id="d9080-105">**注意** 这些示例不适合在所有环境中使用。</span><span class="sxs-lookup"><span data-stu-id="d9080-105">**Note** These examples are not intended for use in all environments.</span></span> <span data-ttu-id="d9080-106">根据你的环境调整配置。</span><span class="sxs-lookup"><span data-stu-id="d9080-106">Adjust the configuration according to your environment.</span></span>

 

**<span data-ttu-id="d9080-107">在持久的 MED-V 工作区中配置典型域设置</span><span class="sxs-lookup"><span data-stu-id="d9080-107">To configure a typical domain setup in a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="d9080-108">在基本映像上配置 Sysprep 以创建唯一的 SID。</span><span class="sxs-lookup"><span data-stu-id="d9080-108">Configure Sysprep on the base image to create a unique SID.</span></span> <span data-ttu-id="d9080-109">有关详细信息，请参阅[创建 med-v 的虚拟 PC 映像](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages)。</span><span class="sxs-lookup"><span data-stu-id="d9080-109">For more information, see [Creating a Virtual PC Image for MED-V](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages).</span></span>

2.  <span data-ttu-id="d9080-110">在 " **VM 设置**" 选项卡上，选中 "**运行 VM 设置**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="d9080-110">On the **VM Setup** tab, select the **Run VM Setup** check box.</span></span>

3.  <span data-ttu-id="d9080-111">在 " **VM 计算机名称模式**" 部分中，配置计算机映像名称的模式。</span><span class="sxs-lookup"><span data-stu-id="d9080-111">In the **VM Computer Name Pattern** section, configure the pattern for the machine image name.</span></span> <span data-ttu-id="d9080-112">有关详细信息，请参阅[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="d9080-112">For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

4.  <span data-ttu-id="d9080-113">单击 "**脚本编辑器**"，然后在 " **VM 设置脚本编辑器**" 对话框中，配置以下操作：</span><span class="sxs-lookup"><span data-stu-id="d9080-113">Click **Script Editor**, and in the **VM Setup Script Editor** dialog box, configure the following actions:</span></span>

    1.  **<span data-ttu-id="d9080-114">重命名计算机</span><span class="sxs-lookup"><span data-stu-id="d9080-114">Rename Computer</span></span>**

    2.  **<span data-ttu-id="d9080-115">重启 Windows</span><span class="sxs-lookup"><span data-stu-id="d9080-115">Restart Windows</span></span>**

    3.  **<span data-ttu-id="d9080-116">检查连接性</span><span class="sxs-lookup"><span data-stu-id="d9080-116">Check Connectivity</span></span>**

    4.  **<span data-ttu-id="d9080-117">加入域</span><span class="sxs-lookup"><span data-stu-id="d9080-117">Join Domain</span></span>**

    5.  **<span data-ttu-id="d9080-118">禁用自动登录</span><span class="sxs-lookup"><span data-stu-id="d9080-118">Disable Auto-Logon</span></span>**

    <span data-ttu-id="d9080-119">有关详细信息，请参阅[如何设置脚本操作](how-to-set-up-script-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="d9080-119">For more information, see [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>

5.  <span data-ttu-id="d9080-120">在 "**策略**" 菜单上，单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="d9080-120">On the **Policy** menu, click **Commit**.</span></span>

**<span data-ttu-id="d9080-121">在 revertible 工作区中配置典型设置</span><span class="sxs-lookup"><span data-stu-id="d9080-121">To configure a typical setup in a revertible workspace</span></span>**

1.  <span data-ttu-id="d9080-122">在 " **VM 设置**" 选项卡上，选中 "**基于计算机名称模式重命名 VM** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="d9080-122">On the **VM Setup** tab, select the **Rename the VM based on the computer name pattern** check box.</span></span>

2.  <span data-ttu-id="d9080-123">在 " **VM 计算机名称模式**" 部分中，配置计算机映像名称的模式。</span><span class="sxs-lookup"><span data-stu-id="d9080-123">In the **VM Computer Name Pattern** section, configure the pattern for the machine image name.</span></span> <span data-ttu-id="d9080-124">有关详细信息，请参阅[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="d9080-124">For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

3.  <span data-ttu-id="d9080-125">在 "**策略**" 菜单上，单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="d9080-125">On the **Policy** menu, click **Commit**.</span></span>

## <span data-ttu-id="d9080-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="d9080-126">Related topics</span></span>


[<span data-ttu-id="d9080-127">如何为 MED-V 工作区配置虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="d9080-127">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[<span data-ttu-id="d9080-128">如何配置 VM 计算机名称模式属性</span><span class="sxs-lookup"><span data-stu-id="d9080-128">How to Configure VM Computer Name Pattern Properties</span></span>](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

[<span data-ttu-id="d9080-129">如何设置脚本操作</span><span class="sxs-lookup"><span data-stu-id="d9080-129">How to Set Up Script Actions</span></span>](how-to-set-up-script-actions.md)

 

 





