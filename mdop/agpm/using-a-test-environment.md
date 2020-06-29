---
title: 使用测试环境
description: 使用测试环境
author: dansimp
ms.assetid: fc5fcc7c-1ac8-483a-a6bd-2279ae2ee3fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fc3ad91747c755efe0576cc62473848094b72ed1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801711"
---
# <span data-ttu-id="60ffe-103">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="60ffe-103">Using a Test Environment</span></span>


<span data-ttu-id="60ffe-104">在请求将组策略对象（GPO）部署到生产环境之前，应在实验室环境中测试 GPO。</span><span class="sxs-lookup"><span data-stu-id="60ffe-104">Before you request that a Group Policy Object (GPO) be deployed to the production environment, you should test the GPO in a lab environment.</span></span> <span data-ttu-id="60ffe-105">如果在测试林中的域中开发 GPO，则可以将 GPO 导出到文件，并将文件导入到生产林中的域。</span><span class="sxs-lookup"><span data-stu-id="60ffe-105">If you develop the GPO in a domain in a test forest, you can export the GPO to a file and import the file to a domain in the production forest.</span></span> <span data-ttu-id="60ffe-106">然后，你可以通过将 GPO 链接到包含测试计算机和用户的组织单位（OU）来测试 GPO。</span><span class="sxs-lookup"><span data-stu-id="60ffe-106">You can then test the GPO by linking it to an organizational unit (OU) that contains test computers and users.</span></span>

-   [<span data-ttu-id="60ffe-107">将 GPO 导出到文件</span><span class="sxs-lookup"><span data-stu-id="60ffe-107">Export a GPO to a File</span></span>](export-a-gpo-to-a-file.md)

-   [<span data-ttu-id="60ffe-108">从文件导入 GPO</span><span class="sxs-lookup"><span data-stu-id="60ffe-108">Import a GPO from a File</span></span>](import-a-gpo-from-a-file-ed.md)

-   [<span data-ttu-id="60ffe-109">在单独的组织单位中测试 GPO</span><span class="sxs-lookup"><span data-stu-id="60ffe-109">Test a GPO in a Separate Organizational Unit</span></span>](test-a-gpo-in-a-separate-organizational-unit-agpm40.md)

<span data-ttu-id="60ffe-110">**注意** 您也可以从域的生产环境导入 GPO。</span><span class="sxs-lookup"><span data-stu-id="60ffe-110">**Note** You can also import a GPO from the production environment of the domain.</span></span> <span data-ttu-id="60ffe-111">有关详细信息，请参阅[从生产导入 GPO](import-a-gpo-from-production-agpm40-ed.md)。</span><span class="sxs-lookup"><span data-stu-id="60ffe-111">For more information, see [Import a GPO from Production](import-a-gpo-from-production-agpm40-ed.md).</span></span>

 

 

 





