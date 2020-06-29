---
title: 如何生成报告
description: 如何生成报告
author: dansimp
ms.assetid: 9f8ba28e-1993-4c11-a28a-493718051e5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 930b7061d3e5e2fb9951d45b1422915836cbc00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804079"
---
# <span data-ttu-id="a4aa8-103">如何生成报告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-103">How to Generate Reports</span></span>


<span data-ttu-id="a4aa8-104">以下报告类型可由管理员在 MED-V 中创建：</span><span class="sxs-lookup"><span data-stu-id="a4aa8-104">The following report types can be created by administrators in MED-V:</span></span>

-   <span data-ttu-id="a4aa8-105">[状态](#bkmk-generatingastatusreport)—使用 "状态" 报表，可根据定义的时间段查看每个用户的所有活动用户和所有 med-v 工作区的当前状态。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-105">[Status](#bkmk-generatingastatusreport)—Use the status report to review the current status of all active users and all MED-V workspaces of each user based on a defined period of time.</span></span> <span data-ttu-id="a4aa8-106">这包括查看当前已连接到服务器的计算机或当前未连接的计算机、其上次连接到服务器的日期和时间、每台计算机的状态以及其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-106">This includes viewing computers that are currently connected to the server or, if they are not currently connected, the date and time they were last connected to the server, the status of each computer, and other relevant information.</span></span>

-   <span data-ttu-id="a4aa8-107">[活动日志](#bkmk-generatinganactivitylogreport)-使用此报告查看来自定义的日期范围内的特定主机或用户的事件。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-107">[Activity Log](#bkmk-generatinganactivitylogreport)—Use this report to review events that originated from a specific host or user in a defined date range.</span></span>

-   <span data-ttu-id="a4aa8-108">[错误日志](#bkmk-generatinganerrorlogreport)-使用此报告查看来自定义的日期范围内的特定主机或用户的错误。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-108">[Error Log](#bkmk-generatinganerrorlogreport)—Use this report to view errors that originated from a specific host or user in a defined date range.</span></span>

<span data-ttu-id="a4aa8-109">可通过单击相应的列名称按任何列对报告结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-109">The report results can be sorted by any column by clicking the appropriate column name.</span></span>

<span data-ttu-id="a4aa8-110">可通过将列标题拖动到报表顶部来对报表结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-110">The report results can be grouped by dragging a column header to the top of the report.</span></span> <span data-ttu-id="a4aa8-111">拖动多个列标题，将一个列逐个分组。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-111">Drag multiple column headers to group one column after another.</span></span>

## <a href="" id="bkmk-generatingastatusreport"></a><span data-ttu-id="a4aa8-112">如何生成状态报告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-112">How to Generate a Status Report</span></span>


**<span data-ttu-id="a4aa8-113">生成状态报告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-113">To generate a status report</span></span>**

1.  <span data-ttu-id="a4aa8-114">单击 "**报告**管理" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-114">Click the **Reports** management button.</span></span>

2.  <span data-ttu-id="a4aa8-115">在 "**报表" 模块的**"**报表类型**" 菜单上，选择 "**状态**"，然后单击 "**生成**"。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-115">In the **Reports** module, on the **Report Types** menu, select **Status**, and click **Generate**.</span></span>

    <span data-ttu-id="a4aa8-116">将显示 "报表参数" 对话框。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-116">The Report Parameters dialog box appears.</span></span>

3.  <span data-ttu-id="a4aa8-117">在 "**报表参数**" 对话框中的 "**天数**" 字段中，输入一个数字或使用箭头选择要在状态报告中包含的天数，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-117">In the **Report Parameters** dialog box, in the **Number of days** field, enter a number or use the arrows to select the number of days to include in the status report, and click **OK**.</span></span>

    <span data-ttu-id="a4aa8-118">将生成状态报告。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-118">A status report is generated.</span></span> <span data-ttu-id="a4aa8-119">下表中定义了报表参数。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-119">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="a4aa8-120">客户端 MED-V 工作区属性</span><span class="sxs-lookup"><span data-stu-id="a4aa8-120">Client MED-V Workspace Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a4aa8-121">属性</span><span class="sxs-lookup"><span data-stu-id="a4aa8-121">Property</span></span></th>
<th align="left"><span data-ttu-id="a4aa8-122">描述</span><span class="sxs-lookup"><span data-stu-id="a4aa8-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-123">时间</span><span class="sxs-lookup"><span data-stu-id="a4aa8-123">Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-124">事件发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-124">The date and time the event occurred.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a4aa8-125">注意</span><span class="sxs-lookup"><span data-stu-id="a4aa8-125">Note</span></span></strong><br/><p><span data-ttu-id="a4aa8-126">默认情况下，事件以降序显示日期顺序。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-126">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="a4aa8-127">但是，可以通过单击 "接收时间" 列来更改它。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-127">However, it can be changed by clicking the Time Received column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-128">用户名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-128">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-129">启动事件的用户。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-129">The user who initiated the event.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a4aa8-130">注意</span><span class="sxs-lookup"><span data-stu-id="a4aa8-130">Note</span></span></strong><br/><p><span data-ttu-id="a4aa8-131">如果在用户登录之前发生事件，则用户名为 "SYSTEM"。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-131">If the event occurred before a user logged on, the user name is SYSTEM.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-132">主机名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-132">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-133">主计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-133">The name of the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-134">工作区名称</span><span class="sxs-lookup"><span data-stu-id="a4aa8-134">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-135">MED-V 工作区的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-135">The name of the MED-V workspace.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-136">工作区计算机名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-136">Workspace Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-137">MED-V 工作区在其上运行的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-137">The name of the computer the MED-V workspace is running on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-138">Online</span><span class="sxs-lookup"><span data-stu-id="a4aa8-138">Online</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-139">客户端计算机的当前状态：</span><span class="sxs-lookup"><span data-stu-id="a4aa8-139">The current state of the client computer:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="a4aa8-140">禁用</span><span class="sxs-lookup"><span data-stu-id="a4aa8-140">Stopped</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="a4aa8-141">在 &lt; 工作区开始的日期和时间开始&gt;</span><span class="sxs-lookup"><span data-stu-id="a4aa8-141">Started at &lt;date and time the workspace was started&gt;</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-142">客户端版本</span><span class="sxs-lookup"><span data-stu-id="a4aa8-142">Client Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-143">客户端的版本号。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-143">The version number of the client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-144">策略版本</span><span class="sxs-lookup"><span data-stu-id="a4aa8-144">Policy Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-145">MED-V 工作区当前使用的策略版本。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-145">The policy version that the MED-V workspace is currently using.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-146">图像名称</span><span class="sxs-lookup"><span data-stu-id="a4aa8-146">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-147">图像的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-147">The name of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-148">图像版本</span><span class="sxs-lookup"><span data-stu-id="a4aa8-148">Image Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-149">MED-V 工作区当前正在使用的映像版本。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-149">The image version that the MED-V workspace is currently using.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a4aa8-150">注意</span><span class="sxs-lookup"><span data-stu-id="a4aa8-150">Note</span></span></strong><br/><p><span data-ttu-id="a4aa8-151">如果 MED-V 工作区版本尚未下载到计算机，则可能是未知的。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-151">MED-V workspace version can be Unknown if it has not yet been downloaded onto a computer.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganactivitylogreport"></a><span data-ttu-id="a4aa8-152">如何生成活动日志报告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-152">How to Generate an Activity Log Report</span></span>


**<span data-ttu-id="a4aa8-153">生成活动日志报告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-153">To generate an activity log report</span></span>**

1.  <span data-ttu-id="a4aa8-154">单击 "**报告**管理" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-154">Click the **Reports** management button.</span></span>

    <span data-ttu-id="a4aa8-155">将显示 "报告" 模块。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-155">The Reports module appears.</span></span>

2.  <span data-ttu-id="a4aa8-156">在 "**报表" 模块的**"**报表类型**" 菜单上，选择 "**活动日志**"，然后单击 "**生成**"。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-156">In the **Reports** module, on the **Report Types** menu, select **Activity Log**, and click **Generate**.</span></span>

3.  <span data-ttu-id="a4aa8-157">在 "**报表参数**" 对话框中，配置以下一个或多个参数：</span><span class="sxs-lookup"><span data-stu-id="a4aa8-157">In the **Report Parameters** dialog box, configure one or more of the following parameters:</span></span>

    -   <span data-ttu-id="a4aa8-158">**天数**-在报表中显示的天数。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-158">**Number of days**—The number of days to display in the report.</span></span>

    -   <span data-ttu-id="a4aa8-159">**用户名包含**-报告中包含用户名包含输入文本的任何事件。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-159">**User name contains**—Any event where the user name contains the text entered is included in the report.</span></span>

    -   <span data-ttu-id="a4aa8-160">**主机名包含**-报告中包含主机名中包含输入文本的任何事件。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-160">**Host name contains**—Any event where the host name contains the text entered is included in the report.</span></span>

4.  <span data-ttu-id="a4aa8-161">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-161">Click **OK**.</span></span>

    <span data-ttu-id="a4aa8-162">将生成一个报表，其中包含所选事件和日期。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-162">A report is generated with the events and dates selected.</span></span> <span data-ttu-id="a4aa8-163">下表中定义了报表参数。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-163">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="a4aa8-164">活动日志报表属性</span><span class="sxs-lookup"><span data-stu-id="a4aa8-164">Activity Log Report Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a4aa8-165">属性</span><span class="sxs-lookup"><span data-stu-id="a4aa8-165">Property</span></span></th>
<th align="left"><span data-ttu-id="a4aa8-166">描述</span><span class="sxs-lookup"><span data-stu-id="a4aa8-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-167">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a4aa8-167">Event ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-168">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-168">The event ID.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-169">严重性</span><span class="sxs-lookup"><span data-stu-id="a4aa8-169">Severity</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="a4aa8-170">信息、错误、警告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-170">Information, Error, Warning</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-171">类型</span><span class="sxs-lookup"><span data-stu-id="a4aa8-171">Category</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-172">报表所引用的模块。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-172">The module that the report is referring to.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-173">描述</span><span class="sxs-lookup"><span data-stu-id="a4aa8-173">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-174">事件的说明。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-174">A description of the event.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-175">收到时间</span><span class="sxs-lookup"><span data-stu-id="a4aa8-175">Time Received</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-176">在服务器上接收事件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-176">The date and time the event was received on the server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a4aa8-177">注意</span><span class="sxs-lookup"><span data-stu-id="a4aa8-177">Note</span></span></strong><br/><p><span data-ttu-id="a4aa8-178">如果客户端脱机工作，服务器将在客户端联机时收到报告。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-178">If the client is working offline, the server receives the reports when the client is online.</span></span></p>
</div>
<div>

</div>
<div class="alert">
<strong><span data-ttu-id="a4aa8-179">注意</span><span class="sxs-lookup"><span data-stu-id="a4aa8-179">Note</span></span></strong><br/><p><span data-ttu-id="a4aa8-180">默认情况下，事件以降序显示日期顺序。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-180">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="a4aa8-181">但是，可以通过单击 "接收时间" 列来更改它 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-181">However, it can be changed by clicking the <strong>Time Received</strong> column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-182">客户端时间</span><span class="sxs-lookup"><span data-stu-id="a4aa8-182">Client Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-183">根据客户端时钟事件发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-183">The date and time the event occurred according to the client clock.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-184">主机名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-184">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-185">主计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-185">The name of the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-186">用户名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-186">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-187">启动事件的用户。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-187">The user who initiated the event.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-188">工作区名称</span><span class="sxs-lookup"><span data-stu-id="a4aa8-188">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-189">MED-V 工作区的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-189">The name of the MED-V workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-190">工作区计算机名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-190">Workspace Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-191">MED-V 工作区在其上运行的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-191">The name of the computer the MED-V workspace is running on.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganerrorlogreport"></a><span data-ttu-id="a4aa8-192">如何生成错误日志报告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-192">How to Generate an Error Log Report</span></span>


**<span data-ttu-id="a4aa8-193">生成错误日志报告</span><span class="sxs-lookup"><span data-stu-id="a4aa8-193">To generate an error log report</span></span>**

1.  <span data-ttu-id="a4aa8-194">单击 "**报告**管理" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-194">Click the **Reports** management button.</span></span>

2.  <span data-ttu-id="a4aa8-195">在 "**报表" 模块的**"**报表类型**" 菜单上，选择 "**错误日志**"，然后单击 "**生成**"。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-195">In the **Reports** module, on the **Report Types** menu, select **Error Log**, and click **Generate**.</span></span>

3.  <span data-ttu-id="a4aa8-196">在 "**报表参数**" 对话框中，配置以下一个或多个参数：</span><span class="sxs-lookup"><span data-stu-id="a4aa8-196">In the **Report Parameters** dialog box, configure one or more of the following parameters:</span></span>

    -   <span data-ttu-id="a4aa8-197">**天数**-在报表中显示的天数。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-197">**Number of days**—The number of days to display in the report.</span></span>

    -   <span data-ttu-id="a4aa8-198">**用户名包含**-报告中包含用户名包含输入文本的任何事件。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-198">**User name contains**—Any event where the user name contains the text entered is included in the report.</span></span>

    -   <span data-ttu-id="a4aa8-199">**主机名包含**-报告中包含主机名中包含输入文本的任何事件。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-199">**Host name contains**—Any event where the host name contains the text entered is included in the report.</span></span>

4.  <span data-ttu-id="a4aa8-200">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-200">Click **OK**.</span></span>

    <span data-ttu-id="a4aa8-201">将生成一个报表，其中包含所选事件和日期。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-201">A report is generated with the events and dates selected.</span></span> <span data-ttu-id="a4aa8-202">下表中定义了报表参数。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-202">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="a4aa8-203">错误日志报告属性</span><span class="sxs-lookup"><span data-stu-id="a4aa8-203">Error Log Report Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a4aa8-204">属性</span><span class="sxs-lookup"><span data-stu-id="a4aa8-204">Property</span></span></th>
<th align="left"><span data-ttu-id="a4aa8-205">描述</span><span class="sxs-lookup"><span data-stu-id="a4aa8-205">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-206">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a4aa8-206">Event ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-207">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-207">The event ID.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-208">类型</span><span class="sxs-lookup"><span data-stu-id="a4aa8-208">Category</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-209">报表所引用的模块。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-209">The module that the report is referring to.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-210">描述</span><span class="sxs-lookup"><span data-stu-id="a4aa8-210">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-211">事件的说明。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-211">A description of the event.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-212">收到时间</span><span class="sxs-lookup"><span data-stu-id="a4aa8-212">Time Received</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-213">在服务器上接收事件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-213">The date and time the event was received on the server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a4aa8-214">注意</span><span class="sxs-lookup"><span data-stu-id="a4aa8-214">Note</span></span></strong><br/><p><span data-ttu-id="a4aa8-215">如果客户端脱机工作，服务器将在客户端联机时收到报告。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-215">If the client is working offline, the server receives the reports when the client is online.</span></span></p>
</div>
<div>

</div>
<div class="alert">
<strong><span data-ttu-id="a4aa8-216">注意</span><span class="sxs-lookup"><span data-stu-id="a4aa8-216">Note</span></span></strong><br/><p><span data-ttu-id="a4aa8-217">默认情况下，事件以降序显示日期顺序。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-217">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="a4aa8-218">但是，可以通过单击 "接收时间" 列来更改它 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-218">However, it can be changed by clicking the <strong>Time Received</strong> column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-219">客户端时间</span><span class="sxs-lookup"><span data-stu-id="a4aa8-219">Client Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-220">根据客户端时钟事件发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-220">The date and time the event occurred according to the client clock.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-221">主机名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-221">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-222">主计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-222">The name of the host computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a4aa8-223">用户名</span><span class="sxs-lookup"><span data-stu-id="a4aa8-223">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-224">启动事件的用户。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-224">The user who initiated the event.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a4aa8-225">工作区名称</span><span class="sxs-lookup"><span data-stu-id="a4aa8-225">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a4aa8-226">MED-V 工作区的名称。</span><span class="sxs-lookup"><span data-stu-id="a4aa8-226">The name of the MED-V workspace.</span></span></p></td>
</tr>
</tbody>
</table>











