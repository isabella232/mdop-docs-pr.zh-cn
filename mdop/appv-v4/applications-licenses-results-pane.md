---
title: “应用程序许可证结果”窗格
description: “应用程序许可证结果”窗格
author: dansimp
ms.assetid: 8b519715-b2fe-451e-ad9b-e9b73f454961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e5a86c22e67e061ec873317c455958536fae75b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802244"
---
# <span data-ttu-id="88dab-103">“应用程序许可证结果”窗格</span><span class="sxs-lookup"><span data-stu-id="88dab-103">Applications Licenses Results Pane</span></span>


<span data-ttu-id="88dab-104">应用程序虚拟化服务器管理控制台中的**应用程序许可证结果**窗格显示可用的应用程序许可证组和应用程序许可证的列表。</span><span class="sxs-lookup"><span data-stu-id="88dab-104">The **Applications Licenses Results** pane in the Application Virtualization Server Management Console displays a list of the available application license groups and application licenses.</span></span>

<span data-ttu-id="88dab-105">右键单击任何应用程序许可证组以显示包含以下元素的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="88dab-105">Right-click any application license group to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-unlimited-license"></a>**<span data-ttu-id="88dab-106">新的无限通许可证</span><span class="sxs-lookup"><span data-stu-id="88dab-106">New Unlimited License</span></span>**  
<span data-ttu-id="88dab-107">显示 "新建无限制许可证" 向导。</span><span class="sxs-lookup"><span data-stu-id="88dab-107">Displays the New Unlimited License Wizard.</span></span> <span data-ttu-id="88dab-108">仅当许可证组没有许可证时，此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="88dab-108">This option is available only when the license group has no licenses.</span></span> <span data-ttu-id="88dab-109">此向导包含三个页面：</span><span class="sxs-lookup"><span data-stu-id="88dab-109">This wizard consists of three pages:</span></span>

1.  <span data-ttu-id="88dab-110">在 "**应用程序许可证组名称**" 字段中输入组名称，在 "**许可证过期警告**" 字段中输入一个值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="88dab-110">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="88dab-111">（可以输入0到100之间的任何值。）您也可以使用向上键和向下键选择分钟数。</span><span class="sxs-lookup"><span data-stu-id="88dab-111">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="88dab-112">在 "**许可证说明**" 字段中输入简短的描述性文本，然后选中 "**已启用**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="88dab-112">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box.</span></span> <span data-ttu-id="88dab-113">或者，您可以使用 "**到期日期**" 字段指定许可证的到期日期。</span><span class="sxs-lookup"><span data-stu-id="88dab-113">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="88dab-114">你可以选择 "默认" 复选框或使用日历实用工具浏览到所需的到期日期。</span><span class="sxs-lookup"><span data-stu-id="88dab-114">You can select the default check box or use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="88dab-115">单击 "**完成**" 以添加新许可证。</span><span class="sxs-lookup"><span data-stu-id="88dab-115">Click **Finish** to add the new license.</span></span>

<a href="" id="new-concurrent-license"></a>**<span data-ttu-id="88dab-116">新的并发许可证</span><span class="sxs-lookup"><span data-stu-id="88dab-116">New Concurrent License</span></span>**  
<span data-ttu-id="88dab-117">显示 "新建并发许可证" 向导。</span><span class="sxs-lookup"><span data-stu-id="88dab-117">Displays the New Concurrent License Wizard.</span></span> <span data-ttu-id="88dab-118">仅当许可证组没有无限许可证时，此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="88dab-118">This option is available only when the license group has no unlimited licenses.</span></span> <span data-ttu-id="88dab-119">此向导包含以下页面，与新的无限许可证向导几乎完全相同：</span><span class="sxs-lookup"><span data-stu-id="88dab-119">This wizard consists of the following pages and is almost identical to the New Unlimited License Wizard:</span></span>

1.  <span data-ttu-id="88dab-120">在 "**应用程序许可证组名称**" 字段中输入组名称，在 "**许可证过期警告**" 字段中输入一个值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="88dab-120">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="88dab-121">（可以输入0到100之间的任何值。）您也可以使用向上键和向下键选择分钟数。</span><span class="sxs-lookup"><span data-stu-id="88dab-121">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="88dab-122">在 "**许可证说明**" 字段中输入简短的描述性文本，然后在 "**并发许可证数量**" 字段中输入一个值。</span><span class="sxs-lookup"><span data-stu-id="88dab-122">Enter brief descriptive text in the **License Description** field, and enter a value in the **Concurrent License Quantity** field.</span></span> <span data-ttu-id="88dab-123">您也可以使用向上键和向下键来指定并发许可证的数量。</span><span class="sxs-lookup"><span data-stu-id="88dab-123">You can also use the up and down arrows to specify the number of concurrent licenses.</span></span> <span data-ttu-id="88dab-124">选中 "**已启用**" 复选框以启用许可证。</span><span class="sxs-lookup"><span data-stu-id="88dab-124">Select the **Enabled** check box to enable the license.</span></span> <span data-ttu-id="88dab-125">或者，您可以使用 "**到期日期**" 字段选择许可证的到期日期。</span><span class="sxs-lookup"><span data-stu-id="88dab-125">Optionally, you can use the **Expiration Date** field to select an expiration date for the license.</span></span> <span data-ttu-id="88dab-126">您可以选中该复选框以使用显示的到期日期，也可以使用日历实用工具浏览到所需的到期日期。</span><span class="sxs-lookup"><span data-stu-id="88dab-126">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="88dab-127">单击 "**完成**" 以添加新许可证。</span><span class="sxs-lookup"><span data-stu-id="88dab-127">Click **Finish** to add the new licenses.</span></span>

<a href="" id="new-named-license"></a>**<span data-ttu-id="88dab-128">新的命名许可证</span><span class="sxs-lookup"><span data-stu-id="88dab-128">New Named License</span></span>**  
<span data-ttu-id="88dab-129">显示 "新建命名的许可证" 向导。</span><span class="sxs-lookup"><span data-stu-id="88dab-129">Displays the New Named License Wizard.</span></span> <span data-ttu-id="88dab-130">仅当许可证组没有无限许可证时，此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="88dab-130">This option is available only when the license group has no unlimited licenses.</span></span> <span data-ttu-id="88dab-131">此向导包含以下页面：</span><span class="sxs-lookup"><span data-stu-id="88dab-131">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="88dab-132">在 "**应用程序许可证组名称**" 字段中输入组名称，在 "**许可证过期警告**" 字段中输入一个值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="88dab-132">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="88dab-133">（可以输入0到100之间的任何值。）您也可以使用向上键和向下键选择分钟数。</span><span class="sxs-lookup"><span data-stu-id="88dab-133">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="88dab-134">在**许可证说明**中输入简短的描述性文本，然后选中 "**已启用**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="88dab-134">Enter brief descriptive text in the **License Description**, and select the **Enabled** check box.</span></span> <span data-ttu-id="88dab-135">或者，您可以使用 "**到期日期**" 字段指定许可证的到期日期。</span><span class="sxs-lookup"><span data-stu-id="88dab-135">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="88dab-136">你可以选中该复选框以使用显示的到期日期，或使用日历实用工具浏览到所需的到期日期。</span><span class="sxs-lookup"><span data-stu-id="88dab-136">You can select the check box to use the displayed expiration date, or use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="88dab-137">单击 "**添加**"、"**编辑**" 或 "**删除**已命名的用户"。</span><span class="sxs-lookup"><span data-stu-id="88dab-137">Click **Add**, **Edit**, or **Remove** named users.</span></span>

4.  <span data-ttu-id="88dab-138">单击 "**完成**" 以添加新许可证。</span><span class="sxs-lookup"><span data-stu-id="88dab-138">Click **Finish** to add the new license.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="88dab-139">从此处新建窗口</span><span class="sxs-lookup"><span data-stu-id="88dab-139">New Window from Here</span></span>**  
<span data-ttu-id="88dab-140">打开新的管理控制台，其中将选定的节点作为根节点。</span><span class="sxs-lookup"><span data-stu-id="88dab-140">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="88dab-141">删除</span><span class="sxs-lookup"><span data-stu-id="88dab-141">Delete</span></span>**  
<span data-ttu-id="88dab-142">从列表中删除许可证组。</span><span class="sxs-lookup"><span data-stu-id="88dab-142">Deletes the license group from the list.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="88dab-143">重命名</span><span class="sxs-lookup"><span data-stu-id="88dab-143">Rename</span></span>**  
<span data-ttu-id="88dab-144">更改应用程序许可证组的名称。</span><span class="sxs-lookup"><span data-stu-id="88dab-144">Changes the name of the applications license group.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="88dab-145">属性</span><span class="sxs-lookup"><span data-stu-id="88dab-145">Properties</span></span>**  
<span data-ttu-id="88dab-146">显示所选应用程序许可证组的 "**属性**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="88dab-146">Displays the **Properties** dialog box for the selected application license groups.</span></span> <span data-ttu-id="88dab-147">此对话框具有下列选项卡：</span><span class="sxs-lookup"><span data-stu-id="88dab-147">This dialog box has the following tabs:</span></span>

-   <span data-ttu-id="88dab-148">"**常规**" 选项卡-显示有关许可证组的常规信息。</span><span class="sxs-lookup"><span data-stu-id="88dab-148">**General** tab—Displays general information about the license group.</span></span> <span data-ttu-id="88dab-149">在此选项卡中，您可以更改 "**许可证过期警告**" 字段中的时间值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="88dab-149">From this tab, you can change the time value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="88dab-150">你可以输入0到100之间的任何值。</span><span class="sxs-lookup"><span data-stu-id="88dab-150">You can enter any value from 0–100.</span></span>

-   <span data-ttu-id="88dab-151">"**应用程序**" 选项卡-显示与许可证组相关联的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="88dab-151">**Applications** tab—Displays the list of applications associated with the license group.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="88dab-152">帮助</span><span class="sxs-lookup"><span data-stu-id="88dab-152">Help</span></span>**  
<span data-ttu-id="88dab-153">显示应用程序虚拟化服务器管理控制台帮助系统。</span><span class="sxs-lookup"><span data-stu-id="88dab-153">Displays the Application Virtualization Server Management Console help system.</span></span>

<span data-ttu-id="88dab-154">当 "**结果**" 窗格显示应用程序许可证组时，右键单击 "**结果**" 窗格中除许可证组之外的任何位置，以显示包含以下元素的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="88dab-154">When the **Results** pane displays application license groups, right-click anywhere in the **Results** pane, except on a license group, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="88dab-155">刷新</span><span class="sxs-lookup"><span data-stu-id="88dab-155">Refresh</span></span>**  
<span data-ttu-id="88dab-156">刷新服务器的视图。</span><span class="sxs-lookup"><span data-stu-id="88dab-156">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="88dab-157">导出列表</span><span class="sxs-lookup"><span data-stu-id="88dab-157">Export List</span></span>**  
<span data-ttu-id="88dab-158">创建一个制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="88dab-158">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="88dab-159">此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="88dab-159">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="88dab-160">视图</span><span class="sxs-lookup"><span data-stu-id="88dab-160">View</span></span>**  
<span data-ttu-id="88dab-161">更改 "**结果**" 窗格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="88dab-161">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="88dab-162">"排列/对齐" 图标</span><span class="sxs-lookup"><span data-stu-id="88dab-162">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="88dab-163">更改图标在 "**结果**" 窗格中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="88dab-163">Changes how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="88dab-164">帮助</span><span class="sxs-lookup"><span data-stu-id="88dab-164">Help</span></span>**  
<span data-ttu-id="88dab-165">显示应用程序虚拟化服务器管理控制台的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="88dab-165">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="88dab-166">当 "**结果**" 窗格显示许可证时，右键单击任何应用程序许可证以显示包含以下元素的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="88dab-166">When the **Results** pane displays licenses, right-click any application license to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="88dab-167">删除</span><span class="sxs-lookup"><span data-stu-id="88dab-167">Delete</span></span>**  
<span data-ttu-id="88dab-168">从列表中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="88dab-168">Deletes the license from the list.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="88dab-169">重命名</span><span class="sxs-lookup"><span data-stu-id="88dab-169">Rename</span></span>**  
<span data-ttu-id="88dab-170">更改许可证的名称。</span><span class="sxs-lookup"><span data-stu-id="88dab-170">Changes the name of the license.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="88dab-171">属性</span><span class="sxs-lookup"><span data-stu-id="88dab-171">Properties</span></span>**  
<span data-ttu-id="88dab-172">显示所选应用程序许可证的 "**属性**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="88dab-172">Displays the **Properties** dialog box for the selected application license.</span></span>

<span data-ttu-id="88dab-173">"**属性**" 对话框的 "**常规**" 选项卡显示有关许可证的信息，并允许您更改 "已启用状态"、"许可证到期日期" 和 "许可证密钥" 信息。</span><span class="sxs-lookup"><span data-stu-id="88dab-173">The **General** tab of the **Properties** dialog box displays information about the license and lets you change the enabled status, license expiration date, and license key information.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="88dab-174">帮助</span><span class="sxs-lookup"><span data-stu-id="88dab-174">Help</span></span>**  
<span data-ttu-id="88dab-175">显示服务器管理控制台帮助系统。</span><span class="sxs-lookup"><span data-stu-id="88dab-175">Displays the server management console help system.</span></span>

<span data-ttu-id="88dab-176">当 "**结果**" 窗格显示许可证时，请右键单击 "**结果**" 窗格中的任意位置（除许可证外），以显示包含以下元素的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="88dab-176">When the **Results** pane displays licenses, right-click anywhere in the **Results** pane, except on a license, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="88dab-177">导出列表</span><span class="sxs-lookup"><span data-stu-id="88dab-177">Export List</span></span>**  
<span data-ttu-id="88dab-178">创建一个制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="88dab-178">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="88dab-179">此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="88dab-179">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="88dab-180">视图</span><span class="sxs-lookup"><span data-stu-id="88dab-180">View</span></span>**  
<span data-ttu-id="88dab-181">更改 "**结果**" 窗格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="88dab-181">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="88dab-182">"排列/对齐" 图标</span><span class="sxs-lookup"><span data-stu-id="88dab-182">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="88dab-183">更改图标在 "**结果**" 窗格中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="88dab-183">Changes how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="88dab-184">属性</span><span class="sxs-lookup"><span data-stu-id="88dab-184">Properties</span></span>**  
<span data-ttu-id="88dab-185">显示所选许可证的 "**属性**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="88dab-185">Displays the **Properties** dialog box for the selected license.</span></span>

<span data-ttu-id="88dab-186">"**属性**" 对话框的 "**常规**" 选项卡显示有关许可证的信息，并允许您更改 "已启用状态"、"许可证到期日期" 和 "许可证密钥" 信息。</span><span class="sxs-lookup"><span data-stu-id="88dab-186">The **General** tab of the **Properties** dialog box displays information about the license and lets you change the enabled status, license expiration date, and license key information.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="88dab-187">帮助</span><span class="sxs-lookup"><span data-stu-id="88dab-187">Help</span></span>**  
<span data-ttu-id="88dab-188">显示应用程序虚拟化服务器管理控制台的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="88dab-188">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="88dab-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="88dab-189">Related topics</span></span>


[<span data-ttu-id="88dab-190">关于应用程序授权</span><span class="sxs-lookup"><span data-stu-id="88dab-190">About Application Licensing</span></span>](about-application-licensing.md)

[<span data-ttu-id="88dab-191">如何在 Server Management Console 中管理应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="88dab-191">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="88dab-192">Server Management Console：“应用程序许可证”节点</span><span class="sxs-lookup"><span data-stu-id="88dab-192">Server Management Console: Application Licenses Node</span></span>](server-management-console-application-licenses-node.md)

 

 





