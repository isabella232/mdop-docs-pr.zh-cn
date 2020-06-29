---
title: 命令行错误
description: 命令行错误
author: dansimp
ms.assetid: eea62568-4e90-4877-9cc7-e27ef5c05068
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab29a77dc15a8c7bd3590b918a7ca8c1ca6e8c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802204"
---
# <span data-ttu-id="bb9ed-103">命令行错误</span><span class="sxs-lookup"><span data-stu-id="bb9ed-103">Command-Line Errors</span></span>


<span data-ttu-id="bb9ed-104">使用以下错误列表来确定命令行顺序不正常工作的原因。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-104">Use the following list of errors to identify the reasons why command-line sequencing is not working properly.</span></span> <span data-ttu-id="bb9ed-105">您也可以通过查看 sequencer 日志文件来查看这些错误。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-105">You can also see these errors by viewing the sequencer log file.</span></span>

<span data-ttu-id="bb9ed-106">**注意** 排序时可能会显示多个错误。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-106">**Note** More than one error might be displayed when sequencing.</span></span> <span data-ttu-id="bb9ed-107">此外，显示的错误代码可能是两个错误代码的和。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-107">Furthermore, the error code displayed might be the sum of two error codes.</span></span> <span data-ttu-id="bb9ed-108">例如，如果缺少 */InstallPath*和 */Outputfile*参数，Microsoft System Center Application virtualization Sequencer 将返回96（这两个错误代码的和）。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-108">For example, if the */InstallPath* and */OutputFile* parameters are missing, the Microsoft System Center Application Virtualization Sequencer will return 96—the sum of the two error codes.</span></span>

 

<a href="" id="01"></a><span data-ttu-id="bb9ed-109">01</span><span class="sxs-lookup"><span data-stu-id="bb9ed-109">01</span></span>  
<span data-ttu-id="bb9ed-110">存在未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-110">There is an unspecified error.</span></span>

<a href="" id="02"></a><span data-ttu-id="bb9ed-111">02</span><span class="sxs-lookup"><span data-stu-id="bb9ed-111">02</span></span>  
<span data-ttu-id="bb9ed-112">指定的指定安装目录（/INSTALLPACKAGE）无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-112">The specified installation directory (/INSTALLPACKAGE) specified is not valid.</span></span>

<a href="" id="04"></a><span data-ttu-id="bb9ed-113">5</span><span class="sxs-lookup"><span data-stu-id="bb9ed-113">04</span></span>  
<span data-ttu-id="bb9ed-114">指定的程序包根目录（/INSTALLPATH）无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-114">The specified package root directory (/INSTALLPATH) is not valid.</span></span>

<a href="" id="08"></a><span data-ttu-id="bb9ed-115">下半年</span><span class="sxs-lookup"><span data-stu-id="bb9ed-115">08</span></span>  
<span data-ttu-id="bb9ed-116">指定的 */outputfile*参数无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-116">The */OutputFile* parameter that was specified is not valid.</span></span>

<a href="" id="16"></a><span data-ttu-id="bb9ed-117">utf-16</span><span class="sxs-lookup"><span data-stu-id="bb9ed-117">16</span></span>  
<span data-ttu-id="bb9ed-118">未指定安装目录（/INSTALLPACKAGE）。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-118">The installation directory (/INSTALLPACKAGE) was not specified.</span></span>

<a href="" id="32"></a><span data-ttu-id="bb9ed-119">32</span><span class="sxs-lookup"><span data-stu-id="bb9ed-119">32</span></span>  
<span data-ttu-id="bb9ed-120">未指定程序包 root 目录（/INSTALLPATH）。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-120">The package root directory (/INSTALLPATH) was not specified.</span></span>

<a href="" id="64"></a><span data-ttu-id="bb9ed-121">64</span><span class="sxs-lookup"><span data-stu-id="bb9ed-121">64</span></span>  
<span data-ttu-id="bb9ed-122">未指定 */outputfile*参数。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-122">The */OutputFile* parameter was not specified.</span></span>

<a href="" id="128"></a><span data-ttu-id="bb9ed-123">128</span><span class="sxs-lookup"><span data-stu-id="bb9ed-123">128</span></span>  
<span data-ttu-id="bb9ed-124">指定的应用程序虚拟化驱动器无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-124">The specified application virtualization drive is not valid.</span></span>

<a href="" id="256"></a><span data-ttu-id="bb9ed-125">256</span><span class="sxs-lookup"><span data-stu-id="bb9ed-125">256</span></span>  
<span data-ttu-id="bb9ed-126">安装程序失败。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-126">The installer failed.</span></span>

<a href="" id="512"></a><span data-ttu-id="bb9ed-127">512</span><span class="sxs-lookup"><span data-stu-id="bb9ed-127">512</span></span>  
<span data-ttu-id="bb9ed-128">对应用程序进行排序失败。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-128">Sequencing the application failed.</span></span>

<a href="" id="1024"></a><span data-ttu-id="bb9ed-129">1024</span><span class="sxs-lookup"><span data-stu-id="bb9ed-129">1024</span></span>  
<span data-ttu-id="bb9ed-130">评估安装的快捷方式失败。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-130">Evaluating installed shortcuts failed.</span></span>

<a href="" id="2048"></a><span data-ttu-id="bb9ed-131">2048</span><span class="sxs-lookup"><span data-stu-id="bb9ed-131">2048</span></span>  
<span data-ttu-id="bb9ed-132">排序后的应用程序包无法保存。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-132">The sequenced application package cannot be saved.</span></span>

<a href="" id="4096"></a><span data-ttu-id="bb9ed-133">4096</span><span class="sxs-lookup"><span data-stu-id="bb9ed-133">4096</span></span>  
<span data-ttu-id="bb9ed-134">指定的程序包名称（/PACKAGENAME）无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-134">The specified package name (/PACKAGENAME) is not valid.</span></span>

<a href="" id="8192"></a><span data-ttu-id="bb9ed-135">8192</span><span class="sxs-lookup"><span data-stu-id="bb9ed-135">8192</span></span>  
<span data-ttu-id="bb9ed-136">指定的块大小（/BLOCKSIZE <em> ） </em> 无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-136">The specified block size (/BLOCKSIZE<em>)</em> is not valid.</span></span>

<a href="" id="16384"></a><span data-ttu-id="bb9ed-137">16384</span><span class="sxs-lookup"><span data-stu-id="bb9ed-137">16384</span></span>  
<span data-ttu-id="bb9ed-138">指定的压缩类型（/COMPRESSION）无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-138">The specified compression type (/COMPRESSION) is not valid.</span></span>

<a href="" id="32768"></a><span data-ttu-id="bb9ed-139">32768</span><span class="sxs-lookup"><span data-stu-id="bb9ed-139">32768</span></span>  
<span data-ttu-id="bb9ed-140">指定的项目路径无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-140">The specified project path is not valid.</span></span>

<a href="" id="65536"></a><span data-ttu-id="bb9ed-141">65536</span><span class="sxs-lookup"><span data-stu-id="bb9ed-141">65536</span></span>  
<span data-ttu-id="bb9ed-142">指定的升级参数无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-142">The specified upgrade parameter is not valid.</span></span>

<a href="" id="131072"></a><span data-ttu-id="bb9ed-143">131072</span><span class="sxs-lookup"><span data-stu-id="bb9ed-143">131072</span></span>  
<span data-ttu-id="bb9ed-144">指定的升级项目参数无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-144">The specified upgrade project parameter is not valid.</span></span>

<a href="" id="262144"></a><span data-ttu-id="bb9ed-145">262144</span><span class="sxs-lookup"><span data-stu-id="bb9ed-145">262144</span></span>  
<span data-ttu-id="bb9ed-146">指定的解码路径参数无效。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-146">The specified decode path parameter is not valid.</span></span>

<a href="" id="525288"></a><span data-ttu-id="bb9ed-147">525288</span><span class="sxs-lookup"><span data-stu-id="bb9ed-147">525288</span></span>  
<span data-ttu-id="bb9ed-148">未指定程序包名称。</span><span class="sxs-lookup"><span data-stu-id="bb9ed-148">The package name was not specified.</span></span>

## <span data-ttu-id="bb9ed-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="bb9ed-149">Related topics</span></span>


[<span data-ttu-id="bb9ed-150">关于使用 Sequencer 命令行</span><span class="sxs-lookup"><span data-stu-id="bb9ed-150">About Using the Sequencer Command Line</span></span>](about-using-the-sequencer-command-line.md)

[<span data-ttu-id="bb9ed-151">命令行参数</span><span class="sxs-lookup"><span data-stu-id="bb9ed-151">Command-Line Parameters</span></span>](command-line-parameters.md)

 

 





