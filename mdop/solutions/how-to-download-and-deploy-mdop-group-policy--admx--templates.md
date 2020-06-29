---
title: 如何下载和部署 MDOP 组策略 (.admx) 模板
description: 如何下载和部署 MDOP 组策略 (.admx) 模板
author: dansimp
ms.assetid: fdb64505-6c66-4fdf-ad74-a6a161191e3f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 5bc5f8d536c113ccbc0a1931e6c7e4ed3c7a9a37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804064"
---
# <span data-ttu-id="79885-103">如何下载和部署 MDOP 组策略 (.admx) 模板</span><span class="sxs-lookup"><span data-stu-id="79885-103">How to Download and Deploy MDOP Group Policy (.admx) Templates</span></span>


<span data-ttu-id="79885-104">你可以使用组策略模板、admx 和 adml 文件管理某些 Microsoft 桌面优化包（MDOP）技术（例如，app-v、UE-V 或 MBAM）的功能设置。</span><span class="sxs-lookup"><span data-stu-id="79885-104">You can manage the feature settings of certain Microsoft Desktop Optimization Pack (MDOP) technologies (for example, App-V, UE-V, or MBAM) by using Group Policy templates, the .admx and .adml files.</span></span> <span data-ttu-id="79885-105">MDOP 组策略模板可在自解压缩的压缩文件中下载，按技术和版本分组。</span><span class="sxs-lookup"><span data-stu-id="79885-105">MDOP Group Policy templates are available for download in a self-extracting, compressed file, grouped by technology and version.</span></span>

## <span data-ttu-id="79885-106">MDOP 组策略模板</span><span class="sxs-lookup"><span data-stu-id="79885-106">MDOP Group Policy templates</span></span>

**<span data-ttu-id="79885-107">如何下载和部署 MDOP 组策略模板</span><span class="sxs-lookup"><span data-stu-id="79885-107">How to download and deploy the MDOP Group Policy templates</span></span>**

1. <span data-ttu-id="79885-108">下载最新的[MDOP 组策略模板](https://www.microsoft.com/download/details.aspx?id=55531)</span><span class="sxs-lookup"><span data-stu-id="79885-108">Download the latest [MDOP Group Policy templates](https://www.microsoft.com/download/details.aspx?id=55531)</span></span> 

2. <span data-ttu-id="79885-109">通过运行展开已下载的 .cab 文件</span><span class="sxs-lookup"><span data-stu-id="79885-109">Expand the downloaded .cab file by running</span></span> `expand <download_folder>\MDOP_ADMX_Templates.cab -F:* <destination_folder>`

   **<span data-ttu-id="79885-110">警告</span><span class="sxs-lookup"><span data-stu-id="79885-110">Warning</span></span>**  
   <span data-ttu-id="79885-111">不要将模板直接提取到组策略部署目录中。</span><span class="sxs-lookup"><span data-stu-id="79885-111">Do not extract the templates directly to the Group Policy deployment directory.</span></span> <span data-ttu-id="79885-112">此文件中捆绑了多项技术和版本。</span><span class="sxs-lookup"><span data-stu-id="79885-112">Multiple technologies and versions are bundled in this file.</span></span>

3. <span data-ttu-id="79885-113">在提取的文件夹中，找到技术版本的 admx 文件。</span><span class="sxs-lookup"><span data-stu-id="79885-113">In the extracted folder, locate the technology-version .admx file.</span></span> <span data-ttu-id="79885-114">某些 MDOP 技术具有多个组策略对象（Gpo）集。</span><span class="sxs-lookup"><span data-stu-id="79885-114">Certain MDOP technologies have multiple sets of Group Policy Objects (GPOs).</span></span> <span data-ttu-id="79885-115">例如，MBAM 包括 MBAM 管理设置和 MBAM 用户设置。</span><span class="sxs-lookup"><span data-stu-id="79885-115">For example, MBAM includes MBAM Management settings and MBAM User settings.</span></span>

4. <span data-ttu-id="79885-116">通过语言（即*En-us*英语-美国）查找相应的 adml 文件。</span><span class="sxs-lookup"><span data-stu-id="79885-116">Locate the appropriate .adml file by language-culture (that is, *en-us* for English-United States).</span></span>

5. <span data-ttu-id="79885-117">将 admx 和 adml 文件复制到策略定义文件夹。</span><span class="sxs-lookup"><span data-stu-id="79885-117">Copy the .admx and .adml files to a policy definition folder.</span></span> <span data-ttu-id="79885-118">根据你存储模板的位置，你可以从本地设备或域上的任何计算机配置组策略设置。</span><span class="sxs-lookup"><span data-stu-id="79885-118">Depending on where you store the templates, you can configure Group Policy settings from the local device or from any computer on the domain.</span></span>

   - <span data-ttu-id="79885-119">**本地文件：** 若要从本地设备配置组策略设置，请将模板文件复制到以下位置：</span><span class="sxs-lookup"><span data-stu-id="79885-119">**Local files:** To configure Group Policy settings from the local device, copy template files to the following locations:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="79885-120">文件类型</span><span class="sxs-lookup"><span data-stu-id="79885-120">File type</span></span></th>
   <th align="left"><span data-ttu-id="79885-121">文件位置</span><span class="sxs-lookup"><span data-stu-id="79885-121">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="79885-122">组策略模板（admx）</span><span class="sxs-lookup"><span data-stu-id="79885-122">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="79885-123">&lt;强有力的 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="79885-123">&lt;strong&gt;policyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="79885-124">组策略语言文件（adml）</span><span class="sxs-lookup"><span data-stu-id="79885-124">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="79885-125">&lt;强有力的 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="79885-125">&lt;strong&gt;policyDefinitions</span></span></strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>

   - <span data-ttu-id="79885-126">**域中央存储：** 若要从域上任何计算机的组策略管理员处启用组策略设置配置，请将文件复制到域控制器上的以下位置：</span><span class="sxs-lookup"><span data-stu-id="79885-126">**Domain central store:** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="79885-127">文件类型</span><span class="sxs-lookup"><span data-stu-id="79885-127">File type</span></span></th>
   <th align="left"><span data-ttu-id="79885-128">文件位置</span><span class="sxs-lookup"><span data-stu-id="79885-128">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="79885-129">组策略模板（admx）</span><span class="sxs-lookup"><span data-stu-id="79885-129">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="79885-130">&lt;强有力的 &gt; sysvol\domain\policies\PolicyDefinitions</span><span class="sxs-lookup"><span data-stu-id="79885-130">&lt;strong&gt;sysvol\domain\policies\PolicyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="79885-131">组策略语言文件（adml）</span><span class="sxs-lookup"><span data-stu-id="79885-131">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="79885-132">&lt;强 &gt; sysvol\domain\policies\PolicyDefinitions [MUIculture]</span><span class="sxs-lookup"><span data-stu-id="79885-132">&lt;strong&gt;sysvol\domain\policies\PolicyDefinitions[MUIculture]</span></span></strong><code>[MUIculture]</code></p>
   <p><span data-ttu-id="79885-133">例如，美国英语 ADML 语言特定的文件将存储在%systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us。</span><span class="sxs-lookup"><span data-stu-id="79885-133">For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</span></span></p></td>
   </tr>
   </tbody>
   </table>

6. <span data-ttu-id="79885-134">使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）编辑组策略设置以配置 MDOP 技术的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="79885-134">Edit the Group Policy settings using Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) to configure Group Policy settings for the MDOP technology.</span></span>

### <span data-ttu-id="79885-135">通过技术 MDOP 组策略</span><span class="sxs-lookup"><span data-stu-id="79885-135">MDOP Group Policy by technology</span></span>

<span data-ttu-id="79885-136">有关受支持的 MDOP 组策略的详细信息，请参阅该技术的特定文档。</span><span class="sxs-lookup"><span data-stu-id="79885-136">For more information about supported MDOP Group Policy, see the specific documentation for the technology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="79885-137">MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="79885-137">MDOP Technology</span></span></th>
<th align="left"><span data-ttu-id="79885-138">版本捆绑</span><span class="sxs-lookup"><span data-stu-id="79885-138">Version bundles</span></span></th>
<th align="left"><span data-ttu-id="79885-139">注释</span><span class="sxs-lookup"><span data-stu-id="79885-139">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="79885-140">应用程序虚拟化 (App-V)</span><span class="sxs-lookup"><span data-stu-id="79885-140">Application Virtualization (App-V)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="79885-141">App-v 5.0 和应用程序-V 5.0 服务包</span><span class="sxs-lookup"><span data-stu-id="79885-141">App-V 5.0 and App-V 5.0 Service Packs</span></span></p></td>
<td align="left"><p><a href="../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md" data-raw-source="[How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)"><span data-ttu-id="79885-142">如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置</span><span class="sxs-lookup"><span data-stu-id="79885-142">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="79885-143">用户体验虚拟化 (UE-V)</span><span class="sxs-lookup"><span data-stu-id="79885-143">User Experience Virtualization (UE-V)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="79885-144">UE-V 2.0 和 UE-V 2。1</span><span class="sxs-lookup"><span data-stu-id="79885-144">UE-V 2.0 and UE-V 2.1</span></span></p></td>
<td align="left"><p><a href="../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md" data-raw-source="[Configuring UE-V 2.x with Group Policy Objects](../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)"><span data-ttu-id="79885-145">通过组策略对象配置 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="79885-145">Configuring UE-V 2.x with Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="79885-146">UE-V 1.0 （包括 1.0 SP1）</span><span class="sxs-lookup"><span data-stu-id="79885-146">UE-V 1.0 including 1.0 SP1</span></span></p></td>
<td align="left"><p><a href="../uev-v1/configuring-ue-v-with-group-policy-objects.md" data-raw-source="[Configuring UE-V with Group Policy Objects](../uev-v1/configuring-ue-v-with-group-policy-objects.md)"><span data-ttu-id="79885-147">使用组策略对象配置 UE-V</span><span class="sxs-lookup"><span data-stu-id="79885-147">Configuring UE-V with Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="79885-148">Microsoft BitLocker 管理和监控 (MBAM)</span><span class="sxs-lookup"><span data-stu-id="79885-148">Microsoft BitLocker Administration and Monitoring (MBAM)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="79885-149">MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="79885-149">MBAM 2.5</span></span></p></td>
<td align="left"><p><a href="../mbam-v25/planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](../mbam-v25/planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="79885-150">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="79885-150">Planning for MBAM 2.5 Group Policy Requirements</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="79885-151">MBAM 2.0 （包括 2.0 SP1）</span><span class="sxs-lookup"><span data-stu-id="79885-151">MBAM 2.0 including 2.0 SP1</span></span></p></td>
<td align="left"><p><a href="../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="79885-152">计划 MBAM 2.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="79885-152">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p>
<p><a href="../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="79885-153">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="79885-153">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="79885-154">MBAM 1。0</span><span class="sxs-lookup"><span data-stu-id="79885-154">MBAM 1.0</span></span></p></td>
<td align="left"><p><a href="../mbam-v1/how-to-edit-mbam-10-gpo-settings.md" data-raw-source="[How to Edit MBAM 1.0 GPO Settings](../mbam-v1/how-to-edit-mbam-10-gpo-settings.md)"><span data-ttu-id="79885-155">如何编辑 MBAM 1.0 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="79885-155">How to Edit MBAM 1.0 GPO Settings</span></span></a></p></td>
</tr>
</tbody>
</table>

 

 

 





