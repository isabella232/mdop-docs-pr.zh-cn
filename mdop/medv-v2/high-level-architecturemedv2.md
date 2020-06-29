---
title: 高级别体系结构
description: 高级别体系结构
author: dansimp
ms.assetid: a00edb9f-207b-4f32-9e8f-522ea2739d2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a5db4a56b2abfb0df19b0d6d86f4bf88380c2bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804139"
---
# <span data-ttu-id="70226-103">高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="70226-103">High-Level Architecture</span></span>


<span data-ttu-id="70226-104">本部分介绍 Microsoft 企业桌面虚拟化（MED-V）2.0 的高级别系统体系结构和组件设计。</span><span class="sxs-lookup"><span data-stu-id="70226-104">This section describes the high-level system architecture and component design of Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="70226-105">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="70226-105">System Architecture</span></span>


<span data-ttu-id="70226-106">MED-V 增强了 Windows 虚拟 PC，可在一个设备上运行两个操作系统、添加虚拟图像、基于组策略的资源调配和集中管理。</span><span class="sxs-lookup"><span data-stu-id="70226-106">MED-V enhances Windows Virtual PC to run two operating systems on one device, adding virtual image delivery, Group Policy-based provisioning, and centralized management.</span></span> <span data-ttu-id="70226-107">通过使用 MED-V，你可以在任何运行 Windows 7 专业版、企业版或 Windows 7 旗舰版的基于 Windows 的桌面上轻松配置、部署和管理公司的 Windows 虚拟 PC 映像。</span><span class="sxs-lookup"><span data-stu-id="70226-107">By using MED-V, you can easily configure, deploy, and manage corporate Windows Virtual PC images on any Windows-based desktop running Windows 7 Professional, Enterprise, or Windows 7 Ultimate.</span></span> <span data-ttu-id="70226-108">MED-V 解决方案包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="70226-108">The MED-V solution includes the following components:</span></span>

<a href="" id="---------------med-v-host"></a> **<span data-ttu-id="70226-109">MED-V 主机</span><span class="sxs-lookup"><span data-stu-id="70226-109">MED-V Host</span></span>**  
<span data-ttu-id="70226-110">Windows 7 环境，其中包括 MED-V 主机代理、电子软件分发（ESD）系统、注册表管理系统和 MED-V 来宾。</span><span class="sxs-lookup"><span data-stu-id="70226-110">A Windows 7 environment that includes a MED-V Host Agent, an electronic software distribution (ESD) system, a registry management system, and a MED-V guest.</span></span> <span data-ttu-id="70226-111">MED-V 主机与 MED-V 来宾交互，以便可以处理某些设置函数和系统信息。</span><span class="sxs-lookup"><span data-stu-id="70226-111">The MED-V host interacts with the MED-V guest so that certain setup functions and system information can be processed.</span></span>

<a href="" id="-------------------med-v-host-agent"></a> **<span data-ttu-id="70226-112">MED-V 主机代理</span><span class="sxs-lookup"><span data-stu-id="70226-112">MED-V Host Agent</span></span>**  
<span data-ttu-id="70226-113">MED-V 主机中包含的用于提供与 MED-V 来宾通信的信道的 MED-V 软件。</span><span class="sxs-lookup"><span data-stu-id="70226-113">The MED-V software contained in the MED-V host that provides a channel to communicate with the MED-V guest.</span></span> <span data-ttu-id="70226-114">它还提供了首次设置和应用程序发布等功能。</span><span class="sxs-lookup"><span data-stu-id="70226-114">It also provides functionality such as first time setup and application publishing.</span></span>

<span data-ttu-id="70226-115">**注意** 安装 MED-V 并安装其所需组件后，必须配置 MED-V-V。</span><span class="sxs-lookup"><span data-stu-id="70226-115">**Note** After MED-V and its required components are installed MED-V must be configured.</span></span> <span data-ttu-id="70226-116">MED-V 的配置称为 "首次设置"。</span><span class="sxs-lookup"><span data-stu-id="70226-116">The configuration of MED-V is referred to as first time setup.</span></span>

 

<a href="" id="esd-system"></a>**<span data-ttu-id="70226-117">ESD 系统</span><span class="sxs-lookup"><span data-stu-id="70226-117">ESD System</span></span>**  
<span data-ttu-id="70226-118">你的现有软件分发方法，可让你部署和安装 MED-V 创建的 MED-V 工作区程序包文件。</span><span class="sxs-lookup"><span data-stu-id="70226-118">Your existing software distribution method that lets you deploy and install the MED-V workspace package files that MED-V creates.</span></span>

<a href="" id="registry-management-system"></a>**<span data-ttu-id="70226-119">注册表管理系统</span><span class="sxs-lookup"><span data-stu-id="70226-119">Registry Management System</span></span>**  
<span data-ttu-id="70226-120">管理组策略设置和首选项的现有方法。</span><span class="sxs-lookup"><span data-stu-id="70226-120">Your existing method of managing Group Policy settings and preferences.</span></span>

<a href="" id="windows-virtual-pc-image"></a>**<span data-ttu-id="70226-121">Windows 虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="70226-121">Windows Virtual PC Image</span></span>**  
<span data-ttu-id="70226-122">管理员定义的虚拟机，其中包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="70226-122">An administrator-defined virtual machine that contains the following components:</span></span>

<a href="" id="corporate-operating-system"></a>**<span data-ttu-id="70226-123">企业操作系统</span><span class="sxs-lookup"><span data-stu-id="70226-123">Corporate Operating System</span></span>**  
<span data-ttu-id="70226-124">您的标准企业操作系统。</span><span class="sxs-lookup"><span data-stu-id="70226-124">Your standard corporate operating system.</span></span>

<a href="" id="management-and-security-tools"></a>**<span data-ttu-id="70226-125">管理和安全工具</span><span class="sxs-lookup"><span data-stu-id="70226-125">Management and Security Tools</span></span>**  
<span data-ttu-id="70226-126">您的标准管理和安全工具，例如病毒防护。</span><span class="sxs-lookup"><span data-stu-id="70226-126">Your standard management and security tools, such as virus protection.</span></span>

<a href="" id="-----------------------med-v-guest"></a> **<span data-ttu-id="70226-127">MED-V 来宾</span><span class="sxs-lookup"><span data-stu-id="70226-127">MED-V Guest</span></span>**  
<span data-ttu-id="70226-128">Windows XP SP3 环境，作为在 Windows 7 上运行的 Windows 虚拟 PC 的一部分，其中包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="70226-128">A Windows XP SP3 environment, as part of a Windows Virtual PC running on Windows 7 that contains the following components:</span></span>

<a href="" id="---------------------------med-v-guest-agent"></a> **<span data-ttu-id="70226-129">MED-V 来宾代理</span><span class="sxs-lookup"><span data-stu-id="70226-129">MED-V Guest Agent</span></span>**  
<span data-ttu-id="70226-130">MED-V 来宾中包含的 MED-V 软件，提供与 MED-V 主机通信的信道。</span><span class="sxs-lookup"><span data-stu-id="70226-130">The MED-V software contained in the MED-V guest that provides a channel to communicate with the MED-V host.</span></span> <span data-ttu-id="70226-131">它还支持 MED-V 主机代理，其功能类似于第一次设置时执行。</span><span class="sxs-lookup"><span data-stu-id="70226-131">It also supports the MED-V Host Agent with functions like performing first time setup.</span></span>

<span data-ttu-id="70226-132">**注意** MED-V 来宾代理将在首次设置时自动安装。</span><span class="sxs-lookup"><span data-stu-id="70226-132">**Note** The MED-V Guest Agent is installed automatically during first time setup.</span></span>

 

<a href="" id="esd-client"></a>**<span data-ttu-id="70226-133">ESD 客户端</span><span class="sxs-lookup"><span data-stu-id="70226-133">ESD Client</span></span>**  
<span data-ttu-id="70226-134">ESD 系统的可选部分，用于安装 ESD 系统的软件包和报告状态。</span><span class="sxs-lookup"><span data-stu-id="70226-134">An optional part of your ESD system that installs software packages and reports status to the ESD system.</span></span>

## <span data-ttu-id="70226-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="70226-135">Related topics</span></span>


[<span data-ttu-id="70226-136">规划应用程序操作系统兼容性</span><span class="sxs-lookup"><span data-stu-id="70226-136">Planning for Application Operating System Compatibility</span></span>](planning-for-application-operating-system-compatibility.md)

[<span data-ttu-id="70226-137">为 MED-V 准备部署环境</span><span class="sxs-lookup"><span data-stu-id="70226-137">Prepare the Deployment Environment for MED-V</span></span>](prepare-the-deployment-environment-for-med-v.md)

 

 





