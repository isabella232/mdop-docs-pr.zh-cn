---
title: 如何为 MED-V 工作区配置虚拟机设置
description: 如何为 MED-V 工作区配置虚拟机设置
author: dansimp
ms.assetid: 50bbf58b-842c-4b63-bb93-3783903f6c7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0ba24f0e9aa5befeaf385acf06273a53feaae29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804095"
---
# <span data-ttu-id="b471f-103">如何为 MED-V 工作区配置虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="b471f-103">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>


<span data-ttu-id="b471f-104">所有虚拟机设置配置设置均在 " **VM 设置**" 选项卡上的 "**策略**" 模块中配置。</span><span class="sxs-lookup"><span data-stu-id="b471f-104">All virtual machine setup configuration settings are configured in the **Policy** module, on the **VM Setup** tab.</span></span>

## <span data-ttu-id="b471f-105">如何为持久的 MED-V 工作区配置虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="b471f-105">How to Configure the Virtual Machine Setup for a Persistent MED-V Workspace</span></span>


**<span data-ttu-id="b471f-106">为持久的 MED-V 工作区配置虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="b471f-106">To configure the virtual machine setup for a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="b471f-107">单击要配置的持久 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="b471f-107">Click a persistent MED-V workspace to be configured.</span></span>

2.  <span data-ttu-id="b471f-108">在 "**永久性 VM 设置**" 部分中，按下表中所述配置属性。</span><span class="sxs-lookup"><span data-stu-id="b471f-108">In the **Persistent VM Setup** section, configure the properties as described in the following table.</span></span>

    **<span data-ttu-id="b471f-109">注意</span><span class="sxs-lookup"><span data-stu-id="b471f-109">Note</span></span>**  
    <span data-ttu-id="b471f-110">仅对持久的 MED-V 工作区启用永久性 VM 设置属性。</span><span class="sxs-lookup"><span data-stu-id="b471f-110">The persistent VM setup properties are enabled only for a persistent MED-V workspace.</span></span>



3.  <span data-ttu-id="b471f-111">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="b471f-111">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="b471f-112">持久性 VM 设置属性</span><span class="sxs-lookup"><span data-stu-id="b471f-112">Persistent VM Setup Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b471f-113">属性</span><span class="sxs-lookup"><span data-stu-id="b471f-113">Property</span></span></th>
<th align="left"><span data-ttu-id="b471f-114">描述</span><span class="sxs-lookup"><span data-stu-id="b471f-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b471f-115">运行 VM 设置</span><span class="sxs-lookup"><span data-stu-id="b471f-115">Run VM Setup</span></span></p></td>
<td align="left"><p><span data-ttu-id="b471f-116">选中此复选框以在 MED-V 工作区首次运行时运行安装脚本。</span><span class="sxs-lookup"><span data-stu-id="b471f-116">Select this check box to run a setup script the first time the MED-V workspace is run.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b471f-117">脚本编辑器</span><span class="sxs-lookup"><span data-stu-id="b471f-117">Script Editor</span></span></p></td>
<td align="left"><p><span data-ttu-id="b471f-118">单击以配置安装脚本。</span><span class="sxs-lookup"><span data-stu-id="b471f-118">Click to configure the setup script.</span></span> <span data-ttu-id="b471f-119">有关详细信息，请参阅 <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)"> 如何设置脚本操作 </a> 。</span><span class="sxs-lookup"><span data-stu-id="b471f-119">For more information, see <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)">How to Set Up Script Actions</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b471f-120">注意</span><span class="sxs-lookup"><span data-stu-id="b471f-120">Note</span></span></strong><br/><p><span data-ttu-id="b471f-121">仅当选择了 " <strong> 运行 VM 安装脚本" 时，此按钮才会启用 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b471f-121">This button is enabled only when <strong>Run VM Setup script</strong> is selected.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b471f-122">脚本运行时显示的消息</span><span class="sxs-lookup"><span data-stu-id="b471f-122">Message displayed when script is running</span></span></p></td>
<td align="left"><p><span data-ttu-id="b471f-123">在脚本运行时要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="b471f-123">A message to be displayed while the script is running.</span></span> <span data-ttu-id="b471f-124">如果保留为空，则显示默认消息。</span><span class="sxs-lookup"><span data-stu-id="b471f-124">If left blank, the default message is displayed.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b471f-125">注意</span><span class="sxs-lookup"><span data-stu-id="b471f-125">Note</span></span></strong><br/><p><span data-ttu-id="b471f-126">仅当 <strong> 选中 "运行 VM 安装脚本" 时，才会启用此字段 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b471f-126">This field is enabled only when <strong>Run VM Setup script</strong> is checked.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b471f-127">如何配置 Revertible MED-V 工作区的虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="b471f-127">How to Configure the Virtual Machine Setup for a Revertible MED-V Workspace</span></span>


**<span data-ttu-id="b471f-128">为 revertible MED-V 工作区配置虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="b471f-128">To configure the virtual machine setup for a revertible MED-V workspace</span></span>**

1.  <span data-ttu-id="b471f-129">单击要配置的 revertible MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="b471f-129">Click a revertible MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="b471f-130">在**REVERTIBLE VM 设置**部分中，按下表中所述配置属性。</span><span class="sxs-lookup"><span data-stu-id="b471f-130">In the **Revertible VM Setup** section, configure the properties as described in the following table.</span></span>

    **<span data-ttu-id="b471f-131">注意</span><span class="sxs-lookup"><span data-stu-id="b471f-131">Note</span></span>**  
    <span data-ttu-id="b471f-132">仅对 revertible MED-V 工作区启用 revertible VM 设置属性。</span><span class="sxs-lookup"><span data-stu-id="b471f-132">The revertible VM setup properties are enabled only for a revertible MED-V workspace.</span></span>



3.  <span data-ttu-id="b471f-133">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="b471f-133">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="b471f-134">Revertible VM 设置属性</span><span class="sxs-lookup"><span data-stu-id="b471f-134">Revertible VM Setup Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b471f-135">属性</span><span class="sxs-lookup"><span data-stu-id="b471f-135">Property</span></span></th>
<th align="left"><span data-ttu-id="b471f-136">描述</span><span class="sxs-lookup"><span data-stu-id="b471f-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b471f-137">基于计算机名称模式重命名 VM</span><span class="sxs-lookup"><span data-stu-id="b471f-137">Rename the VM based on the computer name pattern</span></span></p></td>
<td align="left"><p><span data-ttu-id="b471f-138">选中此复选框可使用 MED-V 工作区为每台计算机分配唯一名称，以便你可以使用相同的 MED-V 工作区区分多台计算机。</span><span class="sxs-lookup"><span data-stu-id="b471f-138">Select this check box to assign a unique name to each computer using the MED-V workspace so that you can differentiate between multiple computers using the same MED-V workspace.</span></span></p>
<p><span data-ttu-id="b471f-139">有关配置计算机映像名称的详细信息，请参阅 <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)"> 如何配置 VM 计算机名称模式属性 </a> 。</span><span class="sxs-lookup"><span data-stu-id="b471f-139">For more information on configuring computer image names, see <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)">How to Configure VM Computer Name Pattern Properties</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b471f-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="b471f-140">Related topics</span></span>


[<span data-ttu-id="b471f-141">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="b471f-141">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="b471f-142">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="b471f-142">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="b471f-143">虚拟机配置示例</span><span class="sxs-lookup"><span data-stu-id="b471f-143">Examples of Virtual Machine Configurations</span></span>](examples-of-virtual-machine-configurationsv2.md)









