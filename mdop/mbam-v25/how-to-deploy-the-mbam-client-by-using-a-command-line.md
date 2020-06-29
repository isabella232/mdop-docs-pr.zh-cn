---
title: 如何使用命令行部署 MBAM 客户端
description: 如何使用命令行部署 MBAM 客户端
author: dansimp
ms.assetid: ac1d4ffe-c26d-41c9-9737-a4f2b37fde24
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 416d76ad876c5114e3a8764111b6a15c879b13b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803578"
---
# <span data-ttu-id="d3ec5-103">如何使用命令行部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="d3ec5-103">How to Deploy the MBAM Client by Using a Command Line</span></span>


<span data-ttu-id="d3ec5-104">你可以使用命令行部署 Microsoft BitLocker 管理和监视（MBAM）客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-104">You can use a command line to deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client software.</span></span>

## <span data-ttu-id="d3ec5-105">部署 MBAM 客户端软件的命令行</span><span class="sxs-lookup"><span data-stu-id="d3ec5-105">Command Line to deploy the MBAM Client software</span></span>


<span data-ttu-id="d3ec5-106">在命令提示符处键入以下命令，以在部署 MBAM 客户端软件时自动接受《最终用户许可协议》。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-106">Type the following command at the command prompt to automatically accept the end user license agreement when deploying the MBAM Client software.</span></span>

**<span data-ttu-id="d3ec5-107">MBAMClientSetup.exe/acceptEula = 是</span><span class="sxs-lookup"><span data-stu-id="d3ec5-107">MBAMClientSetup.exe /acceptEula=Yes</span></span>**

<span data-ttu-id="d3ec5-108">**注意** **/Ju**和 **/jm**命令行选项不受支持，并且不能用于安装 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-108">**Note** The **/ju** and **/jm** command-line options are not supported and cannot be used to install the MBAM Client software.</span></span>

 

<span data-ttu-id="d3ec5-109">在命令提示符处键入以下命令，提取并安装 MSP：</span><span class="sxs-lookup"><span data-stu-id="d3ec5-109">Type the following command at the command prompt to extract and install the MSP:</span></span>

**<span data-ttu-id="d3ec5-110">MBAMClientSetup.exe/extract &lt; path 提取 MSI &gt; /AcceptEula = Yes</span><span class="sxs-lookup"><span data-stu-id="d3ec5-110">MBAMClientSetup.exe /extract &lt;path to extract MSI&gt; /acceptEula=Yes</span></span>**

<span data-ttu-id="d3ec5-111">然后，通过运行以下命令以静默方式安装 MSI：</span><span class="sxs-lookup"><span data-stu-id="d3ec5-111">Then, install the MSI silently by running the following command:</span></span>

**<span data-ttu-id="d3ec5-112">msiexec/i &lt; 用于提取的 MSI &gt; /qb 的路径 = 1 重启 = ReallySuppress</span><span class="sxs-lookup"><span data-stu-id="d3ec5-112">msiexec /i &lt;path to extracted MSI&gt; /qb ALLUSERS=1 REBOOT=ReallySuppress</span></span>**

<span data-ttu-id="d3ec5-113">**注意** 从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-113">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="d3ec5-114">但是，你可以在接受 EULA 后从产品附带的可执行文件（.exe）中提取 MSI。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-114">However, you can extract the MSI from the executable file (.exe) that is included with the product, after accepting the EULA.</span></span>

 

## <a href="" id="optin-for-microsoft-updates-1-command-line-option"></a><span data-ttu-id="d3ec5-115">OPTIN \ _FOR \ _MICROSOFT \ _UPDATES = 1 命令行选项</span><span class="sxs-lookup"><span data-stu-id="d3ec5-115">OPTIN\_FOR\_MICROSOFT\_UPDATES=1 command-line option</span></span>


<span data-ttu-id="d3ec5-116">你可以选择在 `OPTIN_FOR_MICROSOFT_UPDATES=1` 客户端软件安装期间指定命令行选项，以便在客户端计算机上自动安装 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-116">You can optionally specify the command-line option `OPTIN_FOR_MICROSOFT_UPDATES=1` during the Client software installation to automatically install Microsoft Updates on client computers.</span></span> <span data-ttu-id="d3ec5-117">指定此选项会使 Microsoft 更新在客户端软件安装完成后自动启动和搜索可用更新以进行安装。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-117">Specifying this option makes Microsoft Update automatically start and search for available updates to install after the Client software installation finishes.</span></span>

<span data-ttu-id="d3ec5-118">你可以将此命令行选项与以下任一安装方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-118">You can use this command-line option with either of the following installation methods.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d3ec5-119">使用安装 MBAM 客户端软件</span><span class="sxs-lookup"><span data-stu-id="d3ec5-119">Install the MBAM Client software by using</span></span></th>
<th align="left"><span data-ttu-id="d3ec5-120">示例</span><span class="sxs-lookup"><span data-stu-id="d3ec5-120">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d3ec5-121">MBAMClientSetup.exe</span><span class="sxs-lookup"><span data-stu-id="d3ec5-121">MBAMClientSetup.exe</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="d3ec5-122">MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES = 1</span><span class="sxs-lookup"><span data-stu-id="d3ec5-122">MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES=1</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d3ec5-123">msiexec/i MBAMClient.msi</span><span class="sxs-lookup"><span data-stu-id="d3ec5-123">msiexec /i MBAMClient.msi</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="d3ec5-124">msiexec/i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES = 1</span><span class="sxs-lookup"><span data-stu-id="d3ec5-124">msiexec /i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES=1</span></span></strong></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="d3ec5-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3ec5-125">Related topics</span></span>


[<span data-ttu-id="d3ec5-126">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="d3ec5-126">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

 

 
## <span data-ttu-id="d3ec5-127">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="d3ec5-127">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="d3ec5-128">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-128">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="d3ec5-129">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="d3ec5-129">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




