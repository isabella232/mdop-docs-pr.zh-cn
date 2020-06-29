---
title: App-V Application WMI 类
description: App-V Application WMI 类
author: dansimp
ms.assetid: b79b0d5a-ba57-442f-8bb4-d7154fc056f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a4e1e49e35b231ddb2a480a06c46e364121ac2d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803145"
---
# <span data-ttu-id="d45e5-103">App-V Application WMI 类</span><span class="sxs-lookup"><span data-stu-id="d45e5-103">App-V Application WMI Class</span></span>


<span data-ttu-id="d45e5-104">在应用程序虚拟化（App-v）客户端中，**应用程序**类是一个 Windows 管理规范（WMI）类，用于表示客户端上的所有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="d45e5-104">In the Application Virtualization (App-V) Client, the **Application** class is a Windows Management Instrumentation (WMI) class that represents all the virtual applications on the client.</span></span>

<span data-ttu-id="d45e5-105">从托管对象格式（MOF）代码简化了以下语法。</span><span class="sxs-lookup"><span data-stu-id="d45e5-105">The following syntax is simplified from Managed Object Format (MOF) code.</span></span> <span data-ttu-id="d45e5-106">该代码包含所有继承的属性。</span><span class="sxs-lookup"><span data-stu-id="d45e5-106">The code includes all the inherited properties.</span></span>

## <span data-ttu-id="d45e5-107">语法</span><span class="sxs-lookup"><span data-stu-id="d45e5-107">Syntax</span></span>


``` syntax
class Application
{
      string Name;
      string Version;
      string PackageGUID;
      datetime LastLaunchOnSystem;
      uint32 GlobalRunningCount;
      boolean Loading;
      string OriginalOsdPath;
      string CachedOsdPath;
};
```

## <span data-ttu-id="d45e5-108">要求</span><span class="sxs-lookup"><span data-stu-id="d45e5-108">Requirements</span></span>


## <span data-ttu-id="d45e5-109">属性</span><span class="sxs-lookup"><span data-stu-id="d45e5-109">Properties</span></span>


<a href="" id="name"></a>**<span data-ttu-id="d45e5-110">名称</span><span class="sxs-lookup"><span data-stu-id="d45e5-110">Name</span></span>**  
<span data-ttu-id="d45e5-111">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d45e5-111">Data type: **String**</span></span>

<span data-ttu-id="d45e5-112">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-112">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-113">限定符： Key</span><span class="sxs-lookup"><span data-stu-id="d45e5-113">Qualifiers: Key</span></span>

<span data-ttu-id="d45e5-114">虚拟应用程序的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d45e5-114">The display name of the virtual application.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="d45e5-115">版本</span><span class="sxs-lookup"><span data-stu-id="d45e5-115">Version</span></span>**  
<span data-ttu-id="d45e5-116">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d45e5-116">Data type: **String**</span></span>

<span data-ttu-id="d45e5-117">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-117">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-118">限定符： Key</span><span class="sxs-lookup"><span data-stu-id="d45e5-118">Qualifiers: Key</span></span>

<span data-ttu-id="d45e5-119">虚拟应用程序的版本。</span><span class="sxs-lookup"><span data-stu-id="d45e5-119">The version of the virtual application.</span></span>

<a href="" id="packageguid"></a>**<span data-ttu-id="d45e5-120">PackageGUID</span><span class="sxs-lookup"><span data-stu-id="d45e5-120">PackageGUID</span></span>**  
<span data-ttu-id="d45e5-121">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d45e5-121">Data type: **String**</span></span>

<span data-ttu-id="d45e5-122">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-122">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-123">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d45e5-123">Qualifiers: None</span></span>

<span data-ttu-id="d45e5-124">与虚拟应用程序关联的程序包的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d45e5-124">The GUID of the package that the virtual application is associated with.</span></span>

<a href="" id="lastlaunchonsystem"></a>**<span data-ttu-id="d45e5-125">LastLaunchOnSystem</span><span class="sxs-lookup"><span data-stu-id="d45e5-125">LastLaunchOnSystem</span></span>**  
<span data-ttu-id="d45e5-126">数据类型： **DateTime**</span><span class="sxs-lookup"><span data-stu-id="d45e5-126">Data type: **DateTime**</span></span>

<span data-ttu-id="d45e5-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-127">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-128">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d45e5-128">Qualifiers: None</span></span>

<span data-ttu-id="d45e5-129">虚拟应用程序启动的最后日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d45e5-129">The last date and time that the virtual application was launched.</span></span>

<a href="" id="globalrunningcount"></a>**<span data-ttu-id="d45e5-130">GlobalRunningCount</span><span class="sxs-lookup"><span data-stu-id="d45e5-130">GlobalRunningCount</span></span>**  
<span data-ttu-id="d45e5-131">数据类型： **UInt32**</span><span class="sxs-lookup"><span data-stu-id="d45e5-131">Data type: **UInt32**</span></span>

<span data-ttu-id="d45e5-132">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-132">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-133">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d45e5-133">Qualifiers: None</span></span>

<span data-ttu-id="d45e5-134">直接启动的虚拟应用程序的运行实例的计数。</span><span class="sxs-lookup"><span data-stu-id="d45e5-134">A count of the running instances of the virtual application that were started directly.</span></span>

<a href="" id="loading"></a>**<span data-ttu-id="d45e5-135">正在加载</span><span class="sxs-lookup"><span data-stu-id="d45e5-135">Loading</span></span>**  
<span data-ttu-id="d45e5-136">数据类型：**布尔型**</span><span class="sxs-lookup"><span data-stu-id="d45e5-136">Data type: **Boolean**</span></span>

<span data-ttu-id="d45e5-137">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-137">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-138">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d45e5-138">Qualifiers: None</span></span>

<span data-ttu-id="d45e5-139">如果正在启动虚拟应用程序，**则为 true** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="d45e5-139">**true** if the virtual application is being started; otherwise **false**.</span></span>

<a href="" id="originalosdpath"></a>**<span data-ttu-id="d45e5-140">OriginalOsdPath</span><span class="sxs-lookup"><span data-stu-id="d45e5-140">OriginalOsdPath</span></span>**  
<span data-ttu-id="d45e5-141">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d45e5-141">Data type: **String**</span></span>

<span data-ttu-id="d45e5-142">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-142">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-143">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d45e5-143">Qualifiers: None</span></span>

<span data-ttu-id="d45e5-144">在 App-v 客户端注册的 OSD 文件的原始文件路径。</span><span class="sxs-lookup"><span data-stu-id="d45e5-144">The original file path of the OSD file that was registered with the App-V Client.</span></span>

<a href="" id="cachedosdpath"></a>**<span data-ttu-id="d45e5-145">CachedOsdPath</span><span class="sxs-lookup"><span data-stu-id="d45e5-145">CachedOsdPath</span></span>**  
<span data-ttu-id="d45e5-146">数据类型：**字符串**</span><span class="sxs-lookup"><span data-stu-id="d45e5-146">Data type: **String**</span></span>

<span data-ttu-id="d45e5-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d45e5-147">Access type: Read-only</span></span>

<span data-ttu-id="d45e5-148">限定符：无</span><span class="sxs-lookup"><span data-stu-id="d45e5-148">Qualifiers: None</span></span>

<span data-ttu-id="d45e5-149">如果 App-v 客户端已在本地缓存 OSD 文件，则该 OSD 文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="d45e5-149">The file path of the OSD file if the App-V Client has cached the OSD file locally.</span></span>

 

 





