---
title: 如何更改服务器日志记录级别和数据库参数
description: 如何更改服务器日志记录级别和数据库参数
author: dansimp
ms.assetid: e3ebaee5-6c4c-4aa8-9766-c5aeb00f477a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bb35ac09c5e23f4847662171b68284f868e66dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801655"
---
# <span data-ttu-id="b7768-103">如何更改服务器日志记录级别和数据库参数</span><span class="sxs-lookup"><span data-stu-id="b7768-103">How to Change the Server Logging Level and the Database Parameters</span></span>


<span data-ttu-id="b7768-104">你可以使用以下过程来更改应用程序虚拟化服务器管理控制台中的日志记录级别和数据库日志参数。</span><span class="sxs-lookup"><span data-stu-id="b7768-104">You can use the following procedures to change the logging level and the database log parameters from the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="b7768-105">以下日志记录级别可用：</span><span class="sxs-lookup"><span data-stu-id="b7768-105">The following logging levels are available:</span></span>

-   <span data-ttu-id="b7768-106">仅交易记录</span><span class="sxs-lookup"><span data-stu-id="b7768-106">Transaction Only</span></span>

-   <span data-ttu-id="b7768-107">致命错误</span><span class="sxs-lookup"><span data-stu-id="b7768-107">Fatal Errors</span></span>

-   <span data-ttu-id="b7768-108">错误</span><span class="sxs-lookup"><span data-stu-id="b7768-108">Errors</span></span>

-   <span data-ttu-id="b7768-109">警告/错误</span><span class="sxs-lookup"><span data-stu-id="b7768-109">Warnings/Errors</span></span>

-   <span data-ttu-id="b7768-110">信息/警告/错误</span><span class="sxs-lookup"><span data-stu-id="b7768-110">Info/Warnings/Errors</span></span>

-   <span data-ttu-id="b7768-111">详细</span><span class="sxs-lookup"><span data-stu-id="b7768-111">Verbose</span></span>

<span data-ttu-id="b7768-112">**注意** 由于在使用**Verbose**模式时生成的日志文件的大小，因此建议你不要运行具有此日志记录集级别的生产服务器。</span><span class="sxs-lookup"><span data-stu-id="b7768-112">**Note** Because of the size of the log file produced when you use **Verbose** mode, the recommendation is that you do not run production servers with this level of logging set.</span></span>

 

<span data-ttu-id="b7768-113">数据库日志记录参数确定了日志记录数据库的数据库驱动程序类型、访问凭据和位置。</span><span class="sxs-lookup"><span data-stu-id="b7768-113">The database logging parameters determine the database driver type, access credentials, and location of the logging database.</span></span>

**<span data-ttu-id="b7768-114">更改管理服务器的日志记录级别</span><span class="sxs-lookup"><span data-stu-id="b7768-114">To change the logging level for Management Servers</span></span>**

1.  <span data-ttu-id="b7768-115">单击 "**服务器组**" 节点以显示服务器组。</span><span class="sxs-lookup"><span data-stu-id="b7768-115">Click the **Server Groups** node to display the server groups.</span></span>

2.  <span data-ttu-id="b7768-116">右键单击服务器组，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="b7768-116">Right-click the server group, and select **Properties**.</span></span>

3.  <span data-ttu-id="b7768-117">在 "**属性**" 对话框中，选择 "**日志记录**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b7768-117">In the **Properties** dialog box, select the **Logging** tab.</span></span>

4.  <span data-ttu-id="b7768-118">在 "**服务器组属性**" 对话框中，选择服务器，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b7768-118">In the **Server Group Properties** dialog box, select the server and then click **Edit**.</span></span>

5.  <span data-ttu-id="b7768-119">在 "**添加/编辑日志模块**" 对话框中，从 "**事件类型**" 下拉列表中选择日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="b7768-119">In the **Add/Edit Log Module** dialog box, select the logging level from the **Event Type** drop-down list.</span></span>

6.  <span data-ttu-id="b7768-120">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7768-120">Click **OK**.</span></span>

7.  <span data-ttu-id="b7768-121">在 "**服务器组属性**" 对话框中，单击 **"确定" 或 "** **应用**"。</span><span class="sxs-lookup"><span data-stu-id="b7768-121">In the **Server Group Properties** dialog box, click **OK** or **Apply**.</span></span>

**<span data-ttu-id="b7768-122">更改流式服务器的日志记录级别</span><span class="sxs-lookup"><span data-stu-id="b7768-122">To change the logging level for Streaming Servers</span></span>**

1.  <span data-ttu-id="b7768-123">编辑以下注册表项值以更改日志记录级别：</span><span class="sxs-lookup"><span data-stu-id="b7768-123">Edit the following registry key value to change the logging level:</span></span>

    -   <span data-ttu-id="b7768-124">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel</span><span class="sxs-lookup"><span data-stu-id="b7768-124">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel</span></span>

2.  <span data-ttu-id="b7768-125">选择以下值之一以设置日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="b7768-125">Select one of the following values to set the logging level.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="b7768-126">值</span><span class="sxs-lookup"><span data-stu-id="b7768-126">Value</span></span></th>
    <th align="left"><span data-ttu-id="b7768-127">日志记录级别</span><span class="sxs-lookup"><span data-stu-id="b7768-127">Logging Level</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="b7768-128">0</span><span class="sxs-lookup"><span data-stu-id="b7768-128">0</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b7768-129">仅交易记录</span><span class="sxs-lookup"><span data-stu-id="b7768-129">Transactions Only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="b7768-130">raid-1</span><span class="sxs-lookup"><span data-stu-id="b7768-130">1</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b7768-131">致命错误</span><span class="sxs-lookup"><span data-stu-id="b7768-131">Fatal Errors</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="b7768-132">ppls-2</span><span class="sxs-lookup"><span data-stu-id="b7768-132">2</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b7768-133">错误</span><span class="sxs-lookup"><span data-stu-id="b7768-133">Errors</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="b7768-134">三维空间</span><span class="sxs-lookup"><span data-stu-id="b7768-134">3</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b7768-135">警告/错误</span><span class="sxs-lookup"><span data-stu-id="b7768-135">Warnings/Errors</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="b7768-136">第</span><span class="sxs-lookup"><span data-stu-id="b7768-136">4</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b7768-137">信息/警告/错误</span><span class="sxs-lookup"><span data-stu-id="b7768-137">Information/ Warnings/Errors</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="b7768-138">级</span><span class="sxs-lookup"><span data-stu-id="b7768-138">5</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b7768-139">详细</span><span class="sxs-lookup"><span data-stu-id="b7768-139">Verbose</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="b7768-140">更改数据库日志参数</span><span class="sxs-lookup"><span data-stu-id="b7768-140">To change database log parameters</span></span>**

1.  <span data-ttu-id="b7768-141">单击 "**服务器组**" 节点以显示服务器组。</span><span class="sxs-lookup"><span data-stu-id="b7768-141">Click the **Server Groups** node to display the server groups.</span></span>

2.  <span data-ttu-id="b7768-142">右键单击服务器组，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="b7768-142">Right-click the server group, and select **Properties**.</span></span>

3.  <span data-ttu-id="b7768-143">在 "**属性**" 对话框中，选择 "**日志记录**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b7768-143">In the **Properties** dialog box, select the **Logging** tab.</span></span>

4.  <span data-ttu-id="b7768-144">在 "**服务器组属性**" 对话框中，选择服务器，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b7768-144">In the **Server Group Properties** dialog box, select the server and then click **Edit**.</span></span>

5.  <span data-ttu-id="b7768-145">在 "**添加/编辑日志模块**" 对话框中，从 "**数据库驱动程序**" 下拉列表中选择数据库驱动程序。</span><span class="sxs-lookup"><span data-stu-id="b7768-145">In the **Add/Edit Log Module** dialog box, select a database driver from the **Database Driver** drop-down list.</span></span>

6.  <span data-ttu-id="b7768-146">输入**DNS 主机名**。</span><span class="sxs-lookup"><span data-stu-id="b7768-146">Enter a **DNS Host Name**.</span></span>

7.  <span data-ttu-id="b7768-147">单击 "**动态确定端口**" 复选框，或在 "**端口**" 字段中输入一个端口号。</span><span class="sxs-lookup"><span data-stu-id="b7768-147">Click the **Dynamically Determine Port** check box, or enter a port number in the **Port** field.</span></span>

8.  <span data-ttu-id="b7768-148">在对应字段中输入**服务名称**。</span><span class="sxs-lookup"><span data-stu-id="b7768-148">Enter a **Service Name** in the corresponding field.</span></span>

9.  <span data-ttu-id="b7768-149">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7768-149">Click **OK**.</span></span>

10. <span data-ttu-id="b7768-150">在 "**服务器组属性**" 对话框中，单击 **"确定" 或 "** **应用**"。</span><span class="sxs-lookup"><span data-stu-id="b7768-150">On the **Server Group Properties** dialog box, click **OK** or **Apply**.</span></span>

## <span data-ttu-id="b7768-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="b7768-151">Related topics</span></span>


[<span data-ttu-id="b7768-152">如何在 Server Management Console 中自定义 Application Virtualization System</span><span class="sxs-lookup"><span data-stu-id="b7768-152">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

 

 





