---
title: 计划从以前版本的 App-V 迁移
description: 计划从以前版本的 App-V 迁移
author: dansimp
ms.assetid: 4a058047-9674-41bc-8050-c58c97a80a9b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: d7f2496b355aee6a598fee44c84e7e8c0f755c4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798303"
---
# <span data-ttu-id="6096b-103">计划从以前版本的 App-V 迁移</span><span class="sxs-lookup"><span data-stu-id="6096b-103">Planning for Migrating from a Previous Version of App-V</span></span>


<span data-ttu-id="6096b-104">使用以下信息可计划从早期版本的 App-v 迁移到 Microsoft Application Virtualization （App-v）5.1。</span><span class="sxs-lookup"><span data-stu-id="6096b-104">Use the following information to plan how to migrate to Microsoft Application Virtualization (App-V) 5.1 from previous versions of App-V.</span></span>

## <span data-ttu-id="6096b-105">迁移要求</span><span class="sxs-lookup"><span data-stu-id="6096b-105">Migration requirements</span></span>


<span data-ttu-id="6096b-106">开始任何升级之前，请查看以下要求：</span><span class="sxs-lookup"><span data-stu-id="6096b-106">Before you start any upgrades, review the following requirements:</span></span>

-   <span data-ttu-id="6096b-107">如果从早于 App-v 4.6 SP2 的版本升级，请先升级到版本 App-v 4.6 SP3，然后再升级到 app-v 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6096b-107">If you are upgrading from a version earlier than App-V 4.6 SP2, upgrade to version App-V 4.6 SP3 first before upgrading to App-V 5.1 or later.</span></span> <span data-ttu-id="6096b-108">在此方案中，首先升级 App-v 客户端，然后升级服务器组件。</span><span class="sxs-lookup"><span data-stu-id="6096b-108">In this scenario, upgrade the App-V clients first, and then upgrade the server components.</span></span>
<span data-ttu-id="6096b-109">**注意：** App-v 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="6096b-109">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

-   <span data-ttu-id="6096b-110">App-v 5.1 仅支持使用 App-v 5.0 或 App-v 5.1 创建的程序包，或者仅支持已转换为**appv**格式的程序包。</span><span class="sxs-lookup"><span data-stu-id="6096b-110">App-V 5.1 supports only packages that are created using App-V 5.0 or App-V 5.1, or packages that have been converted to the **.appv** format.</span></span>

-   <span data-ttu-id="6096b-111">如果你要从 App-v 5.0 SP1 升级 app-v 服务器，请参阅[关于 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="6096b-111">If you are upgrading the App-V Server from App-V 5.0 SP1, see [About App-V 5.1](about-app-v-51.md#bkmk-migrate-to-51) for instructions.</span></span>

## <span data-ttu-id="6096b-112">与 app-v 4.6 同时运行 app-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="6096b-112">Running the App-V 5.1 client concurrently with App-V 4.6</span></span>


<span data-ttu-id="6096b-113">可以在具有 App-v 4.6 SP3 客户端的同一计算机上同时运行 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="6096b-113">You can run the App-V 5.1 client concurrently on the same computer with the App-V4.6SP3 client.</span></span>

<span data-ttu-id="6096b-114">运行共存的 App-v 客户端时，可以：</span><span class="sxs-lookup"><span data-stu-id="6096b-114">When you run coexisting App-V clients, you can:</span></span>

-   <span data-ttu-id="6096b-115">当同时运行两个客户端时，将 app-v 4.6 SP3 程序包转换为 App-v 5.1 格式并发布这两个程序包。</span><span class="sxs-lookup"><span data-stu-id="6096b-115">Convert an App-V 4.6 SP3 package to the App-V 5.1 format and publish both packages, when you have both clients running.</span></span>

-   <span data-ttu-id="6096b-116">为已转换的程序包定义迁移策略，从而允许已转换的 App-v 5.1 程序包假设来自 App-v 4.6 程序包的文件类型关联和快捷方式。</span><span class="sxs-lookup"><span data-stu-id="6096b-116">Define the migration policy for the converted package, which allows the converted App-V 5.1 package to assume the file type associations and shortcuts from the App-V 4.6 package.</span></span>

### <span data-ttu-id="6096b-117">支持的共存方案</span><span class="sxs-lookup"><span data-stu-id="6096b-117">Supported coexistence scenarios</span></span>

<span data-ttu-id="6096b-118">下表显示了受支持的应用程序-V 共存方案。</span><span class="sxs-lookup"><span data-stu-id="6096b-118">The following table shows the supported App-V coexistence scenarios.</span></span> <span data-ttu-id="6096b-119">我们建议你在运行共存的客户端时，安装给定发布的最新可用更新。</span><span class="sxs-lookup"><span data-stu-id="6096b-119">We recommend that you install the latest available updates of a given release when you are running coexisting clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6096b-120">App-v 4.6 客户端类型</span><span class="sxs-lookup"><span data-stu-id="6096b-120">App-V 4.6 client type</span></span></th>
<th align="left"><span data-ttu-id="6096b-121">App-v 5.1 客户端类型</span><span class="sxs-lookup"><span data-stu-id="6096b-121">App-V 5.1 client type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6096b-122">App-v 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="6096b-122">App-V 4.6 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="6096b-123">App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="6096b-123">App-V 5.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6096b-124">App-v 4.6 SP3 RDS</span><span class="sxs-lookup"><span data-stu-id="6096b-124">App-V 4.6 SP3 RDS</span></span></p></td>
<td align="left"><p><span data-ttu-id="6096b-125">App-v 5.1 RDS</span><span class="sxs-lookup"><span data-stu-id="6096b-125">App-V 5.1 RDS</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6096b-126">运行共存客户端的要求</span><span class="sxs-lookup"><span data-stu-id="6096b-126">Requirements for running coexisting clients</span></span>

<span data-ttu-id="6096b-127">若要运行共存的客户端，您必须：</span><span class="sxs-lookup"><span data-stu-id="6096b-127">To run coexisting clients, you must:</span></span>

-   <span data-ttu-id="6096b-128">在安装 app-v 5.1 客户端之前安装 app-v 4.6 客户端。</span><span class="sxs-lookup"><span data-stu-id="6096b-128">Install the App-V4.6 client before you install the App-V 5.1 client.</span></span>

-   <span data-ttu-id="6096b-129">启用 "**启用迁移模式**" 组策略设置，该设置位于**app-v** &gt; **客户端共存**节点中。</span><span class="sxs-lookup"><span data-stu-id="6096b-129">Enable the **Enable Migration Mode** Group Policy setting, which is in the **App-V** &gt; **Client Coexistence** node.</span></span> <span data-ttu-id="6096b-130">若要部署 admx 模板，请参阅[如何下载和部署 MDOP 组策略（admx）模板](https://technet.microsoft.com/library/dn659707.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6096b-130">To deploy the .admx template, see [How to Download and Deploy MDOP Group Policy (.admx) Templates](https://technet.microsoft.com/library/dn659707.aspx).</span></span>

<span data-ttu-id="6096b-131">**注意** 如果你有共存的 app-v 5.1 和4.6 安装，则 app-v 5.1 程序包可以并排与 App-v 4.6 程序包并行运行。</span><span class="sxs-lookup"><span data-stu-id="6096b-131">**Note** App-V 5.1 packages can run side by side with App-V 4.6 packages if you have coexisting installations of App-V 5.1 and 4.6.</span></span> <span data-ttu-id="6096b-132">但是，app-v 5.1 程序包无法与同一虚拟环境中的 app-v 4.6 程序包交互。</span><span class="sxs-lookup"><span data-stu-id="6096b-132">However, App-V 5.1 packages cannot interact with App-V 4.6 packages in the same virtual environment.</span></span>

 

### <span data-ttu-id="6096b-133">客户端下载和文档</span><span class="sxs-lookup"><span data-stu-id="6096b-133">Client downloads and documentation</span></span>

<span data-ttu-id="6096b-134">下表提供了指向 App-v 4.6 客户端下载以及有关这些版本的 TechNet 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="6096b-134">The following table provides links to the App-V 4.6 client downloads and to the TechNet documentation about the releases.</span></span> <span data-ttu-id="6096b-135">下载内容包括 App-v "常规" 和 RDS 客户端。</span><span class="sxs-lookup"><span data-stu-id="6096b-135">The downloads include the App-V “regular” and RDS clients.</span></span> <span data-ttu-id="6096b-136">有关 App-v 客户端的 TechNet 文档适用于两个客户端，除非另行说明。</span><span class="sxs-lookup"><span data-stu-id="6096b-136">The TechNet documentation about the App-V client applies to both clients, unless stated otherwise.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6096b-137">App-v 版本</span><span class="sxs-lookup"><span data-stu-id="6096b-137">App-V version</span></span></th>
<th align="left"><span data-ttu-id="6096b-138">链接到 TechNet 文档</span><span class="sxs-lookup"><span data-stu-id="6096b-138">Link to TechNet documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6096b-139">App-v 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="6096b-139">App-V 4.6SP3</span></span></p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)"><span data-ttu-id="6096b-140">关于 Microsoft Application Virtualization 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="6096b-140">About Microsoft Application Virtualization 4.6 SP3</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6096b-141">App-v 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="6096b-141">App-V 4.6SP3</span></span></p></td>
<td align="left"><p><a href="about-app-v-51.md" data-raw-source="[About Microsoft Application Virtualization 5.1](about-app-v-51.md)"><span data-ttu-id="6096b-142">关于 Microsoft Application Virtualization 5。1</span><span class="sxs-lookup"><span data-stu-id="6096b-142">About Microsoft Application Virtualization 5.1</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6096b-143">有关如何配置 App-v 5.1 客户端共存的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6096b-143">For more information about how to configure App-V 5.1 client coexistence, see:</span></span>

-   [<span data-ttu-id="6096b-144">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="6096b-144">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

-   [<span data-ttu-id="6096b-145">App-v 5.0 共存和迁移</span><span class="sxs-lookup"><span data-stu-id="6096b-145">App-V 5.0 Coexistence and Migration</span></span>](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a><span data-ttu-id="6096b-146">使用软件包转换器转换 "早期版本" 程序包</span><span class="sxs-lookup"><span data-stu-id="6096b-146">Converting “previous-version” packages using the package converter</span></span>


<span data-ttu-id="6096b-147">将使用应用程序 4.6 SP2 或更早版本创建的程序包迁移到 app-v 5.1 之前，请查看以下要求：</span><span class="sxs-lookup"><span data-stu-id="6096b-147">Before migrating a package, created using App-4.6SP2 or earlier, to App-V 5.1, review the following requirements:</span></span>

-   <span data-ttu-id="6096b-148">必须将程序包转换为**appv**文件格式。</span><span class="sxs-lookup"><span data-stu-id="6096b-148">You must convert the package to the **.appv** file format.</span></span>

-   <span data-ttu-id="6096b-149">程序包转换器仅支持使用 App-v 4.5 和更高版本创建的程序包的直接转换。</span><span class="sxs-lookup"><span data-stu-id="6096b-149">The Package Converter supports only the direct conversion of packages that were created by using App-V 4.5 and later.</span></span> <span data-ttu-id="6096b-150">若要在使用早期版本创建的程序包上使用程序包转换器，必须使用 sequencer 的 app-v 或更高版本升级程序包，然后你可以执行程序包转换。</span><span class="sxs-lookup"><span data-stu-id="6096b-150">To use the package converter on a package that was created using a previous version, you must use an App-V4.5 or later version of the sequencer to upgrade the package, and then you can perform the package conversion.</span></span>

<span data-ttu-id="6096b-151">有关使用程序包转换器转换程序包的详细信息，请参阅[如何转换在早期版本的 app-v 中创建的程序包](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)。</span><span class="sxs-lookup"><span data-stu-id="6096b-151">For more information about using the package converter to convert a package, see [How to Convert a Package Created in a Previous Version of App-V](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md).</span></span> <span data-ttu-id="6096b-152">转换文件后，可将其部署到运行 app-v 5.1 客户端的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="6096b-152">After you convert the file, you can deploy it to target computers that run the App-V 5.1 client.</span></span>






## <span data-ttu-id="6096b-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="6096b-153">Related topics</span></span>


[<span data-ttu-id="6096b-154">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="6096b-154">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





