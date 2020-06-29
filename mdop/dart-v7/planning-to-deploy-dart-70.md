---
title: 计划部署 DaRT 7.0
description: 计划部署 DaRT 7.0
author: dansimp
ms.assetid: 05e97cdb-a8c2-46e4-9c75-a7d12fe26fe8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09725e994a95f4f93ae655402e7577e137e33f18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802944"
---
# <span data-ttu-id="b44dc-103">计划部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="b44dc-103">Planning to Deploy DaRT 7.0</span></span>


<span data-ttu-id="b44dc-104">在创建部署计划之前，必须考虑许多不同的部署配置和先决条件。</span><span class="sxs-lookup"><span data-stu-id="b44dc-104">There are a number of different deployment configurations and prerequisites that you must consider before you create your deployment plan.</span></span> <span data-ttu-id="b44dc-105">本部分包含的信息可帮助您收集可用于制定最符合业务要求的部署计划所必需的信息。</span><span class="sxs-lookup"><span data-stu-id="b44dc-105">This section includes information that can help you gather the information that you must have to formulate a deployment plan that best meets your business requirements.</span></span>

<span data-ttu-id="b44dc-106">规划 Microsoft 诊断和恢复工具集（DaRT）7安装时，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="b44dc-106">Consider the following when you plan your Microsoft Diagnostics and Recovery Toolset (DaRT)7 installation:</span></span>

-   <span data-ttu-id="b44dc-107">安装 DaRT 时，可以在 IT 管理员计算机上安装所有功能，您将执行与运行 DaRT 相关联的所有任务。</span><span class="sxs-lookup"><span data-stu-id="b44dc-107">When you install DaRT, you can either install all functionality on an IT administrator computer where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="b44dc-108">或者，你可以仅安装在 IT 管理员计算机上创建恢复映像的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="b44dc-108">Or you can install only the DaRT functionality that creates the recovery image on the IT administrator computer.</span></span> <span data-ttu-id="b44dc-109">然后，在帮助台代理计算机上安装用于运行 DaRT 的功能，例如**Dart 远程连接查看器**和**故障分析器**。</span><span class="sxs-lookup"><span data-stu-id="b44dc-109">Then, install the functionality used to run DaRT, such as the **DaRT Remote Connection Viewer** and **Crash Analyzer**, on a helpdesk agent computer.</span></span>

-   <span data-ttu-id="b44dc-110">若要能够远程运行 DaRT，请确保帮助台代理计算机和你可能在远程进行故障排除的所有计算机位于同一网络上。</span><span class="sxs-lookup"><span data-stu-id="b44dc-110">To be able to run DaRT remotely, make sure that the helpdesk agent computer and all computers that you might be troubleshooting remotely are on the same network.</span></span>

-   <span data-ttu-id="b44dc-111">在将 DaRT 部署到生产之前，你可以先构建一个实验室环境进行测试。</span><span class="sxs-lookup"><span data-stu-id="b44dc-111">Before you roll out DaRT into production, you can first build a lab environment for testing.</span></span> <span data-ttu-id="b44dc-112">测试实验室至少应包括两台计算机，一台充当 IT 管理员/支持台代理计算机，另一台充当最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="b44dc-112">A test lab should include a minimum of two computers, one to act as the IT administrator/helpdesk agent computer and one to act as an end-user computer.</span></span> <span data-ttu-id="b44dc-113">或者，如果你想要将 IT 管理员的责任与帮助台代理的人员分开，可以在你的实验室中使用三台计算机。</span><span class="sxs-lookup"><span data-stu-id="b44dc-113">Or, you can use three computers in your lab if you want to separate the IT administrator responsibilities from those of the helpdesk agent.</span></span>

## <span data-ttu-id="b44dc-114">查看受支持的配置</span><span class="sxs-lookup"><span data-stu-id="b44dc-114">Review the supported configurations</span></span>


<span data-ttu-id="b44dc-115">你应该查看 Microsoft 诊断和恢复工具集（DaRT）7支持的配置信息，以确认你选择用于客户端或功能安装的计算机是否满足最低硬件和操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="b44dc-115">You should review the Microsoft Diagnostics and Recovery Toolset (DaRT)7 Supported Configurations information to confirm that the computers you have selected for client or feature installation meet the minimum hardware and operating system requirements.</span></span>

[<span data-ttu-id="b44dc-116">DaRT 7.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="b44dc-116">DaRT 7.0 Supported Configurations</span></span>](dart-70-supported-configurations-dart-7.md)

## <span data-ttu-id="b44dc-117">计划创建 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="b44dc-117">Plan for creating the DaRT recovery image</span></span>


<span data-ttu-id="b44dc-118">创建 DaRT 恢复映像时，必须确定要在映像中包含的工具。</span><span class="sxs-lookup"><span data-stu-id="b44dc-118">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="b44dc-119">做出决策时，请记住最终用户可能偶尔有权访问各种 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="b44dc-119">When you make that decision, remember that end users might have access occasionally to the various DaRT tools.</span></span> <span data-ttu-id="b44dc-120">创建恢复映像时，你还将指定是否要包括其他驱动程序或文件。</span><span class="sxs-lookup"><span data-stu-id="b44dc-120">When you create the recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="b44dc-121">确定要包括在 DaRT 恢复映像中的任何其他驱动程序或文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b44dc-121">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

<span data-ttu-id="b44dc-122">你应该了解有关创建 DaRT 恢复映像的先决条件和其他额外计划建议。</span><span class="sxs-lookup"><span data-stu-id="b44dc-122">You should be aware of the prerequisites and other additional planning recommendations for creating the DaRT recovery image.</span></span>

[<span data-ttu-id="b44dc-123">计划创建 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="b44dc-123">Planning to Create the DaRT 7.0 Recovery Image</span></span>](planning-to-create-the-dart-70-recovery-image.md)

## <span data-ttu-id="b44dc-124">计划保存和部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="b44dc-124">Plan for saving and deploying the DaRT recovery image</span></span>


<span data-ttu-id="b44dc-125">可以使用多种方法来保存和部署 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="b44dc-125">Several methods can be used to save and deploy the DaRT recovery image.</span></span> <span data-ttu-id="b44dc-126">确定你将使用的方法时，请考虑每个方法的优缺点。</span><span class="sxs-lookup"><span data-stu-id="b44dc-126">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="b44dc-127">此外，请考虑你希望如何在企业中使用 DaRT。</span><span class="sxs-lookup"><span data-stu-id="b44dc-127">Also, consider how you want to use DaRT in your enterprise.</span></span>

<span data-ttu-id="b44dc-128">**注意** 您可能希望在您的组织中使用多个方法。</span><span class="sxs-lookup"><span data-stu-id="b44dc-128">**Note** You might want to use more than one method in your organization.</span></span> <span data-ttu-id="b44dc-129">例如，在大多数情况下，你可以从远程分区启动到 DaRT，并且在最终用户计算机无法连接到网络时有可用的 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="b44dc-129">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

[<span data-ttu-id="b44dc-130">计划如何保存和部署 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="b44dc-130">Planning How to Save and Deploy the DaRT 7.0 Recovery Image</span></span>](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)

## <span data-ttu-id="b44dc-131">用于规划部署 DaRT 的其他资源</span><span class="sxs-lookup"><span data-stu-id="b44dc-131">Other resources for Planning to Deploy DaRT</span></span>


[<span data-ttu-id="b44dc-132">计划 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="b44dc-132">Planning for DaRT 7.0</span></span>](planning-for-dart-70-new-ia.md)

 

 





