---
title: 如何仅允许管理员启用连接组
description: 如何仅允许管理员启用连接组
author: dansimp
ms.assetid: 60e62426-624f-4f26-851e-41cd78520883
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 53461d5c93bf246210c7427c95a8bbe8acca9cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798551"
---
# <span data-ttu-id="b0feb-103">如何仅允许管理员启用连接组</span><span class="sxs-lookup"><span data-stu-id="b0feb-103">How to Allow Only Administrators to Enable Connection Groups</span></span>


<span data-ttu-id="b0feb-104">你可以配置 App-v 客户端，以便只有管理员（而非最终用户）可以启用或禁用连接组。</span><span class="sxs-lookup"><span data-stu-id="b0feb-104">You can configure the App-V client so that only administrators (not end users) can enable or disable connection groups.</span></span> <span data-ttu-id="b0feb-105">在早期版本的 App-v 中，你不能阻止最终用户执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="b0feb-105">In earlier versions of App-V, you could not prevent end users from performing these tasks.</span></span>

<span data-ttu-id="b0feb-106">**注意** 
**从 app-v 5.0 SP3 开始，支持此功能。**</span><span class="sxs-lookup"><span data-stu-id="b0feb-106">**Note**
**This feature is supported starting in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="b0feb-107">使用以下方法之一，仅允许管理员启用或禁用连接组。</span><span class="sxs-lookup"><span data-stu-id="b0feb-107">Use one of the following methods to allow only administrators to enable or disable connection groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b0feb-108">方法</span><span class="sxs-lookup"><span data-stu-id="b0feb-108">Method</span></span></th>
<th align="left"><span data-ttu-id="b0feb-109">步骤</span><span class="sxs-lookup"><span data-stu-id="b0feb-109">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b0feb-110">组策略设置</span><span class="sxs-lookup"><span data-stu-id="b0feb-110">Group Policy setting</span></span></p></td>
<td align="left"><p><span data-ttu-id="b0feb-111">启用 "要求发布为管理员" 组策略设置，该设置位于以下组策略对象节点中：</span><span class="sxs-lookup"><span data-stu-id="b0feb-111">Enable the “Require publish as administrator” Group Policy setting, which is located in the following Group Policy Object node:</span></span></p>
<p><strong><span data-ttu-id="b0feb-112">计算机配置 &gt; 策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布</span><span class="sxs-lookup"><span data-stu-id="b0feb-112">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b0feb-113">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0feb-113">PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="b0feb-114"><strong> </strong> 通过 <strong> -RequirePublishAsAdmin 参数运行 AppvClientConfiguration cmdlet </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b0feb-114">Run the <strong>Set-AppvClientConfiguration</strong> cmdlet with the <strong>–RequirePublishAsAdmin</strong> parameter.</span></span></p>
<p><span data-ttu-id="b0feb-115">参数值：</span><span class="sxs-lookup"><span data-stu-id="b0feb-115">Parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="b0feb-116">0-假</span><span class="sxs-lookup"><span data-stu-id="b0feb-116">0 - False</span></span></p></li>
<li><p><span data-ttu-id="b0feb-117">1-True</span><span class="sxs-lookup"><span data-stu-id="b0feb-117">1 - True</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="b0feb-118">示例： </strong> ： Set-AppvClientConfiguration-RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="b0feb-118">Example:</strong>: Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b0feb-119">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="b0feb-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="b0feb-120">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="b0feb-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="b0feb-121">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="b0feb-121">Got an App-V issue?</span></span>** <span data-ttu-id="b0feb-122">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="b0feb-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="b0feb-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0feb-123">Related topics</span></span>


[<span data-ttu-id="b0feb-124">管理连接组</span><span class="sxs-lookup"><span data-stu-id="b0feb-124">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





