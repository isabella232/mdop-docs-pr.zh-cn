---
title: 关于虚拟环境
description: 关于虚拟环境
author: dansimp
ms.assetid: e03a8c72-56c1-4ae9-aa45-0283c50a154c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 15f3ae29ae8d5586f83baa98ea6821e09ae5c305
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803159"
---
# <span data-ttu-id="8fdf1-103">关于虚拟环境</span><span class="sxs-lookup"><span data-stu-id="8fdf1-103">About Virtual Environments</span></span>


<span data-ttu-id="8fdf1-104">虚拟应用程序在虚拟环境中运行。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-104">Virtual applications run in virtual environments.</span></span> <span data-ttu-id="8fdf1-105">虚拟环境使每个应用程序能够在桌面版、膝上型计算机或远程桌面会话主机（RDSession 主机）服务器上运行，而无需安装和更改主机操作系统。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-105">Virtual environments enable each application to run on a desktop, laptop, or Remote Desktop Session Host (RDSession Host) server without installation and alteration of the host operating system.</span></span> <span data-ttu-id="8fdf1-106">每个应用程序都在虚拟环境中携带其自己的配置信息。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-106">Each application carries its own configuration information in the virtual environment.</span></span> <span data-ttu-id="8fdf1-107">因此，许多应用程序与同一台计算机上的其他应用程序并排运行，而不存在任何冲突。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-107">As a result, many applications run side by side with other applications on the same computer without any conflicts.</span></span>

<span data-ttu-id="8fdf1-108">虚拟应用程序在本地运行，因此它们使用从本地安装的任何应用程序对本地服务的完全性能、功能和访问权限运行。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-108">Virtual applications run locally, so they run with the full performance, functionality, and access to local services that you would expect from any application installed locally.</span></span>

<span data-ttu-id="8fdf1-109">由于每个应用程序都在虚拟环境中运行，因此以下问题将减少：</span><span class="sxs-lookup"><span data-stu-id="8fdf1-109">Because each application runs in a virtual environment, the following problems are reduced:</span></span>

-   <span data-ttu-id="8fdf1-110">应用程序冲突-在不使用应用程序虚拟化的环境中，必须对每个应用程序进行全面测试，以确保它不会干扰其他已安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-110">Application conflicts—In environments that do not use Application Virtualization, you must thoroughly test every application to ensure that it does not interfere with other installed applications.</span></span>

-   <span data-ttu-id="8fdf1-111">回归测试-由于应用程序不更改基础操作系统，因此消除了冗长的回归测试。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-111">Regression testing—Because the application does not change the underlying operating system, lengthy regression testing is eliminated.</span></span>

-   <span data-ttu-id="8fdf1-112">版本不兼容-同一应用程序的不同版本可以同时在同一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-112">Version incompatibilities—Different versions of the same application can run simultaneously on the same computer.</span></span>

-   <span data-ttu-id="8fdf1-113">多用户访问-不在多用户模式下运行的应用程序，因此不能在 RDSession 主机内运行，现在可以对单个 RDSession 主机上的多个用户执行此操作并正常运行。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-113">Multiuser access—Applications that do not run in multiuser mode, and therefore cannot run within an RDSession Host, can now do so and function correctly for multiple users on a single RDSession Host.</span></span>

-   <span data-ttu-id="8fdf1-114">"多种计算" 问题-同一应用程序中使用不同配置的两个实例可以同时在同一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-114">Multitenancy issues—Two instances of the same application that use different configurations can run on the same computer at the same time.</span></span>

-   <span data-ttu-id="8fdf1-115">服务器 siloing-消除了许多单独的服务器场的需要。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-115">Server siloing—The need for many separate server farms is eliminated.</span></span>

<span data-ttu-id="8fdf1-116">虚拟环境包括每个应用程序的虚拟注册表。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-116">Virtual environments include a virtual registry for each application.</span></span> <span data-ttu-id="8fdf1-117">其他应用程序或实用工具（如 Regedit）无法查看由一个应用程序创建的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-117">Registry settings created by one application cannot be seen by other applications or utilities such as Regedit.</span></span> <span data-ttu-id="8fdf1-118">虚拟注册表使用*覆盖*方法，而不是复制整个注册表。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-118">Rather than copying the entire registry, the virtual registry uses an *overlay* method.</span></span> <span data-ttu-id="8fdf1-119">只要该注册表项的虚拟副本未包含在虚拟注册表中，就可以由应用程序读取客户端注册表中的项目。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-119">Items in the client registry can be read by the application as long as a virtual copy of that registry item is not included in the virtual registry.</span></span> <span data-ttu-id="8fdf1-120">对注册表的所有应用程序写入都包含在虚拟注册表中。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-120">All application writes to the registry are contained in the virtual registry.</span></span>

<span data-ttu-id="8fdf1-121">虚拟环境还包括虚拟文件系统和其他虚拟组件，包括虚拟服务和虚拟 COM。</span><span class="sxs-lookup"><span data-stu-id="8fdf1-121">Virtual environments also include a virtual file system and other virtual components, including virtual services and virtual COM.</span></span>

## <span data-ttu-id="8fdf1-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="8fdf1-122">Related topics</span></span>


[<span data-ttu-id="8fdf1-123">Application Virtualization Client Management Console 概述</span><span class="sxs-lookup"><span data-stu-id="8fdf1-123">Application Virtualization Client Management Console Overview</span></span>](application-virtualization-client-management-console-overview.md)

 

 





