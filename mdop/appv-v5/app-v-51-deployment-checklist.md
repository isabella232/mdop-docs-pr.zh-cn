---
title: App-V 5.1 部署清单
description: App-V 5.1 部署清单
author: dansimp
ms.assetid: 44bed85a-e4f5-49d7-a308-a2b681f76372
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0864335e505996a3ea379b09de6a1aaa7fbe1676
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798629"
---
# <span data-ttu-id="0b143-103">App-V 5.1 部署清单</span><span class="sxs-lookup"><span data-stu-id="0b143-103">App-V 5.1 Deployment Checklist</span></span>


<span data-ttu-id="0b143-104">此清单可用于在 Microsoft Application Virtualization （App-v）5.1 部署期间帮助你。</span><span class="sxs-lookup"><span data-stu-id="0b143-104">This checklist can be used to help you during Microsoft Application Virtualization (App-V) 5.1 deployment.</span></span>

**<span data-ttu-id="0b143-105">注意</span><span class="sxs-lookup"><span data-stu-id="0b143-105">Note</span></span>**  
<span data-ttu-id="0b143-106">此清单列出了部署 app-v 5.1 功能时要考虑的推荐步骤和高级列表。</span><span class="sxs-lookup"><span data-stu-id="0b143-106">This checklist outlines the recommended steps and a high-level list of items to consider when deploying App-V 5.1 features.</span></span> <span data-ttu-id="0b143-107">建议将此清单复制到电子表格程序中，然后对其进行自定义以供使用。</span><span class="sxs-lookup"><span data-stu-id="0b143-107">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="0b143-108">任务</span><span class="sxs-lookup"><span data-stu-id="0b143-108">Task</span></span></th>
<th align="left"><span data-ttu-id="0b143-109">引用</span><span class="sxs-lookup"><span data-stu-id="0b143-109">References</span></span></th>
<th align="left"><span data-ttu-id="0b143-110">注释</span><span class="sxs-lookup"><span data-stu-id="0b143-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0b143-111">完成规划阶段以准备 App-v 5.1 部署的计算环境。</span><span class="sxs-lookup"><span data-stu-id="0b143-111">Complete the planning phase to prepare the computing environment for App-V 5.1 deployment.</span></span></p></td>
<td align="left"><p><a href="app-v-51-planning-checklist.md" data-raw-source="[App-V 5.1 Planning Checklist](app-v-51-planning-checklist.md)"><span data-ttu-id="0b143-112">App-V 5.1 计划清单</span><span class="sxs-lookup"><span data-stu-id="0b143-112">App-V 5.1 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0b143-113">查看 app-v 5.1 支持的配置信息，确保所选客户端和服务器计算机对 App-v 5.1 功能安装受支持。</span><span class="sxs-lookup"><span data-stu-id="0b143-113">Review the App-V 5.1 supported configurations information to make sure selected client and server computers are supported for App-V 5.1 feature installation.</span></span></p></td>
<td align="left"><p><a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"><span data-ttu-id="0b143-114">App-V 5.1 支持的配置</span><span class="sxs-lookup"><span data-stu-id="0b143-114">App-V 5.1 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0b143-115">运行 App-v 5.1 安装程序，以便为你的环境部署所需的 App-v 5.1 功能。</span><span class="sxs-lookup"><span data-stu-id="0b143-115">Run App-V 5.1 Setup to deploy the required App-V 5.1 features for your environment.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0b143-116">注意</span><span class="sxs-lookup"><span data-stu-id="0b143-116">Note</span></span></strong><br/><p><span data-ttu-id="0b143-117">跟踪在安装期间创建的服务器和关联的 URL 的名称。</span><span class="sxs-lookup"><span data-stu-id="0b143-117">Keep track of the names of the servers and associated URL’s created during installation.</span></span> <span data-ttu-id="0b143-118">此信息将在整个安装过程中使用。</span><span class="sxs-lookup"><span data-stu-id="0b143-118">This information will be used throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p></p>
<ul>
<li><p><a href="how-to-install-the-sequencer-51beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md)"><span data-ttu-id="0b143-119">如何安装 Sequencer</span><span class="sxs-lookup"><span data-stu-id="0b143-119">How to Install the Sequencer</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)"><span data-ttu-id="0b143-120">如何部署 App-V Client</span><span class="sxs-lookup"><span data-stu-id="0b143-120">How to Deploy the App-V Client</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"><span data-ttu-id="0b143-121">如何部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="0b143-121">How to Deploy the App-V 5.1 Server</span></span></a></p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="0b143-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="0b143-122">Related topics</span></span>


[<span data-ttu-id="0b143-123">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="0b143-123">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)









