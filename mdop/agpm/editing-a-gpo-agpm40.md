---
title: 编辑 GPO
description: 编辑 GPO
author: dansimp
ms.assetid: ef42eefe-7705-46b2-954d-18966335cbbf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 86ec3b2ac7afdbfde1fc1654c9e3bd5525aacba8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802795"
---
# <span data-ttu-id="9130b-103">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="9130b-103">Editing a GPO</span></span>


<span data-ttu-id="9130b-104">组策略对象（GPO）必须通过高级组策略管理（AGPM）进行控制才能进行编辑。</span><span class="sxs-lookup"><span data-stu-id="9130b-104">A Group Policy Object (GPO) must be controlled by Advanced Group Policy Management (AGPM) before you can edit it.</span></span> <span data-ttu-id="9130b-105">有关控制 GPO 的详细信息，请参阅[创建或控制 gpo](creating-or-controlling-a-gpo-agpm40-ed.md) 。</span><span class="sxs-lookup"><span data-stu-id="9130b-105">See [Creating or Controlling a GPO](creating-or-controlling-a-gpo-agpm40-ed.md) for more information about controlling a GPO.</span></span>

<span data-ttu-id="9130b-106">若要在不立即影响生产环境中 GPO 的已部署副本的情况下对 GPO 进行更改，请从存档中签出 GPO 的副本。</span><span class="sxs-lookup"><span data-stu-id="9130b-106">To make changes to a GPO offline without immediately impacting the deployed copy of the GPO in the production environment, check out a copy of the GPO from the archive.</span></span> <span data-ttu-id="9130b-107">更改完成后，将 GPO 签入到存档中，对其进行测试，然后请求将 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="9130b-107">When changes are complete, check the GPO back into the archive, test it, and request deployment of the GPO to the production environment.</span></span>

-   [<span data-ttu-id="9130b-108">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="9130b-108">Edit a GPO Offline</span></span>](edit-a-gpo-offline-agpm40.md)

-   [<span data-ttu-id="9130b-109">标记当前版本的 GPO</span><span class="sxs-lookup"><span data-stu-id="9130b-109">Label the Current Version of a GPO</span></span>](label-the-current-version-of-a-gpo-agpm40.md)

-   [<span data-ttu-id="9130b-110">重命名 GPO 或模板</span><span class="sxs-lookup"><span data-stu-id="9130b-110">Rename a GPO or Template</span></span>](rename-a-gpo-or-template-agpm40.md)

 

 





