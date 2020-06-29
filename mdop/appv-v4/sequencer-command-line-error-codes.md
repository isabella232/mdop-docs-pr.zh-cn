---
title: Sequencer 命令行错误代码
description: Sequencer 命令行错误代码
author: dansimp
ms.assetid: 3d491314-4923-45fd-9839-c541c5e620bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74f5bd0c1b66656ac6891dcc1c019254fa36fdac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798795"
---
# <span data-ttu-id="9c1bd-103">Sequencer 命令行错误代码</span><span class="sxs-lookup"><span data-stu-id="9c1bd-103">Sequencer Command-Line Error Codes</span></span>


<span data-ttu-id="9c1bd-104">使用以下列表，通过使用命令行帮助识别与序列化应用程序相关的错误。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-104">Use the following list to help identify errors that are related to sequencing applications by using the command line.</span></span> <span data-ttu-id="9c1bd-105">你还可以通过查看关联的 App-v Sequencer 日志文件来查看此信息。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-105">You can also see this information by viewing the associated App-V Sequencer log file.</span></span>

<span data-ttu-id="9c1bd-106">**注意** 排序期间可能会出现多个错误，如果发生这种情况，则显示的错误代码可能是两个错误代码的和。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-106">**Note** Multiple errors can occur during sequencing, and if this happens, the error code that is displayed might be the sum of two error codes.</span></span> <span data-ttu-id="9c1bd-107">例如，如果缺少 */InstallPath*和 */outputfile*参数，则 app-v Sequencer 将返回**96**-这两个错误代码的和。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-107">For example, if the */InstallPath* and */OutputFile* parameters are missing, the App-V Sequencer will return **96**—the sum of the two error codes.</span></span>

 

<a href="" id="01"></a><span data-ttu-id="9c1bd-108">01</span><span class="sxs-lookup"><span data-stu-id="9c1bd-108">01</span></span>  
<span data-ttu-id="9c1bd-109">存在未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-109">There is an unspecified error.</span></span>

<a href="" id="02"></a><span data-ttu-id="9c1bd-110">02</span><span class="sxs-lookup"><span data-stu-id="9c1bd-110">02</span></span>  
<span data-ttu-id="9c1bd-111">指定的安装目录（/INSTALLPACKAGE）无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-111">The specified installation directory (/INSTALLPACKAGE) is not valid.</span></span>

<a href="" id="04"></a><span data-ttu-id="9c1bd-112">5</span><span class="sxs-lookup"><span data-stu-id="9c1bd-112">04</span></span>  
<span data-ttu-id="9c1bd-113">指定的程序包根目录（/INSTALLPATH）无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-113">The specified package root directory (/INSTALLPATH) is not valid.</span></span>

<a href="" id="08"></a><span data-ttu-id="9c1bd-114">下半年</span><span class="sxs-lookup"><span data-stu-id="9c1bd-114">08</span></span>  
<span data-ttu-id="9c1bd-115">指定的 */outputfile*参数无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-115">The specified */OutputFile* parameter is not valid.</span></span>

<a href="" id="16"></a><span data-ttu-id="9c1bd-116">utf-16</span><span class="sxs-lookup"><span data-stu-id="9c1bd-116">16</span></span>  
<span data-ttu-id="9c1bd-117">未指定安装目录（/INSTALLPACKAGE）。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-117">The installation directory (/INSTALLPACKAGE) is not specified.</span></span>

<a href="" id="32"></a><span data-ttu-id="9c1bd-118">32</span><span class="sxs-lookup"><span data-stu-id="9c1bd-118">32</span></span>  
<span data-ttu-id="9c1bd-119">未指定程序包 root 目录（/INSTALLPATH）。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-119">The package root directory (/INSTALLPATH) is not specified.</span></span>

<a href="" id="64"></a><span data-ttu-id="9c1bd-120">64</span><span class="sxs-lookup"><span data-stu-id="9c1bd-120">64</span></span>  
<span data-ttu-id="9c1bd-121">未指定 */outputfile*参数。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-121">The */OutputFile* parameter is not specified.</span></span>

<a href="" id="128"></a><span data-ttu-id="9c1bd-122">128</span><span class="sxs-lookup"><span data-stu-id="9c1bd-122">128</span></span>  
<span data-ttu-id="9c1bd-123">指定的应用程序虚拟化驱动器无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-123">The specified application virtualization drive is not valid.</span></span>

<a href="" id="256"></a><span data-ttu-id="9c1bd-124">256</span><span class="sxs-lookup"><span data-stu-id="9c1bd-124">256</span></span>  
<span data-ttu-id="9c1bd-125">安装程序失败。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-125">The installer failed.</span></span>

<a href="" id="512"></a><span data-ttu-id="9c1bd-126">512</span><span class="sxs-lookup"><span data-stu-id="9c1bd-126">512</span></span>  
<span data-ttu-id="9c1bd-127">对应用程序进行排序失败。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-127">Sequencing the application failed.</span></span>

<a href="" id="1024"></a><span data-ttu-id="9c1bd-128">1024</span><span class="sxs-lookup"><span data-stu-id="9c1bd-128">1024</span></span>  
<span data-ttu-id="9c1bd-129">评估安装的快捷方式失败。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-129">Evaluating installed shortcuts failed.</span></span>

<a href="" id="2048"></a><span data-ttu-id="9c1bd-130">2048</span><span class="sxs-lookup"><span data-stu-id="9c1bd-130">2048</span></span>  
<span data-ttu-id="9c1bd-131">排序后的应用程序包无法保存。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-131">The sequenced application package cannot be saved.</span></span>

<a href="" id="4096"></a><span data-ttu-id="9c1bd-132">4096</span><span class="sxs-lookup"><span data-stu-id="9c1bd-132">4096</span></span>  
<span data-ttu-id="9c1bd-133">指定的程序包名称（/PACKAGENAME）无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-133">The specified package name (/PACKAGENAME) is not valid.</span></span>

<a href="" id="8192"></a><span data-ttu-id="9c1bd-134">8192</span><span class="sxs-lookup"><span data-stu-id="9c1bd-134">8192</span></span>  
<span data-ttu-id="9c1bd-135">指定的块大小（/BLOCKSIZE）无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-135">The specified block size (/BLOCKSIZE) is not valid.</span></span>

<a href="" id="16384"></a><span data-ttu-id="9c1bd-136">16384</span><span class="sxs-lookup"><span data-stu-id="9c1bd-136">16384</span></span>  
<span data-ttu-id="9c1bd-137">指定的压缩类型（/COMPRESSION）无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-137">The specified compression type (/COMPRESSION) is not valid.</span></span>

<a href="" id="32768"></a><span data-ttu-id="9c1bd-138">32768</span><span class="sxs-lookup"><span data-stu-id="9c1bd-138">32768</span></span>  
<span data-ttu-id="9c1bd-139">指定的项目路径无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-139">The specified project path is not valid.</span></span>

<a href="" id="65536"></a><span data-ttu-id="9c1bd-140">65536</span><span class="sxs-lookup"><span data-stu-id="9c1bd-140">65536</span></span>  
<span data-ttu-id="9c1bd-141">指定的升级参数无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-141">The specified upgrade parameter is not valid.</span></span>

<a href="" id="131072"></a><span data-ttu-id="9c1bd-142">131072</span><span class="sxs-lookup"><span data-stu-id="9c1bd-142">131072</span></span>  
<span data-ttu-id="9c1bd-143">指定的升级项目参数无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-143">The specified upgrade project parameter is not valid.</span></span>

<a href="" id="262144"></a><span data-ttu-id="9c1bd-144">262144</span><span class="sxs-lookup"><span data-stu-id="9c1bd-144">262144</span></span>  
<span data-ttu-id="9c1bd-145">指定的解码路径参数无效。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-145">The specified decode path parameter is not valid.</span></span>

<a href="" id="525288"></a><span data-ttu-id="9c1bd-146">525288</span><span class="sxs-lookup"><span data-stu-id="9c1bd-146">525288</span></span>  
<span data-ttu-id="9c1bd-147">未指定包名称。</span><span class="sxs-lookup"><span data-stu-id="9c1bd-147">The package name is not specified.</span></span>

## <span data-ttu-id="9c1bd-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="9c1bd-148">Related topics</span></span>


[<span data-ttu-id="9c1bd-149">Application Virtualization Sequencer 参考</span><span class="sxs-lookup"><span data-stu-id="9c1bd-149">Application Virtualization Sequencer Reference</span></span>](application-virtualization-sequencer-reference.md)

[<span data-ttu-id="9c1bd-150">Sequencer 命令行参数</span><span class="sxs-lookup"><span data-stu-id="9c1bd-150">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)

 

 





