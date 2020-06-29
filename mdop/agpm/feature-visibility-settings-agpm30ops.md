---
title: 功能可见性设置
description: 功能可见性设置
author: dansimp
ms.assetid: 6a844478-a6b0-490d-923f-5a6f82467831
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b147ab79872b5dd37f24a859625562bd2198a786
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802775"
---
# <span data-ttu-id="4ee36-103">功能可见性设置</span><span class="sxs-lookup"><span data-stu-id="4ee36-103">Feature Visibility Settings</span></span>


<span data-ttu-id="4ee36-104">通过高级组策略管理（AGPM）的管理模板设置，你可以集中配置组策略对象（GPO）应用了组策略对象（GPO）的 "**更改控制**文件夹和**历史记录**" 选项卡的可见性。</span><span class="sxs-lookup"><span data-stu-id="4ee36-104">The Administrative template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure the visibility of the **Change Control** folder and **History** tab for Group Policy administrators to whom a Group Policy Object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="4ee36-105">编辑 GPO 时，"用户 Configuration\\Policies\\Administrative" 下的 "用户 Templates\\Windows" 下提供了以下设置： Components\\Microsoft 管理控制台 \ \ 受限/允许 Snap-ins\\Extension 管理单元。</span><span class="sxs-lookup"><span data-stu-id="4ee36-105">The following settings are available under User Configuration\\Policies\\Administrative Templates\\Windows Components\\Microsoft Management Console\\Restricted/Permitted Snap-ins\\Extension Snap-ins when editing a GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ee36-106">设置</span><span class="sxs-lookup"><span data-stu-id="4ee36-106">Setting</span></span></th>
<th align="left"><span data-ttu-id="4ee36-107">作用</span><span class="sxs-lookup"><span data-stu-id="4ee36-107">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4ee36-108">AGPM：显示 "更改控件" 选项卡</span><span class="sxs-lookup"><span data-stu-id="4ee36-108">AGPM: Show Change Control tab</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ee36-109">此策略设置允许你控制 <strong> </strong> 组策略管理控制台（GPMC）中 "更改控制" 文件夹的可见性。</span><span class="sxs-lookup"><span data-stu-id="4ee36-109">This policy setting allows you to control the visibility of the <strong>Change Control</strong> folder in the Group Policy Management Console (GPMC).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4ee36-110">AGPM：链接的 Gpo 的 "显示历史记录" 选项卡</span><span class="sxs-lookup"><span data-stu-id="4ee36-110">AGPM: Show History tab for linked GPOs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ee36-111"><strong> </strong> 当你在 GPMC 中查看链接的 GPO 时，此策略设置允许你控制由 AGPM 提供的 "历史记录" 选项卡的可见性。</span><span class="sxs-lookup"><span data-stu-id="4ee36-111">This policy setting allows you to control the visibility of the <strong>History</strong> tab provided by AGPM when you view a linked GPO in the GPMC.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4ee36-112">AGPM： Gpo 的 "显示历史记录" 选项卡</span><span class="sxs-lookup"><span data-stu-id="4ee36-112">AGPM: Show History tab for GPOs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ee36-113">通过此策略设置，你可以控制 <strong> </strong> 当你在 GPMC 中查看 GPO 时由 AGPM 提供的 "历史记录" 选项卡的可见性。</span><span class="sxs-lookup"><span data-stu-id="4ee36-113">This policy setting allows you to control the visibility of the <strong>History</strong> tab provided by AGPM when you view a GPO in the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4ee36-114">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="4ee36-114">Additional references</span></span>

-   [<span data-ttu-id="4ee36-115">“管理模板”文件夹</span><span class="sxs-lookup"><span data-stu-id="4ee36-115">Administrative Templates Folder</span></span>](administrative-templates-folder-agpm30ops.md)

 

 





