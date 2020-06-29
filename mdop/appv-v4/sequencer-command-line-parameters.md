---
title: Sequencer 命令行参数
description: Sequencer 命令行参数
author: dansimp
ms.assetid: 28fb875a-c302-4d95-b2e0-8dc0c5dbb0f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ecfa269de04cf3dcba30cbb4a40f9176f03f6571
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798794"
---
# <span data-ttu-id="27a92-103">Sequencer 命令行参数</span><span class="sxs-lookup"><span data-stu-id="27a92-103">Sequencer Command-Line Parameters</span></span>


<span data-ttu-id="27a92-104">你可以使用以下应用程序虚拟化（App-v） Sequencer 参数对应用程序进行排序，并使用命令行升级现有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="27a92-104">You can use the following Application Virtualization (App-V) Sequencer parameters to sequence an application and to upgrade an existing virtual application by using a command line.</span></span> <span data-ttu-id="27a92-105">有关使用命令行对应用程序进行排序的详细信息，请参阅[如何使用命令行对新应用程序](how-to-sequence-a-new-application-by-using-the-command-line.md)进行排序。</span><span class="sxs-lookup"><span data-stu-id="27a92-105">For more information about sequencing an application by using a command line, see [How to Sequence a New Application by Using the Command Line](how-to-sequence-a-new-application-by-using-the-command-line.md).</span></span>

## <span data-ttu-id="27a92-106">Sequencer 命令行参数</span><span class="sxs-lookup"><span data-stu-id="27a92-106">Sequencer Command-Line Parameters</span></span>


<a href="" id="-help-or---"></a>**<span data-ttu-id="27a92-107">/HELP 还是/？</span><span class="sxs-lookup"><span data-stu-id="27a92-107">/HELP or /?</span></span>**  
<span data-ttu-id="27a92-108">显示有关可使用命令行序列化应用程序的参数的信息。</span><span class="sxs-lookup"><span data-stu-id="27a92-108">Displays information about parameters that are available for using a command line to sequence applications.</span></span>

<a href="" id="-installpackage-or--i"></a>**<span data-ttu-id="27a92-109">/INSTALLPACKAGE 或/I</span><span class="sxs-lookup"><span data-stu-id="27a92-109">/INSTALLPACKAGE or /I</span></span>**  
<span data-ttu-id="27a92-110">指定将用于安装应用程序的 Windows 安装程序或批处理文件，以便可以对其进行排序。</span><span class="sxs-lookup"><span data-stu-id="27a92-110">Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</span></span>

<a href="" id="-installpath-or--p"></a>**<span data-ttu-id="27a92-111">/INSTALLPATH 或/P</span><span class="sxs-lookup"><span data-stu-id="27a92-111">/INSTALLPATH or /P</span></span>**  
<span data-ttu-id="27a92-112">指定应用程序的程序包根目录。</span><span class="sxs-lookup"><span data-stu-id="27a92-112">Specifies the package root directory for an application.</span></span>

<a href="" id="-outputfile-or--o"></a>**<span data-ttu-id="27a92-113">/OUTPUTFILE 或/O</span><span class="sxs-lookup"><span data-stu-id="27a92-113">/OUTPUTFILE or /O</span></span>**  
<span data-ttu-id="27a92-114">指定将生成的 SPRJ 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="27a92-114">Specifies the path and file name of the SPRJ file that will be generated.</span></span>

<a href="" id="-fullload-or--f"></a>**<span data-ttu-id="27a92-115">/FULLLOAD 或/F</span><span class="sxs-lookup"><span data-stu-id="27a92-115">/FULLLOAD or /F</span></span>**  
<span data-ttu-id="27a92-116">指定是否将所有文件包含在主要功能块中。</span><span class="sxs-lookup"><span data-stu-id="27a92-116">Specifies whether all files will be contained in the primary feature block.</span></span> <span data-ttu-id="27a92-117">如果在命令行上指定了 **/FULLLOAD**参数，则所有关联的应用程序数据都将添加到主功能块。</span><span class="sxs-lookup"><span data-stu-id="27a92-117">If the **/FULLLOAD** parameter is specified on the command line, all of the associated application data is added to primary feature block.</span></span> <span data-ttu-id="27a92-118">如果未在命令行上指定 **/FULLLOAD**参数，则不会将任何关联的应用程序数据添加到主功能块。</span><span class="sxs-lookup"><span data-stu-id="27a92-118">If the **/FULLLOAD** parameter is not specified on the command line, then none of the associated application data is added to the primary feature block.</span></span>

<a href="" id="-packagename-or--k"></a>**<span data-ttu-id="27a92-119">/PACKAGENAME 或/K</span><span class="sxs-lookup"><span data-stu-id="27a92-119">/PACKAGENAME or /K</span></span>**  
<span data-ttu-id="27a92-120">指定将分配给序列化应用程序的程序包名称。</span><span class="sxs-lookup"><span data-stu-id="27a92-120">Specifies the package name that will be assigned to the sequenced application.</span></span>

<a href="" id="-blocksize"></a>**<span data-ttu-id="27a92-121">/BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="27a92-121">/BLOCKSIZE</span></span>**  
<span data-ttu-id="27a92-122">指定将用于将程序包流式传输到客户端计算机的 SFT 文件块大小。</span><span class="sxs-lookup"><span data-stu-id="27a92-122">Specifies the SFT file block size that will be used to stream the package to client computers.</span></span> <span data-ttu-id="27a92-123">你可以选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="27a92-123">You can select one of the following values:</span></span>

-   <span data-ttu-id="27a92-124">4 KB</span><span class="sxs-lookup"><span data-stu-id="27a92-124">4 KB</span></span>

-   <span data-ttu-id="27a92-125">16 KB</span><span class="sxs-lookup"><span data-stu-id="27a92-125">16 KB</span></span>

-   <span data-ttu-id="27a92-126">32 KB</span><span class="sxs-lookup"><span data-stu-id="27a92-126">32 KB</span></span>

-   <span data-ttu-id="27a92-127">64 KB</span><span class="sxs-lookup"><span data-stu-id="27a92-127">64 KB</span></span>

<span data-ttu-id="27a92-128">指定块大小时，应考虑 SFT 文件的大小。</span><span class="sxs-lookup"><span data-stu-id="27a92-128">You should consider the size of the SFT file when you specify the block size.</span></span> <span data-ttu-id="27a92-129">块大小较小的文件需要花费较长时间才能通过网络传输，但占用带宽较少。</span><span class="sxs-lookup"><span data-stu-id="27a92-129">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="27a92-130">块大小较大的文件使用更多网络带宽。</span><span class="sxs-lookup"><span data-stu-id="27a92-130">Files with larger block sizes use more network bandwidth.</span></span>

<a href="" id="-compression"></a>**<span data-ttu-id="27a92-131">/COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="27a92-131">/COMPRESSION</span></span>**  
<span data-ttu-id="27a92-132">指定用于压缩将流入到客户端的 SFT 文件的方法。</span><span class="sxs-lookup"><span data-stu-id="27a92-132">Specifies the method for compressing the SFT file that will be streamed to the client.</span></span>

<a href="" id="-msi-or--m"></a>**<span data-ttu-id="27a92-133">/MSI 或/M</span><span class="sxs-lookup"><span data-stu-id="27a92-133">/MSI or /M</span></span>**  
<span data-ttu-id="27a92-134">指定是否应创建序列化应用程序的 Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="27a92-134">Specifies whether a Windows Installer for the sequenced application should be created.</span></span>

<a href="" id="-default"></a>**<span data-ttu-id="27a92-135">/DEFAULT</span><span class="sxs-lookup"><span data-stu-id="27a92-135">/DEFAULT</span></span>**  
<span data-ttu-id="27a92-136">指定创建虚拟应用程序包时将使用的默认 SPRJ 文件。</span><span class="sxs-lookup"><span data-stu-id="27a92-136">Specifies the default SPRJ file that will be used when creating a virtual application package.</span></span> <span data-ttu-id="27a92-137">当第一次对应用程序进行排序时，此文件用作 sprj 模板。</span><span class="sxs-lookup"><span data-stu-id="27a92-137">This file is used as the .sprj template when the application is sequenced for the first time.</span></span>

<a href="" id="-upgrade"></a>**<span data-ttu-id="27a92-138">/UPGRADE</span><span class="sxs-lookup"><span data-stu-id="27a92-138">/UPGRADE</span></span>**  
<span data-ttu-id="27a92-139">指定将升级的 SPRJ 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="27a92-139">Specifies the path and file name of the SPRJ file that will be upgraded.</span></span>

<a href="" id="-decodepath"></a>**<span data-ttu-id="27a92-140">/DECODEPATH</span><span class="sxs-lookup"><span data-stu-id="27a92-140">/DECODEPATH</span></span>**  
<span data-ttu-id="27a92-141">指定排序计算机上安装了与序列化应用程序包相关联的文件的目录。</span><span class="sxs-lookup"><span data-stu-id="27a92-141">Specifies the directory on the sequencing computer where the files associated with the sequenced application package are installed.</span></span> <span data-ttu-id="27a92-142">指定目录时，请使用以下格式之一：</span><span class="sxs-lookup"><span data-stu-id="27a92-142">Use one of the following formats when specifying the directory:</span></span>

-   <span data-ttu-id="27a92-143">/decodepath：问：</span><span class="sxs-lookup"><span data-stu-id="27a92-143">/decodepath:Q:</span></span>

-   <span data-ttu-id="27a92-144">/decodepath:Q:.</span><span class="sxs-lookup"><span data-stu-id="27a92-144">/decodepath:Q:.</span></span>

-   <span data-ttu-id="27a92-145">/decodepath:"Q:."</span><span class="sxs-lookup"><span data-stu-id="27a92-145">/decodepath:”Q:.”</span></span>

-   <span data-ttu-id="27a92-146">/decodepath： "Q："</span><span class="sxs-lookup"><span data-stu-id="27a92-146">/decodepath:”Q:”</span></span>

## <span data-ttu-id="27a92-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="27a92-147">Related topics</span></span>


[<span data-ttu-id="27a92-148">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="27a92-148">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

[<span data-ttu-id="27a92-149">Sequencer 命令行错误代码</span><span class="sxs-lookup"><span data-stu-id="27a92-149">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

 

 





