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
ms.openlocfilehash: 262cd8c259dc37b291cdaf02caf0e20b7515d38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803459"
---
# <span data-ttu-id="0c7d8-103">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="0c7d8-103">MBAM 2.5 Supported Configurations</span></span>


<span data-ttu-id="0c7d8-104">你可以在独立拓扑中或在与 System Center Configuration Manager 集成 MBAM 的 Configuration Manager 集成拓扑中运行 Microsoft BitLocker 管理和监视（MBAM）2.5。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-104">You can run Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in a Stand-alone topology or in a Configuration Manager Integration topology that integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="0c7d8-105">如果对生产环境中的任一拓扑使用推荐的配置，MBAM 最多支持 500000 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-105">If you use the recommended configuration for either topology in a production environment, MBAM supports up to 500,000 MBAM clients.</span></span> <span data-ttu-id="0c7d8-106">有关在每个服务器上为每个拓扑配置的推荐体系结构和功能的信息，请参阅[MBAM 2.5 的高级体系结构](high-level-architecture-for-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-106">For information about the recommended architecture and features that are configured on each server for each topology, see [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<span data-ttu-id="0c7d8-107">有关特定于 Configuration Manager 集成拓扑的其他配置，请参阅[MBAM 支持的 Configuration Manager 版本](#bkmk-cm-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-107">For additional configurations that are specific to the Configuration Manager Integration topology, see [Versions of Configuration Manager that MBAM supports](#bkmk-cm-ramreqs).</span></span>

**<span data-ttu-id="0c7d8-108">注意</span><span class="sxs-lookup"><span data-stu-id="0c7d8-108">Note</span></span>**  
<span data-ttu-id="0c7d8-109">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="0c7d8-110">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="0c7d8-111">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



## <span data-ttu-id="0c7d8-112">MBAM 支持的语言</span><span class="sxs-lookup"><span data-stu-id="0c7d8-112">MBAM Supported Languages</span></span>


<span data-ttu-id="0c7d8-113">下表显示了 MBAM 2.5 和 MBAM 2.5 SP1 中的 MBAM 客户端（包括自助门户）和 MBAM 服务器支持的语言。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-113">The following tables show the languages that are supported for the MBAM Client (including the Self-Service Portal) and the MBAM Server in MBAM 2.5 and MBAM 2.5 SP1.</span></span>

**<span data-ttu-id="0c7d8-114">MBAM 2.5 SP1 中支持的语言：</span><span class="sxs-lookup"><span data-stu-id="0c7d8-114">Supported Languages in MBAM 2.5 SP1:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-115">客户端语言</span><span class="sxs-lookup"><span data-stu-id="0c7d8-115">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-116">服务器语言</span><span class="sxs-lookup"><span data-stu-id="0c7d8-116">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-117">捷克语（捷克共和国） cs-CZ</span><span class="sxs-lookup"><span data-stu-id="0c7d8-117">Czech (Czech Republic) cs-CZ</span></span></p>
<p><span data-ttu-id="0c7d8-118">丹麦语（丹麦） da-深色</span><span class="sxs-lookup"><span data-stu-id="0c7d8-118">Danish (Denmark) da-DK</span></span></p>
<p><span data-ttu-id="0c7d8-119">荷兰语（荷兰） nl-NL</span><span class="sxs-lookup"><span data-stu-id="0c7d8-119">Dutch (Netherlands) nl-NL</span></span></p>
<p><span data-ttu-id="0c7d8-120">英语（美国） en-us</span><span class="sxs-lookup"><span data-stu-id="0c7d8-120">English (United States) en-US</span></span></p>
<p><span data-ttu-id="0c7d8-121">芬兰语（芬兰） wlan</span><span class="sxs-lookup"><span data-stu-id="0c7d8-121">Finnish (Finland) fi-FI</span></span></p>
<p><span data-ttu-id="0c7d8-122">法语（法国） fr-fr</span><span class="sxs-lookup"><span data-stu-id="0c7d8-122">French (France) fr-FR</span></span></p>
<p><span data-ttu-id="0c7d8-123">德语（德国） de</span><span class="sxs-lookup"><span data-stu-id="0c7d8-123">German (Germany) de-DE</span></span></p>
<p><span data-ttu-id="0c7d8-124">希腊语（希腊） el-GR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-124">Greek (Greece) el-GR</span></span></p>
<p><span data-ttu-id="0c7d8-125">匈牙利语（匈牙利） hu-HU</span><span class="sxs-lookup"><span data-stu-id="0c7d8-125">Hungarian (Hungary) hu-HU</span></span></p>
<p><span data-ttu-id="0c7d8-126">意大利语（意大利） it</span><span class="sxs-lookup"><span data-stu-id="0c7d8-126">Italian (Italy) it-IT</span></span></p>
<p><span data-ttu-id="0c7d8-127">日语（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="0c7d8-127">Japanese (Japan) ja-JP</span></span></p>
<p><span data-ttu-id="0c7d8-128">朝鲜语（韩国） ko-KR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-128">Korean (Korea) ko-KR</span></span></p>
<p><span data-ttu-id="0c7d8-129">挪威语、博克马尔语（挪威） nb-否</span><span class="sxs-lookup"><span data-stu-id="0c7d8-129">Norwegian, Bokmål (Norway) nb-NO</span></span></p>
<p><span data-ttu-id="0c7d8-130">波兰语（波兰） pl-PL</span><span class="sxs-lookup"><span data-stu-id="0c7d8-130">Polish (Poland) pl-PL</span></span></p>
<p><span data-ttu-id="0c7d8-131">葡萄牙语（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-131">Portuguese (Brazil) pt-BR</span></span></p>
<p><span data-ttu-id="0c7d8-132">葡萄牙语（葡萄牙） pt</span><span class="sxs-lookup"><span data-stu-id="0c7d8-132">Portuguese (Portugal) pt-PT</span></span></p>
<p><span data-ttu-id="0c7d8-133">俄语（俄罗斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="0c7d8-133">Russian (Russia) ru-RU</span></span></p>
<p><span data-ttu-id="0c7d8-134">斯洛伐克语（斯洛伐克） sk-SK</span><span class="sxs-lookup"><span data-stu-id="0c7d8-134">Slovak (Slovakia) sk-SK</span></span></p>
<p><span data-ttu-id="0c7d8-135">西班牙语（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="0c7d8-135">Spanish (Spain) es-ES</span></span></p>
<p><span data-ttu-id="0c7d8-136">瑞典语（瑞典） sv-SE</span><span class="sxs-lookup"><span data-stu-id="0c7d8-136">Swedish (Sweden) sv-SE</span></span></p>
<p><span data-ttu-id="0c7d8-137">土耳其语（土耳其） tr-TR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-137">Turkish (Turkey) tr-TR</span></span></p>
<p><span data-ttu-id="0c7d8-138">斯洛文尼亚语（斯洛文尼亚） sl-SI</span><span class="sxs-lookup"><span data-stu-id="0c7d8-138">Slovenian (Slovenia) sl-SI</span></span></p>
<p><span data-ttu-id="0c7d8-139">简体中文版简体中文（PRC） zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="0c7d8-139">Simplified Chinese (PRC) zh-CN</span></span></p>
<p><span data-ttu-id="0c7d8-140">繁体中文（台湾） zh-cn&platform-幼圆</span><span class="sxs-lookup"><span data-stu-id="0c7d8-140">Traditional Chinese (Taiwan) zh-TW</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0c7d8-141">英语（美国） en-us</span><span class="sxs-lookup"><span data-stu-id="0c7d8-141">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-142">法语（法国） fr-fr</span><span class="sxs-lookup"><span data-stu-id="0c7d8-142">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-143">德语（德国） de</span><span class="sxs-lookup"><span data-stu-id="0c7d8-143">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-144">意大利语（意大利） it</span><span class="sxs-lookup"><span data-stu-id="0c7d8-144">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-145">日语（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="0c7d8-145">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-146">朝鲜语（韩国） ko-KR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-146">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-147">葡萄牙语（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-147">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-148">俄语（俄罗斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="0c7d8-148">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-149">西班牙语（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="0c7d8-149">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-150">简体中文版简体中文（PRC） zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="0c7d8-150">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-151">繁体中文（台湾） zh-cn&platform-幼圆</span><span class="sxs-lookup"><span data-stu-id="0c7d8-151">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="0c7d8-152">MBAM 2.5 中支持的语言：</span><span class="sxs-lookup"><span data-stu-id="0c7d8-152">Supported Languages in MBAM 2.5:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-153">客户端语言</span><span class="sxs-lookup"><span data-stu-id="0c7d8-153">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-154">服务器语言</span><span class="sxs-lookup"><span data-stu-id="0c7d8-154">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="0c7d8-155">英语（美国） en-us</span><span class="sxs-lookup"><span data-stu-id="0c7d8-155">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-156">法语（法国） fr-fr</span><span class="sxs-lookup"><span data-stu-id="0c7d8-156">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-157">德语（德国） de</span><span class="sxs-lookup"><span data-stu-id="0c7d8-157">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-158">意大利语（意大利） it</span><span class="sxs-lookup"><span data-stu-id="0c7d8-158">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-159">日语（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="0c7d8-159">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-160">朝鲜语（韩国） ko-KR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-160">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-161">葡萄牙语（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-161">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-162">俄语（俄罗斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="0c7d8-162">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-163">西班牙语（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="0c7d8-163">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-164">简体中文版简体中文（PRC） zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="0c7d8-164">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-165">繁体中文（台湾） zh-cn&platform-幼圆</span><span class="sxs-lookup"><span data-stu-id="0c7d8-165">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0c7d8-166">英语（美国） en-us</span><span class="sxs-lookup"><span data-stu-id="0c7d8-166">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-167">法语（法国） fr-fr</span><span class="sxs-lookup"><span data-stu-id="0c7d8-167">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-168">德语（德国） de</span><span class="sxs-lookup"><span data-stu-id="0c7d8-168">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-169">意大利语（意大利） it</span><span class="sxs-lookup"><span data-stu-id="0c7d8-169">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-170">日语（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="0c7d8-170">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-171">朝鲜语（韩国） ko-KR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-171">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-172">葡萄牙语（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="0c7d8-172">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-173">俄语（俄罗斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="0c7d8-173">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-174">西班牙语（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="0c7d8-174">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-175">简体中文版简体中文（PRC） zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="0c7d8-175">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="0c7d8-176">繁体中文（台湾） zh-cn&platform-幼圆</span><span class="sxs-lookup"><span data-stu-id="0c7d8-176">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="0c7d8-177">MBAM 服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-177">MBAM Server system requirements</span></span>


### <span data-ttu-id="0c7d8-178">MBAM 服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-178">MBAM Server operating system requirements</span></span>

<span data-ttu-id="0c7d8-179">我们强烈建议你在同一操作系统上运行 MBAM 客户端和 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-179">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="0c7d8-180">例如，windows 10 windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-180">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="0c7d8-181">下表列出了 MBAM 服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-181">The following table lists the operating systems that are supported for the MBAM Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-182">操作系统</span><span class="sxs-lookup"><span data-stu-id="0c7d8-182">Operating system</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-183">版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-183">Edition</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-184">Service pack</span><span class="sxs-lookup"><span data-stu-id="0c7d8-184">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-185">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0c7d8-185">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-186">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0c7d8-186">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-187">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-187">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="0c7d8-188">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-188">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-189">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0c7d8-189">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-190">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-190">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-191">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-191">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-192">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0c7d8-192">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-193">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-193">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="0c7d8-194">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-194">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-195">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0c7d8-195">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-196">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-196">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-197">SP1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-197">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-198">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-198">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="0c7d8-199">企业域必须包含至少一个 Windows Server 2008 （或更高版本）域控制器。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-199">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span>

### <a href="" id="bkmk-stand-alone-ramreqs"></a><span data-ttu-id="0c7d8-200">MBAM 服务器处理器、RAM 和磁盘空间要求-独立拓扑</span><span class="sxs-lookup"><span data-stu-id="0c7d8-200">MBAM Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="0c7d8-201">这些要求适用于 MBAM 独立拓扑。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-201">These requirements are for the MBAM Stand-alone topology.</span></span> <span data-ttu-id="0c7d8-202">有关 Configuration Manager 集成拓扑的要求，请参阅[MBAM 服务器处理器、RAM 和磁盘空间要求-配置管理器集成拓扑](#bkmk-cm-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-202">For the requirements for the Configuration Manager Integration topology, see [MBAM Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-203">硬件项</span><span class="sxs-lookup"><span data-stu-id="0c7d8-203">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-204">最低要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-204">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-205">建议的要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-205">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-206">处理者</span><span class="sxs-lookup"><span data-stu-id="0c7d8-206">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-207">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="0c7d8-207">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-208">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-208">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-209">RAM</span><span class="sxs-lookup"><span data-stu-id="0c7d8-209">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-210">8 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-210">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-211">12 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-211">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-212">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="0c7d8-212">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-213">1 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-213">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-214">2 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-214">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-ramreqs"></a><span data-ttu-id="0c7d8-215">MBAM 服务器处理器、RAM 和磁盘空间要求-配置管理器集成拓扑</span><span class="sxs-lookup"><span data-stu-id="0c7d8-215">MBAM Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="0c7d8-216">下表列出了使用 Configuration Manager 集成拓扑时 MBAM 服务器的服务器处理器、RAM 和磁盘空间要求。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-216">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span> <span data-ttu-id="0c7d8-217">有关独立拓扑的要求，请参阅[MBAM 服务器处理器、RAM 和磁盘空间要求-独立拓扑](#bkmk-stand-alone-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-217">For the requirements for the Stand-alone topology, see [MBAM Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-218">硬件项</span><span class="sxs-lookup"><span data-stu-id="0c7d8-218">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-219">最低要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-219">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-220">建议的要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-220">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-221">处理者</span><span class="sxs-lookup"><span data-stu-id="0c7d8-221">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-222">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="0c7d8-222">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-223">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-223">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-224">RAM</span><span class="sxs-lookup"><span data-stu-id="0c7d8-224">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-225">4 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-225">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-226">8 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-226">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-227">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="0c7d8-227">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-228">1 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-228">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-229">2 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-229">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cmversions"></a><span data-ttu-id="0c7d8-230">MBAM 支持的 Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-230">Versions of Configuration Manager that MBAM supports</span></span>

<span data-ttu-id="0c7d8-231">MBAM 支持以下版本的 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-231">MBAM supports the following versions of Configuration Manager.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-232">支持的版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-232">Supported version</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-233">Service pack</span><span class="sxs-lookup"><span data-stu-id="0c7d8-233">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-234">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0c7d8-234">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-235">Microsoft System Center Configuration Manager （当前分支），最高为1902的版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-235">Microsoft System Center Configuration Manager (Current Branch), versions up to 1902</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-236">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-236">64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-237">Microsoft System Center Configuration Manager 1806</span><span class="sxs-lookup"><span data-stu-id="0c7d8-237">Microsoft System Center Configuration Manager 1806</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-238">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-238">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-239">Microsoft System Center Configuration Manager （LTSB-版本1606）</span><span class="sxs-lookup"><span data-stu-id="0c7d8-239">Microsoft System Center Configuration Manager (LTSB - version 1606)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-240">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-240">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-241">Microsoft System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0c7d8-241">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-242">SP1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-242">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-243">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-243">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-244">Microsoft System Center Configuration Manager 2007 R2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-244">Microsoft System Center Configuration Manager 2007 R2 or later</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-245">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-245">64-bit</span></span></p>

<span data-ttu-id="0c7d8-246">&gt;<strong>注意 </strong> 虽然 Configuration Manager 2007 R2 为32位，但必须在64位操作系统上安装它和 SQL Server 才能匹配64位 MBAM 软件。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-246">&gt;<strong>Note</strong> Although Configuration Manager 2007 R2 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span>
</td>
</tr>
</tbody>
</table>



<span data-ttu-id="0c7d8-247">有关 Configuration Manager 服务器支持的配置的列表，请参阅适用于你正在使用的 Configuration Manager 版本的相应 TechNet 文档。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-247">For a list of supported configurations for the Configuration Manager Server, see the appropriate TechNet documentation for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="0c7d8-248">MBAM 配置管理器服务器没有其他系统要求。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-248">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="0c7d8-249">SQL Server 数据库要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-249">SQL Server database requirements</span></span>

<span data-ttu-id="0c7d8-250">下表列出了 MBAM 服务器功能支持的 Microsoft SQL Server 版本，其中包括恢复数据库、合规性和审核数据库以及报表功能。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-250">The following table lists the Microsoft SQL Server versions that are supported for the MBAM Server features, which include the Recovery Database, Compliance and Audit Database, and the Reports feature.</span></span> <span data-ttu-id="0c7d8-251">所需版本适用于独立版或 Configuration Manager 集成拓扑。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-251">The required versions apply to the Stand-alone or the Configuration Manager Integration topologies.</span></span>

<span data-ttu-id="0c7d8-252">必须以**sql \ _Latin1 \ _General \ _CP1 _CI \ _AS**排序规则安装 sql Server。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-252">You must install SQL Server with the **SQL\_Latin1\_General\_CP1\_CI\_AS** collation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-253">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-253">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-254">版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-254">Edition</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-255">Service pack</span><span class="sxs-lookup"><span data-stu-id="0c7d8-255">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-256">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0c7d8-256">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-257">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="0c7d8-257">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-258">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-258">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-259">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-259">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-260">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="0c7d8-260">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-261">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-261">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-262">SP1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-262">SP1</span></span></p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p><span data-ttu-id="0c7d8-263">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-263">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-264">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0c7d8-264">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-265">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-265">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-266">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="0c7d8-266">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-267">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-267">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-268">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="0c7d8-268">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-269">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-269">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-270">又</span><span class="sxs-lookup"><span data-stu-id="0c7d8-270">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-271">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-271">64-bit</span></span></p></td>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-272">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0c7d8-272">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-273">Standard 或 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0c7d8-273">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-274">又</span><span class="sxs-lookup"><span data-stu-id="0c7d8-274">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-275">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-275">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

**<span data-ttu-id="0c7d8-276">注意</span><span class="sxs-lookup"><span data-stu-id="0c7d8-276">Note</span></span>**  
<span data-ttu-id="0c7d8-277">为了支持 SQL 2016，您必须安装 MDOP 的三月2017服务版本 https://www.microsoft.com/download/details.aspx?id=54967 ，并支持 SQL 2017 必须安装用于 mdop 的2018年7月的服务发布 https://www.microsoft.com/download/details.aspx?id=57157 。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-277">In order to support SQL 2016 you must install the March 2017 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=54967  and to support SQL 2017 you must install the July 2018 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=57157.</span></span> <span data-ttu-id="0c7d8-278">通常，通过始终使用最近的服务更新保持最新，因为它还包括所有缺陷修复和新功能。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-278">In general stay current by always using the most recent servicing update as it also includes all bugfixes and new features.</span></span>


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a><span data-ttu-id="0c7d8-279">SQL Server 处理器、RAM 和磁盘空间要求-独立拓扑</span><span class="sxs-lookup"><span data-stu-id="0c7d8-279">SQL Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="0c7d8-280">下表列出了使用独立拓扑时所推荐的 SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-280">The following table lists the recommended server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Stand-alone topology.</span></span> <span data-ttu-id="0c7d8-281">将这些要求用作指南。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-281">Use these requirements as a guide.</span></span> <span data-ttu-id="0c7d8-282">特定要求将根据您的企业中支持的客户端计算机的数量而有所不同。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-282">Your specific requirements will vary based on the number of client computers you are supporting in your enterprise.</span></span> <span data-ttu-id="0c7d8-283">若要查看 Configuration Manager 集成拓扑的要求，请参阅[SQL Server 处理器、RAM 和磁盘空间要求-配置管理器集成拓扑](#bkmk-cm-sql-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-283">To view the requirements for the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-sql-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-284">硬件项</span><span class="sxs-lookup"><span data-stu-id="0c7d8-284">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-285">最低要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-285">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-286">建议的要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-286">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-287">处理者</span><span class="sxs-lookup"><span data-stu-id="0c7d8-287">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-288">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="0c7d8-288">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-289">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-289">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-290">RAM</span><span class="sxs-lookup"><span data-stu-id="0c7d8-290">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-291">8 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-291">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-292">12 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-292">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-293">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="0c7d8-293">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-294">5 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-294">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-295">5 GB 或以上</span><span class="sxs-lookup"><span data-stu-id="0c7d8-295">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-sql-ramreqs"></a><span data-ttu-id="0c7d8-296">SQL Server 处理器、RAM 和磁盘空间要求-配置管理器集成拓扑</span><span class="sxs-lookup"><span data-stu-id="0c7d8-296">SQL Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="0c7d8-297">下表列出了使用 Configuration Manager 集成拓扑时 Microsoft SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求，请参阅[SQL Server 处理器、RAM 和磁盘空间要求-独立拓扑](#bkmk-sql-stand-alone-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-297">The following table lists the server processor, RAM, and disk space requirements for the Microsoft SQL Server computer when you are using the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-sql-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-298">硬件项</span><span class="sxs-lookup"><span data-stu-id="0c7d8-298">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-299">最低要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-299">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-300">建议的要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-300">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-301">处理者</span><span class="sxs-lookup"><span data-stu-id="0c7d8-301">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-302">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="0c7d8-302">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-303">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-303">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-304">RAM</span><span class="sxs-lookup"><span data-stu-id="0c7d8-304">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-305">4 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-305">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-306">8 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-306">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-307">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="0c7d8-307">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-308">5 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-308">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-309">5 GB</span><span class="sxs-lookup"><span data-stu-id="0c7d8-309">5 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="0c7d8-310">MBAM 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-310">MBAM Client system requirements</span></span>


### <span data-ttu-id="0c7d8-311">客户端操作系统要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-311">Client operating system requirements</span></span>

<span data-ttu-id="0c7d8-312">我们强烈建议你在同一操作系统上运行 MBAM 客户端和 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-312">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="0c7d8-313">例如，windows 10 windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-313">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="0c7d8-314">下表列出了 MBAM 客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-314">The following table lists the operating systems that are supported for MBAM Client installation.</span></span> <span data-ttu-id="0c7d8-315">相同的要求适用于独立和 Configuration Manager 集成拓扑。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-315">The same requirements apply to the Stand-alone and the Configuration Manager Integration topologies.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-316">操作系统</span><span class="sxs-lookup"><span data-stu-id="0c7d8-316">Operating system</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-317">版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-317">Edition</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-318">Service pack</span><span class="sxs-lookup"><span data-stu-id="0c7d8-318">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-319">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0c7d8-319">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
    <td align="left"><p><span data-ttu-id="0c7d8-320">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="0c7d8-320">Windows 10 IoT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0c7d8-321">企业</span><span class="sxs-lookup"><span data-stu-id="0c7d8-321">Enterprise</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p><span data-ttu-id="0c7d8-322">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-322">32-bit or 64-bit</span></span></p></td>
</tr><br/><tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0c7d8-323">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-324">企业</span><span class="sxs-lookup"><span data-stu-id="0c7d8-324">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-325">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-325">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-326">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-326">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-327">企业</span><span class="sxs-lookup"><span data-stu-id="0c7d8-327">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-328">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-328">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-329">Windows 7</span><span class="sxs-lookup"><span data-stu-id="0c7d8-329">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-330">企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="0c7d8-330">Enterprise or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-331">SP1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-331">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-332">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-332">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-333">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="0c7d8-333">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-334">Windows 8.1 和 Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="0c7d8-334">Windows 8.1 and Windows 10 Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-335">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-335">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="0c7d8-336">客户端 RAM 要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-336">Client RAM requirements</span></span>

<span data-ttu-id="0c7d8-337">没有特定于 MBAM 客户端安装的 RAM 要求。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-337">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="0c7d8-338">MBAM 组策略系统要求</span><span class="sxs-lookup"><span data-stu-id="0c7d8-338">MBAM Group Policy system requirements</span></span>


<span data-ttu-id="0c7d8-339">下表列出了 MBAM 组策略模板安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-339">The following table lists the operating systems that are supported for MBAM Group Policy Templates installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c7d8-340">操作系统</span><span class="sxs-lookup"><span data-stu-id="0c7d8-340">Operating system</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-341">版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-341">Edition</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-342">Service pack</span><span class="sxs-lookup"><span data-stu-id="0c7d8-342">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0c7d8-343">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0c7d8-343">System architecture</span></span></th>
</tr>
</thead>
<tbody>
 <tr class="even">
      <td align="left"><p><span data-ttu-id="0c7d8-344">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="0c7d8-344">Windows 10 IoT</span></span></p></td>
      <td align="left"><p><span data-ttu-id="0c7d8-345">企业</span><span class="sxs-lookup"><span data-stu-id="0c7d8-345">Enterprise</span></span></p></td>
      <td align="left"><p></p></td>
      <td align="left"><p><span data-ttu-id="0c7d8-346">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-346">32-bit or 64-bit</span></span></p></td>
 </tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-347">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0c7d8-347">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-348">企业</span><span class="sxs-lookup"><span data-stu-id="0c7d8-348">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-349">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-349">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-350">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-350">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-351">企业</span><span class="sxs-lookup"><span data-stu-id="0c7d8-351">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-352">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-352">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-353">Windows 7</span><span class="sxs-lookup"><span data-stu-id="0c7d8-353">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-354">企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="0c7d8-354">Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-355">SP1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-355">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-356">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-356">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-357">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0c7d8-357">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-358">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-358">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-359">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-359">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c7d8-360">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0c7d8-360">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-361">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-361">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-362">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-362">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c7d8-363">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0c7d8-363">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-364">标准版、企业版或数据中心</span><span class="sxs-lookup"><span data-stu-id="0c7d8-364">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-365">SP1</span><span class="sxs-lookup"><span data-stu-id="0c7d8-365">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c7d8-366">64 位</span><span class="sxs-lookup"><span data-stu-id="0c7d8-366">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="0c7d8-367">Azure IaaS 中的 MBAM</span><span class="sxs-lookup"><span data-stu-id="0c7d8-367">MBAM In Azure IaaS</span></span>

<span data-ttu-id="0c7d8-368">MBAM 服务器可以在上述任何支持的操作系统版本上以服务（IaaS）的形式部署在上述任何支持的操作系统版本上，连接到在本地托管的 Active Directory 或也托管在 Azure IaaS 中的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-368">The MBAM server can be deployed in Azure Infrastructure as a Service (IaaS) on any of the supported OS versions listed above, connecting to an Active Directory hosted on premises or an Active Directory also hosted in Azure IaaS.</span></span>  <span data-ttu-id="0c7d8-369">[此处](https://msdn.microsoft.com/library/azure/jj156090.aspx)提供了在 Azure IaaS 上设置和配置 Active Directory 的文档。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-369">Documentation for setting up and configuring Active Directory on Azure IaaS is [here](https://msdn.microsoft.com/library/azure/jj156090.aspx).</span></span>

<span data-ttu-id="0c7d8-370">MBAM 客户端在虚拟机上不受支持，并且在 Azure IaaS 上也不受支持。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-370">The MBAM client is not supported on virtual machines and is also not supported on Azure IaaS.</span></span>


## <span data-ttu-id="0c7d8-371">服务版本</span><span class="sxs-lookup"><span data-stu-id="0c7d8-371">Service releases</span></span> 

- [<span data-ttu-id="0c7d8-372">2016年4月的修复程序</span><span class="sxs-lookup"><span data-stu-id="0c7d8-372">April 2016 hotfix</span></span>](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="0c7d8-373">2016年9月</span><span class="sxs-lookup"><span data-stu-id="0c7d8-373">September 2016</span></span>](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [<span data-ttu-id="0c7d8-374">2016 年 12 月</span><span class="sxs-lookup"><span data-stu-id="0c7d8-374">December 2016</span></span>](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [<span data-ttu-id="0c7d8-375">2017 年 3 月</span><span class="sxs-lookup"><span data-stu-id="0c7d8-375">March 2017</span></span>](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [<span data-ttu-id="0c7d8-376">2017 年 6 月</span><span class="sxs-lookup"><span data-stu-id="0c7d8-376">June 2017</span></span>](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="0c7d8-377">2017 年 9 月</span><span class="sxs-lookup"><span data-stu-id="0c7d8-377">September 2017</span></span>](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [<span data-ttu-id="0c7d8-378">2018 年 3 月</span><span class="sxs-lookup"><span data-stu-id="0c7d8-378">March 2018</span></span>](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="0c7d8-379">2018年7月</span><span class="sxs-lookup"><span data-stu-id="0c7d8-379">July 2018</span></span>](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="0c7d8-380">五月2019</span><span class="sxs-lookup"><span data-stu-id="0c7d8-380">May 2019</span></span>](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## <span data-ttu-id="0c7d8-381">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c7d8-381">Related topics</span></span>


[<span data-ttu-id="0c7d8-382">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="0c7d8-382">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="0c7d8-383">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="0c7d8-383">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)




## <span data-ttu-id="0c7d8-384">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="0c7d8-384">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="0c7d8-385">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-385">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="0c7d8-386">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="0c7d8-386">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




