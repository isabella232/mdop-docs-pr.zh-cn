---
title: 计划从以前版本的 App-V 迁移
description: 计划从以前版本的 App-V 迁移
author: dansimp
ms.assetid: d4ca8f09-86fd-456f-8ec2-242ff94ae9a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2242f58a29473e116506ec013b94a79d1bb814a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798304"
---
# <span data-ttu-id="a518d-103">计划从以前版本的 App-V 迁移</span><span class="sxs-lookup"><span data-stu-id="a518d-103">Planning for Migrating from a Previous Version of App-V</span></span>


<span data-ttu-id="a518d-104">使用以下信息规划如何从 app-v 的早期版本迁移到 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="a518d-104">Use the following information to plan how to migrate to App-V 5.0 from previous versions of App-V.</span></span>

## <span data-ttu-id="a518d-105">迁移要求</span><span class="sxs-lookup"><span data-stu-id="a518d-105">Migration requirements</span></span>


<span data-ttu-id="a518d-106">开始任何升级之前，请查看以下要求：</span><span class="sxs-lookup"><span data-stu-id="a518d-106">Before you start any upgrades, review the following requirements:</span></span>

-   <span data-ttu-id="a518d-107">如果从早于 App-v 4.6 SP2 的版本升级，请先升级到版本 App-v 4.6 SP3，然后再升级到 app-v 5.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a518d-107">If you are upgrading from a version earlier than App-V 4.6 SP2, upgrade to version App-V 4.6 SP3 first before upgrading to App-V 5.0 or later.</span></span> <span data-ttu-id="a518d-108">在此方案中，首先升级 App-v 客户端，然后升级服务器组件。</span><span class="sxs-lookup"><span data-stu-id="a518d-108">In this scenario, upgrade the App-V clients first, and then upgrade the server components.</span></span>
<span data-ttu-id="a518d-109">**注意：** App-v 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="a518d-109">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

-   <span data-ttu-id="a518d-110">App-v 5.0 仅支持使用 App-v 5.0 创建的程序包，或者仅支持已转换为 App-v 5.0 （**appv**）格式的程序包。</span><span class="sxs-lookup"><span data-stu-id="a518d-110">App-V 5.0 supports only packages that are created using App-V 5.0, or packages that have been converted to the App-V 5.0 (**.appv**) format.</span></span>

-   <span data-ttu-id="a518d-111">仅限 app-v 5.0 SP3：如果你要从 App-v 5.0 SP1 升级 app-v 服务器，请参阅[关于 app-v 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="a518d-111">App-V 5.0 SP3 only: If you are upgrading the App-V Server from App-V 5.0 SP1, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3) for instructions.</span></span>

## <span data-ttu-id="a518d-112">与 app-v 4.6 同时运行 app-v 5.0 客户端</span><span class="sxs-lookup"><span data-stu-id="a518d-112">Running the App-V 5.0 client concurrently with App-V 4.6</span></span>


<span data-ttu-id="a518d-113">可以在具有 App-v 4.6 SP3 客户端的同一计算机上同时运行 app-v 5.0 客户端。</span><span class="sxs-lookup"><span data-stu-id="a518d-113">You can run the App-V 5.0 client concurrently on the same computer with the App-V4.6SP3 client.</span></span>

<span data-ttu-id="a518d-114">运行共存的 App-v 客户端时，可以：</span><span class="sxs-lookup"><span data-stu-id="a518d-114">When you run coexisting App-V clients, you can:</span></span>

-   <span data-ttu-id="a518d-115">当同时运行两个客户端时，将 app-v 4.6 SP3 程序包转换为 App-v 5.0 格式并发布这两个程序包。</span><span class="sxs-lookup"><span data-stu-id="a518d-115">Convert an App-V 4.6 SP3 package to the App-V 5.0 format and publish both packages, when you have both clients running.</span></span>

-   <span data-ttu-id="a518d-116">为已转换的程序包定义迁移策略，从而允许已转换的 App-v 5.0 程序包假设来自 App-v 4.6 程序包的文件类型关联和快捷方式。</span><span class="sxs-lookup"><span data-stu-id="a518d-116">Define the migration policy for the converted package, which allows the converted App-V 5.0 package to assume the file type associations and shortcuts from the App-V 4.6 package.</span></span>

### <span data-ttu-id="a518d-117">支持的共存方案</span><span class="sxs-lookup"><span data-stu-id="a518d-117">Supported coexistence scenarios</span></span>

<span data-ttu-id="a518d-118">下表显示了受支持的应用程序-V 共存方案。</span><span class="sxs-lookup"><span data-stu-id="a518d-118">The following table shows the supported App-V coexistence scenarios.</span></span> <span data-ttu-id="a518d-119">我们建议你在运行共存的客户端时，安装给定发布的最新可用更新。</span><span class="sxs-lookup"><span data-stu-id="a518d-119">We recommend that you install the latest available updates of a given release when you are running coexisting clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a518d-120">App-v 4.6 客户端类型</span><span class="sxs-lookup"><span data-stu-id="a518d-120">App-V 4.6 client type</span></span></th>
<th align="left"><span data-ttu-id="a518d-121">App-v 5.0 客户端类型</span><span class="sxs-lookup"><span data-stu-id="a518d-121">App-V 5.0 client type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a518d-122">App-v 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="a518d-122">App-V 4.6 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="a518d-123">App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="a518d-123">App-V 5.0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a518d-124">App-v 4.6 SP3 RDS</span><span class="sxs-lookup"><span data-stu-id="a518d-124">App-V 4.6 SP3 RDS</span></span></p></td>
<td align="left"><p><span data-ttu-id="a518d-125">App-v 5.0 RDS</span><span class="sxs-lookup"><span data-stu-id="a518d-125">App-V 5.0 RDS</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="a518d-126">运行共存客户端的要求</span><span class="sxs-lookup"><span data-stu-id="a518d-126">Requirements for running coexisting clients</span></span>

<span data-ttu-id="a518d-127">若要运行共存的客户端，您必须：</span><span class="sxs-lookup"><span data-stu-id="a518d-127">To run coexisting clients, you must:</span></span>

-   <span data-ttu-id="a518d-128">在安装 app-v 5.0 客户端之前安装 app-v 4.6 客户端。</span><span class="sxs-lookup"><span data-stu-id="a518d-128">Install the App-V4.6 client before you install the App-V 5.0 client.</span></span>

-   <span data-ttu-id="a518d-129">启用 "**启用迁移模式**" 组策略设置，该设置位于**app-v** &gt; **客户端共存**节点中。</span><span class="sxs-lookup"><span data-stu-id="a518d-129">Enable the **Enable Migration Mode** Group Policy setting, which is in the **App-V** &gt; **Client Coexistence** node.</span></span> <span data-ttu-id="a518d-130">若要获取该 admx 模板的部署，请参阅[如何下载和部署 MDOP 组策略（admx）模板](https://technet.microsoft.com/library/dn659707.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a518d-130">To get the deploy the .admx template, see [How to Download and Deploy MDOP Group Policy (.admx) Templates](https://technet.microsoft.com/library/dn659707.aspx).</span></span>

### <span data-ttu-id="a518d-131">客户端下载和文档</span><span class="sxs-lookup"><span data-stu-id="a518d-131">Client downloads and documentation</span></span>

<span data-ttu-id="a518d-132">下表提供了有关发布的 TechNet 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="a518d-132">The following table provides link to the TechNet documentation about the releases.</span></span> <span data-ttu-id="a518d-133">有关 App-v 客户端的 TechNet 文档适用于两个客户端，除非另行说明。</span><span class="sxs-lookup"><span data-stu-id="a518d-133">The TechNet documentation about the App-V client applies to both clients, unless stated otherwise.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a518d-134">App-v 版本</span><span class="sxs-lookup"><span data-stu-id="a518d-134">App-V version</span></span></th>
<th align="left"><span data-ttu-id="a518d-135">链接到 TechNet 文档</span><span class="sxs-lookup"><span data-stu-id="a518d-135">Link to TechNet documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a518d-136">App-v 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="a518d-136">App-V 4.6SP3</span></span></p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)"><span data-ttu-id="a518d-137">关于 Microsoft Application Virtualization 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="a518d-137">About Microsoft Application Virtualization 4.6 SP3</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a518d-138">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="a518d-138">App-V 5.0SP3</span></span></p></td>
<td align="left"><p><a href="about-app-v-50-sp3.md" data-raw-source="[About Microsoft Application Virtualization 5.0 SP3](about-app-v-50-sp3.md)"><span data-ttu-id="a518d-139">关于 Microsoft Application Virtualization 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="a518d-139">About Microsoft Application Virtualization 5.0 SP3</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a518d-140">有关如何配置 App-v 5.0 客户端共存的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a518d-140">For more information about how to configure App-V 5.0 client coexistence, see:</span></span>

-   [<span data-ttu-id="a518d-141">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端</span><span class="sxs-lookup"><span data-stu-id="a518d-141">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

-   [<span data-ttu-id="a518d-142">App-v 5.0 共存和迁移</span><span class="sxs-lookup"><span data-stu-id="a518d-142">App-V 5.0 Coexistence and Migration</span></span>](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a><span data-ttu-id="a518d-143">使用软件包转换器转换 "早期版本" 程序包</span><span class="sxs-lookup"><span data-stu-id="a518d-143">Converting “previous-version” packages using the package converter</span></span>


<span data-ttu-id="a518d-144">将使用 App-v 4.6 SP3 或更早版本创建的程序包迁移到 app-v 5.0 之前，请查看以下要求：</span><span class="sxs-lookup"><span data-stu-id="a518d-144">Before migrating a package, created using App-V4.6SP3 or earlier, to App-V 5.0, review the following requirements:</span></span>

-   <span data-ttu-id="a518d-145">必须将程序包转换为**appv**文件格式。</span><span class="sxs-lookup"><span data-stu-id="a518d-145">You must convert the package to the **.appv** file format.</span></span>

-   <span data-ttu-id="a518d-146">程序包转换器仅支持使用 App-v 4.5 和更高版本创建的程序包的直接转换。</span><span class="sxs-lookup"><span data-stu-id="a518d-146">The Package Converter supports only the direct conversion of packages that were created by using App-V 4.5 and later.</span></span> <span data-ttu-id="a518d-147">若要在使用早期版本创建的程序包上使用程序包转换器，必须使用 sequencer 的 app-v 或更高版本升级程序包，然后你可以执行程序包转换。</span><span class="sxs-lookup"><span data-stu-id="a518d-147">To use the package converter on a package that was created using a previous version, you must use an App-V4.5 or later version of the sequencer to upgrade the package, and then you can perform the package conversion.</span></span>

<span data-ttu-id="a518d-148">有关使用程序包转换器转换程序包的详细信息，请参阅[如何转换在早期版本的 app-v 中创建的程序包](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)。</span><span class="sxs-lookup"><span data-stu-id="a518d-148">For more information about using the package converter to convert a package, see [How to Convert a Package Created in a Previous Version of App-V](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md).</span></span> <span data-ttu-id="a518d-149">转换文件后，可将其部署到运行 app-v 5.0 客户端的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="a518d-149">After you convert the file, you can deploy it to target computers that run the App-V 5.0 client.</span></span>






## <span data-ttu-id="a518d-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="a518d-150">Related topics</span></span>


[<span data-ttu-id="a518d-151">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="a518d-151">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





