---
title: 如何配置 VM 计算机名称模式属性
description: 如何配置 VM 计算机名称模式属性
author: dansimp
ms.assetid: ddf79ace-8cc3-4ee6-be5a-5940b4df5c36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa171712b6624b73fb5e0756aaf56277baa4c8cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804096"
---
# <span data-ttu-id="a073a-103">如何配置 VM 计算机名称模式属性</span><span class="sxs-lookup"><span data-stu-id="a073a-103">How to Configure VM Computer Name Pattern Properties</span></span>


<span data-ttu-id="a073a-104">可以为 revertible 和持久的 MED-V 工作区分配虚拟机计算机名称模式。</span><span class="sxs-lookup"><span data-stu-id="a073a-104">A virtual machine computer name pattern can be assigned both for revertible and for persistent MED-V workspaces.</span></span>

-   <span data-ttu-id="a073a-105">Revertible-管理员可以为每个 Revertible MED-V 工作区实例分配一个唯一名称，以便使用同一 MED-V 工作区区分多台计算机。</span><span class="sxs-lookup"><span data-stu-id="a073a-105">Revertible—Administrators can assign a unique name to each revertible MED-V workspace instance to differentiate between multiple computers using the same MED-V workspace.</span></span>

-   <span data-ttu-id="a073a-106">持久性—在永久性的 MED-V 工作区中，管理员可以将计算机设置为在安装脚本期间重命名。</span><span class="sxs-lookup"><span data-stu-id="a073a-106">Persistent—In a persistent MED-V workspace, administrators can set a computer to be renamed during a setup script.</span></span>

## <span data-ttu-id="a073a-107">如何将虚拟机计算机名模式分配给 Revertible MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a073a-107">How to Assign a Virtual Machine Computer Name Pattern to a Revertible MED-V Workspace</span></span>


**<span data-ttu-id="a073a-108">将虚拟机计算机名模式分配给 revertible MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a073a-108">To assign a virtual machine computer name pattern to a revertible MED-V workspace</span></span>**

1.  <span data-ttu-id="a073a-109">单击要配置的 revertible MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="a073a-109">Click the revertible MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="a073a-110">在 " **REVERTIBLE VM 设置**" 部分中，选中 "**基于计算机名称模式重命名 VM** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="a073a-110">In the **Revertible VM Setup** section, select the **Rename the VM based on the computer name pattern** check box.</span></span>

3.  <span data-ttu-id="a073a-111">在 " **VM 计算机名称模式**" 部分中，输入用于命名虚拟机映像的模式，使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="a073a-111">In the **VM Computer Name Pattern** section, enter the pattern to use for naming virtual machine images, using the following options:</span></span>

    -   <span data-ttu-id="a073a-112">**常量**-使用 med-v 工作区输入将在所有计算机上保持不变的自由文本。</span><span class="sxs-lookup"><span data-stu-id="a073a-112">**Constant**—Enter free text that will be constant on all computers using the MED-V workspace.</span></span>

    -   <span data-ttu-id="a073a-113">**变量**-输入变量，方法是单击 "**插入变量**"，然后选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a073a-113">**Variable**—Enter a variable, by clicking **Insert Variable**, and select from one of the following:</span></span>

        -   **<span data-ttu-id="a073a-114">用户名</span><span class="sxs-lookup"><span data-stu-id="a073a-114">User name</span></span>**

        -   **<span data-ttu-id="a073a-115">域名</span><span class="sxs-lookup"><span data-stu-id="a073a-115">Domain name</span></span>**

        -   **<span data-ttu-id="a073a-116">主机名</span><span class="sxs-lookup"><span data-stu-id="a073a-116">Host name</span></span>**

        -   **<span data-ttu-id="a073a-117">工作区名称</span><span class="sxs-lookup"><span data-stu-id="a073a-117">Workspace name</span></span>**

        -   **<span data-ttu-id="a073a-118">虚拟机名称</span><span class="sxs-lookup"><span data-stu-id="a073a-118">Virtual machine name</span></span>**

        <span data-ttu-id="a073a-119">所选变量将使用 MED-V 工作区特定于计算机。</span><span class="sxs-lookup"><span data-stu-id="a073a-119">The variable selected will be specific to the computer using the MED-V workspace.</span></span> <span data-ttu-id="a073a-120">例如，如果选择了 "**域名**"，每台计算机的唯一名称将包含计算机的域名。</span><span class="sxs-lookup"><span data-stu-id="a073a-120">For example, if **Domain name** is selected, the unique name for each computer will include the computer's domain name.</span></span>

    -   <span data-ttu-id="a073a-121">**随机字符**-为要包括在模式中的每个随机字符输入 "\ #"。</span><span class="sxs-lookup"><span data-stu-id="a073a-121">**Random characters**—Enter “\#” for each random character to include in the pattern.</span></span> <span data-ttu-id="a073a-122">使用 MED-V 工作区的每台计算机都将具有指定长度的后缀，该后缀是随机生成的。</span><span class="sxs-lookup"><span data-stu-id="a073a-122">Each computer using the MED-V workspace will have a suffix of the length specified, which is generated randomly.</span></span>

    **<span data-ttu-id="a073a-123">注意</span><span class="sxs-lookup"><span data-stu-id="a073a-123">Note</span></span>**  
    <span data-ttu-id="a073a-124">计算机名的长度限制为15个字符。</span><span class="sxs-lookup"><span data-stu-id="a073a-124">The computer name has a limit of 15 characters.</span></span> <span data-ttu-id="a073a-125">如果模式超过限制，将被截尾取整。</span><span class="sxs-lookup"><span data-stu-id="a073a-125">If the pattern exceeds the limit, it will be truncated.</span></span>



4.  <span data-ttu-id="a073a-126">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="a073a-126">On the **Policy** menu, select **Commit**.</span></span>

    **<span data-ttu-id="a073a-127">注意</span><span class="sxs-lookup"><span data-stu-id="a073a-127">Note</span></span>**  
    <span data-ttu-id="a073a-128">仅当选中 "**基于计算机名称模式**（在**revertible VM 设置**" 部分）重命名 vm 时，才能分配 revertible vm 计算机名称模式。</span><span class="sxs-lookup"><span data-stu-id="a073a-128">A revertible VM computer name pattern can be assigned only when **Rename the VM based on the computer name patterns** (in the **Revertible VM Setup** section) is checked.</span></span>



~~~
**Note**  
A unique computer name can be assigned only if it is configured prior to MED-V workspace setup. Changing the name will not affect MED-V workspaces that were already set up.
~~~



## <span data-ttu-id="a073a-129">如何将虚拟机计算机名模式分配给持久的 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a073a-129">How to Assign a Virtual Machine Computer Name Pattern to a Persistent MED-V Workspace</span></span>


**<span data-ttu-id="a073a-130">将虚拟机计算机名模式分配给持久的 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a073a-130">To assign a virtual machine computer name pattern to a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="a073a-131">单击要配置的持久 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="a073a-131">Click the persistent MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="a073a-132">在 "**永久性 VM 设置**" 部分中，单击 "**脚本编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="a073a-132">In the **Persistent VM Setup** section, click **Script Editor**.</span></span>

3.  <span data-ttu-id="a073a-133">在 "**脚本操作**" 对话框中，单击 "**添加**"，然后在子菜单上单击 "**重命名计算机**"。</span><span class="sxs-lookup"><span data-stu-id="a073a-133">In the **Script Actions** dialog box, click **Add**, and on the submenu, click **Rename Computer**.</span></span>

4.  <span data-ttu-id="a073a-134">单击 **"确定"** 关闭 "**脚本操作**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="a073a-134">Click **OK** to close the **Script Actions** dialog box.</span></span>

5.  <span data-ttu-id="a073a-135">在 " **Vm 设置**" 选项卡上的 " **Vm 计算机名称模式**" 部分中，输入用于重命名计算机的模式，使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="a073a-135">On the **VM Setup** tab, in the **VM Computer Name Pattern** section, enter the pattern to use for renaming the computer, using the following:</span></span>

    -   <span data-ttu-id="a073a-136">**常量**-输入将包含在计算机名称中的任意文本。</span><span class="sxs-lookup"><span data-stu-id="a073a-136">**Constant**— Enter free text that will be included in the computer name.</span></span>

    -   <span data-ttu-id="a073a-137">**变量**-输入变量，方法是单击 "**插入变量**"，然后选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a073a-137">**Variable**—Enter a variable, by clicking **Insert Variable**, and select from one of the following:</span></span>

        -   **<span data-ttu-id="a073a-138">用户名</span><span class="sxs-lookup"><span data-stu-id="a073a-138">User name</span></span>**

        -   **<span data-ttu-id="a073a-139">域名</span><span class="sxs-lookup"><span data-stu-id="a073a-139">Domain name</span></span>**

        -   **<span data-ttu-id="a073a-140">主机名</span><span class="sxs-lookup"><span data-stu-id="a073a-140">Host name</span></span>**

        -   **<span data-ttu-id="a073a-141">工作区名称</span><span class="sxs-lookup"><span data-stu-id="a073a-141">Workspace name</span></span>**

        -   **<span data-ttu-id="a073a-142">虚拟机名称</span><span class="sxs-lookup"><span data-stu-id="a073a-142">Virtual machine name</span></span>**

        <span data-ttu-id="a073a-143">所选变量将特定于正在重命名的计算机。</span><span class="sxs-lookup"><span data-stu-id="a073a-143">The variable selected will be specific to the computer that is being renamed.</span></span> <span data-ttu-id="a073a-144">例如，如果选择了 "**域名**"，计算机名称将包含计算机的域名。</span><span class="sxs-lookup"><span data-stu-id="a073a-144">For example, if **Domain name** is selected, the computer name will include the computer's domain name.</span></span>

    -   <span data-ttu-id="a073a-145">**随机字符**-为要包括在模式中的每个随机字符输入 "\ #"。</span><span class="sxs-lookup"><span data-stu-id="a073a-145">**Random characters**— Enter “\#” for each random character to include in the pattern.</span></span> <span data-ttu-id="a073a-146">计算机将具有指定长度的后缀，该后缀是随机生成的。</span><span class="sxs-lookup"><span data-stu-id="a073a-146">The computer will have a suffix of the length specified, which is generated randomly.</span></span>

    **<span data-ttu-id="a073a-147">注意</span><span class="sxs-lookup"><span data-stu-id="a073a-147">Note</span></span>**  
    <span data-ttu-id="a073a-148">计算机名的长度限制为15个字符。</span><span class="sxs-lookup"><span data-stu-id="a073a-148">The computer name has a limit of 15 characters.</span></span> <span data-ttu-id="a073a-149">如果模式超过限制，将被截尾取整。</span><span class="sxs-lookup"><span data-stu-id="a073a-149">If the pattern exceeds the limit, it will be truncated.</span></span>



6.  <span data-ttu-id="a073a-150">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="a073a-150">On the **Policy** menu, select **Commit**.</span></span>

    **<span data-ttu-id="a073a-151">注意</span><span class="sxs-lookup"><span data-stu-id="a073a-151">Note</span></span>**  
    <span data-ttu-id="a073a-152">只有将计算机设置为 "**脚本操作**" 对话框中的操作时，才会重命名计算机。</span><span class="sxs-lookup"><span data-stu-id="a073a-152">The computer will be renamed only if it is set as an action in the **Script Actions** dialog box.</span></span> <span data-ttu-id="a073a-153">有关详细信息，请参阅[如何设置脚本操作](how-to-set-up-script-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="a073a-153">For detailed information, see [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>



## <span data-ttu-id="a073a-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="a073a-154">Related topics</span></span>


[<span data-ttu-id="a073a-155">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="a073a-155">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="a073a-156">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a073a-156">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="a073a-157">如何设置脚本操作</span><span class="sxs-lookup"><span data-stu-id="a073a-157">How to Set Up Script Actions</span></span>](how-to-set-up-script-actions.md)

[<span data-ttu-id="a073a-158">虚拟机配置示例</span><span class="sxs-lookup"><span data-stu-id="a073a-158">Examples of Virtual Machine Configurations</span></span>](examples-of-virtual-machine-configurationsv2.md)









