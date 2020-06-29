---
title: 仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
description: 仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
author: dansimp
ms.assetid: 74180d8d-7b0f-460f-b301-53595cde8381
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9b89e1a1383997d6ebc92f8e034fbf2945823f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798077"
---
# <span data-ttu-id="78c13-103">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="78c13-103">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span>


<span data-ttu-id="78c13-104">如果你要使用 System Center Configuration Manager 集成功能安装 Microsoft BitLocker 管理和监视（MBAM）2.5，则必须完成本主题中所述的先决条件，以及[独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器必备条件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)中所述的先决条件。</span><span class="sxs-lookup"><span data-stu-id="78c13-104">If you are installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 by using the System Center Configuration Manager Integration feature, you must complete the prerequisites described in this topic, in addition to those in [MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md).</span></span> <span data-ttu-id="78c13-105">你还必须创建或修改 Configuration Manager 集成拓扑所需的 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="78c13-105">You must also create or modify .mof files that are needed for the Configuration Manager Integration topology.</span></span>

## <span data-ttu-id="78c13-106">Configuration Manager 集成功能的先决条件</span><span class="sxs-lookup"><span data-stu-id="78c13-106">Prerequisites for the Configuration Manager Integration Feature</span></span>


<span data-ttu-id="78c13-107">如果你正在通过 System Center Configuration Manager 集成拓扑配置 MBAM，则必须完成 Configuration Manager 所需的其他先决条件。</span><span class="sxs-lookup"><span data-stu-id="78c13-107">If you are configuring MBAM with the System Center Configuration Manager Integration topology, you must complete additional prerequisites that are required for Configuration Manager.</span></span>

[<span data-ttu-id="78c13-108">Configuration Manager 集成功能的先决条件</span><span class="sxs-lookup"><span data-stu-id="78c13-108">Prerequisites for the Configuration Manager Integration Feature</span></span>](prerequisites-for-the-configuration-manager-integration-feature.md)

## <span data-ttu-id="78c13-109">编辑配置 mof 文件</span><span class="sxs-lookup"><span data-stu-id="78c13-109">Edit the Configuration.mof file</span></span>


<span data-ttu-id="78c13-110">若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，您必须编辑 SystemCenter2012 ConfigurationManager 和 Microsoft System Center Configuration Manager 2007 的 Configuration mof 文件。</span><span class="sxs-lookup"><span data-stu-id="78c13-110">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager Reports, you have to edit the Configuration.mof file for SystemCenter2012 ConfigurationManager and Microsoft System Center Configuration Manager 2007.</span></span>

[<span data-ttu-id="78c13-111">编辑 Configuration.mof 文件</span><span class="sxs-lookup"><span data-stu-id="78c13-111">Edit the Configuration.mof File</span></span>](edit-the-configurationmof-file-mbam-25.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a><span data-ttu-id="78c13-112">创建或编辑 Sms \ _def 的 mof 文件</span><span class="sxs-lookup"><span data-stu-id="78c13-112">Create or edit the Sms\_def.mof file</span></span>


<span data-ttu-id="78c13-113">若要使客户端计算机能够在 MBAM Configuration Manager 报表中报告 BitLocker 合规性详细信息，您必须创建或编辑 Sms \ _def 的 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="78c13-113">To enable the client computers to report BitLocker compliance details in the MBAM Configuration Manager Reports, you have to create or edit the Sms\_def.mof file.</span></span> <span data-ttu-id="78c13-114">如果您使用的是 SystemCenter2012 ConfigurationManager，则必须创建该文件。</span><span class="sxs-lookup"><span data-stu-id="78c13-114">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span> <span data-ttu-id="78c13-115">在 Configuration Manager 2007 中，文件已存在，因此你需要编辑现有文件，但不能覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="78c13-115">In Configuration Manager 2007, the file already exists, so you need to edit, but not overwrite, the existing file.</span></span>

[<span data-ttu-id="78c13-116">创建或编辑 Sms \ _def 的 mof 文件</span><span class="sxs-lookup"><span data-stu-id="78c13-116">Create or Edit the Sms\_def.mof File</span></span>](create-or-edit-the-sms-defmof-file-mbam-25.md)


## <span data-ttu-id="78c13-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="78c13-117">Related topics</span></span>


[<span data-ttu-id="78c13-118">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="78c13-118">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="78c13-119">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="78c13-119">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

[<span data-ttu-id="78c13-120">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="78c13-120">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 

 
## <span data-ttu-id="78c13-121">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="78c13-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="78c13-122">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="78c13-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="78c13-123">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="78c13-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




