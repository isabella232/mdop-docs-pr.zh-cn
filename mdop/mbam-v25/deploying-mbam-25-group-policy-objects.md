---
title: 部署 MBAM 2.5 组策略对象
description: 部署 MBAM 2.5 组策略对象
author: dansimp
ms.assetid: 4b835054-6846-463d-af58-8ac4639a1188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9624b94e9d4808a35e1199290f4cd90a8122f767
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803558"
---
# <span data-ttu-id="43d96-103">部署 MBAM 2.5 组策略对象</span><span class="sxs-lookup"><span data-stu-id="43d96-103">Deploying MBAM 2.5 Group Policy Objects</span></span>


<span data-ttu-id="43d96-104">若要部署 MBAM，你必须设置用于定义 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="43d96-104">To deploy MBAM, you have to set Group Policy settings that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="43d96-105">若要完成此任务，必须将 MBAM 组策略模板复制到能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的服务器或工作站，然后编辑设置。</span><span class="sxs-lookup"><span data-stu-id="43d96-105">To complete this task, you must copy the MBAM Group Policy Templates to a server or workstation that are capable of running Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM), and then edit the settings.</span></span>

<span data-ttu-id="43d96-106">**重要提示** 请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="43d96-106">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="43d96-107">在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。</span><span class="sxs-lookup"><span data-stu-id="43d96-107">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

## <span data-ttu-id="43d96-108">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="43d96-108">Copying the MBAM 2.5 Group Policy Templates</span></span>


<span data-ttu-id="43d96-109">在安装 MBAM 客户端之前，必须将 MBAM 特定的组策略对象（Gpo）复制到管理工作站。</span><span class="sxs-lookup"><span data-stu-id="43d96-109">Before you install the MBAM Client, you must copy MBAM-specific Group Policy Objects (GPOs) to the Management Workstation.</span></span> <span data-ttu-id="43d96-110">这些 Gpo 定义了用于 BitLocker 驱动器加密的 MBAM 实现设置。</span><span class="sxs-lookup"><span data-stu-id="43d96-110">These GPOs define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="43d96-111">你可以将组策略模板复制到受支持的 Windows server 或客户端计算机的任何服务器或工作站，并且能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="43d96-111">You can copy the Group Policy templates to any server or workstation that is a supported Windows server or client computer and that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="43d96-112">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="43d96-112">Copying the MBAM 2.5 Group Policy Templates</span></span>](copying-the-mbam-25-group-policy-templates.md)

## <span data-ttu-id="43d96-113">编辑 MBAM 2.0 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="43d96-113">Editing MBAM 2.0 GPO settings</span></span>


<span data-ttu-id="43d96-114">创建必要的 Gpo 后，必须将 MBAM 组策略设置部署到你的组织的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="43d96-114">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span> <span data-ttu-id="43d96-115">若要查看和创建 Gpo，必须安装组策略管理控制台（GPMC）或高级组策略管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="43d96-115">To view and create GPOs, you must have Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) installed.</span></span>

[<span data-ttu-id="43d96-116">编辑 MBAM 2.5 组策略设置</span><span class="sxs-lookup"><span data-stu-id="43d96-116">Editing the MBAM 2.5 Group Policy Settings</span></span>](editing-the-mbam-25-group-policy-settings.md)

## <span data-ttu-id="43d96-117">显示或隐藏 Windows "控制面板" 中的 "MBAM 控制面板"</span><span class="sxs-lookup"><span data-stu-id="43d96-117">Showing or hiding the MBAM Control Panel in Windows Control Panel</span></span>


<span data-ttu-id="43d96-118">由于 MBAM 提供了一个可替换默认 Windows BitLocker 控制面板的自定义 MBAM 控制面板，因此你也可以选择使用组策略设置显示或隐藏最终用户的默认 BitLocker 控制面板。</span><span class="sxs-lookup"><span data-stu-id="43d96-118">Since MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to show or hide the default BitLocker Control Panel from end users by using Group Policy settings.</span></span>

[<span data-ttu-id="43d96-119">在控制面板中隐藏默认的“BitLocker 驱动器加密”项目</span><span class="sxs-lookup"><span data-stu-id="43d96-119">Hiding the Default BitLocker Drive Encryption Item in Control Panel</span></span>](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)

## <span data-ttu-id="43d96-120">用于部署 MBAM 2.0 组策略对象的其他资源</span><span class="sxs-lookup"><span data-stu-id="43d96-120">Other Resources for deploying MBAM 2.0 Group Policy Objects</span></span>


[<span data-ttu-id="43d96-121">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="43d96-121">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

## <span data-ttu-id="43d96-122">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="43d96-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="43d96-123">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="43d96-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="43d96-124">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="43d96-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





