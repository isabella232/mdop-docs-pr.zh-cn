---
title: AGPM 服务器连接设置
description: AGPM 服务器连接设置
author: dansimp
ms.assetid: faf78e5b-2b0d-4069-9b8c-910add892200
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63163de0a1adf744e6d442b8073e5b32352ed67
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798191"
---
# <span data-ttu-id="14a47-103">AGPM 服务器连接设置</span><span class="sxs-lookup"><span data-stu-id="14a47-103">AGPM Server Connection Settings</span></span>


<span data-ttu-id="14a47-104">你可以使用高级组策略管理（AGPM）的管理模板设置来集中配置组策略对象（GPO）应用了组策略对象（GPO）的 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="14a47-104">You can use Administrative template settings for Advanced Group Policy Management (AGPM) to centrally configure AGPM Server connections for Group Policy administrators to whom a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="14a47-105">编辑 GPO 时，用户 Configuration\\Administrative Templates\\Windows Components\\AGPM 下提供以下设置。</span><span class="sxs-lookup"><span data-stu-id="14a47-105">The following settings are available under User Configuration\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span> <span data-ttu-id="14a47-106">如果此路径不可见，请右键单击 "**管理模板**"，然后添加 "agpm" 或 "agpm .adm" 模板。</span><span class="sxs-lookup"><span data-stu-id="14a47-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="14a47-107">设置</span><span class="sxs-lookup"><span data-stu-id="14a47-107">Setting</span></span></th>
<th align="left"><span data-ttu-id="14a47-108">作用</span><span class="sxs-lookup"><span data-stu-id="14a47-108">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="14a47-109">AGPM 服务器（所有域）</span><span class="sxs-lookup"><span data-stu-id="14a47-109">AGPM Server (all domains)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="14a47-110">如果已启用，此设置将集中配置一个 AGPM 服务器连接供所有域使用，并禁用 <strong> 组策略管理员的 AGPM 服务器选项卡上的设置 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="14a47-110">If enabled, this setting centrally configures one AGPM Server connection for use by all domains and disables the settings on the <strong>AGPM Server</strong> tab for Group Policy administrators.</span></span> <span data-ttu-id="14a47-111">对于多个 AGPM 服务器，使用默认服务器配置此设置，然后 <strong> </strong> 在 "管理模板" 中配置 AGPM 服务器设置以替代其他域的此服务器。</span><span class="sxs-lookup"><span data-stu-id="14a47-111">For multiple AGPM Servers, configure this setting with a default server and then configure the <strong>AGPM Server</strong> setting in the Administrative template to override this server for other domains.</span></span></p>
<p><span data-ttu-id="14a47-112">如果已禁用或未配置，每个组策略管理员必须在 <strong> agpm 的 Agpm 服务器选项卡上选择要为每个域显示的 AGPM 服务器 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="14a47-112">If disabled or not configured, each Group Policy administrator must select the AGPM Server to display for each domain on the <strong>AGPM Server</strong> tab in AGPM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="14a47-113">AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="14a47-113">AGPM Server</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="14a47-114">如果启用，此设置将集中配置多个特定于域的 AGPM 服务器，替代 <strong> 管理模板中的 "AGPM 服务器（所有域）" </strong> 设置。</span><span class="sxs-lookup"><span data-stu-id="14a47-114">If enabled, this setting centrally configures multiple domain-specific AGPM Servers, overriding the <strong>AGPM Server (all domains)</strong> setting in the Administrative template.</span></span> <span data-ttu-id="14a47-115">如果你的环境仅需要单个 AGPM 服务器，请仅使用 <strong> 管理模板中的 "Agpm 服务器（所有域）" </strong> 设置。</span><span class="sxs-lookup"><span data-stu-id="14a47-115">If your environment requires only a single AGPM Server, use only the <strong>AGPM Server (all domains)</strong> setting in the Administrative template.</span></span></p>
<p><span data-ttu-id="14a47-116">如果 "已禁用" 或 "未配置"，则 <strong> 管理模板中的 "AGPM 服务器（所有域）" </strong> 设置将配置 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="14a47-116">If disabled or not configured, the <strong>AGPM Server (all domains)</strong> setting in the Administrative template configures the AGPM Server connection.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="14a47-117">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="14a47-117">Additional references</span></span>

-   [<span data-ttu-id="14a47-118">管理模板设置</span><span class="sxs-lookup"><span data-stu-id="14a47-118">Administrative Template Settings</span></span>](administrative-template-settings.md)

-   [<span data-ttu-id="14a47-119">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="14a47-119">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





