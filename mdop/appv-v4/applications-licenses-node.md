---
title: “应用程序许可证”节点
description: “应用程序许可证”节点
author: dansimp
ms.assetid: 2b8752ff-aa56-483e-b844-966941af2d94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 720de1860e72ae2c71298f93e9b346afd66da569
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802247"
---
# <span data-ttu-id="8c914-103">“应用程序许可证”节点</span><span class="sxs-lookup"><span data-stu-id="8c914-103">Applications Licenses Node</span></span>


<span data-ttu-id="8c914-104">应用程序**许可证**节点是应用程序虚拟化服务器管理控制台的**范围**窗格中 "应用程序虚拟化系统" 节点下的一个级别。</span><span class="sxs-lookup"><span data-stu-id="8c914-104">The **Applications Licenses** node is one level below the Application Virtualization System node in the **Scope** pane in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="8c914-105">选择此节点时，"**结果**" 窗格将显示许可证和许可证组的列表。</span><span class="sxs-lookup"><span data-stu-id="8c914-105">When you select this node, the **Results** pane displays a list of licenses and license groups.</span></span> <span data-ttu-id="8c914-106">以下许可证类型可用：</span><span class="sxs-lookup"><span data-stu-id="8c914-106">The following license types are available:</span></span>

-   <span data-ttu-id="8c914-107">**无限制许可证**—为任意数量的同时用户提供访问权限。</span><span class="sxs-lookup"><span data-stu-id="8c914-107">**Unlimited License**—Provides access for any number of simultaneous users.</span></span> <span data-ttu-id="8c914-108">如果你想要将企业范围许可证与应用程序关联，则此许可方法非常合适。</span><span class="sxs-lookup"><span data-stu-id="8c914-108">This method of licensing is appropriate when you want to associate an enterprise-wide license with an application.</span></span>

-   <span data-ttu-id="8c914-109">**并发许可证**-允许你定义允许使用该应用程序的并发用户的最大数量。</span><span class="sxs-lookup"><span data-stu-id="8c914-109">**Concurrent License**—Enables you to define the maximum number of concurrent users who are allowed to use the application.</span></span>

-   <span data-ttu-id="8c914-110">**命名许可证**-使您可以为单个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="8c914-110">**Named License**—Enables you to assign a license to an individual user.</span></span> <span data-ttu-id="8c914-111">命名许可证可用于确保特定用户始终能够运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c914-111">A named license can be used to ensure that a particular user will always be able to run the application.</span></span>

<span data-ttu-id="8c914-112">**注意** 你可以将同一应用程序的并发和命名许可证合并在一起。</span><span class="sxs-lookup"><span data-stu-id="8c914-112">**Note** You can combine concurrent and named licenses for the same application.</span></span>

 

<span data-ttu-id="8c914-113">右键单击 "**应用程序许可证**" 节点以显示包含以下元素的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="8c914-113">Right-click the **Applications Licenses** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-unlimited-license"></a>**<span data-ttu-id="8c914-114">新的无限通许可证</span><span class="sxs-lookup"><span data-stu-id="8c914-114">New Unlimited License</span></span>**  
<span data-ttu-id="8c914-115">显示 "新建无限制许可证" 向导。</span><span class="sxs-lookup"><span data-stu-id="8c914-115">Displays the New Unlimited License Wizard.</span></span> <span data-ttu-id="8c914-116">此向导包含以下页面：</span><span class="sxs-lookup"><span data-stu-id="8c914-116">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="8c914-117">在 "**应用程序许可证组名称**" 字段中输入许可证组的名称，然后在 "**许可证过期警告**" 字段中输入一个值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="8c914-117">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="8c914-118">（可以输入从0到100的任何值。）您也可以使用向上键和向下键选择分钟数。</span><span class="sxs-lookup"><span data-stu-id="8c914-118">(You can enter any value from 0 through 100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="8c914-119">在 "**许可证说明**" 字段中输入简短的描述性文本，然后选中 "**已启用**" 复选框以启用许可证。</span><span class="sxs-lookup"><span data-stu-id="8c914-119">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="8c914-120">或者，您可以使用 "**到期日期**" 字段指定许可证的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8c914-120">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="8c914-121">您可以选中该复选框以使用显示的到期日期，也可以使用日历实用工具浏览到所需的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8c914-121">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="8c914-122">单击 "**完成**" 以添加新许可证。</span><span class="sxs-lookup"><span data-stu-id="8c914-122">Click **Finish** to add the new license.</span></span>

<a href="" id="new-concurrent-license"></a>**<span data-ttu-id="8c914-123">新的并发许可证</span><span class="sxs-lookup"><span data-stu-id="8c914-123">New Concurrent License</span></span>**  
<span data-ttu-id="8c914-124">显示 "新建并发许可证" 向导。</span><span class="sxs-lookup"><span data-stu-id="8c914-124">Displays the New Concurrent License Wizard.</span></span> <span data-ttu-id="8c914-125">此向导包含以下三个页面，与新的无限通许可证向导几乎完全相同：</span><span class="sxs-lookup"><span data-stu-id="8c914-125">This wizard consists of the following three pages and is almost identical to the New Unlimited License Wizard:</span></span>

1.  <span data-ttu-id="8c914-126">在 "**应用程序许可证组名称**" 字段中输入许可证组的名称，然后在 "**许可证过期警告**" 字段中输入一个值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="8c914-126">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="8c914-127">（可以输入从0到100的任何值。）您也可以使用向上键和向下键选择分钟数。</span><span class="sxs-lookup"><span data-stu-id="8c914-127">(You can enter any value from 0 through 100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="8c914-128">在 "**许可证说明**" 字段中输入简短的描述性文本，然后在 "**并发许可证数量**" 字段中输入一个值。</span><span class="sxs-lookup"><span data-stu-id="8c914-128">Enter brief descriptive text in the **License Description** field, and enter a value in the **Concurrent License Quantity** field.</span></span>

    <span data-ttu-id="8c914-129">您也可以使用向上键和向下键来指定并发许可证的数量。</span><span class="sxs-lookup"><span data-stu-id="8c914-129">You can also use the up and down arrows to specify the number of concurrent licenses.</span></span> <span data-ttu-id="8c914-130">选中 "**已启用**" 复选框以启用许可证。</span><span class="sxs-lookup"><span data-stu-id="8c914-130">Select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="8c914-131">或者，您可以使用 "**到期日期**" 字段指定许可证的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8c914-131">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="8c914-132">您可以选中该复选框以使用显示的到期日期，也可以使用日历实用工具浏览到所需的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8c914-132">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="8c914-133">单击 "**完成**" 以添加新许可证。</span><span class="sxs-lookup"><span data-stu-id="8c914-133">Click **Finish** to add the new licenses.</span></span>

<a href="" id="new-named-license"></a>**<span data-ttu-id="8c914-134">新的命名许可证</span><span class="sxs-lookup"><span data-stu-id="8c914-134">New Named License</span></span>**  
<span data-ttu-id="8c914-135">显示 "新建命名的许可证" 向导。</span><span class="sxs-lookup"><span data-stu-id="8c914-135">Displays the New Named License Wizard.</span></span> <span data-ttu-id="8c914-136">此向导包含以下四个页面：</span><span class="sxs-lookup"><span data-stu-id="8c914-136">This wizard consists of the following four pages:</span></span>

1.  <span data-ttu-id="8c914-137">在 "**应用程序许可证组名称**" 字段中输入许可证组的名称，然后在 "**许可证过期警告**" 字段中输入一个值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="8c914-137">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="8c914-138">（可以输入从0到100的任何值）。</span><span class="sxs-lookup"><span data-stu-id="8c914-138">(You can enter any value from 0 through 100).</span></span> <span data-ttu-id="8c914-139">您也可以使用向上键和向下键选择分钟数。</span><span class="sxs-lookup"><span data-stu-id="8c914-139">You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="8c914-140">在 "**许可证说明**" 字段中输入简短的描述性文本，然后选中 "**已启用**" 复选框以启用许可证。</span><span class="sxs-lookup"><span data-stu-id="8c914-140">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="8c914-141">或者，您可以使用 "**到期日期**" 字段指定许可证的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8c914-141">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="8c914-142">您可以选中该复选框以使用显示的到期日期，也可以使用日历实用工具浏览到所需的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8c914-142">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="8c914-143">单击 "**添加**"、"**编辑**" 或 "**删除**已命名的用户"。</span><span class="sxs-lookup"><span data-stu-id="8c914-143">Click **Add**, **Edit**, or **Remove** named users.</span></span>

4.  <span data-ttu-id="8c914-144">单击 "**完成**" 以添加新许可证。</span><span class="sxs-lookup"><span data-stu-id="8c914-144">Click **Finish** to add the new license.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="8c914-145">视图</span><span class="sxs-lookup"><span data-stu-id="8c914-145">View</span></span>**  
<span data-ttu-id="8c914-146">更改 "**结果**" 窗格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="8c914-146">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="8c914-147">从此处新建窗口</span><span class="sxs-lookup"><span data-stu-id="8c914-147">New Window from Here</span></span>**  
<span data-ttu-id="8c914-148">打开新的管理控制台，其中将选定的节点作为根节点。</span><span class="sxs-lookup"><span data-stu-id="8c914-148">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="8c914-149">刷新</span><span class="sxs-lookup"><span data-stu-id="8c914-149">Refresh</span></span>**  
<span data-ttu-id="8c914-150">刷新服务器的视图。</span><span class="sxs-lookup"><span data-stu-id="8c914-150">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="8c914-151">导出列表</span><span class="sxs-lookup"><span data-stu-id="8c914-151">Export List</span></span>**  
<span data-ttu-id="8c914-152">创建一个制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="8c914-152">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="8c914-153">此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="8c914-153">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="8c914-154">帮助</span><span class="sxs-lookup"><span data-stu-id="8c914-154">Help</span></span>**  
<span data-ttu-id="8c914-155">显示应用程序虚拟化服务器管理控制台的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="8c914-155">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="8c914-156">如果您单击 "**范围**" 窗格中 "**应用程序许可证**" 节点下显示的许可证组或许可证，则可以使用以下元素。</span><span class="sxs-lookup"><span data-stu-id="8c914-156">If you click a license group or license that appears under the **Application Licenses** node in the **Scope** pane, the following elements are available.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="8c914-157">视图</span><span class="sxs-lookup"><span data-stu-id="8c914-157">View</span></span>**  
<span data-ttu-id="8c914-158">更改 "**结果**" 窗格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="8c914-158">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="8c914-159">从此处新建窗口</span><span class="sxs-lookup"><span data-stu-id="8c914-159">New Window from Here</span></span>**  
<span data-ttu-id="8c914-160">打开新的管理控制台，其中将选定的节点作为根节点。</span><span class="sxs-lookup"><span data-stu-id="8c914-160">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="8c914-161">删除</span><span class="sxs-lookup"><span data-stu-id="8c914-161">Delete</span></span>**  
<span data-ttu-id="8c914-162">从 "**结果**" 窗格中删除程序包。</span><span class="sxs-lookup"><span data-stu-id="8c914-162">Deletes a package from the **Results** pane.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="8c914-163">重命名</span><span class="sxs-lookup"><span data-stu-id="8c914-163">Rename</span></span>**  
<span data-ttu-id="8c914-164">更改 "**结果**" 窗格中的程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="8c914-164">Changes the name of a package in the **Results** pane.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="8c914-165">导出列表</span><span class="sxs-lookup"><span data-stu-id="8c914-165">Export List</span></span>**  
<span data-ttu-id="8c914-166">创建一个制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="8c914-166">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="8c914-167">此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="8c914-167">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="8c914-168">属性</span><span class="sxs-lookup"><span data-stu-id="8c914-168">Properties</span></span>**  
<span data-ttu-id="8c914-169">显示所选许可证组的 "**属性**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="8c914-169">Displays the **Properties** dialog box for the selected license group.</span></span> <span data-ttu-id="8c914-170">"**属性**" 对话框的 "**常规**" 选项卡显示有关许可证组的信息，并允许您更改 "**许可证过期警告**" 字段中的时间值。</span><span class="sxs-lookup"><span data-stu-id="8c914-170">The **General** tab of the **Properties** dialog box displays information about the license group and lets you change the time value in the **License Expiration Warning** field.</span></span> <span data-ttu-id="8c914-171">"**应用程序**" 选项卡显示与许可证组相关联的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="8c914-171">The **Applications** tab displays the list of applications associated with the license group.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="8c914-172">帮助</span><span class="sxs-lookup"><span data-stu-id="8c914-172">Help</span></span>**  
<span data-ttu-id="8c914-173">显示应用程序虚拟化服务器管理控制台的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="8c914-173">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="8c914-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="8c914-174">Related topics</span></span>


[<span data-ttu-id="8c914-175">关于应用程序授权</span><span class="sxs-lookup"><span data-stu-id="8c914-175">About Application Licensing</span></span>](about-application-licensing.md)

[<span data-ttu-id="8c914-176">如何在 Server Management Console 中管理应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="8c914-176">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="8c914-177">Server Management Console：“应用程序许可证”节点</span><span class="sxs-lookup"><span data-stu-id="8c914-177">Server Management Console: Application Licenses Node</span></span>](server-management-console-application-licenses-node.md)

 

 





