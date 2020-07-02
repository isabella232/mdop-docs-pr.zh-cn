---
title: 高级组策略管理
description: 高级组策略管理
author: dansimp
ms.assetid: 493ca3c3-c3d6-4bb1-9430-dc1e43c86bb0
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/23/2017
ms.openlocfilehash: 457cca9db5d39466691b0bc7c41455910b4483d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795402"
---
# <span data-ttu-id="4d0c8-103">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="4d0c8-103">Advanced Group Policy Management</span></span>


<span data-ttu-id="4d0c8-104">Microsoft 高级组策略管理（AGPM）扩展了组策略管理控制台（GPMC）的功能，以便为组策略对象（Gpo）提供全面的更改控制和改进的管理。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-104">Microsoft Advanced Group Policy Management (AGPM) extends the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span> <span data-ttu-id="4d0c8-105">对于软件保证，AGPM 可用作 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-105">AGPM is available as part of the Microsoft Desktop Optimization Pack (MDOP) for Software Assurance.</span></span>

## <span data-ttu-id="4d0c8-106">AGPM 版本信息</span><span class="sxs-lookup"><span data-stu-id="4d0c8-106">AGPM Version Information</span></span>


<span data-ttu-id="4d0c8-107">[AGPM 4.0 SP3](agpm-40-sp3-navengl.md)支持 windows 10、windows server 2019、windows server 2016、windows Server 2012 R2、windows 8.1、windows server 2012、windows Server 2008 R2、windows 7、windows server 2008 和 WINDOWS Vista SP1。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-107">[AGPM 4.0 SP3](agpm-40-sp3-navengl.md) supports Windows 10, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="4d0c8-108">[AGPM 4.0 SP2](agpm-40-sp2-navengl.md)支持 windows Server 2012 R2、windows 8.1、windows server 2012、windows Server 2008 R2、windows 7、windows Server 2008 和 WINDOWS Vista SP1。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-108">[AGPM 4.0 SP2](agpm-40-sp2-navengl.md) supports Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="4d0c8-109">[AGPM 4.0 SP1](agpm-40-sp1-navengl.md)支持 windows server 2012、windows Server 2008 R2、windows 7、windows server 2008 和 WINDOWS Vista SP1。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-109">[AGPM 4.0 SP1](agpm-40-sp1-navengl.md) supports Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="4d0c8-110">[AGPM 4](agpm-4-navengl.md)支持 windows Server 2008 R2、windows 7、windows Server 2008 和带有 SP1 的 windows Vista。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-110">[AGPM 4](agpm-4-navengl.md) supports Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="4d0c8-111">[AGPM 3](agpm-3-navengl.md)支持 windows Server 2008 和 WINDOWS Vista SP1。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-111">[AGPM 3](agpm-3-navengl.md) supports Windows Server 2008 and Windows Vista with SP1.</span></span>

<span data-ttu-id="4d0c8-112">[AGPM 2.5](agpm-25-navengl.md)支持 Windows Vista （32位），无服务包和 Windows Server 2003 （32位）。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-112">[AGPM 2.5](agpm-25-navengl.md) supports Windows Vista (32-bit) with no service pack and Windows Server 2003 (32-bit).</span></span>

## <span data-ttu-id="4d0c8-113">附加的 MDOP 产品指南</span><span class="sxs-lookup"><span data-stu-id="4d0c8-113">Supplemental MDOP Product Guidance</span></span>


<span data-ttu-id="4d0c8-114">除了在线提供的产品文档，有关详细的产品指南（如信息性视频和虚拟实验）可用于大多数 MDOP 产品。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-114">In addition to the product documentation available online, supplemental product guidance such as informational videos and virtual labs are available for most MDOP products.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4d0c8-115">MDOP 虚拟实验室</span><span class="sxs-lookup"><span data-stu-id="4d0c8-115">MDOP Virtual Labs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d0c8-116">有关可用 MDOP 虚拟实验室的列表，请转到 <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="[Microsoft Desktop Optimization Pack (MDOP) Virtual Labs](https://go.microsoft.com/fwlink/?LinkId=234276)"> Microsoft 桌面优化包（MDOP）虚拟实验室 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=234276"> https://go.microsoft.com/fwlink/?LinkId=234276 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-116">For a list of available MDOP virtual labs, go to <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="[Microsoft Desktop Optimization Pack (MDOP) Virtual Labs](https://go.microsoft.com/fwlink/?LinkId=234276)">Microsoft Desktop Optimization Pack (MDOP) Virtual Labs</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=234276">https://go.microsoft.com/fwlink/?LinkId=234276</a>).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4d0c8-117">MDOP 技术中心</span><span class="sxs-lookup"><span data-stu-id="4d0c8-117">MDOP TechCenter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d0c8-118">对于技术白皮书、评估资料、博客和其他 MDOP 资源，请转到 <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="[MDOP TechCenter](https://go.microsoft.com/fwlink/?LinkId=225286)"> MDOP 技术中心 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=225286"> https://go.microsoft.com/fwlink/?LinkId=225286 </a> ）</span><span class="sxs-lookup"><span data-stu-id="4d0c8-118">For technical whitepapers, evaluation materials, blogs, and additional MDOP resources, go to <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="[MDOP TechCenter](https://go.microsoft.com/fwlink/?LinkId=225286)">MDOP TechCenter</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=225286">https://go.microsoft.com/fwlink/?LinkId=225286</a>)</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-getmdop"></a><span data-ttu-id="4d0c8-119">如何获取 MDOP</span><span class="sxs-lookup"><span data-stu-id="4d0c8-119">How to Get MDOP</span></span>


<span data-ttu-id="4d0c8-120">MDOP 是一套产品，可帮助简化整个企业的桌面部署、管理和支持。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-120">MDOP is a suite of products that can help streamline desktop deployment, management, and support across the enterprise.</span></span> <span data-ttu-id="4d0c8-121">MDOP 可作为软件保障客户的附加订阅。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-121">MDOP is available as an additional subscription for Software Assurance customers.</span></span>

<a href="" id="evaluate-mdop"></a><span data-ttu-id="4d0c8-122">**评估 MDOP**MDOP 还可用于根据 MSDN 和 TechNet 协议对[msdn](https://msdn.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178)和[technet](https://technet.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178)订阅者进行测试和评估。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-122">**Evaluate MDOP** MDOP is also available for test and evaluation to [MSDN](https://msdn.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178) and [TechNet](https://technet.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178) subscribers in accordance with MSDN and TechNet agreements.</span></span>

<a href="" id="download-mdop"></a><span data-ttu-id="4d0c8-123">**下载 MDOP**MDOP 订阅者可在[Microsoft 批量许可网站（MVLS）](https://go.microsoft.com/fwlink/?LinkId=166331)下载软件。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-123">**Download MDOP** MDOP subscribers can download the software at the [Microsoft Volume Licensing website (MVLS)](https://go.microsoft.com/fwlink/?LinkId=166331).</span></span>

<a href="" id="purchase-mdop"></a><span data-ttu-id="4d0c8-124">**购买 MDOP**访问企业版[购买 Windows 企业版许可](https://www.microsoft.com/windows/enterprise/how-to-buy.aspx)网站，了解如何为您的企业购买 MDOP。</span><span class="sxs-lookup"><span data-stu-id="4d0c8-124">**Purchase MDOP** Visit the enterprise [Purchase Windows Enterprise Licensing](https://www.microsoft.com/windows/enterprise/how-to-buy.aspx) website to find out how to purchase MDOP for your business.</span></span>

 

 





