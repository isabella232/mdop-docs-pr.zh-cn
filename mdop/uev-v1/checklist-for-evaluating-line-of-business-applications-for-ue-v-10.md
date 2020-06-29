---
title: 评估 UE-V 1.0 的业务线应用程序清单
description: 评估 UE-V 1.0 的业务线应用程序清单
author: dansimp
ms.assetid: 3bfaab30-59f7-4099-abb1-d248ce0086b8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 133bc5d195763b7281fd8d152e153231ac4c4d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803972"
---
# <span data-ttu-id="05cc7-103">评估 UE-V 1.0 的业务线应用程序清单</span><span class="sxs-lookup"><span data-stu-id="05cc7-103">Checklist for Evaluating Line-of-Business Applications for UE-V 1.0</span></span>


<span data-ttu-id="05cc7-104">若要评估在 UE-V 部署中应包括哪些业务线应用程序，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="05cc7-104">To evaluate which line-of-business applications should be included in your UE-V deployment, consider the following:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="05cc7-105">描述</span><span class="sxs-lookup"><span data-stu-id="05cc7-105">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="05cc7-106">此应用程序是否包含用户可自定义的设置？</span><span class="sxs-lookup"><span data-stu-id="05cc7-106">Does this application contain settings that the user can customize?</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="05cc7-107">用户是否对这些设置进行漫游非常重要？</span><span class="sxs-lookup"><span data-stu-id="05cc7-107">Is it important for the user that these settings roam?</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="05cc7-108">这些用户设置是否已由应用程序管理或设置策略解决方案管理？</span><span class="sxs-lookup"><span data-stu-id="05cc7-108">Are these user settings already managed by an application management or settings policy solution?</span></span> <span data-ttu-id="05cc7-109">UE-V 在登录、解锁或远程连接事件时，在应用程序启动和 Windows 设置中应用应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="05cc7-109">UE-V applies application settings at application launch and Windows settings at logon, unlock, or remote connect events.</span></span> <span data-ttu-id="05cc7-110">如果你将 UE-V 与其他设置策略解决方案配合使用，则用户在漫游设置中可能会遇到不一致的情况。</span><span class="sxs-lookup"><span data-stu-id="05cc7-110">If you use UE-V with other settings policy solutions, users might experience inconsistency across roamed settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="05cc7-111">应用程序设置是否特定于计算机？</span><span class="sxs-lookup"><span data-stu-id="05cc7-111">Are the application settings specific to the computer?</span></span> <span data-ttu-id="05cc7-112">与硬件或特定计算机配置相关联的应用程序首选项和自定义不会在多个会话之间持续漫游，并且可能导致应用程序体验较差。</span><span class="sxs-lookup"><span data-stu-id="05cc7-112">Application preferences and customizations that are associated with hardware or specific computer configurations do not consistently roam across sessions and can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="05cc7-113">应用程序将设置存储在 "程序文件" 目录中还是位于 " <strong> 用户 </strong> 名称" \ <strong> AppData </strong>  \  <strong> LocalLow </strong> 目录中的文件目录？</span><span class="sxs-lookup"><span data-stu-id="05cc7-113">Does the application store settings in the Program Files directory or in the file directory that is located in the <strong>Users</strong> \ [User name] \ <strong>AppData</strong> \ <strong>LocalLow</strong> directory?</span></span> <span data-ttu-id="05cc7-114">存储在其中任一位置的应用程序数据通常不应与用户漫游，因为此数据特定于计算机，或者由于数据太大而无法进行漫游。</span><span class="sxs-lookup"><span data-stu-id="05cc7-114">Application data that is stored in either of these locations usually should not roam with the user, because this data is specific to the computer or because the data is too large to roam.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="05cc7-115">应用程序是否在包含不应漫游的其他应用程序数据的文件中存储任何设置？</span><span class="sxs-lookup"><span data-stu-id="05cc7-115">Does the application store any settings in a file that contains other application data that should not roam?</span></span> <span data-ttu-id="05cc7-116">UE-V 将文件作为单个单元进行同步。</span><span class="sxs-lookup"><span data-stu-id="05cc7-116">UE-V synchronizes files as a single unit.</span></span> <span data-ttu-id="05cc7-117">如果设置存储在包含应用程序数据而不是设置的文件中，则同步这些附加数据可能会导致应用程序体验较差。</span><span class="sxs-lookup"><span data-stu-id="05cc7-117">If settings are stored in files that include application data other than settings, then synchronizing this additional data may cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="05cc7-118">包含这些设置的文件有多大？</span><span class="sxs-lookup"><span data-stu-id="05cc7-118">How large are the files that contain the settings?</span></span> <span data-ttu-id="05cc7-119">设置同步的性能可能会受到大型文件的影响。</span><span class="sxs-lookup"><span data-stu-id="05cc7-119">The performance of the settings synchronization can be affected by large files.</span></span> <span data-ttu-id="05cc7-120">包括大型文件会影响设置同步的性能。</span><span class="sxs-lookup"><span data-stu-id="05cc7-120">Including large files can impact the performance of settings synchronization.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="05cc7-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="05cc7-121">Related topics</span></span>


[<span data-ttu-id="05cc7-122">规划 UE-V 配置方法</span><span class="sxs-lookup"><span data-stu-id="05cc7-122">Planning for UE-V Configuration Methods</span></span>](planning-for-ue-v-configuration-methods.md)

[<span data-ttu-id="05cc7-123">规划 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="05cc7-123">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

 

 





