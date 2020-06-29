---
title: 部署 MBAM 1.0 组策略对象
description: 部署 MBAM 1.0 组策略对象
author: dansimp
ms.assetid: 2129291e-d2b2-41ed-b643-1e311c49fee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d14123f1d5b197146e425cba063e8ce4c180641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802924"
---
# <span data-ttu-id="54ef2-103">部署 MBAM 1.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="54ef2-103">Deploying MBAM 1.0 Group Policy Objects</span></span>


<span data-ttu-id="54ef2-104">若要成功部署 Microsoft BitLocker 管理和监视（MBAM），必须首先确定你将在 MBAM 实现中使用的组策略。</span><span class="sxs-lookup"><span data-stu-id="54ef2-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you must first determine the Group Policies that you will use in your implementation of MBAM.</span></span> <span data-ttu-id="54ef2-105">有关各种可用策略的详细信息，请参阅[规划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54ef2-105">For more information about the various available policies, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span> <span data-ttu-id="54ef2-106">确定要使用的策略后，必须使用 MBAM 1.0 组策略模板来创建和部署一个或多个包含 MBAM 策略设置的组策略对象（GPO）。</span><span class="sxs-lookup"><span data-stu-id="54ef2-106">When you have determined the policies that you are going to use, you must use the MBAM 1.0 Group Policy template to create and deploy one or more Group Policy objects (GPO) that include the MBAM policy settings.</span></span>

## <span data-ttu-id="54ef2-107">安装 MBAM 1.0 组策略模板</span><span class="sxs-lookup"><span data-stu-id="54ef2-107">Install the MBAM 1.0 Group Policy template</span></span>


<span data-ttu-id="54ef2-108">除了提供 MBAM 服务器相关的功能，服务器设置应用程序还包含一个 MBAM 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="54ef2-108">In addition to providing server-related features of MBAM, the server setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="54ef2-109">你可以在可运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的任何计算机上安装此模板。</span><span class="sxs-lookup"><span data-stu-id="54ef2-109">You can install this template on any computer that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="54ef2-110">如何安装 MBAM 1.0 组策略模板</span><span class="sxs-lookup"><span data-stu-id="54ef2-110">How to Install the MBAM 1.0 Group Policy Template</span></span>](how-to-install-the-mbam-10-group-policy-template.md)

## <span data-ttu-id="54ef2-111">部署 MBAM 1.0 组策略设置</span><span class="sxs-lookup"><span data-stu-id="54ef2-111">Deploy MBAM 1.0 Group Policy settings</span></span>


<span data-ttu-id="54ef2-112">创建必要的 Gpo 后，必须将 MBAM 组策略设置部署到你的组织的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="54ef2-112">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span>

[<span data-ttu-id="54ef2-113">如何编辑 MBAM 1.0 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="54ef2-113">How to Edit MBAM 1.0 GPO Settings</span></span>](how-to-edit-mbam-10-gpo-settings.md)

## <span data-ttu-id="54ef2-114">在 Windows 中显示 "MBAM 控制面板"</span><span class="sxs-lookup"><span data-stu-id="54ef2-114">Display the MBAM Control Panel in Windows</span></span>


<span data-ttu-id="54ef2-115">由于 MBAM 提供了可替换默认 Windows BitLocker 控制面板的自定义 MBAM 控制面板，因此你也可以选择通过使用组策略隐藏最终用户的默认 BitLocker 控制面板。</span><span class="sxs-lookup"><span data-stu-id="54ef2-115">Because MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to hide the default BitLocker Control Panel from end users by using Group Policy.</span></span>

[<span data-ttu-id="54ef2-116">如何在 Windows 控制面板中隐藏默认的 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="54ef2-116">How to Hide Default BitLocker Encryption in The Windows Control Panel</span></span>](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)

## <span data-ttu-id="54ef2-117">用于部署 MBAM 1.0 组策略对象的其他资源</span><span class="sxs-lookup"><span data-stu-id="54ef2-117">Other resources for deploying MBAM 1.0 Group Policy Objects</span></span>


[<span data-ttu-id="54ef2-118">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="54ef2-118">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





