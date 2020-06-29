---
title: 如何安装 Sequencer
description: 如何安装 Sequencer
author: dansimp
ms.assetid: 5e8f1696-9bc0-4f44-8cb7-b809b2daae10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b72330718a14cb8ffb0e582c946ff1e70539036c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798427"
---
# <span data-ttu-id="cfb79-103">如何安装 Sequencer</span><span class="sxs-lookup"><span data-stu-id="cfb79-103">How to Install the Sequencer</span></span>


<span data-ttu-id="cfb79-104">使用以下过程安装 Microsoft Application Virtualization （App-v） 5.1 sequencer。</span><span class="sxs-lookup"><span data-stu-id="cfb79-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.1 sequencer.</span></span> <span data-ttu-id="cfb79-105">将运行 sequencer 的计算机不能运行任何版本的 App-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="cfb79-105">The computer that will run the sequencer must not be running any version of the App-V 5.1 client.</span></span>

<span data-ttu-id="cfb79-106">不支持升级以前安装的 app-v sequencer。</span><span class="sxs-lookup"><span data-stu-id="cfb79-106">Upgrading a previous installation of the App-V sequencer is not supported.</span></span>

<span data-ttu-id="cfb79-107">**重要提示** 有关 sequencer 要求的完整列表，请参阅[app-v 5.1 先决条件](app-v-51-prerequisites.md)和[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)的 sequencer 部分。</span><span class="sxs-lookup"><span data-stu-id="cfb79-107">**Important** For a full list of the sequencer requirements see sequencer sections of [App-V 5.1 Prerequisites](app-v-51-prerequisites.md) and [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

 

<span data-ttu-id="cfb79-108">你还可以使用命令行安装 app-v 5.1 sequencer。</span><span class="sxs-lookup"><span data-stu-id="cfb79-108">You can also use the command line to install the App-V 5.1 sequencer.</span></span> <span data-ttu-id="cfb79-109">以下列表显示有关使用命令行和**appv\_sequencer\_setup.exe**安装 sequencer 的选项的信息：</span><span class="sxs-lookup"><span data-stu-id="cfb79-109">The following list displays information about options for installing the sequencer using the command line and **appv\_sequencer\_setup.exe**:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cfb79-110">命令</span><span class="sxs-lookup"><span data-stu-id="cfb79-110">Command</span></span></th>
<th align="left"><span data-ttu-id="cfb79-111">描述</span><span class="sxs-lookup"><span data-stu-id="cfb79-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cfb79-112">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="cfb79-112">/INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-113">指定安装目录。</span><span class="sxs-lookup"><span data-stu-id="cfb79-113">Specifies the installation directory.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cfb79-114">/CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="cfb79-114">/CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-115">允许参与 Microsoft 客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="cfb79-115">Enables participation in the Microsoft Customer Experience Improvement Program.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cfb79-116">/Log</span><span class="sxs-lookup"><span data-stu-id="cfb79-116">/Log</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-117">指定将保存安装日志的位置，默认位置为 <strong> % Temp% </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cfb79-117">Specifies where the installation log will be saved, the default location is <strong>%Temp%</strong>.</span></span> <span data-ttu-id="cfb79-118">例如， <strong> C：\日志记录 \ </strong> .log。</span><span class="sxs-lookup"><span data-stu-id="cfb79-118">For example, <strong>C:\ Logs \ log.log</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cfb79-119">/q</span><span class="sxs-lookup"><span data-stu-id="cfb79-119">/q</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-120">指定安静或静默安装。</span><span class="sxs-lookup"><span data-stu-id="cfb79-120">Specifies a quiet or silent installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cfb79-121">/Uninstall</span><span class="sxs-lookup"><span data-stu-id="cfb79-121">/Uninstall</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-122">指定删除 sequencer。</span><span class="sxs-lookup"><span data-stu-id="cfb79-122">Specifies the removal of the sequencer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cfb79-123">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="cfb79-123">/ACCEPTEULA</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-124">接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="cfb79-124">Accepts the license agreement.</span></span> <span data-ttu-id="cfb79-125">这是无人参与安装所必需的。</span><span class="sxs-lookup"><span data-stu-id="cfb79-125">This is required for an unattended installation.</span></span> <span data-ttu-id="cfb79-126">示例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cfb79-126">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cfb79-127">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="cfb79-127">/LAYOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-128">指定关联的布局操作。</span><span class="sxs-lookup"><span data-stu-id="cfb79-128">Specifies the associated layout action.</span></span> <span data-ttu-id="cfb79-129">它还将 Windows Installer （.msi）和脚本文件提取到文件夹中，但不安装 app-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="cfb79-129">It also extracts the Windows Installer (.msi) and script files to a folder without installing App-V 5.1.</span></span> <span data-ttu-id="cfb79-130">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="cfb79-130">No value is expected.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cfb79-131">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="cfb79-131">/LAYOUTDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-132">指定布局目录。</span><span class="sxs-lookup"><span data-stu-id="cfb79-132">Specifies the layout directory.</span></span> <span data-ttu-id="cfb79-133">需要字符串值。</span><span class="sxs-lookup"><span data-stu-id="cfb79-133">Requires a string value.</span></span> <span data-ttu-id="cfb79-134">示例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 客户端" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cfb79-134">Example usage: <strong>/LAYOUTDIR=”C:\Application Virtualization Client”</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cfb79-135">/?</span><span class="sxs-lookup"><span data-stu-id="cfb79-135">/?</span></span> <span data-ttu-id="cfb79-136">或/h 或/help</span><span class="sxs-lookup"><span data-stu-id="cfb79-136">Or /h or /help</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfb79-137">显示相关帮助。</span><span class="sxs-lookup"><span data-stu-id="cfb79-137">Displays associated help.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="cfb79-138">安装 app-v 5.1 sequencer</span><span class="sxs-lookup"><span data-stu-id="cfb79-138">To install the App-V 5.1 sequencer</span></span>**

1.  <span data-ttu-id="cfb79-139">将 app-v 5.1 sequencer 安装文件复制到将在其上安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="cfb79-139">Copy the App-V 5.1 sequencer installation files to the computer on which it will be installed.</span></span> <span data-ttu-id="cfb79-140">双击 " **appv\_sequencer\_setup.exe** "，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="cfb79-140">Double-click **appv\_sequencer\_setup.exe** and then click **Install**.</span></span>

2.  <span data-ttu-id="cfb79-141">在 "**软件许可条款**" 页面上，应查看许可条款。</span><span class="sxs-lookup"><span data-stu-id="cfb79-141">On the **Software License Terms** page, you should review the license terms.</span></span> <span data-ttu-id="cfb79-142">接受许可条款选择 "**我接受许可条款"。**</span><span class="sxs-lookup"><span data-stu-id="cfb79-142">To accept the license terms select **I accept the license terms.**</span></span> <span data-ttu-id="cfb79-143">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfb79-143">Click **Next**.</span></span>

3.  <span data-ttu-id="cfb79-144">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="cfb79-144">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="cfb79-145">若要从运行中禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="cfb79-145">To disable Microsoft updates from running select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="cfb79-146">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfb79-146">Click **Next**.</span></span>

4.  <span data-ttu-id="cfb79-147">在 "**客户体验改善计划**" 页面上，若要参与计划，请选择 "**加入客户体验改善计划"**。</span><span class="sxs-lookup"><span data-stu-id="cfb79-147">On the **Customer Experience Improvement Program** page, to participate in the program select **Join the Customer Experience Improvement Program**.</span></span> <span data-ttu-id="cfb79-148">这将允许收集有关使用 app-v 5.1 的方式的信息。</span><span class="sxs-lookup"><span data-stu-id="cfb79-148">This will allow information to be collected about how you are using App-V 5.1.</span></span> <span data-ttu-id="cfb79-149">如果您不想参与该计划，请选择 "**我现在不想加入程序"**。</span><span class="sxs-lookup"><span data-stu-id="cfb79-149">If you don’t want to participate in the program select **I don’t want to join the program at this time**.</span></span> <span data-ttu-id="cfb79-150">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="cfb79-150">Click **Install**.</span></span>

5.  <span data-ttu-id="cfb79-151">若要打开排序器，请单击 "**开始**"，然后单击 " **Microsoft Application Virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="cfb79-151">To open the sequencer, click **Start** and then click **Microsoft Application Virtualization Sequencer**.</span></span>

**<span data-ttu-id="cfb79-152">解决 app-v 5.1 sequencer 安装</span><span class="sxs-lookup"><span data-stu-id="cfb79-152">To troubleshoot the App-V 5.1 sequencer installation</span></span>**

-   <span data-ttu-id="cfb79-153">有关 sequencer 安装的详细信息，您可以在 **% temp%** 文件夹中查看错误日志。</span><span class="sxs-lookup"><span data-stu-id="cfb79-153">For more information regarding the sequencer installation, you can view the error log in the **%temp%** folder.</span></span> <span data-ttu-id="cfb79-154">若要查看日志文件，请单击 "**开始**"，键入 **% temp%**，然后查找**appv\_ 日志**。</span><span class="sxs-lookup"><span data-stu-id="cfb79-154">To review the log files, click **Start**, type **%temp%**, and then look for the **appv\_ log**.</span></span>

    <span data-ttu-id="cfb79-155">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="cfb79-155">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="cfb79-156">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="cfb79-156">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="cfb79-157">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="cfb79-157">Got an App-V issue?</span></span>** <span data-ttu-id="cfb79-158">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="cfb79-158">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="cfb79-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="cfb79-159">Related topics</span></span>


[<span data-ttu-id="cfb79-160">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="cfb79-160">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





