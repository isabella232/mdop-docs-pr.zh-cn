---
title: 删除 MBAM 服务器功能或软件
description: 删除 MBAM 服务器功能或软件
author: dansimp
ms.assetid: 5212ba3f-124d-43c5-824a-608e9a192e86
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e6e57c3d2a62a4e01242ade7a82a7bfa551da83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803676"
---
# <span data-ttu-id="324fe-103">删除 MBAM 服务器功能或软件</span><span class="sxs-lookup"><span data-stu-id="324fe-103">Removing MBAM Server Features or Software</span></span>


<span data-ttu-id="324fe-104">这些说明介绍了如何从 Microsoft BitLocker 管理和监视（MBAM）中删除软件和功能。</span><span class="sxs-lookup"><span data-stu-id="324fe-104">These instructions explain how to remove software and features from Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="324fe-105">如果您删除 MBAM 服务器功能，则只会从服务器中删除已配置的功能，而不是 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="324fe-105">If you remove MBAM Server features, only the configured features are removed from the server, not the MBAM Server software.</span></span> <span data-ttu-id="324fe-106">如果您删除 MBAM 服务器软件，将删除该软件以及您在该服务器上配置的任何 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="324fe-106">If you remove the MBAM Server software, the software and any MBAM Server features that you configured on that server are removed.</span></span>

<span data-ttu-id="324fe-107">**注意** 为了防止意外删除数据，MBAM 不提供用于删除数据库的机制;您必须手动执行此操作。</span><span class="sxs-lookup"><span data-stu-id="324fe-107">**Note** To prevent the accidental removal of data, MBAM provides no mechanism for removing the databases; you must do that manually.</span></span>

 

## <a href="" id="bkmk-removeserverfeatures"></a><span data-ttu-id="324fe-108">删除 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="324fe-108">Removing MBAM Server features</span></span>


<span data-ttu-id="324fe-109">你可以使用以下任一方法来删除已配置的 MBAM 服务器功能：</span><span class="sxs-lookup"><span data-stu-id="324fe-109">You can use either of the following methods to remove MBAM Server features that you have configured:</span></span>

-   <span data-ttu-id="324fe-110">MBAM Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="324fe-110">MBAM Server Configuration wizard</span></span>

-   <span data-ttu-id="324fe-111">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="324fe-111">Windows PowerShell cmdlets</span></span>

### <span data-ttu-id="324fe-112">使用 MBAM 服务器配置向导删除功能</span><span class="sxs-lookup"><span data-stu-id="324fe-112">Using the MBAM Server Configuration wizard to remove features</span></span>

<span data-ttu-id="324fe-113">按照这些说明操作，使用 MBAM 服务器配置向导从服务器中删除配置的 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="324fe-113">Follow these instructions to use the MBAM Server Configuration wizard to remove configured MBAM Server features from a server.</span></span>

**<span data-ttu-id="324fe-114">使用向导删除 MBAM 功能</span><span class="sxs-lookup"><span data-stu-id="324fe-114">To remove MBAM features by using the wizard</span></span>**

1.  <span data-ttu-id="324fe-115">在要删除功能的服务器上，选择 " **MBAM 服务器配置**" 以打开配置向导。</span><span class="sxs-lookup"><span data-stu-id="324fe-115">On the server where you want to remove features, select **MBAM Server Configuration** to open the configuration wizard.</span></span>

2.  <span data-ttu-id="324fe-116">单击 "**删除功能**"，选择要删除的功能，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="324fe-116">Click **Remove Features**, select the features to remove, and then click **Next**.</span></span> <span data-ttu-id="324fe-117">"**摘要**" 页面显示您选择要删除的功能。</span><span class="sxs-lookup"><span data-stu-id="324fe-117">A **Summary** page displays the features you selected for removal.</span></span>

3.  <span data-ttu-id="324fe-118">单击 "**删除**" 开始删除这些功能，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="324fe-118">Click **Remove** to start removing the features, and then click **Close**.</span></span>

### <span data-ttu-id="324fe-119">使用 Windows PowerShell 删除功能</span><span class="sxs-lookup"><span data-stu-id="324fe-119">Using Windows PowerShell to remove features</span></span>

<span data-ttu-id="324fe-120">使用以下步骤作为一般指南，使用 Windows PowerShell cmdlet 删除 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="324fe-120">Use the following steps as a general guide to remove MBAM Server features by using Windows PowerShell cmdlets.</span></span>

**<span data-ttu-id="324fe-121">使用 Windows PowerShell 删除 MBAM 功能</span><span class="sxs-lookup"><span data-stu-id="324fe-121">To remove MBAM features by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="324fe-122">在删除任何功能之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="324fe-122">Before removing any features, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="324fe-123">使用以下 cmdlet 删除 MBAM Server 功能：</span><span class="sxs-lookup"><span data-stu-id="324fe-123">Use the following cmdlets to remove MBAM Server features:</span></span>

    -   <span data-ttu-id="324fe-124">Disable-MbamReport</span><span class="sxs-lookup"><span data-stu-id="324fe-124">Disable-MbamReport</span></span>

    -   <span data-ttu-id="324fe-125">Disable-MbamWebApplication</span><span class="sxs-lookup"><span data-stu-id="324fe-125">Disable-MbamWebApplication</span></span>

    -   <span data-ttu-id="324fe-126">Disable-MbamCMIntegration</span><span class="sxs-lookup"><span data-stu-id="324fe-126">Disable-MbamCMIntegration</span></span>

    <span data-ttu-id="324fe-127">若要获取有关 windows powershell cmdlet 的帮助，请键入**get-help** &lt; *cmdlet* &gt; 或查看适用于 windows powershell cmdlet 的[windows powershell 页面的 Microsoft 桌面优化包自动化](https://go.microsoft.com/fwlink/?LinkId=393498)MBAM。</span><span class="sxs-lookup"><span data-stu-id="324fe-127">To get help with Windows PowerShell cmdlets, type **Get-Help** &lt;*cmdlet*&gt; or see the [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=393498) page for the MBAM Windows PowerShell cmdlets.</span></span>

## <span data-ttu-id="324fe-128">删除 MBAM Server 软件</span><span class="sxs-lookup"><span data-stu-id="324fe-128">Removing MBAM Server software</span></span>


<span data-ttu-id="324fe-129">使用以下步骤删除 MBAM Server 软件和你在该服务器上配置的任何 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="324fe-129">Use the following steps to remove the MBAM Server software and any MBAM Server features that you configured on that server.</span></span>

**<span data-ttu-id="324fe-130">删除 MBAM 服务器软件</span><span class="sxs-lookup"><span data-stu-id="324fe-130">To remove the MBAM Server software</span></span>**

1.  <span data-ttu-id="324fe-131">在要卸载 MBAM Server 软件的服务器上，运行**MBAMserversetup.exe**以启动 Microsoft BitLocker 管理和监视设置向导。</span><span class="sxs-lookup"><span data-stu-id="324fe-131">On the server where you want to uninstall the MBAM Server software, run **MBAMserversetup.exe** to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2.  <span data-ttu-id="324fe-132">选择 "**卸载**"，然后按照其余提示完成卸载 MBAM Server 软件的过程。</span><span class="sxs-lookup"><span data-stu-id="324fe-132">Select **Uninstall**, and follow the remaining prompts to complete the process of uninstalling the MBAM Server software.</span></span>



## <span data-ttu-id="324fe-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="324fe-133">Related topics</span></span>


[<span data-ttu-id="324fe-134">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="324fe-134">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

 

 

## <span data-ttu-id="324fe-135">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="324fe-135">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="324fe-136">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="324fe-136">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="324fe-137">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="324fe-137">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



