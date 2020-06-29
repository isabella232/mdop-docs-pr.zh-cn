---
title: 计划使用电子软件分发系统部署 App-V 5.1
description: 计划使用电子软件分发系统部署 App-V 5.1
author: dansimp
ms.assetid: c26602c2-5e8d-44e6-90df-adacc593607e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fde3f0ea4f1dec72b97143b4b27dd0b32a503b15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798286"
---
# <span data-ttu-id="82273-103">计划使用电子软件分发系统部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="82273-103">Planning to Deploy App-V 5.1 with an Electronic Software Distribution System</span></span>


<span data-ttu-id="82273-104">如果您使用电子软件分发系统来部署 app-v 程序包，请查看以下规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="82273-104">If you are using an electronic software distribution system to deploy App-V packages, review the following planning considerations.</span></span> <span data-ttu-id="82273-105">有关使用 System Center Configuration Manager 部署 app-v 的信息，请参阅[配置管理器中的应用程序管理简介](https://go.microsoft.com/fwlink/?LinkId=281816)。</span><span class="sxs-lookup"><span data-stu-id="82273-105">For information about using System Center Configuration Manager to deploy App-V, see [Introduction to Application Management in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=281816).</span></span>

<span data-ttu-id="82273-106">查看使用 ESD 部署 app-v 程序包时应用的以下组件和体系结构要求选项：</span><span class="sxs-lookup"><span data-stu-id="82273-106">Review the following component and architecture requirements options that apply when you use an ESD to deploy App-V packages:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="82273-107">部署要求或选项</span><span class="sxs-lookup"><span data-stu-id="82273-107">Deployment requirement or option</span></span></th>
<th align="left"><span data-ttu-id="82273-108">描述</span><span class="sxs-lookup"><span data-stu-id="82273-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="82273-109">不需要 app-v 管理服务器、管理数据库和发布服务器。</span><span class="sxs-lookup"><span data-stu-id="82273-109">The App-V Management server, Management database, and Publishing server are not required.</span></span></p></td>
<td align="left"><p><span data-ttu-id="82273-110">这些函数由实施的 ESD 解决方案处理。</span><span class="sxs-lookup"><span data-stu-id="82273-110">These functions are handled by the implemented ESD solution.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="82273-111">你可以与 ESD 并排部署 app-v 报告服务器和报告数据库。</span><span class="sxs-lookup"><span data-stu-id="82273-111">You can deploy the App-V Reporting server and Reporting database side by side with the ESD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="82273-112">并行部署使你可以收集数据并生成报表。</span><span class="sxs-lookup"><span data-stu-id="82273-112">The side-by-side deployment lets you to collect data and generate reports.</span></span></p>
<p><span data-ttu-id="82273-113">如果你启用 App-v 客户端以发送报表信息，而你未使用 App-v 报告服务器，则报告数据将存储在关联的 .xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="82273-113">If you enable the App-V client to send report information, and you are not using the App-V Reporting server, the reporting data is stored in associated .xml files.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="82273-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="82273-114">Related topics</span></span>


[<span data-ttu-id="82273-115">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="82273-115">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





