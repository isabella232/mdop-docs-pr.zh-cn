---
title: App-V Package WMI 类
description: App-V Package WMI 类
author: dansimp
ms.assetid: 0fc26c3b-9706-4804-be2d-645771dc33ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa452afaaeb2f490c179a928b24de47207d6dc63
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802360"
---
# <span data-ttu-id="d7a47-103">App-V Package WMI 类</span><span class="sxs-lookup"><span data-stu-id="d7a47-103">App-V Package WMI Class</span></span>


<span data-ttu-id="d7a47-104">在应用程序虚拟化（App-v）客户端中，**程序包**类是一个 Windows 管理规范（WMI）类，用于表示客户端上的所有虚拟程序包。</span><span class="sxs-lookup"><span data-stu-id="d7a47-104">In the Application Virtualization (App-V) Client, the **Package** class is a Windows Management Instrumentation (WMI) class that represents all the virtual packages on the client.</span></span> <span data-ttu-id="d7a47-105">虚拟程序包可以包含许多虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7a47-105">The virtual packages can contain many virtual applications.</span></span>

## <span data-ttu-id="d7a47-106">语法</span><span class="sxs-lookup"><span data-stu-id="d7a47-106">Syntax</span></span>


``` syntax
class Package
{
      string Name;
      string Version;
      string PackageGUID;
      string SftPath;
      uint64 TotalSize;
      uint64 CachedSize;
      uint64 LaunchSize;
      uint64 CachedLaunchSize;
      boolean InUse;
      boolean Locked;
      uint16 CachedPercentage;
      string VersionGUID;
 };
```

## <span data-ttu-id="d7a47-107">属性</span><span class="sxs-lookup"><span data-stu-id="d7a47-107">Properties</span></span>


<a href="" id="name"></a>**<span data-ttu-id="d7a47-108">名称</span><span class="sxs-lookup"><span data-stu-id="d7a47-108">Name</span></span>**  
<span data-ttu-id="d7a47-109">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d7a47-109">Data type: **String**</span></span>

<span data-ttu-id="d7a47-110">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-110">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-111">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-111">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-112">虚拟程序包的用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="d7a47-112">The user-friendly name of the virtual package.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="d7a47-113">版本</span><span class="sxs-lookup"><span data-stu-id="d7a47-113">Version</span></span>**  
<span data-ttu-id="d7a47-114">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d7a47-114">Data type: **String**</span></span>

<span data-ttu-id="d7a47-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-115">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-116">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-116">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-117">虚拟包的版本。</span><span class="sxs-lookup"><span data-stu-id="d7a47-117">The version of the virtual package.</span></span>

<a href="" id="packageguid"></a>**<span data-ttu-id="d7a47-118">PackageGUID</span><span class="sxs-lookup"><span data-stu-id="d7a47-118">PackageGUID</span></span>**  
<span data-ttu-id="d7a47-119">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d7a47-119">Data type: **String**</span></span>

<span data-ttu-id="d7a47-120">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-120">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-121">限定符： Key</span><span class="sxs-lookup"><span data-stu-id="d7a47-121">Qualifiers: Key</span></span>

<span data-ttu-id="d7a47-122">程序包配置和源文件的 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="d7a47-122">The GUID identifier of the package configuration and source files.</span></span>

<a href="" id="sftpath"></a>**<span data-ttu-id="d7a47-123">SftPath</span><span class="sxs-lookup"><span data-stu-id="d7a47-123">SftPath</span></span>**  
<span data-ttu-id="d7a47-124">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d7a47-124">Data type: **String**</span></span>

<span data-ttu-id="d7a47-125">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-125">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-126">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-126">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-127">SFT 文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="d7a47-127">The file path of the SFT file.</span></span>

<a href="" id="totalsize"></a>**<span data-ttu-id="d7a47-128">TotalSize</span><span class="sxs-lookup"><span data-stu-id="d7a47-128">TotalSize</span></span>**  
<span data-ttu-id="d7a47-129">数据类型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="d7a47-129">Data type: **UInt64**</span></span>

<span data-ttu-id="d7a47-130">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-130">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-131">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-131">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-132">虚拟包的总大小（以 kb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d7a47-132">The total size of the virtual package, in kilobytes.</span></span>

<a href="" id="cachedsize"></a>**<span data-ttu-id="d7a47-133">CachedSize</span><span class="sxs-lookup"><span data-stu-id="d7a47-133">CachedSize</span></span>**  
<span data-ttu-id="d7a47-134">数据类型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="d7a47-134">Data type: **UInt64**</span></span>

<span data-ttu-id="d7a47-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-135">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-136">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-136">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-137">虚拟包的缓存的总大小（以 kb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d7a47-137">The total size of the cache for the virtual package, in kilobytes.</span></span>

<a href="" id="launchsize"></a>**<span data-ttu-id="d7a47-138">LaunchSize</span><span class="sxs-lookup"><span data-stu-id="d7a47-138">LaunchSize</span></span>**  
<span data-ttu-id="d7a47-139">数据类型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="d7a47-139">Data type: **UInt64**</span></span>

<span data-ttu-id="d7a47-140">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-140">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-141">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-141">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-142">虚拟包的主功能块的总大小（以 kb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d7a47-142">The total size of the virtual package’s primary feature block, in kilobytes.</span></span>

<a href="" id="cachedlaunchsize"></a>**<span data-ttu-id="d7a47-143">CachedLaunchSize</span><span class="sxs-lookup"><span data-stu-id="d7a47-143">CachedLaunchSize</span></span>**  
<span data-ttu-id="d7a47-144">数据类型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="d7a47-144">Data type: **UInt64**</span></span>

<span data-ttu-id="d7a47-145">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-145">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-146">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-146">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-147">已缓存的虚拟程序包主功能块的总大小（以 kb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d7a47-147">Total size of the virtual package’s primary feature block that has been cached, in kilobytes.</span></span>

<a href="" id="inuse"></a>**<span data-ttu-id="d7a47-148">InUse</span><span class="sxs-lookup"><span data-stu-id="d7a47-148">InUse</span></span>**  
<span data-ttu-id="d7a47-149">数据类型：**布尔型**</span><span class="sxs-lookup"><span data-stu-id="d7a47-149">Data type: **Boolean**</span></span>

<span data-ttu-id="d7a47-150">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-150">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-151">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-151">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-152">如果虚拟程序包中的任何虚拟应用程序正在运行，**则为 true** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="d7a47-152">**true** if any virtual application in the virtual package is running; otherwise **false**.</span></span>

<a href="" id="locked"></a>**<span data-ttu-id="d7a47-153">已锁定</span><span class="sxs-lookup"><span data-stu-id="d7a47-153">Locked</span></span>**  
<span data-ttu-id="d7a47-154">数据类型：**布尔型**</span><span class="sxs-lookup"><span data-stu-id="d7a47-154">Data type: **Boolean**</span></span>

<span data-ttu-id="d7a47-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-155">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-156">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-156">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-157">如果虚拟包已锁定，**则为 true** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="d7a47-157">**true** if the virtual package is locked; otherwise **false**.</span></span>

<a href="" id="cachedpercentage"></a>**<span data-ttu-id="d7a47-158">CachedPercentage</span><span class="sxs-lookup"><span data-stu-id="d7a47-158">CachedPercentage</span></span>**  
<span data-ttu-id="d7a47-159">数据类型： **UInt16**</span><span class="sxs-lookup"><span data-stu-id="d7a47-159">Data type: **UInt16**</span></span>

<span data-ttu-id="d7a47-160">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-160">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-161">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-161">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-162">缓存文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="d7a47-162">The percentage of the cache files.</span></span> <span data-ttu-id="d7a47-163">基于以下公式： CachedSize/TotalSize ×100。</span><span class="sxs-lookup"><span data-stu-id="d7a47-163">Based on the following formula: CachedSize / TotalSize × 100.</span></span>

<a href="" id="versionguid"></a>**<span data-ttu-id="d7a47-164">VersionGUID</span><span class="sxs-lookup"><span data-stu-id="d7a47-164">VersionGUID</span></span>**  
<span data-ttu-id="d7a47-165">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d7a47-165">Data type: **String**</span></span>

<span data-ttu-id="d7a47-166">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d7a47-166">Access type: Read-only</span></span>

<span data-ttu-id="d7a47-167">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d7a47-167">Qualifiers: None</span></span>

<span data-ttu-id="d7a47-168">程序包版本的 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="d7a47-168">The GUID identifier of the package version.</span></span>

 

 





