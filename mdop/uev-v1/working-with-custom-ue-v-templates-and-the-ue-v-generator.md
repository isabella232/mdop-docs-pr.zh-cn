---
title: 使用自定义 UE-V 模板和 UE-V 生成器
description: 使用自定义 UE-V 模板和 UE-V 生成器
author: dansimp
ms.assetid: 7bb2583a-b032-4800-9bf9-eb33528e1d0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db5387254842bfdcf3898089bc12a8e929e3813a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803476"
---
# <span data-ttu-id="02fc6-103">使用自定义 UE-V 模板和 UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="02fc6-103">Working with Custom UE-V Templates and the UE-V Generator</span></span>


<span data-ttu-id="02fc6-104">为了在用户计算机之间漫游应用程序，Microsoft 用户体验虚拟化（UE-V）使用*设置位置模板*。</span><span class="sxs-lookup"><span data-stu-id="02fc6-104">In order to roam applications between user computers, Microsoft User Experience Virtualization (UE-V) uses *settings location templates*.</span></span> <span data-ttu-id="02fc6-105">某些设置位置模板包含在用户体验虚拟化中。</span><span class="sxs-lookup"><span data-stu-id="02fc6-105">Some settings location templates are included with User Experience Virtualization.</span></span> <span data-ttu-id="02fc6-106">你还可以通过 UE-V 生成器创建、编辑或验证自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="02fc6-106">You can also create, edit, or validate custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="02fc6-107">UE-V 生成器监视应用程序以发现和捕获应用程序存储其设置的位置。</span><span class="sxs-lookup"><span data-stu-id="02fc6-107">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="02fc6-108">正在监视的应用程序必须是传统应用程序。</span><span class="sxs-lookup"><span data-stu-id="02fc6-108">The application being monitored must be a traditional application.</span></span> <span data-ttu-id="02fc6-109">UE-V 生成器无法为以下应用程序类型创建设置位置模板：</span><span class="sxs-lookup"><span data-stu-id="02fc6-109">The UE-V Generator cannot create a settings location template for the following application types:</span></span>

-   <span data-ttu-id="02fc6-110">虚拟化应用程序</span><span class="sxs-lookup"><span data-stu-id="02fc6-110">Virtualized applications</span></span>

-   <span data-ttu-id="02fc6-111">通过终端服务提供的应用程序</span><span class="sxs-lookup"><span data-stu-id="02fc6-111">Application offered through terminal services</span></span>

-   <span data-ttu-id="02fc6-112">Java 应用程序</span><span class="sxs-lookup"><span data-stu-id="02fc6-112">Java applications</span></span>

-   <span data-ttu-id="02fc6-113">Windows 8 应用程序</span><span class="sxs-lookup"><span data-stu-id="02fc6-113">Windows 8 applications</span></span>

## <span data-ttu-id="02fc6-114">使用 UE-V 生成器创建 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="02fc6-114">Create UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="02fc6-115">如何使用 UE-V 生成器创建设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="02fc6-115">How to use the UE-V Generator to create settings location templates.</span></span>

[<span data-ttu-id="02fc6-116">使用 UE-V 生成器创建 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="02fc6-116">Create UE-V Settings Location Templates with the UE-V Generator</span></span>](create-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## <span data-ttu-id="02fc6-117">使用 UE-V 生成器编辑 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="02fc6-117">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="02fc6-118">如何使用 UE-V 生成器编辑设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="02fc6-118">How to use the UE-V Generator to edit settings location templates.</span></span>

[<span data-ttu-id="02fc6-119">使用 UE-V 生成器编辑 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="02fc6-119">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>](edit-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## <span data-ttu-id="02fc6-120">使用 UE-V 生成器验证 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="02fc6-120">Validate UE-V Settings Location Templates with UE-V Generator</span></span>


<span data-ttu-id="02fc6-121">如何使用 UE-V 生成器验证在 UE-V 生成器外部修改的设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="02fc6-121">How to use the UE-V Generator to validate settings location templates modified outside the UE-V Generator.</span></span>

[<span data-ttu-id="02fc6-122">使用 UE-V 生成器验证 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="02fc6-122">Validate UE-V Settings Location Templates with UE-V Generator</span></span>](validate-ue-v-settings-location-templates-with-ue-v-generator.md)

## <a href="" id="bkmk-standardnonstandardsettingslocations"></a><span data-ttu-id="02fc6-123">标准和非标准设置位置</span><span class="sxs-lookup"><span data-stu-id="02fc6-123">Standard and Nonstandard settings locations</span></span>


<span data-ttu-id="02fc6-124">UE-V 生成器可帮助你识别应用程序在何处查找应用程序用于存储设置信息的设置文件和注册表设置。</span><span class="sxs-lookup"><span data-stu-id="02fc6-124">The UE-V Generator helps you identify where applications look for settings files and registry settings that applications use to store settings information.</span></span> <span data-ttu-id="02fc6-125">你可以使用 UE-V 生成器作为发现过程的一部分打开应用程序，以捕获标准位置中的设置。</span><span class="sxs-lookup"><span data-stu-id="02fc6-125">You can use the UE-V Generator to open the application as part of the discovery process to capture settings in standard locations.</span></span> <span data-ttu-id="02fc6-126">标准位置包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="02fc6-126">Standard locations include the following:</span></span>

-   <span data-ttu-id="02fc6-127">**注册表设置**- **HKEY \ _CURRENT \ _USER**下的注册表位置</span><span class="sxs-lookup"><span data-stu-id="02fc6-127">**Registry Settings** – Registry locations under **HKEY\_CURRENT\_USER**</span></span>

-   <span data-ttu-id="02fc6-128">**应用程序设置文件**-存储在 \\**用户**\\ [用户名 \] \\ **AppData**  \\  **漫游**中的文件</span><span class="sxs-lookup"><span data-stu-id="02fc6-128">**Application Settings Files** – Files stored under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**</span></span>

<span data-ttu-id="02fc6-129">UE-V 发电机排除了通常存储应用软件文件的位置不会在用户计算机或环境之间很好地漫游。</span><span class="sxs-lookup"><span data-stu-id="02fc6-129">The UE-V Generator excludes locations which commonly store application software files do not roam well between user computers or environments.</span></span> <span data-ttu-id="02fc6-130">UE-V 生成器将排除这些位置。</span><span class="sxs-lookup"><span data-stu-id="02fc6-130">The UE-V Generator excludes these locations.</span></span> <span data-ttu-id="02fc6-131">排除的位置如下所示：</span><span class="sxs-lookup"><span data-stu-id="02fc6-131">Excluded locations are as follows:</span></span>

-   <span data-ttu-id="02fc6-132">HKEY \ _CURRENT 已登录用户无法向其写入值的 _USER 注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="02fc6-132">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="02fc6-133">HKEY \ _CURRENT \ _USER 与 Windows 操作系统的核心功能相关联的注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="02fc6-133">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="02fc6-134">位于 HKEY _LOCAL \ _MACHINE 配置单元中的所有注册表项（需要管理员权限，并且可能需要 UAC 协议才能设置）</span><span class="sxs-lookup"><span data-stu-id="02fc6-134">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive (Requires Administrator rights and might require UAC agreement to set)</span></span>

-   <span data-ttu-id="02fc6-135">位于 "程序文件" 目录中的文件（需要管理员权限，并且可能需要 UAC 协议才能设置）</span><span class="sxs-lookup"><span data-stu-id="02fc6-135">Files that are located in Program Files directories (Requires Administrator rights and might require UAC agreement to set)</span></span>

-   <span data-ttu-id="02fc6-136">位于用户 \\ [用户名 \] \\ AppData \\ LocalLow 中的文件</span><span class="sxs-lookup"><span data-stu-id="02fc6-136">Files located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="02fc6-137">位于% systemroot% 中的 Windows 操作系统文件（需要管理员权限，并且可能需要 UAC 协议才能设置）</span><span class="sxs-lookup"><span data-stu-id="02fc6-137">Windows operating system files that are located in %systemroot% (Requires Administrator rights and might require UAC agreement to set)</span></span>

<span data-ttu-id="02fc6-138">如果需要在这些位置存储的注册表项和文件才能漫游应用程序设置，则可以在模板创建过程中手动将排除的位置添加到设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="02fc6-138">If registry keys and files stored in these locations are required in order to roam application settings, you can manually add the excluded locations to the settings location template during the template creation process.</span></span>

## <span data-ttu-id="02fc6-139">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="02fc6-139">Other resources for this product</span></span>


[<span data-ttu-id="02fc6-140">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="02fc6-140">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

[<span data-ttu-id="02fc6-141">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="02fc6-141">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

 

 





