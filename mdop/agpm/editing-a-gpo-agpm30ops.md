---
title: 编辑 GPO
description: 编辑 GPO
author: dansimp
ms.assetid: 3024051a-ff33-46d0-9c3e-68ebae7f6b60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1849b020c5be1d24d018e947d674d606bb1a32d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802791"
---
# <span data-ttu-id="f31cd-103">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="f31cd-103">Editing a GPO</span></span>


<span data-ttu-id="f31cd-104">组策略对象（GPO）必须通过高级组策略管理（AGPM）进行控制才能进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f31cd-104">A Group Policy Object (GPO) must be controlled by Advanced Group Policy Management (AGPM) before you can edit it.</span></span> <span data-ttu-id="f31cd-105">有关控制 GPO 的详细信息，请参阅[创建、控制或导入 gpo](creating-controlling-or-importing-a-gpo-agpm30ops.md) 。</span><span class="sxs-lookup"><span data-stu-id="f31cd-105">See [Creating, Controlling, or Importing a GPO](creating-controlling-or-importing-a-gpo-agpm30ops.md) for more information about controlling a GPO.</span></span>

<span data-ttu-id="f31cd-106">若要在不立即影响生产环境中 GPO 的已部署副本的情况下对 GPO 进行更改，请从存档中签出 GPO 的副本。</span><span class="sxs-lookup"><span data-stu-id="f31cd-106">To make changes to a GPO offline without immediately impacting the deployed copy of the GPO in the production environment, check out a copy of the GPO from the archive.</span></span> <span data-ttu-id="f31cd-107">完成更改后，将 GPO 签入到存档中，并向生产环境请求 GPO 部署。</span><span class="sxs-lookup"><span data-stu-id="f31cd-107">When changes are complete, check the GPO back into the archive and request deployment of the GPO to the production environment.</span></span>

-   [<span data-ttu-id="f31cd-108">脱机编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="f31cd-108">Edit a GPO Offline</span></span>](edit-a-gpo-offline-agpm30ops.md)

-   [<span data-ttu-id="f31cd-109">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="f31cd-109">Use a Test Environment</span></span>](use-a-test-environment-agpm30ops.md)

-   [<span data-ttu-id="f31cd-110">请求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="f31cd-110">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="f31cd-111">标记当前版本的 GPO</span><span class="sxs-lookup"><span data-stu-id="f31cd-111">Label the Current Version of a GPO</span></span>](label-the-current-version-of-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="f31cd-112">重命名 GPO 或模板</span><span class="sxs-lookup"><span data-stu-id="f31cd-112">Rename a GPO or Template</span></span>](rename-a-gpo-or-template-agpm30ops.md)

 

 





