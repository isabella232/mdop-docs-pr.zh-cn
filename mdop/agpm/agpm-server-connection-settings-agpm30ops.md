---
title: AGPM 服务器连接设置
description: AGPM 服务器连接设置
author: dansimp
ms.assetid: 5f03e397-b868-4c49-9cbf-a5f5d0ddcc39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ee1e67eb2c565bcf833314d82cdf611e2caa85
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798183"
---
# <span data-ttu-id="79b06-103">AGPM 服务器连接设置</span><span class="sxs-lookup"><span data-stu-id="79b06-103">AGPM Server Connection Settings</span></span>


<span data-ttu-id="79b06-104">你可以使用高级组策略管理（AGPM）的管理模板设置来集中配置组策略对象（GPO）应用了组策略对象（GPO）的 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="79b06-104">You can use Administrative template settings for Advanced Group Policy Management (AGPM) to centrally configure AGPM Server connections for Group Policy administrators to whom a Group Policy Object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="79b06-105">编辑 GPO 时，用户 Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM 下提供以下设置。</span><span class="sxs-lookup"><span data-stu-id="79b06-105">The following settings are available under User Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79b06-106">设置</span><span class="sxs-lookup"><span data-stu-id="79b06-106">Setting</span></span></th>
<th align="left"><span data-ttu-id="79b06-107">作用</span><span class="sxs-lookup"><span data-stu-id="79b06-107">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="79b06-108">AGPM：指定默认的 AGPM 服务器（所有域）</span><span class="sxs-lookup"><span data-stu-id="79b06-108">AGPM: Specify default AGPM Server (all domains)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="79b06-109">通过此策略设置，你可以为所有域指定默认的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="79b06-109">This policy setting allows you to specify a default AGPM Server for all domains.</span></span> <span data-ttu-id="79b06-110">这仅由 AGPM 客户端使用，并且限制组策略管理员连接到另一个存档。</span><span class="sxs-lookup"><span data-stu-id="79b06-110">This is used only by AGPM Clients, and restricts Group Policy administrators from connecting to another archive.</span></span> <span data-ttu-id="79b06-111">你可以使用 AGPM： "指定 AGPM 服务器" 设置替代单个域的此默认 <strong> </strong> 设置。</span><span class="sxs-lookup"><span data-stu-id="79b06-111">You can override this default for individual domains using the <strong>AGPM: Specify AGPM Servers</strong> setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="79b06-112">AGPM：指定 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="79b06-112">AGPM: Specify AGPM Servers</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="79b06-113">通过此策略设置，你可以为单个域指定 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="79b06-113">This policy setting allows you to specify the AGPM Servers for individual domains.</span></span> <span data-ttu-id="79b06-114">这仅由 AGPM 客户端使用，并且限制组策略管理员连接到指定域的其他存档。</span><span class="sxs-lookup"><span data-stu-id="79b06-114">This is used only by AGPM Clients, and restricts Group Policy administrators from connecting to a different archive for the specified domain.</span></span> <span data-ttu-id="79b06-115">若要指定默认的 AGPM 服务器，请使用 " <strong> AGPM：指定默认 Agpm 服务器（所有域）" </strong> 设置，并使用此策略设置替代每个域的默认值。</span><span class="sxs-lookup"><span data-stu-id="79b06-115">To specify a default AGPM Server, use the <strong>AGPM: Specify default AGPM Server (all domains)</strong> setting and use this policy setting to override the default on a per domain basis.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="79b06-116">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="79b06-116">Additional references</span></span>

-   [<span data-ttu-id="79b06-117">“管理模板”文件夹</span><span class="sxs-lookup"><span data-stu-id="79b06-117">Administrative Templates Folder</span></span>](administrative-templates-folder-agpm30ops.md)

-   [<span data-ttu-id="79b06-118">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="79b06-118">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





