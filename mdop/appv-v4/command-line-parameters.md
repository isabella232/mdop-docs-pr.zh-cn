---
title: 命令行参数
description: 命令行参数
author: dansimp
ms.assetid: d90a0591-f1ce-4cb8-b244-85cc70461922
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31d6ca1215648e2519e9818817ab5cc779a746d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802203"
---
# <span data-ttu-id="41890-103">命令行参数</span><span class="sxs-lookup"><span data-stu-id="41890-103">Command-Line Parameters</span></span>


<span data-ttu-id="41890-104">使用以下应用程序虚拟化 Sequencer 参数对应用程序进行排序，并在命令提示符处升级顺序应用程序包。</span><span class="sxs-lookup"><span data-stu-id="41890-104">Use the following Application Virtualization Sequencer parameters to sequence an application and to upgrade a sequenced application package at the command prompt.</span></span> <span data-ttu-id="41890-105">在 Microsoft Application Virtualization Sequencer 目录中，输入**SFTSequencer**，然后输入相应的参数。</span><span class="sxs-lookup"><span data-stu-id="41890-105">In the Microsoft Application Virtualization Sequencer directory, you would enter **SFTSequencer**, followed by the appropriate parameter.</span></span>

<a href="" id="-help-or---"></a><span data-ttu-id="41890-106">*/Help*还是 */？*</span><span class="sxs-lookup"><span data-stu-id="41890-106">*/HELP* or */?*</span></span>  
<span data-ttu-id="41890-107">用于显示可用于命令行序列化的参数列表。</span><span class="sxs-lookup"><span data-stu-id="41890-107">Use to display the list of parameters available for command-line sequencing.</span></span>

<a href="" id="-installpackage-or--i"></a><span data-ttu-id="41890-108">*/INSTALLPACKAGE*或 */i*</span><span class="sxs-lookup"><span data-stu-id="41890-108">*/INSTALLPACKAGE* or */I*</span></span>  
<span data-ttu-id="41890-109">用于指定要对其进行排序的应用程序或批处理文件。</span><span class="sxs-lookup"><span data-stu-id="41890-109">Use to specify the installer or a batch file for the application to be sequenced.</span></span>

<a href="" id="-installpath-or--p"></a><span data-ttu-id="41890-110">*/INSTALLPATH*或 */p*</span><span class="sxs-lookup"><span data-stu-id="41890-110">*/INSTALLPATH* or */P*</span></span>  
<span data-ttu-id="41890-111">用于指定程序包根目录。</span><span class="sxs-lookup"><span data-stu-id="41890-111">Use to specify the package root directory.</span></span>

<a href="" id="-outputfile-or--o"></a><span data-ttu-id="41890-112">*/Outputfile*或 */o*</span><span class="sxs-lookup"><span data-stu-id="41890-112">*/OUTPUTFILE* or */O*</span></span>  
<span data-ttu-id="41890-113">用于指定将生成的 SPRJ 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="41890-113">Use to specify the path and file name of the SPRJ file that will be generated.</span></span>

<span data-ttu-id="41890-114">**重要提示** 当打开不打算升级的程序包时， */outputfile*参数不可用。</span><span class="sxs-lookup"><span data-stu-id="41890-114">**Important** The */OUTPUTFILE* parameter is not available when opening a package that you do not intend to upgrade.</span></span>

 

<a href="" id="-fullload-or--f"></a><span data-ttu-id="41890-115">*/FULLLOAD*或 */f*</span><span class="sxs-lookup"><span data-stu-id="41890-115">*/FULLLOAD* or */F*</span></span>  
<span data-ttu-id="41890-116">用于指定是否将所有内容放在主功能块中。</span><span class="sxs-lookup"><span data-stu-id="41890-116">Use to specify whether to put everything in the primary feature block.</span></span>

<a href="" id="-packagename-or--k"></a><span data-ttu-id="41890-117">*/Packagename*或 */k*</span><span class="sxs-lookup"><span data-stu-id="41890-117">*/PACKAGENAME* or */K*</span></span>  
<span data-ttu-id="41890-118">用于指定序列化的应用程序的程序包名称。</span><span class="sxs-lookup"><span data-stu-id="41890-118">Use to specify the package name of the sequenced application.</span></span>

<a href="" id="-blocksize"></a>*<span data-ttu-id="41890-119">/BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="41890-119">/BLOCKSIZE</span></span>*  
<span data-ttu-id="41890-120">指定将用于将程序包流式传输到客户端计算机的 SFT 文件块大小。</span><span class="sxs-lookup"><span data-stu-id="41890-120">Specifies the SFT file block size that will be used to stream the package to client computers.</span></span> <span data-ttu-id="41890-121">你可以选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="41890-121">You can select one of the following values:</span></span>

-   <span data-ttu-id="41890-122">4 KB</span><span class="sxs-lookup"><span data-stu-id="41890-122">4 KB</span></span>

-   <span data-ttu-id="41890-123">16 KB</span><span class="sxs-lookup"><span data-stu-id="41890-123">16 KB</span></span>

-   <span data-ttu-id="41890-124">32 KB</span><span class="sxs-lookup"><span data-stu-id="41890-124">32 KB</span></span>

-   <span data-ttu-id="41890-125">64 KB</span><span class="sxs-lookup"><span data-stu-id="41890-125">64 KB</span></span>

<span data-ttu-id="41890-126">指定块大小时，应考虑 SFT 文件的大小。</span><span class="sxs-lookup"><span data-stu-id="41890-126">You should consider the size of the SFT file when you specify the block size.</span></span> <span data-ttu-id="41890-127">块大小较小的文件需要花费较长时间才能通过网络传输，但占用带宽较少。</span><span class="sxs-lookup"><span data-stu-id="41890-127">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="41890-128">块大小较大的文件使用更多网络带宽。</span><span class="sxs-lookup"><span data-stu-id="41890-128">Files with larger block sizes use more network bandwidth.</span></span>

<a href="" id="-compression"></a>*<span data-ttu-id="41890-129">/COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="41890-129">/COMPRESSION</span></span>*  
<span data-ttu-id="41890-130">用于指定在将 SFT 文件传输到客户端时对该文件进行压缩的方法。</span><span class="sxs-lookup"><span data-stu-id="41890-130">Use to specify the method for compressing the SFT file as it is streamed to the client.</span></span>

<a href="" id="-msi-or--m"></a><span data-ttu-id="41890-131">*/MSI*或 */m*</span><span class="sxs-lookup"><span data-stu-id="41890-131">*/MSI* or */M*</span></span>  
<span data-ttu-id="41890-132">用于为序列化的应用程序指定生成 Microsoft Windows Installer 程序包。</span><span class="sxs-lookup"><span data-stu-id="41890-132">Use to specify generating a Microsoft Windows Installer package for the sequenced application.</span></span>

<a href="" id="-default"></a>*<span data-ttu-id="41890-133">/DEFAULT</span><span class="sxs-lookup"><span data-stu-id="41890-133">/DEFAULT</span></span>*  
<span data-ttu-id="41890-134">指定创建虚拟应用程序包时将使用的默认 SPRJ 文件。</span><span class="sxs-lookup"><span data-stu-id="41890-134">Specifies the default SPRJ file that will be used when creating a virtual application package.</span></span> <span data-ttu-id="41890-135">当第一次对应用程序进行排序时，此文件用作 sprj 模板。</span><span class="sxs-lookup"><span data-stu-id="41890-135">This file is used as the .sprj template when the application is sequenced for the first time.</span></span>

<a href="" id="-upgrade"></a>*<span data-ttu-id="41890-136">/UPGRADE</span><span class="sxs-lookup"><span data-stu-id="41890-136">/UPGRADE</span></span>*  
<span data-ttu-id="41890-137">指定将升级的 SPRJ 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="41890-137">Specifies the path and file name of the SPRJ file that will be upgraded.</span></span>

<a href="" id="-decodepath"></a>*<span data-ttu-id="41890-138">/DECODEPATH</span><span class="sxs-lookup"><span data-stu-id="41890-138">/DECODEPATH</span></span>*  
<span data-ttu-id="41890-139">指定排序计算机上安装了与序列化应用程序包相关联的文件的目录。</span><span class="sxs-lookup"><span data-stu-id="41890-139">Specifies the directory on the sequencing computer where the files associated with the sequenced application package are installed.</span></span> <span data-ttu-id="41890-140">指定目录时，请使用以下格式之一：</span><span class="sxs-lookup"><span data-stu-id="41890-140">Use one of the following formats when specifying the directory:</span></span>

-   <span data-ttu-id="41890-141">/decodepath：问：</span><span class="sxs-lookup"><span data-stu-id="41890-141">/decodepath:Q:</span></span>

-   <span data-ttu-id="41890-142">/decodepath:Q:.</span><span class="sxs-lookup"><span data-stu-id="41890-142">/decodepath:Q:.</span></span>

-   <span data-ttu-id="41890-143">/decodepath:"Q:."</span><span class="sxs-lookup"><span data-stu-id="41890-143">/decodepath:”Q:.”</span></span>

-   <span data-ttu-id="41890-144">/decodepath： "Q："</span><span class="sxs-lookup"><span data-stu-id="41890-144">/decodepath:”Q:”</span></span>

## <span data-ttu-id="41890-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="41890-145">Related topics</span></span>


[<span data-ttu-id="41890-146">关于使用 Sequencer 命令行</span><span class="sxs-lookup"><span data-stu-id="41890-146">About Using the Sequencer Command Line</span></span>](about-using-the-sequencer-command-line.md)

[<span data-ttu-id="41890-147">如何使用命令行打开已排序的应用程序</span><span class="sxs-lookup"><span data-stu-id="41890-147">How to Open a Sequenced Application Using the Command Line</span></span>](how-to-open-a-sequenced-application-using-the-command-line.md)

[<span data-ttu-id="41890-148">如何使用“打开程序包”命令升级程序包</span><span class="sxs-lookup"><span data-stu-id="41890-148">How to Upgrade a Package Using the Open Package Command</span></span>](how-to-upgrade-a-package-using-the-open-package-command.md)

 

 





