---
title: Application Virtualization 部署和升级注意事项
description: Application Virtualization 部署和升级注意事项
author: dansimp
ms.assetid: c3c38930-0da3-43e6-b240-945edfd00a01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09e6943c74c7f17b6a61bc7be4bcde925a54be56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803135"
---
# <span data-ttu-id="3577d-103">Application Virtualization 部署和升级注意事项</span><span class="sxs-lookup"><span data-stu-id="3577d-103">Application Virtualization Deployment and Upgrade Considerations</span></span>


<span data-ttu-id="3577d-104">开始部署 Microsoft Application Virtualization （App-v）之前，可能需要查看环境要求，包括安装各种应用程序虚拟化组件的硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="3577d-104">Before you begin the deployment of Microsoft Application Virtualization (App-V), you might have to review your environment requirements that includes the hardware and software requirements for installing the various Application Virtualization components.</span></span> <span data-ttu-id="3577d-105">此外，如果您从早期版本升级，本部分中的主题将提供有关如何升级当前 Sequencer、服务器和客户端版本的信息。</span><span class="sxs-lookup"><span data-stu-id="3577d-105">Also, if you are upgrading from an earlier version, the topics in this section provide information about how to upgrade your current Sequencer, Server, and Client versions.</span></span>

## <span data-ttu-id="3577d-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3577d-106">In This Section</span></span>


<a href="" id="application-virtualization-deployment-requirements"></a>[<span data-ttu-id="3577d-107">Application Virtualization 部署要求</span><span class="sxs-lookup"><span data-stu-id="3577d-107">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)  
<span data-ttu-id="3577d-108">提供有关你的应用程序虚拟化部署的系统要求和升级注意事项的一般信息。</span><span class="sxs-lookup"><span data-stu-id="3577d-108">Provides general information about system requirements and upgrade considerations for your Application Virtualization deployment.</span></span>

<a href="" id="application-virtualization-deployment-and-upgrade-checklists"></a>[<span data-ttu-id="3577d-109">Application Virtualization 部署和升级清单</span><span class="sxs-lookup"><span data-stu-id="3577d-109">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)  
<span data-ttu-id="3577d-110">提供包含特定过程链接的安装和升级任务的详细列表。</span><span class="sxs-lookup"><span data-stu-id="3577d-110">Provides detailed lists of installation and upgrade tasks with links to the specific procedures.</span></span>

<a href="" id="how-to-install-the-servers-and-system-components"></a>[<span data-ttu-id="3577d-111">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="3577d-111">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)  
<span data-ttu-id="3577d-112">介绍如何安装基于服务器的部署所需的应用程序虚拟化（App-v）平台组件。</span><span class="sxs-lookup"><span data-stu-id="3577d-112">Describes how to install the Application Virtualization (App-V) platform components required for your server-based deployment.</span></span>

<a href="" id="how-to-manually-install-the-application-virtualization-client"></a>[<span data-ttu-id="3577d-113">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="3577d-113">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)  
<span data-ttu-id="3577d-114">介绍如何安装应用程序虚拟化客户端软件。</span><span class="sxs-lookup"><span data-stu-id="3577d-114">Describes how to install the Application Virtualization Client software.</span></span>

<a href="" id="how-to-install-the-application-virtualization-sequencer"></a>[<span data-ttu-id="3577d-115">如何安装 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="3577d-115">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)  
<span data-ttu-id="3577d-116">介绍如何安装 Application Virtualization Sequencer。</span><span class="sxs-lookup"><span data-stu-id="3577d-116">Describes how to install the Application Virtualization Sequencer.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-client"></a>[<span data-ttu-id="3577d-117">如何升级 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="3577d-117">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)  
<span data-ttu-id="3577d-118">介绍如何升级应用程序虚拟化桌面客户端或远程桌面服务的应用程序虚拟化客户端（以前称为 "终端服务"）。</span><span class="sxs-lookup"><span data-stu-id="3577d-118">Describes how to upgrade the Application Virtualization Desktop Client or the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services).</span></span>

<a href="" id="how-to-upgrade-the-servers-and-system-components"></a>[<span data-ttu-id="3577d-119">如何升级服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="3577d-119">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)  
<span data-ttu-id="3577d-120">介绍如何升级安装在所有应用程序虚拟化管理系统计算机上的软件组件。</span><span class="sxs-lookup"><span data-stu-id="3577d-120">Describes how to upgrade the software components installed on all Application Virtualization Management System computers.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-sequencer"></a>[<span data-ttu-id="3577d-121">如何升级 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="3577d-121">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)  
<span data-ttu-id="3577d-122">介绍如何在运行 WindowsVista 或 WindowsXP 的计算机上升级 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="3577d-122">Describes how to upgrade the Sequencer on computers that are running WindowsVista or WindowsXP.</span></span>

## <span data-ttu-id="3577d-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="3577d-123">Related topics</span></span>


[<span data-ttu-id="3577d-124">Application Virtualization 参考</span><span class="sxs-lookup"><span data-stu-id="3577d-124">Application Virtualization Reference</span></span>](application-virtualization-reference.md)

[<span data-ttu-id="3577d-125">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="3577d-125">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="3577d-126">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="3577d-126">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="3577d-127">适用于 Application Virtualization Client 的独立传递方案</span><span class="sxs-lookup"><span data-stu-id="3577d-127">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





