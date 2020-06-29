---
title: 如何配置域用户或组
description: 如何配置域用户或组
author: dansimp
ms.assetid: 055aba81-a9c9-4b98-969d-775e603becf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c51da13808df657c1341572767c24860d9d5e8b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804120"
---
# <span data-ttu-id="a4a8d-103">如何配置域用户或组</span><span class="sxs-lookup"><span data-stu-id="a4a8d-103">How to Configure a Domain User or Group</span></span>


<span data-ttu-id="a4a8d-104">部署设置使你能够控制哪些用户或组可以访问 MED-V 工作区，以及可以使用 MED-V 工作区的时间以及它是否可以脱机使用。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-104">The deployment settings enable you to control which users or groups can access the MED-V workspace, as well as how long the MED-V workspace can be utilized and whether it can be used offline.</span></span> <span data-ttu-id="a4a8d-105">你还可以配置其他规则来控制 MED-V 工作区和主机之间的访问。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-105">You can also configure additional rules to control access between the MED-V workspace and the host.</span></span>

<span data-ttu-id="a4a8d-106">所有 MED-V 工作区权限都在 "**部署**" 选项卡上的 "**策略**" 模块中配置。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-106">All MED-V workspace permissions are configured in the **Policy** module, on the **Deployment** tab.</span></span>

<span data-ttu-id="a4a8d-107">若要允许用户利用 MED-V 工作区，必须首先将域用户或组添加到 MED-V 工作区权限。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-107">To allow users to utilize the MED-V workspace, you must first add domain users or groups to the MED-V workspace permissions.</span></span> <span data-ttu-id="a4a8d-108">然后，你可以为每个用户或组设置权限。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-108">You can then set permissions for each user or group.</span></span>

## <span data-ttu-id="a4a8d-109">如何添加域用户或组</span><span class="sxs-lookup"><span data-stu-id="a4a8d-109">How to Add a Domain User or Group</span></span>


**<span data-ttu-id="a4a8d-110">添加域用户或组</span><span class="sxs-lookup"><span data-stu-id="a4a8d-110">To add a domain user or group</span></span>**

1.  <span data-ttu-id="a4a8d-111">在 "**用户/组**" 窗口中，单击 "**添加"。**</span><span class="sxs-lookup"><span data-stu-id="a4a8d-111">In the **Users / Groups** window, click **Add.**</span></span>

2.  <span data-ttu-id="a4a8d-112">在 "**输入用户或组名称**" 对话框中，通过执行下列操作之一选择 "域用户" 或 "组"：</span><span class="sxs-lookup"><span data-stu-id="a4a8d-112">In the **Enter User or Group names** dialog box, select domain users or groups by doing one of the following:</span></span>

    -   <span data-ttu-id="a4a8d-113">在 "**输入用户或组名称**" 字段中，键入域中存在的用户或组，或者键入作为计算机上的本地用户或组的用户或组。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-113">In the **Enter User or Group names** field, type a user or group that exists in the domain or as a local user or group on the computer.</span></span> <span data-ttu-id="a4a8d-114">然后单击 "**检查姓名**" 以将其解析为完整的现有名称。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-114">Then click **Check Names** to resolve it to the full existent name.</span></span>

    -   <span data-ttu-id="a4a8d-115">单击 "**查找**" 以打开 "标准**选择用户或组**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-115">Click **Find** to open the standard **Select Users or Groups** dialog box.</span></span> <span data-ttu-id="a4a8d-116">然后选择 "域用户" 或 "组"。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-116">Then select domain users or groups.</span></span>

3.  <span data-ttu-id="a4a8d-117">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-117">Click **OK**.</span></span>

    <span data-ttu-id="a4a8d-118">添加域用户或组。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-118">The domain users or groups are added.</span></span>

    **<span data-ttu-id="a4a8d-119">注意</span><span class="sxs-lookup"><span data-stu-id="a4a8d-119">Note</span></span>**  
    <span data-ttu-id="a4a8d-120">应手动添加来自受信任域的用户。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-120">Users from trusted domains should be added manually.</span></span>



~~~
**Warning**  
Do not run the management application from a computer that is part of a domain that is not trusted by the domain the server is installed on.
~~~



## <span data-ttu-id="a4a8d-121">如何删除域用户或组</span><span class="sxs-lookup"><span data-stu-id="a4a8d-121">How to Remove a Domain User or Group</span></span>


**<span data-ttu-id="a4a8d-122">删除域用户或组</span><span class="sxs-lookup"><span data-stu-id="a4a8d-122">To remove a domain user or group</span></span>**

1.  <span data-ttu-id="a4a8d-123">在 "**用户/组**" 窗口中，选择一个用户或组。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-123">In the **Users / Groups** window, select a user or group.</span></span>

2.  <span data-ttu-id="a4a8d-124">单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-124">Click **Remove**.</span></span>

    <span data-ttu-id="a4a8d-125">已删除用户或组。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-125">The user or group is deleted.</span></span>

## <span data-ttu-id="a4a8d-126">如何为用户或组设置权限</span><span class="sxs-lookup"><span data-stu-id="a4a8d-126">How to Set Permissions for a User or a Group</span></span>


**<span data-ttu-id="a4a8d-127">为用户或组设置权限</span><span class="sxs-lookup"><span data-stu-id="a4a8d-127">To set permissions for a user or a group</span></span>**

1.  <span data-ttu-id="a4a8d-128">单击要为其设置权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-128">Click the user or group for which you are setting the permissions.</span></span>

2.  <span data-ttu-id="a4a8d-129">按下表所述配置 MED-V 工作区属性。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-129">Configure the MED-V workspace properties as described in the following table.</span></span>

3.  <span data-ttu-id="a4a8d-130">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-130">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="a4a8d-131">工作区部署属性</span><span class="sxs-lookup"><span data-stu-id="a4a8d-131">Workspace Deployment Properties</span></span>**

<span data-ttu-id="a4a8d-132">属性说明*常规*</span><span class="sxs-lookup"><span data-stu-id="a4a8d-132">Property Description *General*</span></span>

<span data-ttu-id="a4a8d-133">为 &lt; 用户或组启用工作区&gt;</span><span class="sxs-lookup"><span data-stu-id="a4a8d-133">Enable Workspace for &lt;user or group&gt;</span></span>

<span data-ttu-id="a4a8d-134">选中此复选框以启用此用户或组的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-134">Select this check box to enable the MED-V workspace for this user or group.</span></span>

<span data-ttu-id="a4a8d-135">工作区将在此日期到期</span><span class="sxs-lookup"><span data-stu-id="a4a8d-135">Workspace expires on this date</span></span>

<span data-ttu-id="a4a8d-136">选中此复选框可为此用户或组分配权限集的到期日期。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-136">Select this check box to assign an expiration date for the permissions set for this user or group.</span></span>

<span data-ttu-id="a4a8d-137">选中后，将启用 "日期" 框。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-137">When selected, the date box is enabled.</span></span> <span data-ttu-id="a4a8d-138">设置日期和权限将在指定日期结束时过期。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-138">Set the date, and permissions will expire at the end of the date specified.</span></span>

<span data-ttu-id="a4a8d-139">脱机工作限制为</span><span class="sxs-lookup"><span data-stu-id="a4a8d-139">Offline work is restricted to</span></span>

<span data-ttu-id="a4a8d-140">选中此复选框以分配必须为此用户或组刷新策略的时间段。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-140">Select this check box to assign a time period in which the policy must be refreshed for this user or group.</span></span> <span data-ttu-id="a4a8d-141">选中此选项时，将启用 "时间段" 框。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-141">When selected, the time period box is enabled.</span></span> <span data-ttu-id="a4a8d-142">设置天数或小时数，在指定的时间段结束时，如果未刷新策略，用户或组将无法连接。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-142">Set the number of days or hours, and at the end of the specified time period, the user or group will not be able to connect if the policy is not refreshed.</span></span>

<span data-ttu-id="a4a8d-143">工作区删除选项</span><span class="sxs-lookup"><span data-stu-id="a4a8d-143">Workspace deletion options</span></span>

<span data-ttu-id="a4a8d-144">单击以设置 MED-V 工作区删除选项。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-144">Click to set the MED-V workspace deletion options.</span></span> <span data-ttu-id="a4a8d-145">有关详细信息，请参阅[如何设置 Med-v 工作区删除选项](how-to-set-med-v-workspace-deletion-options.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-145">For more information, see [How to Set MED-V Workspace Deletion Options](how-to-set-med-v-workspace-deletion-options.md).</span></span>

*<span data-ttu-id="a4a8d-146">数据传输</span><span class="sxs-lookup"><span data-stu-id="a4a8d-146">Data Transfer</span></span>*

<span data-ttu-id="a4a8d-147">在主机和工作区之间支持剪贴板</span><span class="sxs-lookup"><span data-stu-id="a4a8d-147">Support clipboard between host and Workspace</span></span>

<span data-ttu-id="a4a8d-148">选中此复选框以启用主机和 MED-V 工作区之间的复制和粘贴。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-148">Select this check box to enable copying and pasting between the host and the MED-V workspace.</span></span>

<span data-ttu-id="a4a8d-149">在主机和工作区之间支持文件传输</span><span class="sxs-lookup"><span data-stu-id="a4a8d-149">Support file transfer between the host and Workspace</span></span>

<span data-ttu-id="a4a8d-150">选中此复选框以启用在主机和 MED-V 工作区之间传输文件。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-150">Select this check box to enable transferring files between the host and MED-V workspace.</span></span> <span data-ttu-id="a4a8d-151">从 "**文件传输**" 框中选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="a4a8d-151">Select one of the following options from the **File Transfer** box:</span></span>

-   <span data-ttu-id="a4a8d-152">**Both**-启用在主机和 med-v 工作区之间传输文件。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-152">**Both**—Enable transferring files between the host and the MED-V workspace.</span></span>

-   <span data-ttu-id="a4a8d-153">**主机到工作区**-启用将文件从主机传输到 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-153">**Host to Workspace**—Enable transferring files from the host to the MED-V workspace.</span></span>

-   <span data-ttu-id="a4a8d-154">**要承载的工作区**—支持将文件从 med-v 工作区传输到主机。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-154">**Workspace to Host**—Enable transferring files from the MED-V workspace to the host.</span></span>

**<span data-ttu-id="a4a8d-155">注意</span><span class="sxs-lookup"><span data-stu-id="a4a8d-155">Note</span></span>**  
<span data-ttu-id="a4a8d-156">如果没有权限的用户尝试传输文件，则会显示一个窗口，提示他输入具有执行文件传输权限的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-156">If a user without permissions attempts to transfer files, a window will appear prompting him to enter the credentials of a user with permissions to perform the file transfer.</span></span>



**<span data-ttu-id="a4a8d-157">重要提示</span><span class="sxs-lookup"><span data-stu-id="a4a8d-157">Important</span></span>**  
<span data-ttu-id="a4a8d-158">若要支持 Windows XP SP3 中的文件传输，必须通过编辑注册表禁用脱机文件同步，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a4a8d-158">To support file transfer in Windows XP SP3, you must disable offline file synchronization by editing the registry as follows:</span></span>

`REG ADD HKLM\software\microsoft\windows\currentversion\netcache /V Enabled /T REG_DWORD /F /D 0`



<span data-ttu-id="a4a8d-159">高级</span><span class="sxs-lookup"><span data-stu-id="a4a8d-159">Advanced</span></span>

<span data-ttu-id="a4a8d-160">单击以设置高级文件传送选项。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-160">Click to set the advanced file transfer options.</span></span> <span data-ttu-id="a4a8d-161">有关详细信息，请参阅[如何设置高级文件传输选项](how-to-set-advanced-file-transfer-options.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-161">For more information, see [How to Set Advanced File Transfer Options](how-to-set-advanced-file-transfer-options.md).</span></span>

*<span data-ttu-id="a4a8d-162">设备控件</span><span class="sxs-lookup"><span data-stu-id="a4a8d-162">Device Control</span></span>*

<span data-ttu-id="a4a8d-163">允许打印到连接到主机的打印机</span><span class="sxs-lookup"><span data-stu-id="a4a8d-163">Enable printing to printers connected to the host</span></span>

<span data-ttu-id="a4a8d-164">选中此复选框可允许用户使用主机打印机从 MED-V 工作区进行打印。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-164">Select this check box to enable users to print from the MED-V workspace using the host printer.</span></span>

**<span data-ttu-id="a4a8d-165">注意</span><span class="sxs-lookup"><span data-stu-id="a4a8d-165">Note</span></span>**  
<span data-ttu-id="a4a8d-166">打印由主机上定义的打印机执行。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-166">The printing is performed by the printers defined on the host.</span></span>



<span data-ttu-id="a4a8d-167">启用对 CD/DVD 的访问</span><span class="sxs-lookup"><span data-stu-id="a4a8d-167">Enable access to CD / DVD</span></span>

<span data-ttu-id="a4a8d-168">选中此复选框可允许通过此 MED-V 工作区访问 CD 或 DVD 驱动器。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-168">Select this check box to allow access to a CD or DVD drive from this MED-V workspace.</span></span>



**<span data-ttu-id="a4a8d-169">多个成员身份</span><span class="sxs-lookup"><span data-stu-id="a4a8d-169">Multiple Memberships</span></span>**

1.  <span data-ttu-id="a4a8d-170">如果用户是组的一部分，并且权限应用于用户以及它们所属的组，则应用所有权限。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-170">If the user is part of a group and permissions are applied to the user as well as to the group they are part of, all permissions are applied.</span></span>

2.  <span data-ttu-id="a4a8d-171">如果用户是两个不同组的成员，则应用限制性最少的权限。</span><span class="sxs-lookup"><span data-stu-id="a4a8d-171">If the user is a member of two different groups, the least restrictive permissions are applied.</span></span>

## <span data-ttu-id="a4a8d-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="a4a8d-172">Related topics</span></span>


[<span data-ttu-id="a4a8d-173">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="a4a8d-173">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="a4a8d-174">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a4a8d-174">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="a4a8d-175">如何设置 MED-V 工作区删除选项</span><span class="sxs-lookup"><span data-stu-id="a4a8d-175">How to Set MED-V Workspace Deletion Options</span></span>](how-to-set-med-v-workspace-deletion-options.md)

[<span data-ttu-id="a4a8d-176">如何设置高级文件传输选项</span><span class="sxs-lookup"><span data-stu-id="a4a8d-176">How to Set Advanced File Transfer Options</span></span>](how-to-set-advanced-file-transfer-options.md)









