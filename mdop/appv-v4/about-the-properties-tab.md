---
title: 关于“属性”选项卡
description: 关于“属性”选项卡
author: dansimp
ms.assetid: a6cf6f51-3778-4c8d-9632-3af4005775d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b2d6c3e01dde48fdd6701984f66610ea0333b74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802411"
---
# <span data-ttu-id="59875-103">关于“属性”选项卡</span><span class="sxs-lookup"><span data-stu-id="59875-103">About the Properties Tab</span></span>


<span data-ttu-id="59875-104">使用 "**属性**" 选项卡查看有关序列化应用程序包的基本统计信息。</span><span class="sxs-lookup"><span data-stu-id="59875-104">Use the **Properties** tab to view basic statistical information about a sequenced application package.</span></span> <span data-ttu-id="59875-105">除非另有说明，否则将自动生成信息。</span><span class="sxs-lookup"><span data-stu-id="59875-105">The information is automatically generated unless otherwise noted.</span></span> <span data-ttu-id="59875-106">此选项卡包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="59875-106">This tab contains the following elements.</span></span>

## <span data-ttu-id="59875-107">程序包信息</span><span class="sxs-lookup"><span data-stu-id="59875-107">Package Information</span></span>


<a href="" id="package-name"></a>**<span data-ttu-id="59875-108">程序包名称</span><span class="sxs-lookup"><span data-stu-id="59875-108">Package Name</span></span>**  
<span data-ttu-id="59875-109">用于可能包含一个或多个应用程序的序列化应用程序包的单个名称，例如，Microsoft Office 可以用于标记序列化应用程序包，其中包含在同一虚拟环境中运行的 Microsoft Word 和 Microsoft Excel 应用程序。</span><span class="sxs-lookup"><span data-stu-id="59875-109">The single name used for a sequenced application package that might contain one or more applications—for example, Microsoft Office could be used to label a sequenced application package that contains Microsoft Word and Microsoft Excel applications that run in the same virtual environment.</span></span>

<a href="" id="comments"></a>**<span data-ttu-id="59875-110">备注</span><span class="sxs-lookup"><span data-stu-id="59875-110">Comments</span></span>**  
<span data-ttu-id="59875-111">显示将在开放软件描述符（OSD）文件摘要元素中显示的软件包的简短说明。</span><span class="sxs-lookup"><span data-stu-id="59875-111">Displays a short description of the software package that will appear in the Open Software Descriptor (OSD) file ABSTRACT element.</span></span> <span data-ttu-id="59875-112">此项目是可选的。</span><span class="sxs-lookup"><span data-stu-id="59875-112">This item is optional.</span></span>

<a href="" id="package-version"></a>**<span data-ttu-id="59875-113">程序包版本</span><span class="sxs-lookup"><span data-stu-id="59875-113">Package Version</span></span>**  
<span data-ttu-id="59875-114">序列化应用程序包版本。</span><span class="sxs-lookup"><span data-stu-id="59875-114">The sequenced application package version.</span></span>

<a href="" id="package-guid"></a>**<span data-ttu-id="59875-115">程序包 GUID</span><span class="sxs-lookup"><span data-stu-id="59875-115">Package GUID</span></span>**  
<span data-ttu-id="59875-116">自动分配给顺序应用程序包的全局唯一标识符（GUID）将其与可能在序列化应用程序包流入的计算机上运行的其他序列化应用程序包区分开。</span><span class="sxs-lookup"><span data-stu-id="59875-116">The globally unique identifier (GUID) automatically assigned to the sequenced application package to distinguish it from other sequenced application packages that might be running on the computer to which a sequenced application package is streamed.</span></span>

<a href="" id="package-version-guid"></a>**<span data-ttu-id="59875-117">程序包版本 GUID</span><span class="sxs-lookup"><span data-stu-id="59875-117">Package Version GUID</span></span>**  
<span data-ttu-id="59875-118">序列化应用程序包版本 GUID。</span><span class="sxs-lookup"><span data-stu-id="59875-118">The sequenced application package version GUID.</span></span>

<a href="" id="root-directory"></a>**<span data-ttu-id="59875-119">根目录</span><span class="sxs-lookup"><span data-stu-id="59875-119">Root Directory</span></span>**  
<span data-ttu-id="59875-120">排序计算机上安装了序列化应用程序包的文件的目录。</span><span class="sxs-lookup"><span data-stu-id="59875-120">The directory on the sequencing computer in which files for the sequenced application package are installed.</span></span> <span data-ttu-id="59875-121">还会在将对序列化应用程序包进行流式处理的计算机上创建此目录。</span><span class="sxs-lookup"><span data-stu-id="59875-121">This directory is also created on the computer to which a sequenced application package will be streamed.</span></span> <span data-ttu-id="59875-122">建议向后兼容，这是 Q 驱动器根目录下的8.3 格式目录名称，例如 Q:\\MyApp.1\\。</span><span class="sxs-lookup"><span data-stu-id="59875-122">It is recommended for backwards compatibility that this be an 8.3 format directory name at the root of the Q drive, such as Q:\\MyApp.1\\.</span></span>

<a href="" id="created"></a>**<span data-ttu-id="59875-123">已创建</span><span class="sxs-lookup"><span data-stu-id="59875-123">Created</span></span>**  
<span data-ttu-id="59875-124">已排序的应用程序包的创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="59875-124">The date and time the sequenced application package was created.</span></span>

<a href="" id="modified"></a>**<span data-ttu-id="59875-125">修改日期</span><span class="sxs-lookup"><span data-stu-id="59875-125">Modified</span></span>**  
<span data-ttu-id="59875-126">已排序的应用程序包的上次修改日期和时间。</span><span class="sxs-lookup"><span data-stu-id="59875-126">The date and time the sequenced application package was last modified.</span></span>

<a href="" id="package-size"></a>**<span data-ttu-id="59875-127">程序包大小</span><span class="sxs-lookup"><span data-stu-id="59875-127">Package Size</span></span>**  
<span data-ttu-id="59875-128">程序包的大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="59875-128">The size of the package in megabytes.</span></span>

<a href="" id="launch-size"></a>**<span data-ttu-id="59875-129">启动大小</span><span class="sxs-lookup"><span data-stu-id="59875-129">Launch Size</span></span>**  
<span data-ttu-id="59875-130">启动应用程序所需的 SFT 文件部分的大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="59875-130">The size in megabytes of the portion of the SFT file that is required to start the application.</span></span>

## <span data-ttu-id="59875-131">排序参数</span><span class="sxs-lookup"><span data-stu-id="59875-131">Sequencing Parameters</span></span>


<a href="" id="block-size"></a>**<span data-ttu-id="59875-132">块大小</span><span class="sxs-lookup"><span data-stu-id="59875-132">Block Size</span></span>**  
<span data-ttu-id="59875-133">指定为跨网络传输 SFT 文件的主要和辅助功能块的大小。</span><span class="sxs-lookup"><span data-stu-id="59875-133">Specifies the size of the primary and secondary feature blocks into which the SFT file is divided for streaming across a network.</span></span> <span data-ttu-id="59875-134">所有块都等于指定的大小;但是，最后一个块可能小于指定的大小。</span><span class="sxs-lookup"><span data-stu-id="59875-134">All blocks equal the specified size; however, the last block might be smaller than specified.</span></span> <span data-ttu-id="59875-135">你将看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="59875-135">You will see one of the following values:</span></span>

-   <span data-ttu-id="59875-136">4 KB</span><span class="sxs-lookup"><span data-stu-id="59875-136">4 KB</span></span>

-   <span data-ttu-id="59875-137">16 KB</span><span class="sxs-lookup"><span data-stu-id="59875-137">16 KB</span></span>

-   <span data-ttu-id="59875-138">32 KB</span><span class="sxs-lookup"><span data-stu-id="59875-138">32 KB</span></span>

-   <span data-ttu-id="59875-139">64 KB</span><span class="sxs-lookup"><span data-stu-id="59875-139">64 KB</span></span>

<span data-ttu-id="59875-140">**注意** 创建初始程序包后，"块大小" 值不可更改。</span><span class="sxs-lookup"><span data-stu-id="59875-140">**Note** After the initial package has been created, the block size value is not changeable.</span></span>

 

## <span data-ttu-id="59875-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="59875-141">Related topics</span></span>


[<span data-ttu-id="59875-142">如何更改程序包属性</span><span class="sxs-lookup"><span data-stu-id="59875-142">How to Change Package Properties</span></span>](how-to-change-package-properties.md)

[<span data-ttu-id="59875-143">Sequencer 控制台</span><span class="sxs-lookup"><span data-stu-id="59875-143">Sequencer Console</span></span>](sequencer-console.md)

 

 





