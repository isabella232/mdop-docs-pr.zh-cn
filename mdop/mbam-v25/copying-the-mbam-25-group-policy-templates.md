---
title: 复制 MBAM 2.5 组策略模板
description: 复制 MBAM 2.5 组策略模板
author: dansimp
ms.assetid: e526ecec-07ff-435e-bc90-3084b617b84b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/28/2017
ms.openlocfilehash: a3436552256b1632a11037dc94751207cde89d5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803725"
---
# <span data-ttu-id="908e8-103">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="908e8-103">Copying the MBAM 2.5 Group Policy Templates</span></span>


<span data-ttu-id="908e8-104">在部署 MBAM 客户端安装之前，必须下载 MBAM 组策略模板，其中包含定义用于 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="908e8-104">Before deploying the MBAM Client installation, you must download the MBAM Group Policy Templates, which contain Group Policy settings that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="908e8-105">下载模板后，您可以将组策略设置设置为在整个企业中实施。</span><span class="sxs-lookup"><span data-stu-id="908e8-105">After downloading the templates, you then set the Group Policy settings to implement across your enterprise.</span></span>

## <span data-ttu-id="908e8-106">下载和部署 MDOP 组策略模板</span><span class="sxs-lookup"><span data-stu-id="908e8-106">Downloading and deploying the MDOP Group Policy templates</span></span>


<span data-ttu-id="908e8-107">MDOP 组策略模板可在自解压缩的压缩文件中下载，按技术和版本分组。</span><span class="sxs-lookup"><span data-stu-id="908e8-107">MDOP Group Policy templates are available for download in a self-extracting, compressed file, grouped by technology and version.</span></span>

**<span data-ttu-id="908e8-108">如何下载和部署 MDOP 组策略模板</span><span class="sxs-lookup"><span data-stu-id="908e8-108">How to download and deploy the MDOP Group Policy templates</span></span>**

1. <span data-ttu-id="908e8-109">从[Microsoft 桌面优化包组策略管理模板](https://www.microsoft.com/download/details.aspx?id=55531)下载 MDOP 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="908e8-109">Download the MDOP Group Policy templates from [Microsoft Desktop Optimization Pack Group Policy Administrative Templates](https://www.microsoft.com/download/details.aspx?id=55531).</span></span>

2. <span data-ttu-id="908e8-110">运行下载的文件以提取模板文件夹。</span><span class="sxs-lookup"><span data-stu-id="908e8-110">Run the downloaded file to extract the template folders.</span></span>

   **<span data-ttu-id="908e8-111">警告</span><span class="sxs-lookup"><span data-stu-id="908e8-111">Warning</span></span>**  
   <span data-ttu-id="908e8-112">不要将模板直接提取到组策略部署目录中。</span><span class="sxs-lookup"><span data-stu-id="908e8-112">Do not extract the templates directly to the Group Policy deployment directory.</span></span> <span data-ttu-id="908e8-113">此文件中捆绑了多项技术和版本。</span><span class="sxs-lookup"><span data-stu-id="908e8-113">Multiple technologies and versions are bundled in this file.</span></span>



3. <span data-ttu-id="908e8-114">在提取的文件夹中，找到技术版本的 admx 文件。</span><span class="sxs-lookup"><span data-stu-id="908e8-114">In the extracted folder, locate the technology-version .admx file.</span></span> <span data-ttu-id="908e8-115">某些 MDOP 技术具有多个组策略对象（Gpo）集。</span><span class="sxs-lookup"><span data-stu-id="908e8-115">Certain MDOP technologies have multiple sets of Group Policy Objects (GPOs).</span></span> <span data-ttu-id="908e8-116">例如，MBAM 包括 MBAM 管理设置和 MBAM 用户设置。</span><span class="sxs-lookup"><span data-stu-id="908e8-116">For example, MBAM includes MBAM Management settings and MBAM User settings.</span></span>

4. <span data-ttu-id="908e8-117">按语言-区域性（即*En*英语-美国）查找相应的 adml 文件。</span><span class="sxs-lookup"><span data-stu-id="908e8-117">Locate the appropriate .adml file by language-culture (that is, *en* for English-United States).</span></span>

5. <span data-ttu-id="908e8-118">将 admx 和 adml 文件复制到策略定义文件夹。</span><span class="sxs-lookup"><span data-stu-id="908e8-118">Copy the .admx and .adml files to a policy definition folder.</span></span> <span data-ttu-id="908e8-119">根据你存储模板的位置，你可以从本地设备或域上的任何计算机配置组策略设置。</span><span class="sxs-lookup"><span data-stu-id="908e8-119">Depending on where you store the templates, you can configure Group Policy settings from the local device or from any computer on the domain.</span></span>

   **<span data-ttu-id="908e8-120">本地文件。</span><span class="sxs-lookup"><span data-stu-id="908e8-120">Local files.</span></span>** <span data-ttu-id="908e8-121">若要从本地设备配置组策略设置，请将模板文件复制到以下位置：</span><span class="sxs-lookup"><span data-stu-id="908e8-121">To configure Group Policy settings from the local device, copy template files to the following locations:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="908e8-122">文件类型</span><span class="sxs-lookup"><span data-stu-id="908e8-122">File type</span></span></th>
   <th align="left"><span data-ttu-id="908e8-123">文件位置</span><span class="sxs-lookup"><span data-stu-id="908e8-123">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="908e8-124">组策略模板（admx）</span><span class="sxs-lookup"><span data-stu-id="908e8-124">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="908e8-125">&lt;强有力的 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="908e8-125">&lt;strong&gt;policyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="908e8-126">组策略语言文件（adml）</span><span class="sxs-lookup"><span data-stu-id="908e8-126">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="908e8-127">&lt;强有力的 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="908e8-127">&lt;strong&gt;policyDefinitions</span></span></strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Domain central store.** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">File type</th>
<th align="left">File location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Group Policy template (.admx)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Group Policy language file (.adml)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions\[MUIculture]</strong><code>\[MUIculture]</code></p>
<p>For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</p></td>
</tr>
</tbody>
</table>
~~~



6. <span data-ttu-id="908e8-128">使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）编辑组策略设置以配置 MDOP 技术的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="908e8-128">Edit the Group Policy settings using Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) to configure Group Policy settings for the MDOP technology.</span></span> <span data-ttu-id="908e8-129">有关详细信息，请参阅[编辑 MBAM 2.5 组策略设置](editing-the-mbam-25-group-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="908e8-129">See [Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md) for more information.</span></span>

   <span data-ttu-id="908e8-130">有关组策略设置的说明，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="908e8-130">For descriptions of the Group Policy settings, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>


## <span data-ttu-id="908e8-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="908e8-131">Related topics</span></span>


[<span data-ttu-id="908e8-132">部署 MBAM 2.5 组策略对象</span><span class="sxs-lookup"><span data-stu-id="908e8-132">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)


## <span data-ttu-id="908e8-133">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="908e8-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="908e8-134">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="908e8-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="908e8-135">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="908e8-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






