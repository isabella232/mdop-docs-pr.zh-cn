---
title: 如何使用电子软件分发部署 App-V 5.1 程序包
description: 如何使用电子软件分发部署 App-V 5.1 程序包
author: dansimp
ms.assetid: e1957a5a-1f18-42da-b2c1-a5ae5a4cca7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a9ed5fbb264f8fb9676d7fa18fe4de8019ea8e79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798482"
---
# <span data-ttu-id="f6b52-103">如何使用电子软件分发部署 App-V 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="f6b52-103">How to deploy App-V 5.1 Packages Using Electronic Software Distribution</span></span>


<span data-ttu-id="f6b52-104">你可以使用电子软件分发（ESD）系统将 app-v 5.1 虚拟应用程序部署到 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="f6b52-104">You can use an electronic software distribution (ESD) system to deploy App-V 5.1 virtual applications to App-V clients.</span></span> <span data-ttu-id="f6b52-105">有关详细信息，请参阅您正在使用的 ESD 提供的文档。</span><span class="sxs-lookup"><span data-stu-id="f6b52-105">For details, see the documentation available with the ESD you are using.</span></span>

<span data-ttu-id="f6b52-106">有关使用 ESD 部署 app-v 程序包的组件要求和选项，请参阅[计划使用电子软件分发系统部署 app-v 5.1](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b52-106">For component requirements and options for using an ESD to deploy App-V packages, see [Planning to Deploy App-V 5.1 with an Electronic Software Distribution System](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md).</span></span>

<span data-ttu-id="f6b52-107">使用以下方法之一将程序包发布到带有 ESD 的 App-v 客户端计算机：</span><span class="sxs-lookup"><span data-stu-id="f6b52-107">Use one of the following methods to publish packages to App-V client computers with an ESD:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6b52-108">方法</span><span class="sxs-lookup"><span data-stu-id="f6b52-108">Method</span></span></th>
<th align="left"><span data-ttu-id="f6b52-109">描述</span><span class="sxs-lookup"><span data-stu-id="f6b52-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6b52-110">由第三方 ESD 提供的功能</span><span class="sxs-lookup"><span data-stu-id="f6b52-110">Functionality provided by a third-party ESD</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6b52-111">使用第三方 ESD 中的功能。</span><span class="sxs-lookup"><span data-stu-id="f6b52-111">Use the functionality in a third-party ESD.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6b52-112">独立 Windows Installer</span><span class="sxs-lookup"><span data-stu-id="f6b52-112">Stand-alone Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6b52-113">在目标客户端计算机上通过使用在最初对应用程序进行序列化时创建的关联的 Windows Installer （.msi）文件来安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="f6b52-113">Install the application on the target client computer by using the associated Windows Installer (.msi) file that is created when you initially sequence an application.</span></span> <span data-ttu-id="f6b52-114">Windows Installer 文件包含用于配置程序包的关联 App-v 5.1 包文件信息，并将所需的程序包文件复制到客户端。</span><span class="sxs-lookup"><span data-stu-id="f6b52-114">The Windows Installer file contains the associated App-V 5.1 package file information used to configure a package and copies the required package files to the client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6b52-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6b52-115">PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6b52-116">使用 PowerShell cmdlet 部署虚拟化应用程序。</span><span class="sxs-lookup"><span data-stu-id="f6b52-116">Use PowerShell cmdlets to deploy virtualized applications.</span></span> <span data-ttu-id="f6b52-117">有关使用 PowerShell 和 App-v 5.1 的详细信息，请参阅 <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)"> 使用 powershell 管理 app-v 5.1 </a> 。</span><span class="sxs-lookup"><span data-stu-id="f6b52-117">For more information about using PowerShell and App-V 5.1, see <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)">Administering App-V 5.1 by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="f6b52-118">使用 ESD 部署 app-v 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="f6b52-118">To deploy App-V 5.1 packages by using an ESD</span></span>**

1.  <span data-ttu-id="f6b52-119">在环境中的计算机上安装 App-v 5.1 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="f6b52-119">Install the App-V 5.1 Sequencer on a computer in your environment.</span></span> <span data-ttu-id="f6b52-120">有关安装 sequencer 的详细信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-51beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b52-120">For more information about installing the sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  <span data-ttu-id="f6b52-121">使用 app-v 5.1 Sequencer 创建虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="f6b52-121">Use the App-V 5.1 Sequencer to create virtual application.</span></span> <span data-ttu-id="f6b52-122">有关创建虚拟应用程序的信息，请参阅[创建和管理 app-v 5.1 虚拟化应用程序](creating-and-managing-app-v-51-virtualized-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b52-122">For information about creating a virtual application, see [Creating and Managing App-V 5.1 Virtualized Applications](creating-and-managing-app-v-51-virtualized-applications.md).</span></span>

3.  <span data-ttu-id="f6b52-123">创建虚拟应用程序后，使用 ESD 解决方案部署程序包。</span><span class="sxs-lookup"><span data-stu-id="f6b52-123">After you create the virtual application, deploy the package by using your ESD solution.</span></span>

    <span data-ttu-id="f6b52-124">如果您使用的是 System Center Configuration Manager，请首先查看[配置管理器中的应用程序管理简介](https://go.microsoft.com/fwlink/?LinkId=281816)，了解有关使用 app-v 5.1 和 System Center2012 Configuration Manager 的信息。</span><span class="sxs-lookup"><span data-stu-id="f6b52-124">If you are using System Center Configuration Manager, start by reviewing [Introduction to Application Management in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=281816) for information about using App-V 5.1 and System Center2012 Configuration Manager.</span></span>

    <span data-ttu-id="f6b52-125">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="f6b52-125">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="f6b52-126">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="f6b52-126">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="f6b52-127">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="f6b52-127">Got an App-V issue?</span></span>** <span data-ttu-id="f6b52-128">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="f6b52-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="f6b52-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="f6b52-129">Related topics</span></span>


[<span data-ttu-id="f6b52-130">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="f6b52-130">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





