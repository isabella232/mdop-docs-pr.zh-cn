---
title: MBAM 2.5 支持的配置
description: MBAM 2.5 支持的配置
author: dansimp
ms.assetid: ce689aff-9a55-4ae7-a968-23c7bda9b4d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 10/24/2018
ms.openlocfilehash: 8ed7915e33c5e4735a7c58674ed5f7d6da8e9a06
ms.sourcegitcommit: 9087f0a1b5bd3f81a9b790d5e39fdf39c18a2411
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "11182924"
---
# <span data-ttu-id="a0a35-103">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="a0a35-103">MBAM 2.5 Supported Configurations</span></span>


<span data-ttu-id="a0a35-104">可以在独立拓扑中或在与 System Center Configuration Manager 集成 MBAM 的 Configuration Manager 集成拓扑中运行 Microsoft BitLocker 管理和监视 (MBAM) 2.5。</span><span class="sxs-lookup"><span data-stu-id="a0a35-104">You can run Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in a Stand-alone topology or in a Configuration Manager Integration topology that integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="a0a35-105">如果对生产环境中的任一拓扑使用推荐的配置，MBAM 最多支持 500000 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="a0a35-105">If you use the recommended configuration for either topology in a production environment, MBAM supports up to 500,000 MBAM clients.</span></span> <span data-ttu-id="a0a35-106">有关在每个服务器上为每个拓扑配置的推荐体系结构和功能的信息，请参阅 [MBAM 2.5 的高级体系结构](high-level-architecture-for-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-106">For information about the recommended architecture and features that are configured on each server for each topology, see [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<span data-ttu-id="a0a35-107">有关特定于 Configuration Manager 集成拓扑的其他配置，请参阅 [MBAM 支持的 Configuration Manager 版本](#bkmk-cm-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-107">For additional configurations that are specific to the Configuration Manager Integration topology, see [Versions of Configuration Manager that MBAM supports](#bkmk-cm-ramreqs).</span></span>

**<span data-ttu-id="a0a35-108">注意</span><span class="sxs-lookup"><span data-stu-id="a0a35-108">Note</span></span>**  
<span data-ttu-id="a0a35-109">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="a0a35-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="a0a35-110">若要查找产品的支持时间表，请参阅 [支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="a0a35-111">有关 Microsoft 支持生命周期策略的其他信息，请参阅 [Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



## <span data-ttu-id="a0a35-112">MBAM 支持的语言</span><span class="sxs-lookup"><span data-stu-id="a0a35-112">MBAM Supported Languages</span></span>


<span data-ttu-id="a0a35-113">下表显示了 MBAM 客户端支持的语言 (包括 Self-Service 门户) 和 MBAM 2.5 和 MBAM 2.5 SP1 中的 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="a0a35-113">The following tables show the languages that are supported for the MBAM Client (including the Self-Service Portal) and the MBAM Server in MBAM 2.5 and MBAM 2.5 SP1.</span></span>

**<span data-ttu-id="a0a35-114">MBAM 2.5 SP1 中支持的语言：</span><span class="sxs-lookup"><span data-stu-id="a0a35-114">Supported Languages in MBAM 2.5 SP1:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-115">客户端语言</span><span class="sxs-lookup"><span data-stu-id="a0a35-115">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="a0a35-116">服务器语言</span><span class="sxs-lookup"><span data-stu-id="a0a35-116">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-117">捷克 (捷克共和国) CZ</span><span class="sxs-lookup"><span data-stu-id="a0a35-117">Czech (Czech Republic) cs-CZ</span></span></p>
<p><span data-ttu-id="a0a35-118">丹麦 (丹麦) da-深色</span><span class="sxs-lookup"><span data-stu-id="a0a35-118">Danish (Denmark) da-DK</span></span></p>
<p><span data-ttu-id="a0a35-119">荷兰语 (荷兰) nl-NL</span><span class="sxs-lookup"><span data-stu-id="a0a35-119">Dutch (Netherlands) nl-NL</span></span></p>
<p><span data-ttu-id="a0a35-120">英语 (美国) en-us</span><span class="sxs-lookup"><span data-stu-id="a0a35-120">English (United States) en-US</span></span></p>
<p><span data-ttu-id="a0a35-121">芬兰语 (芬兰) fi</span><span class="sxs-lookup"><span data-stu-id="a0a35-121">Finnish (Finland) fi-FI</span></span></p>
<p><span data-ttu-id="a0a35-122">法语 (法国) fr-fr</span><span class="sxs-lookup"><span data-stu-id="a0a35-122">French (France) fr-FR</span></span></p>
<p><span data-ttu-id="a0a35-123">德国 () de</span><span class="sxs-lookup"><span data-stu-id="a0a35-123">German (Germany) de-DE</span></span></p>
<p><span data-ttu-id="a0a35-124">希腊语 (希腊) el-GR</span><span class="sxs-lookup"><span data-stu-id="a0a35-124">Greek (Greece) el-GR</span></span></p>
<p><span data-ttu-id="a0a35-125">匈牙利语 (匈牙利) hu-HU</span><span class="sxs-lookup"><span data-stu-id="a0a35-125">Hungarian (Hungary) hu-HU</span></span></p>
<p><span data-ttu-id="a0a35-126">意大利 (意大利) it</span><span class="sxs-lookup"><span data-stu-id="a0a35-126">Italian (Italy) it-IT</span></span></p>
<p><span data-ttu-id="a0a35-127">日语 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="a0a35-127">Japanese (Japan) ja-JP</span></span></p>
<p><span data-ttu-id="a0a35-128">韩国 (韩国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="a0a35-128">Korean (Korea) ko-KR</span></span></p>
<p><span data-ttu-id="a0a35-129">挪威语、博克马尔语 (挪威) nb-否</span><span class="sxs-lookup"><span data-stu-id="a0a35-129">Norwegian, Bokmål (Norway) nb-NO</span></span></p>
<p><span data-ttu-id="a0a35-130">波兰语 (波兰) pl</span><span class="sxs-lookup"><span data-stu-id="a0a35-130">Polish (Poland) pl-PL</span></span></p>
<p><span data-ttu-id="a0a35-131">葡萄牙语 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="a0a35-131">Portuguese (Brazil) pt-BR</span></span></p>
<p><span data-ttu-id="a0a35-132">葡萄牙语 (葡萄牙) pt</span><span class="sxs-lookup"><span data-stu-id="a0a35-132">Portuguese (Portugal) pt-PT</span></span></p>
<p><span data-ttu-id="a0a35-133">俄语 (俄罗斯) ru</span><span class="sxs-lookup"><span data-stu-id="a0a35-133">Russian (Russia) ru-RU</span></span></p>
<p><span data-ttu-id="a0a35-134">斯洛伐克语 (斯洛伐克) sk-SK</span><span class="sxs-lookup"><span data-stu-id="a0a35-134">Slovak (Slovakia) sk-SK</span></span></p>
<p><span data-ttu-id="a0a35-135">西班牙 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="a0a35-135">Spanish (Spain) es-ES</span></span></p>
<p><span data-ttu-id="a0a35-136">瑞典语 (瑞典) sv-SE</span><span class="sxs-lookup"><span data-stu-id="a0a35-136">Swedish (Sweden) sv-SE</span></span></p>
<p><span data-ttu-id="a0a35-137">土耳其语 (土耳其) tr-TR</span><span class="sxs-lookup"><span data-stu-id="a0a35-137">Turkish (Turkey) tr-TR</span></span></p>
<p><span data-ttu-id="a0a35-138">斯洛文尼亚语 (斯洛文尼亚) sl-SI</span><span class="sxs-lookup"><span data-stu-id="a0a35-138">Slovenian (Slovenia) sl-SI</span></span></p>
<p><span data-ttu-id="a0a35-139">简体中文 (中国) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="a0a35-139">Simplified Chinese (PRC) zh-CN</span></span></p>
<p><span data-ttu-id="a0a35-140">繁体中文 (台湾) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="a0a35-140">Traditional Chinese (Taiwan) zh-TW</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a0a35-141">英语 (美国) en-us</span><span class="sxs-lookup"><span data-stu-id="a0a35-141">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="a0a35-142">法语 (法国) fr-fr</span><span class="sxs-lookup"><span data-stu-id="a0a35-142">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-143">德国 () de</span><span class="sxs-lookup"><span data-stu-id="a0a35-143">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="a0a35-144">意大利 (意大利) it</span><span class="sxs-lookup"><span data-stu-id="a0a35-144">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="a0a35-145">日语 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="a0a35-145">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="a0a35-146">韩国 (韩国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="a0a35-146">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-147">葡萄牙语 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="a0a35-147">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-148">俄语 (俄罗斯) ru</span><span class="sxs-lookup"><span data-stu-id="a0a35-148">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="a0a35-149">西班牙 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="a0a35-149">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="a0a35-150">简体中文 (中国) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="a0a35-150">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="a0a35-151">繁体中文 (台湾) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="a0a35-151">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="a0a35-152">MBAM 2.5 中支持的语言：</span><span class="sxs-lookup"><span data-stu-id="a0a35-152">Supported Languages in MBAM 2.5:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-153">客户端语言</span><span class="sxs-lookup"><span data-stu-id="a0a35-153">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="a0a35-154">服务器语言</span><span class="sxs-lookup"><span data-stu-id="a0a35-154">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="a0a35-155">英语 (美国) en-us</span><span class="sxs-lookup"><span data-stu-id="a0a35-155">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="a0a35-156">法语 (法国) fr-fr</span><span class="sxs-lookup"><span data-stu-id="a0a35-156">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-157">德国 () de</span><span class="sxs-lookup"><span data-stu-id="a0a35-157">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="a0a35-158">意大利 (意大利) it</span><span class="sxs-lookup"><span data-stu-id="a0a35-158">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="a0a35-159">日语 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="a0a35-159">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="a0a35-160">韩国 (韩国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="a0a35-160">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-161">葡萄牙语 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="a0a35-161">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-162">俄语 (俄罗斯) ru</span><span class="sxs-lookup"><span data-stu-id="a0a35-162">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="a0a35-163">西班牙 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="a0a35-163">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="a0a35-164">简体中文 (中国) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="a0a35-164">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="a0a35-165">繁体中文 (台湾) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="a0a35-165">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a0a35-166">英语 (美国) en-us</span><span class="sxs-lookup"><span data-stu-id="a0a35-166">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="a0a35-167">法语 (法国) fr-fr</span><span class="sxs-lookup"><span data-stu-id="a0a35-167">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-168">德国 () de</span><span class="sxs-lookup"><span data-stu-id="a0a35-168">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="a0a35-169">意大利 (意大利) it</span><span class="sxs-lookup"><span data-stu-id="a0a35-169">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="a0a35-170">日语 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="a0a35-170">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="a0a35-171">韩国 (韩国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="a0a35-171">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-172">葡萄牙语 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="a0a35-172">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="a0a35-173">俄语 (俄罗斯) ru</span><span class="sxs-lookup"><span data-stu-id="a0a35-173">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="a0a35-174">西班牙 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="a0a35-174">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="a0a35-175">简体中文 (中国) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="a0a35-175">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="a0a35-176">繁体中文 (台湾) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="a0a35-176">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="a0a35-177">MBAM 服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-177">MBAM Server system requirements</span></span>


### <span data-ttu-id="a0a35-178">MBAM 服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-178">MBAM Server operating system requirements</span></span>

<span data-ttu-id="a0a35-179">我们强烈建议你在同一操作系统上运行 MBAM 客户端和 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="a0a35-179">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="a0a35-180">例如，windows 10 windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="a0a35-180">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="a0a35-181">下表列出了 MBAM 服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0a35-181">The following table lists the operating systems that are supported for the MBAM Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-182">操作系统</span><span class="sxs-lookup"><span data-stu-id="a0a35-182">Operating system</span></span></th>
<th align="left"><span data-ttu-id="a0a35-183">版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-183">Edition</span></span></th>
<th align="left"><span data-ttu-id="a0a35-184">Service pack</span><span class="sxs-lookup"><span data-stu-id="a0a35-184">Service pack</span></span></th>
<th align="left"><span data-ttu-id="a0a35-185">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="a0a35-185">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-186">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a0a35-186">Windows Server 2019</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-187">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-187">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="a0a35-188">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-188">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-189">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a0a35-189">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-190">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-190">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="a0a35-191">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-191">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-192">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a0a35-192">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-193">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-193">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-194">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-194">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-195">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a0a35-195">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-196">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-196">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="a0a35-197">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-197">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-198">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a0a35-198">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-199">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-199">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-200">SP1</span><span class="sxs-lookup"><span data-stu-id="a0a35-200">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-201">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-201">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="a0a35-202">企业域必须包含至少一个 Windows Server 2008 (或更高版本) 域控制器。</span><span class="sxs-lookup"><span data-stu-id="a0a35-202">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span>

### <a href="" id="bkmk-stand-alone-ramreqs"></a><span data-ttu-id="a0a35-203">MBAM 服务器处理器、RAM 和磁盘空间要求-独立拓扑</span><span class="sxs-lookup"><span data-stu-id="a0a35-203">MBAM Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="a0a35-204">这些要求适用于 MBAM 独立拓扑。</span><span class="sxs-lookup"><span data-stu-id="a0a35-204">These requirements are for the MBAM Stand-alone topology.</span></span> <span data-ttu-id="a0a35-205">有关 Configuration Manager 集成拓扑的要求，请参阅 [MBAM 服务器处理器、RAM 和磁盘空间要求-配置管理器集成拓扑](#bkmk-cm-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-205">For the requirements for the Configuration Manager Integration topology, see [MBAM Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-206">硬件项</span><span class="sxs-lookup"><span data-stu-id="a0a35-206">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="a0a35-207">最低要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-207">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="a0a35-208">建议的要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-208">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-209">处理器</span><span class="sxs-lookup"><span data-stu-id="a0a35-209">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-210">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="a0a35-210">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-211">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-211">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-212">RAM</span><span class="sxs-lookup"><span data-stu-id="a0a35-212">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-213">8 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-213">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-214">12 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-214">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-215">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="a0a35-215">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-216">1 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-216">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-217">2 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-217">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-ramreqs"></a><span data-ttu-id="a0a35-218">MBAM 服务器处理器、RAM 和磁盘空间要求-配置管理器集成拓扑</span><span class="sxs-lookup"><span data-stu-id="a0a35-218">MBAM Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="a0a35-219">下表列出了使用 Configuration Manager 集成拓扑时 MBAM 服务器的服务器处理器、RAM 和磁盘空间要求。</span><span class="sxs-lookup"><span data-stu-id="a0a35-219">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span> <span data-ttu-id="a0a35-220">有关独立拓扑的要求，请参阅 [MBAM 服务器处理器、RAM 和磁盘空间要求-独立拓扑](#bkmk-stand-alone-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-220">For the requirements for the Stand-alone topology, see [MBAM Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-221">硬件项</span><span class="sxs-lookup"><span data-stu-id="a0a35-221">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="a0a35-222">最低要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-222">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="a0a35-223">建议的要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-223">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-224">处理器</span><span class="sxs-lookup"><span data-stu-id="a0a35-224">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-225">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="a0a35-225">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-226">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-226">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-227">RAM</span><span class="sxs-lookup"><span data-stu-id="a0a35-227">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-228">4 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-228">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-229">8 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-229">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-230">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="a0a35-230">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-231">1 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-231">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-232">2 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-232">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cmversions"></a><span data-ttu-id="a0a35-233">MBAM 支持的 Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-233">Versions of Configuration Manager that MBAM supports</span></span>

<span data-ttu-id="a0a35-234">MBAM 支持以下版本的 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="a0a35-234">MBAM supports the following versions of Configuration Manager.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-235">支持的版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-235">Supported version</span></span></th>
<th align="left"><span data-ttu-id="a0a35-236">Service pack</span><span class="sxs-lookup"><span data-stu-id="a0a35-236">Service pack</span></span></th>
<th align="left"><span data-ttu-id="a0a35-237">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="a0a35-237">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-238">Microsoft System Center Configuration Manager (当前分支) ，最高为1902的版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-238">Microsoft System Center Configuration Manager (Current Branch), versions up to 1902</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-239">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-239">64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-240">Microsoft System Center Configuration Manager 1806</span><span class="sxs-lookup"><span data-stu-id="a0a35-240">Microsoft System Center Configuration Manager 1806</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-241">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-241">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-242">Microsoft System Center Configuration Manager (LTSB-版本 1606) </span><span class="sxs-lookup"><span data-stu-id="a0a35-242">Microsoft System Center Configuration Manager (LTSB - version 1606)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-243">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-243">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-244">Microsoft System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a0a35-244">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-245">SP1</span><span class="sxs-lookup"><span data-stu-id="a0a35-245">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-246">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-246">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-247">Microsoft System Center Configuration Manager 2007 R2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-247">Microsoft System Center Configuration Manager 2007 R2 or later</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-248">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-248">64-bit</span></span></p>

<span data-ttu-id="a0a35-249">&gt;<strong>注意 </strong> 虽然 Configuration Manager 2007 R2 为32位，但必须在64位操作系统上安装它和 SQL Server 才能匹配64位 MBAM 软件。</span><span class="sxs-lookup"><span data-stu-id="a0a35-249">&gt;<strong>Note</strong> Although Configuration Manager 2007 R2 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span>
</td>
</tr>
</tbody>
</table>



<span data-ttu-id="a0a35-250">有关 Configuration Manager 服务器支持的配置的列表，请参阅适用于你正在使用的 Configuration Manager 版本的相应 TechNet 文档。</span><span class="sxs-lookup"><span data-stu-id="a0a35-250">For a list of supported configurations for the Configuration Manager Server, see the appropriate TechNet documentation for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="a0a35-251">MBAM 配置管理器服务器没有其他系统要求。</span><span class="sxs-lookup"><span data-stu-id="a0a35-251">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="a0a35-252">SQL Server 数据库要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-252">SQL Server database requirements</span></span>

<span data-ttu-id="a0a35-253">下表列出了 MBAM 服务器功能支持的 Microsoft SQL Server 版本，其中包括恢复数据库、合规性和审核数据库以及报表功能。</span><span class="sxs-lookup"><span data-stu-id="a0a35-253">The following table lists the Microsoft SQL Server versions that are supported for the MBAM Server features, which include the Recovery Database, Compliance and Audit Database, and the Reports feature.</span></span> <span data-ttu-id="a0a35-254">所需版本适用于独立版或 Configuration Manager 集成拓扑。</span><span class="sxs-lookup"><span data-stu-id="a0a35-254">The required versions apply to the Stand-alone or the Configuration Manager Integration topologies.</span></span>

<span data-ttu-id="a0a35-255">必须以 **sql \ _Latin1 \ _General \ _CP1 _CI \ _AS** 排序规则安装 sql Server。</span><span class="sxs-lookup"><span data-stu-id="a0a35-255">You must install SQL Server with the **SQL\_Latin1\_General\_CP1\_CI\_AS** collation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-256">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-256">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="a0a35-257">版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-257">Edition</span></span></th>
<th align="left"><span data-ttu-id="a0a35-258">Service pack</span><span class="sxs-lookup"><span data-stu-id="a0a35-258">Service pack</span></span></th>
<th align="left"><span data-ttu-id="a0a35-259">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="a0a35-259">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-260">Microsoft SQL Server 2019</span><span class="sxs-lookup"><span data-stu-id="a0a35-260">Microsoft SQL Server 2019</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-261">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-261">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-262">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-262">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-263">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="a0a35-263">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-264">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-264">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-265">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-265">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-266">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="a0a35-266">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-267">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-267">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-268">SP1</span><span class="sxs-lookup"><span data-stu-id="a0a35-268">SP1</span></span></p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p><span data-ttu-id="a0a35-269">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-269">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-270">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a0a35-270">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-271">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-271">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-272">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="a0a35-272">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-273">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-273">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-274">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="a0a35-274">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-275">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-275">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-276">又</span><span class="sxs-lookup"><span data-stu-id="a0a35-276">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-277">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-277">64-bit</span></span></p></td>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-278">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a0a35-278">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-279">Standard 或 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a0a35-279">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-280">又</span><span class="sxs-lookup"><span data-stu-id="a0a35-280">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-281">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-281">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

**<span data-ttu-id="a0a35-282">注意</span><span class="sxs-lookup"><span data-stu-id="a0a35-282">Note</span></span>**  
<span data-ttu-id="a0a35-283">MBAM 具有最高支持的兼容性级别140。</span><span class="sxs-lookup"><span data-stu-id="a0a35-283">MBAM has a maximum supported compatibility level of 140.</span></span> <span data-ttu-id="a0a35-284">在 SQL Server 2019 上创建的新数据库的默认兼容级别是150，在创建数据库之后，需要使用 ALTER DATABASE 命令将其更改为140或更低。</span><span class="sxs-lookup"><span data-stu-id="a0a35-284">The default compatibility level for new databases created on SQL Server 2019 is 150 which will need to be altered to 140 or lower, using the ALTER DATABASE command, after the database has been created.</span></span> <span data-ttu-id="a0a35-285">从 SQL server 2017 或更低版本迁移的现有数据库将保持其以前的兼容级别，无需更改。</span><span class="sxs-lookup"><span data-stu-id="a0a35-285">Existing databases migrated from SQL server 2017 or below will remain at their previous compatibility level and do not need to be altered.</span></span>

<span data-ttu-id="a0a35-286">为了支持 SQL 2016，您必须安装 MDOP 的三月2017服务版本 https://www.microsoft.com/download/details.aspx?id=54967  ，并支持 SQL 2017 必须安装用于 mdop 的2018年7月的服务发布 https://www.microsoft.com/download/details.aspx?id=57157 。</span><span class="sxs-lookup"><span data-stu-id="a0a35-286">In order to support SQL 2016 you must install the March 2017 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=54967  and to support SQL 2017 you must install the July 2018 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=57157.</span></span> <span data-ttu-id="a0a35-287">通常，通过始终使用最近的服务更新保持最新，因为它还包括所有缺陷修复和新功能。</span><span class="sxs-lookup"><span data-stu-id="a0a35-287">In general stay current by always using the most recent servicing update as it also includes all bugfixes and new features.</span></span>


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a><span data-ttu-id="a0a35-288">SQL Server 处理器、RAM 和磁盘空间要求-独立拓扑</span><span class="sxs-lookup"><span data-stu-id="a0a35-288">SQL Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="a0a35-289">下表列出了使用独立拓扑时所推荐的 SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求。</span><span class="sxs-lookup"><span data-stu-id="a0a35-289">The following table lists the recommended server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Stand-alone topology.</span></span> <span data-ttu-id="a0a35-290">将这些要求用作指南。</span><span class="sxs-lookup"><span data-stu-id="a0a35-290">Use these requirements as a guide.</span></span> <span data-ttu-id="a0a35-291">特定要求将根据您的企业中支持的客户端计算机的数量而有所不同。</span><span class="sxs-lookup"><span data-stu-id="a0a35-291">Your specific requirements will vary based on the number of client computers you are supporting in your enterprise.</span></span> <span data-ttu-id="a0a35-292">若要查看 Configuration Manager 集成拓扑的要求，请参阅 [SQL Server 处理器、RAM 和磁盘空间要求-配置管理器集成拓扑](#bkmk-cm-sql-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-292">To view the requirements for the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-sql-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-293">硬件项</span><span class="sxs-lookup"><span data-stu-id="a0a35-293">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="a0a35-294">最低要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-294">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="a0a35-295">建议的要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-295">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-296">处理器</span><span class="sxs-lookup"><span data-stu-id="a0a35-296">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-297">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="a0a35-297">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-298">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-298">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-299">RAM</span><span class="sxs-lookup"><span data-stu-id="a0a35-299">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-300">8 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-300">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-301">12 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-301">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-302">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="a0a35-302">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-303">5 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-303">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-304">5 GB 或以上</span><span class="sxs-lookup"><span data-stu-id="a0a35-304">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-sql-ramreqs"></a><span data-ttu-id="a0a35-305">SQL Server 处理器、RAM 和磁盘空间要求-配置管理器集成拓扑</span><span class="sxs-lookup"><span data-stu-id="a0a35-305">SQL Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="a0a35-306">下表列出了使用 Configuration Manager 集成拓扑时 Microsoft SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求，请参阅 [SQL Server 处理器、RAM 和磁盘空间要求-独立拓扑](#bkmk-sql-stand-alone-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-306">The following table lists the server processor, RAM, and disk space requirements for the Microsoft SQL Server computer when you are using the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-sql-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-307">硬件项</span><span class="sxs-lookup"><span data-stu-id="a0a35-307">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="a0a35-308">最低要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-308">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="a0a35-309">建议的要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-309">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-310">处理器</span><span class="sxs-lookup"><span data-stu-id="a0a35-310">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-311">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="a0a35-311">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-312">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-312">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-313">RAM</span><span class="sxs-lookup"><span data-stu-id="a0a35-313">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-314">4 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-314">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-315">8 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-315">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-316">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="a0a35-316">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-317">5 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-317">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-318">5 GB</span><span class="sxs-lookup"><span data-stu-id="a0a35-318">5 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="a0a35-319">MBAM 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-319">MBAM Client system requirements</span></span>


### <span data-ttu-id="a0a35-320">客户端操作系统要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-320">Client operating system requirements</span></span>

<span data-ttu-id="a0a35-321">我们强烈建议你在同一操作系统上运行 MBAM 客户端和 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="a0a35-321">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="a0a35-322">例如，windows 10 windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="a0a35-322">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="a0a35-323">下表列出了 MBAM 客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0a35-323">The following table lists the operating systems that are supported for MBAM Client installation.</span></span> <span data-ttu-id="a0a35-324">相同的要求适用于独立和 Configuration Manager 集成拓扑。</span><span class="sxs-lookup"><span data-stu-id="a0a35-324">The same requirements apply to the Stand-alone and the Configuration Manager Integration topologies.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-325">操作系统</span><span class="sxs-lookup"><span data-stu-id="a0a35-325">Operating system</span></span></th>
<th align="left"><span data-ttu-id="a0a35-326">版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-326">Edition</span></span></th>
<th align="left"><span data-ttu-id="a0a35-327">Service pack</span><span class="sxs-lookup"><span data-stu-id="a0a35-327">Service pack</span></span></th>
<th align="left"><span data-ttu-id="a0a35-328">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="a0a35-328">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
    <td align="left"><p><span data-ttu-id="a0a35-329">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="a0a35-329">Windows 10 IoT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a0a35-330">企业</span><span class="sxs-lookup"><span data-stu-id="a0a35-330">Enterprise</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p><span data-ttu-id="a0a35-331">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-331">32-bit or 64-bit</span></span></p></td>
</tr><br/><tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-332">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a0a35-332">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-333">企业</span><span class="sxs-lookup"><span data-stu-id="a0a35-333">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-334">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-334">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-335">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a0a35-335">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-336">企业</span><span class="sxs-lookup"><span data-stu-id="a0a35-336">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-337">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-337">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-338">Windows 7</span><span class="sxs-lookup"><span data-stu-id="a0a35-338">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-339">企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="a0a35-339">Enterprise or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-340">SP1</span><span class="sxs-lookup"><span data-stu-id="a0a35-340">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-341">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-341">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-342">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="a0a35-342">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-343">Windows 8.1 和 Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="a0a35-343">Windows 8.1 and Windows 10 Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-344">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-344">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="a0a35-345">客户端 RAM 要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-345">Client RAM requirements</span></span>

<span data-ttu-id="a0a35-346">没有特定于 MBAM 客户端安装的 RAM 要求。</span><span class="sxs-lookup"><span data-stu-id="a0a35-346">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="a0a35-347">MBAM 组策略系统要求</span><span class="sxs-lookup"><span data-stu-id="a0a35-347">MBAM Group Policy system requirements</span></span>


<span data-ttu-id="a0a35-348">下表列出了 MBAM 组策略模板安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0a35-348">The following table lists the operating systems that are supported for MBAM Group Policy Templates installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a0a35-349">操作系统</span><span class="sxs-lookup"><span data-stu-id="a0a35-349">Operating system</span></span></th>
<th align="left"><span data-ttu-id="a0a35-350">版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-350">Edition</span></span></th>
<th align="left"><span data-ttu-id="a0a35-351">Service pack</span><span class="sxs-lookup"><span data-stu-id="a0a35-351">Service pack</span></span></th>
<th align="left"><span data-ttu-id="a0a35-352">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="a0a35-352">System architecture</span></span></th>
</tr>
</thead>
<tbody>
 <tr class="even">
      <td align="left"><p><span data-ttu-id="a0a35-353">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="a0a35-353">Windows 10 IoT</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a0a35-354">企业</span><span class="sxs-lookup"><span data-stu-id="a0a35-354">Enterprise</span></span></p></td>
      <td align="left"><p></p></td>
      <td align="left"><p><span data-ttu-id="a0a35-355">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-355">32-bit or 64-bit</span></span></p></td>
 </tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-356">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a0a35-356">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-357">企业</span><span class="sxs-lookup"><span data-stu-id="a0a35-357">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-358">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-358">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-359">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a0a35-359">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-360">企业</span><span class="sxs-lookup"><span data-stu-id="a0a35-360">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-361">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-361">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-362">Windows 7</span><span class="sxs-lookup"><span data-stu-id="a0a35-362">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-363">企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="a0a35-363">Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-364">SP1</span><span class="sxs-lookup"><span data-stu-id="a0a35-364">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-365">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-365">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-366">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a0a35-366">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-367">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-367">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-368">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-368">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a0a35-369">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a0a35-369">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-370">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-370">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="a0a35-371">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-371">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a0a35-372">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a0a35-372">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-373">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="a0a35-373">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-374">SP1</span><span class="sxs-lookup"><span data-stu-id="a0a35-374">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a0a35-375">64 位</span><span class="sxs-lookup"><span data-stu-id="a0a35-375">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="a0a35-376">Azure IaaS 中的 MBAM</span><span class="sxs-lookup"><span data-stu-id="a0a35-376">MBAM In Azure IaaS</span></span>

<span data-ttu-id="a0a35-377">MBAM 服务器可以作为服务部署在以上列出的任何受支持的操作系统版本上的服务 (IaaS) ，连接到托管在本地的 Active Directory 或也托管在 Azure IaaS 中的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="a0a35-377">The MBAM server can be deployed in Azure Infrastructure as a Service (IaaS) on any of the supported OS versions listed above, connecting to an Active Directory hosted on premises or an Active Directory also hosted in Azure IaaS.</span></span>  <span data-ttu-id="a0a35-378">[此处](https://msdn.microsoft.com/library/azure/jj156090.aspx)提供了在 Azure IaaS 上设置和配置 Active Directory 的文档。</span><span class="sxs-lookup"><span data-stu-id="a0a35-378">Documentation for setting up and configuring Active Directory on Azure IaaS is [here](https://msdn.microsoft.com/library/azure/jj156090.aspx).</span></span>

<span data-ttu-id="a0a35-379">MBAM 客户端在虚拟机上不受支持，并且在 Azure IaaS 上也不受支持。</span><span class="sxs-lookup"><span data-stu-id="a0a35-379">The MBAM client is not supported on virtual machines and is also not supported on Azure IaaS.</span></span>


## <span data-ttu-id="a0a35-380">服务版本</span><span class="sxs-lookup"><span data-stu-id="a0a35-380">Service releases</span></span> 

- [<span data-ttu-id="a0a35-381">2016年4月的修复程序</span><span class="sxs-lookup"><span data-stu-id="a0a35-381">April 2016 hotfix</span></span>](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="a0a35-382">2016年9月</span><span class="sxs-lookup"><span data-stu-id="a0a35-382">September 2016</span></span>](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [<span data-ttu-id="a0a35-383">2016 年 12 月</span><span class="sxs-lookup"><span data-stu-id="a0a35-383">December 2016</span></span>](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [<span data-ttu-id="a0a35-384">2017 年 3 月</span><span class="sxs-lookup"><span data-stu-id="a0a35-384">March 2017</span></span>](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [<span data-ttu-id="a0a35-385">2017 年 6 月</span><span class="sxs-lookup"><span data-stu-id="a0a35-385">June 2017</span></span>](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="a0a35-386">2017 年 9 月</span><span class="sxs-lookup"><span data-stu-id="a0a35-386">September 2017</span></span>](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [<span data-ttu-id="a0a35-387">2018 年 3 月</span><span class="sxs-lookup"><span data-stu-id="a0a35-387">March 2018</span></span>](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="a0a35-388">2018年7月</span><span class="sxs-lookup"><span data-stu-id="a0a35-388">July 2018</span></span>](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="a0a35-389">五月2019</span><span class="sxs-lookup"><span data-stu-id="a0a35-389">May 2019</span></span>](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## <span data-ttu-id="a0a35-390">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0a35-390">Related topics</span></span>


[<span data-ttu-id="a0a35-391">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="a0a35-391">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="a0a35-392">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="a0a35-392">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)




## <span data-ttu-id="a0a35-393">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="a0a35-393">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="a0a35-394">在 [此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="a0a35-394">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="a0a35-395">对于 MBAM 问题，请使用 [MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="a0a35-395">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




