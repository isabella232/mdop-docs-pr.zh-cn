---
title: 功能可见性设置
description: 功能可见性设置
author: dansimp
ms.assetid: 9db2ba03-fb75-4f95-9138-ec89b9fc8d01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f19895d0a9163885779688ba7d89f6d16f2a17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802764"
---
# <span data-ttu-id="37822-103">功能可见性设置</span><span class="sxs-lookup"><span data-stu-id="37822-103">Feature Visibility Settings</span></span>


<span data-ttu-id="37822-104">通过高级组策略管理（AGPM）的管理模板设置，你可以集中配置组策略对象（GPO）应用了组策略对象（GPO）的 "**更改控制**节点和**历史记录**" 选项卡的可见性。</span><span class="sxs-lookup"><span data-stu-id="37822-104">The Administrative template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure the visibility of the **Change Control** node and **History** tab for Group Policy administrators to whom a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="37822-105">在组策略管理控制台（GPMC）中编辑 GPO 时，"组策略对象编辑器" 中的 "用户 Configuration\\Administrative" 下提供了以下设置： "**组策略对象编辑器**" 中的 "Components\\Microsoft 管理控制台 \ \ 受限/允许 Snap-ins\\Extension" 管理单元。</span><span class="sxs-lookup"><span data-stu-id="37822-105">The following settings are available under User Configuration\\Administrative Templates\\Windows Components\\Microsoft Management Console\\Restricted/Permitted Snap-ins\\Extension Snap-ins in the **Group Policy Object Editor** when editing a GPO in the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="37822-106">如果此路径不可见，请右键单击 "**管理模板**"，然后添加 "agpm" 或 "agpm .adm" 模板。</span><span class="sxs-lookup"><span data-stu-id="37822-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="37822-107">设置</span><span class="sxs-lookup"><span data-stu-id="37822-107">Setting</span></span></th>
<th align="left"><span data-ttu-id="37822-108">作用</span><span class="sxs-lookup"><span data-stu-id="37822-108">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="37822-109">AGPM 更改控件</span><span class="sxs-lookup"><span data-stu-id="37822-109">AGPM Change Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="37822-110">如果已启用或未配置，则在 <strong> GPMC 中将显示 "更改控制 </strong> " 节点。</span><span class="sxs-lookup"><span data-stu-id="37822-110">If enabled or not configured, the <strong>Change Control</strong> node is visible in the GPMC.</span></span></p>
<p><span data-ttu-id="37822-111">如果已禁用，则 " <strong> 更改控制" </strong> 节点在 GPMC 中不可见。</span><span class="sxs-lookup"><span data-stu-id="37822-111">If disabled, the <strong>Change Control</strong> node is not visible in the GPMC.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="37822-112">AGPM 链接扩展</span><span class="sxs-lookup"><span data-stu-id="37822-112">AGPM Link Extension</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="37822-113">如果已启用或未配置， <strong> 则 </strong> 会在 GPMC 中为每个链接的 GPO 显示 "历史记录" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="37822-113">If enabled or not configured, a <strong>History</strong> tab appears in the GPMC for each linked GPO.</span></span></p>
<p><span data-ttu-id="37822-114">如果已禁用，则 " <strong> 历史记录" </strong> 选项卡对于链接的 gpo 不可见。</span><span class="sxs-lookup"><span data-stu-id="37822-114">If disabled, the <strong>History</strong> tab is not visible for linked GPOs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="37822-115">AGPM GPO 扩展</span><span class="sxs-lookup"><span data-stu-id="37822-115">AGPM GPO Extension</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="37822-116">如果已启用或未配置， <strong> 则 </strong> 会在 GPMC 中为每个 GPO 显示 "历史记录" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="37822-116">If enabled or not configured, a <strong>History</strong> tab appears in the GPMC for each GPO.</span></span></p>
<p><span data-ttu-id="37822-117">如果禁用，则 " <strong> 历史记录" </strong> 选项卡对于 gpo 不可见。</span><span class="sxs-lookup"><span data-stu-id="37822-117">If disabled, the <strong>History</strong> tab is not visible for GPOs.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="37822-118">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="37822-118">Additional references</span></span>

-   [<span data-ttu-id="37822-119">管理模板设置</span><span class="sxs-lookup"><span data-stu-id="37822-119">Administrative Template Settings</span></span>](administrative-template-settings.md)

 

 





