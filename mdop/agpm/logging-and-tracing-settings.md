---
title: 记录和跟踪设置
description: 记录和跟踪设置
author: dansimp
ms.assetid: db6b43c7-fdde-4d11-b5ab-a81346e56940
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bef0f8367647aad688c2aec7586ecdaae2e22143
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802676"
---
# <span data-ttu-id="b3ba7-103">记录和跟踪设置</span><span class="sxs-lookup"><span data-stu-id="b3ba7-103">Logging and Tracing Settings</span></span>


<span data-ttu-id="b3ba7-104">通过高级组策略管理（AGPM）的管理模板设置，你可以为已应用了组策略对象（GPO）的 AGPM 服务器和客户集中配置日志记录和跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="b3ba7-104">The Administrative Template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure logging and tracing options for AGPM Servers and clients to which a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="b3ba7-105">在组策略管理控制台（GPMC）中编辑 GPO 时，"**组策略对象编辑器**" 中的 "计算机 Configuration\\Administrative Templates\\Windows Components\\AGPM 下将提供以下设置。</span><span class="sxs-lookup"><span data-stu-id="b3ba7-105">The following setting is available under Computer Configuration\\Administrative Templates\\Windows Components\\AGPM in the **Group Policy Object Editor** when editing a GPO in the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="b3ba7-106">如果此路径不可见，请右键单击 "**管理模板**"，然后添加 "agpm" 或 "agpm .adm" 模板。</span><span class="sxs-lookup"><span data-stu-id="b3ba7-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<span data-ttu-id="b3ba7-107">**跟踪文件位置**：</span><span class="sxs-lookup"><span data-stu-id="b3ba7-107">**Trace file locations**:</span></span>

-   <span data-ttu-id="b3ba7-108">客户端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="b3ba7-108">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

-   <span data-ttu-id="b3ba7-109">服务器：%CommonAppData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="b3ba7-109">Server: %CommonAppData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b3ba7-110">设置</span><span class="sxs-lookup"><span data-stu-id="b3ba7-110">Setting</span></span></th>
<th align="left"><span data-ttu-id="b3ba7-111">作用</span><span class="sxs-lookup"><span data-stu-id="b3ba7-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b3ba7-112">AGPM 日志记录</span><span class="sxs-lookup"><span data-stu-id="b3ba7-112">AGPM Logging</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b3ba7-113">如果已启用，此设置将配置跟踪是否处于打开状态以及详细级别。</span><span class="sxs-lookup"><span data-stu-id="b3ba7-113">If enabled, this setting configures whether tracing is turned on and the level of detail.</span></span> <span data-ttu-id="b3ba7-114">此设置会影响 AGPM 的客户端和服务器组件。</span><span class="sxs-lookup"><span data-stu-id="b3ba7-114">This setting affects both client and server components of AGPM.</span></span></p>
<p><span data-ttu-id="b3ba7-115">如果已禁用或未配置，此设置将不起作用。</span><span class="sxs-lookup"><span data-stu-id="b3ba7-115">If disabled or not configured, this setting has no effect.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="b3ba7-116">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="b3ba7-116">Additional references</span></span>

-   [<span data-ttu-id="b3ba7-117">管理模板设置</span><span class="sxs-lookup"><span data-stu-id="b3ba7-117">Administrative Template Settings</span></span>](administrative-template-settings.md)

 

 





