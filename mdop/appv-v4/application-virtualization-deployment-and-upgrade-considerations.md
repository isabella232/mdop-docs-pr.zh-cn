---
title: Application Virtualization 部署和升级注意事项
description: Application Virtualization 部署和升级注意事项
author: dansimp
ms.assetid: adc562ee-7276-4b14-b10a-da17f05e1682
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9e6c1a624b9da18bba75c5f3816a8e9c5391a8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803129"
---
# <span data-ttu-id="2ccf7-103">Application Virtualization 部署和升级注意事项</span><span class="sxs-lookup"><span data-stu-id="2ccf7-103">Application Virtualization Deployment and Upgrade Considerations</span></span>


<span data-ttu-id="2ccf7-104">开始部署 Microsoft Application 虚拟化之前，你可能需要查看环境要求，包括安装各种应用程序虚拟化组件的硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-104">Before you begin the deployment of Microsoft Application Virtualization, you might need to review your environment requirements, including the hardware and software requirements for installing the various Application Virtualization components.</span></span> <span data-ttu-id="2ccf7-105">此外，如果您从以前的版本升级，本部分中的主题将提供有关升级当前 Sequencer、服务器和客户端版本的信息。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-105">Also, if you are upgrading from a previous version, the topics in this section provide information about upgrading your current Sequencer, server, and client versions.</span></span>

## <span data-ttu-id="2ccf7-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="2ccf7-106">In This Section</span></span>


<a href="" id="application-virtualization-deployment-requirements"></a>[<span data-ttu-id="2ccf7-107">Application Virtualization 部署要求</span><span class="sxs-lookup"><span data-stu-id="2ccf7-107">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)  
<span data-ttu-id="2ccf7-108">提供有关你的应用程序虚拟化部署的系统要求和升级注意事项的一般信息。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-108">Provides general information about system requirements and upgrade considerations for your Application Virtualization deployment.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-client"></a>[<span data-ttu-id="2ccf7-109">如何升级 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="2ccf7-109">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)  
<span data-ttu-id="2ccf7-110">提供针对远程桌面服务（以前称为终端服务）升级应用程序虚拟化桌面客户端或应用程序虚拟化客户端的分步过程。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-110">Provides step-by-step procedures for upgrading the Application Virtualization Desktop Client or the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services).</span></span>

<a href="" id="how-to-upgrade-the-servers-and-system-components"></a>[<span data-ttu-id="2ccf7-111">如何升级服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="2ccf7-111">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)  
<span data-ttu-id="2ccf7-112">提供可用于升级在所有应用程序虚拟化系统计算机上安装的软件组件的分步过程。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-112">Provides a step-by-step procedure you can use to upgrade the software components installed on all Application Virtualization System computers.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-sequencer"></a>[<span data-ttu-id="2ccf7-113">如何升级 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="2ccf7-113">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)  
<span data-ttu-id="2ccf7-114">提供在运行 Windows Vista 或 WindowsXP 的计算机上升级 Sequencer 的分步过程。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-114">Provides step-by-step procedures for upgrading the Sequencer on computers running Windows Vista or WindowsXP.</span></span>

<a href="" id="how-to-install-the-application-virtualization-sequencer"></a>[<span data-ttu-id="2ccf7-115">如何安装 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="2ccf7-115">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)  
<span data-ttu-id="2ccf7-116">提供安装 Sequencer 的分步过程。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-116">Provides a step-by-step procedure for installing the Sequencer.</span></span>

## <span data-ttu-id="2ccf7-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="2ccf7-117">Related topics</span></span>


[<span data-ttu-id="2ccf7-118">Application Virtualization 参考</span><span class="sxs-lookup"><span data-stu-id="2ccf7-118">Application Virtualization Reference</span></span>](application-virtualization-reference.md)

[<span data-ttu-id="2ccf7-119">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="2ccf7-119">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="2ccf7-120">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="2ccf7-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="2ccf7-121">适用于 Application Virtualization Client 的独立传递方案</span><span class="sxs-lookup"><span data-stu-id="2ccf7-121">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





