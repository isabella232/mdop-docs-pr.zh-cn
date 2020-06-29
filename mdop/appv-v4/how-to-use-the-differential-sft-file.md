---
title: 如何使用 Differential SFT 文件
description: 如何使用 Differential SFT 文件
author: dansimp
ms.assetid: 607e30fd-2f0e-4e2f-b669-0b3f010aebb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 85cc45f9665569d77fcf275db6dbc080eb919229
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798961"
---
# <span data-ttu-id="d3edd-103">如何使用 Differential SFT 文件</span><span class="sxs-lookup"><span data-stu-id="d3edd-103">How to Use the Differential SFT File</span></span>


<span data-ttu-id="d3edd-104">当对应用程序进行排序时，Microsoft Application Virtualization （App-v） Sequencer 将创建 SFT 文件（SFT）以存储虚拟应用程序的所有文件内容和配置信息。</span><span class="sxs-lookup"><span data-stu-id="d3edd-104">When sequencing an application, the Microsoft Application Virtualization (App-V) Sequencer creates SFT files (.sft) to store all of the virtual application’s files content and configuration information.</span></span> <span data-ttu-id="d3edd-105">在 App-v 的4.5 版本中，引入了差异 SFT （dsft）文件。</span><span class="sxs-lookup"><span data-stu-id="d3edd-105">In version4.5 of App-V, the Differential SFT (.dsft) file has been introduced.</span></span> <span data-ttu-id="d3edd-106">使用 Sequencer 创建现有程序包的升级后，你可以选择生成此文件，以便仅存储原始顺序应用程序包与新版本之间的差异。</span><span class="sxs-lookup"><span data-stu-id="d3edd-106">After using the Sequencer to create an upgrade for an existing package, you can choose to generate this file to store only the differences between the original sequenced application package and the new version.</span></span> <span data-ttu-id="d3edd-107">因此，它比完整的 SFT 文件小得多，它将用于新版本的应用程序，并减少通过低带宽网络连接发送程序包更新的影响。</span><span class="sxs-lookup"><span data-stu-id="d3edd-107">It is therefore much smaller than the full SFT file would be for the new version of the application and reduces the impact of sending package updates over low-bandwidth network connections.</span></span> <span data-ttu-id="d3edd-108">但是，仅在某些受限制的情况下才支持它的使用。</span><span class="sxs-lookup"><span data-stu-id="d3edd-108">However, its use is supported only in certain restricted situations.</span></span> <span data-ttu-id="d3edd-109">此功能旨在在你使用电子软件分发（ESD）系统的地方使用，以便通过低带宽连接管理具有本地文件服务器的一组用户，并且不使用 App-v 流式处理服务器。</span><span class="sxs-lookup"><span data-stu-id="d3edd-109">This feature was intended to be used specifically where you are using an electronic software distribution (ESD) system to manage a group of users with a local file server over a low-bandwidth connection and you are not using App-V streaming servers.</span></span>

<span data-ttu-id="d3edd-110">如果使用配置 Manager2007 管理用户，则无需使用差异 SFT 文件，因为 Configuration Manager 支持已内置的低带宽部署。</span><span class="sxs-lookup"><span data-stu-id="d3edd-110">You do not need to use the Differential SFT file if you are using Configuration Manager2007 to manage the users, because Configuration Manager has support for low-bandwidth deployments already built in.</span></span> <span data-ttu-id="d3edd-111">如果你将应用程序虚拟化（App-v）管理或流服务器用于活动升级，也不是必需的，因为客户将仅检索旧版本和新程序包版本之间的差异。</span><span class="sxs-lookup"><span data-stu-id="d3edd-111">It is also not required if you are using Application Virtualization (App-V) Management or Streaming Servers with Active Upgrade because the client will retrieve only the differences between the old and new package versions.</span></span>

<span data-ttu-id="d3edd-112">以下过程介绍了如何使用 Sequencer 安装中包含的 mkdiffpkg.exe 来创建差异 SFT 文件，完成虚拟应用程序包升级后，并部署差异 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="d3edd-112">The following procedure shows how to use the mkdiffpkg.exe that is included in the Sequencer installation to create the Differential SFT file, after completing the upgrade of the virtual application package, and to deploy the Differential SFT file.</span></span> <span data-ttu-id="d3edd-113">完成此过程有助于确保从客户端计算机上卸载程序包的过程中，当用户下次尝试运行应用程序时，客户端将回退到替代 URL，该 URL 被设置为从本地文件共享中流出完整的程序包 V2。</span><span class="sxs-lookup"><span data-stu-id="d3edd-113">Completing this procedure helps ensure that if the package is somehow unloaded from the client computer, the next time the user tries to run the application, the client will fall back to the override URL, which is set to stream the full package V2.sft from the local file share.</span></span> <span data-ttu-id="d3edd-114">这将在启动应用程序时避免任何用户出现故障。</span><span class="sxs-lookup"><span data-stu-id="d3edd-114">This will avoid any failure for the user when starting the application.</span></span> <span data-ttu-id="d3edd-115">如果整个客户端损坏或卸载，建议将 ESD 系统配置为将已升级程序包的完整版本（即 sft）部署到客户端。</span><span class="sxs-lookup"><span data-stu-id="d3edd-115">If the entire client becomes corrupted or is uninstalled, it is recommended that the ESD system be configured to deploy the full version of the upgraded package, V2.sft, to the client.</span></span>

<span data-ttu-id="d3edd-116">有关升级程序包的详细信息，请参阅 App-v 4.5 操作指南中的 "如何升级现有虚拟应用程序"</span><span class="sxs-lookup"><span data-stu-id="d3edd-116">For more information about upgrading a package, see “How to Upgrade an Existing Virtual Application” in the App-V4.5 Operations Guide at</span></span> <https://go.microsoft.com/fwlink/?LinkId=133129>

<span data-ttu-id="d3edd-117">**注意** 作为先决条件，由 ESD 定向的所有用户计算机必须将 V1 文件完全加载到其本地缓存中，并且必须在所有计算机上启用文件流。</span><span class="sxs-lookup"><span data-stu-id="d3edd-117">**Note** As a prerequisite, all user computers being targeted by the ESD must have the V1.sft file fully loaded into their local cache, and file streaming must be enabled on all computers.</span></span>

 

**<span data-ttu-id="d3edd-118">使用差异 SFT 文件</span><span class="sxs-lookup"><span data-stu-id="d3edd-118">To use the Differential SFT file</span></span>**

1.  <span data-ttu-id="d3edd-119">使用具有管理员权限的帐户登录到 Sequencer 计算机。</span><span class="sxs-lookup"><span data-stu-id="d3edd-119">Log on to the Sequencer computer by using an account with administrator rights.</span></span> <span data-ttu-id="d3edd-120">在 Sequencer 中打开原始程序包（V1）进行升级，然后将该程序包升级到新版本（V2），并将其另存为新的 V2. sft。</span><span class="sxs-lookup"><span data-stu-id="d3edd-120">Open the original package (V1) for upgrade in the Sequencer, and then upgrade the package to the new version (V2) and save it as a new V2.sft.</span></span>

2.  <span data-ttu-id="d3edd-121">在 App-v 4.5 Sequencer 安装文件夹中打开一个命令窗口，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d3edd-121">Open a command window in the App-V4.5 Sequencer installation folder, and run the following command:</span></span>

    `“mkdiffpkg.exe V2.sft V2.dsft”`

3.  <span data-ttu-id="d3edd-122">使用 ESD 系统或其他文件复制过程，将完整的 V2 程序包内容文件 V2 复制到本地文件共享，用户计算机在连接良好的网络连接时可访问该文件。</span><span class="sxs-lookup"><span data-stu-id="d3edd-122">Using the ESD system or other file copy process, copy the full V2 package content file, V2.sft, to a local file share that is accessible to the user computers on a well-connected network connection.</span></span>

4.  <span data-ttu-id="d3edd-123">使用 ESD 系统，在每台用户计算机上放置差异 SFT 文件 dsft 的副本。</span><span class="sxs-lookup"><span data-stu-id="d3edd-123">Using the ESD system, place a copy of the Differential SFT file, V2.dsft, on each user computer.</span></span>

5.  <span data-ttu-id="d3edd-124">若要导入 dsft 文件，请在每台用户计算机上运行以下 SFTMIME 命令：</span><span class="sxs-lookup"><span data-stu-id="d3edd-124">To import the V2.dsft file, run the following SFTMIME command on each user computer:</span></span>

    `“SFTMIME load package:<package name> /SFTPATH <path to V2.dsft>”`

6.  <span data-ttu-id="d3edd-125">在每台用户计算机上运行以下 SFTMIME 命令，将替代 URL 设置为指向 V2 文件：</span><span class="sxs-lookup"><span data-stu-id="d3edd-125">Run the following SFTMIME command on each user computer to set the override URL to point to the V2.sft file:</span></span>

    `“SFTMIME configure package:<package name> /OverrideURL FILE://<network path to V2.sft>”`

**<span data-ttu-id="d3edd-126">注意</span><span class="sxs-lookup"><span data-stu-id="d3edd-126">Note</span></span>**  
-   <span data-ttu-id="d3edd-127">差异 SFT 文件必须按正确的顺序应用到客户端。</span><span class="sxs-lookup"><span data-stu-id="d3edd-127">Differential SFT files must be applied to clients in the correct order.</span></span> <span data-ttu-id="d3edd-128">例如，dsft 必须应用于 V1 应用程序，然后才能应用 V3 dsft。</span><span class="sxs-lookup"><span data-stu-id="d3edd-128">For example, V2.dsft must be applied to a V1 application before V3.dsft is applied.</span></span>

-   <span data-ttu-id="d3edd-129">Sequencer 中的 "**生成 Microsoft Windows Installer （MSI）" 程序包**功能不能与差异 SFT 文件配合使用。</span><span class="sxs-lookup"><span data-stu-id="d3edd-129">The **Generate Microsoft Windows Installer (MSI) Package** capability in the Sequencer cannot be used with the Differential SFT file.</span></span>

 

## <span data-ttu-id="d3edd-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3edd-130">Related topics</span></span>


[<span data-ttu-id="d3edd-131">如何使用 App-v Sequencer 创建或升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="d3edd-131">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





