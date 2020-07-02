---
title: 诊断和恢复工具集8管理员指南
description: 诊断和恢复工具集8管理员指南
author: dansimp
ms.assetid: 33685dd7-844f-4864-b504-3ef384ef01de
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2017
ms.openlocfilehash: c4f4e7cb49b89759acc4c3c738ff74a4a197b120
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795423"
---
# <span data-ttu-id="b878b-103">诊断和恢复工具集8管理员指南</span><span class="sxs-lookup"><span data-stu-id="b878b-103">Diagnostics and Recovery Toolset 8 Administrator's Guide</span></span>


<span data-ttu-id="b878b-104">Microsoft 诊断和恢复工具集（DaRT）8.0 让你可以诊断和修复无法启动的计算机或出现意外问题的计算机。</span><span class="sxs-lookup"><span data-stu-id="b878b-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 lets you diagnose and repair a computer that cannot be started or that has problems starting as expected.</span></span> <span data-ttu-id="b878b-105">通过使用 DaRT 8.0，你可以恢复已不可用的最终用户计算机，诊断问题的可能原因，并快速修复无法启动或锁定的计算机。</span><span class="sxs-lookup"><span data-stu-id="b878b-105">By using DaRT 8.0, you can recover end-user computers that have become unusable, diagnose probable causes of issues, and quickly repair unbootable or locked-out computers.</span></span> <span data-ttu-id="b878b-106">如果需要，您还可以快速还原重要的丢失文件，并检测和删除恶意软件，即使计算机未联机。</span><span class="sxs-lookup"><span data-stu-id="b878b-106">When it is necessary, you can also quickly restore important lost files and detect and remove malware, even when the computer is not online.</span></span>

<span data-ttu-id="b878b-107">DaRT 8.0 允许你在国际标准化组织（ISO）和 Windows 映像（WIM）文件格式中创建 DaRT 恢复映像，并将映像刻录到 CD、DVD 或 USB。</span><span class="sxs-lookup"><span data-stu-id="b878b-107">DaRT 8.0 lets you create a DaRT recovery image in International Organization for Standardization (ISO) and Windows Imaging (WIM) file formats and burn the image to a CD, DVD, or USB.</span></span> <span data-ttu-id="b878b-108">然后，你可以使用恢复图像文件并将其部署到本地或远程分区或恢复分区。</span><span class="sxs-lookup"><span data-stu-id="b878b-108">You can then use the recovery image files and deploy them locally or to a remote partition or a recovery partition.</span></span>

<span data-ttu-id="b878b-109">DaRT 8.0 是 Microsoft 桌面优化包（MDOP）的重要部分，可供软件保障客户使用的动态解决方案，可帮助降低软件安装成本，支持将应用程序作为服务提供，并帮助管理和控制企业桌面环境。</span><span class="sxs-lookup"><span data-stu-id="b878b-109">DaRT 8.0 is an important part of the Microsoft Desktop Optimization Pack (MDOP), a dynamic solution available to Software Assurance customers that helps reduce software installation costs, enables delivery of applications as services, and helps manage and control enterprise desktop environments.</span></span>

<a href="" id="getting-started-with-dart-8-0"></a>[<span data-ttu-id="b878b-110">DaRT 8.0 入门</span><span class="sxs-lookup"><span data-stu-id="b878b-110">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)  

<span data-ttu-id="b878b-111">[关于 DaRT 8.0](about-dart-80-dart-8.md) **|**[DaRT 8.0](release-notes-for-dart-80--dart-8.md) **|** 的发行说明[关于 DaRT 8.0 SP1](about-dart-80-sp1.md) **|**[适用于 DaRT 8.0 SP1](release-notes-for-dart-80-sp1.md) **|** 的发行说明[关于 DaRT 8.1](about-dart-81.md) **|**[DaRT 8.1](release-notes-for-dart-81.md) **|** 的发行说明[DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md) **|** 中的工具概述[适用于 DaRT 8.0 的辅助功能](accessibility-for-dart-80-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="b878b-111">[About DaRT 8.0](about-dart-80-dart-8.md)**|**[Release Notes for DaRT 8.0](release-notes-for-dart-80--dart-8.md)**|**[About DaRT 8.0 SP1](about-dart-80-sp1.md)**|**[Release Notes for DaRT 8.0 SP1](release-notes-for-dart-80-sp1.md)**|**[About DaRT 8.1](about-dart-81.md)**|**[Release Notes for DaRT 8.1](release-notes-for-dart-81.md)**|**[Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md)**|**[Accessibility for DaRT 8.0](accessibility-for-dart-80-dart-8.md)</span></span>

<a href="" id="planning-for-dart-8-0"></a>[<span data-ttu-id="b878b-112">计划 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="b878b-112">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)  

<span data-ttu-id="b878b-113">[规划部署 DaRT 8.0](planning-to-deploy-dart-80-dart-8.md) **|**[DaRT 8.0 支持的配置](dart-80-supported-configurations-dart-8.md) **|**[计划创建 DaRT 8.0 恢复映像](planning-to-create-the-dart-80-recovery-image-dart-8.md) **|**[规划如何保存和部署 DaRT 8.0 恢复映像](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md) **|**[DaRT 8.0 规划清单](dart-80-planning-checklist-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="b878b-113">[Planning to Deploy DaRT 8.0](planning-to-deploy-dart-80-dart-8.md)**|**[DaRT 8.0 Supported Configurations](dart-80-supported-configurations-dart-8.md)**|**[Planning to Create the DaRT 8.0 Recovery Image](planning-to-create-the-dart-80-recovery-image-dart-8.md)**|**[Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)**|**[DaRT 8.0 Planning Checklist](dart-80-planning-checklist-dart-8.md)</span></span>

<a href="" id="deploying-dart-8-0"></a>[<span data-ttu-id="b878b-114">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="b878b-114">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)  

<span data-ttu-id="b878b-115">[将 DaRT 8.0 部署到管理员计算机](deploying-dart-80-to-administrator-computers-dart-8.md) **|**[创建 DaRT 8.0 恢复映像](creating-the-dart-80-recovery-image-dart-8.md) **|**[部署 DaRT 恢复映像](deploying-the-dart-recovery-image-dart-8.md) **|**[DaRT 8.0 部署清单](dart-80-deployment-checklist-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="b878b-115">[Deploying DaRT 8.0 to Administrator Computers](deploying-dart-80-to-administrator-computers-dart-8.md)**|**[Creating the DaRT 8.0 Recovery Image](creating-the-dart-80-recovery-image-dart-8.md)**|**[Deploying the DaRT Recovery Image](deploying-the-dart-recovery-image-dart-8.md)**|**[DaRT 8.0 Deployment Checklist](dart-80-deployment-checklist-dart-8.md)</span></span>

<a href="" id="operations-for-dart-8-0"></a>[<span data-ttu-id="b878b-116">DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="b878b-116">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)  

<span data-ttu-id="b878b-117">[使用 DaRT 8.0](recovering-computers-using-dart-80-dart-8.md) **|** 恢复计算机[通过崩溃分析](diagnosing-system-failures-with-crash-analyzer--dart-8.md) **|** 程序诊断系统故障[DaRT 8.0](security-and-privacy-for-dart-80-dart-8.md) **|** 的安全和隐私[使用 PowerShell 管理 DaRT 8.0](administering-dart-80-using-powershell-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="b878b-117">[Recovering Computers Using DaRT 8.0](recovering-computers-using-dart-80-dart-8.md)**|**[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-8.md)**|**[Security and Privacy for DaRT 8.0](security-and-privacy-for-dart-80-dart-8.md)**|**[Administering DaRT 8.0 Using PowerShell](administering-dart-80-using-powershell-dart-8.md)</span></span>

<a href="" id="technical-reference-for-dart-8-0"></a>[<span data-ttu-id="b878b-118">DaRT 8.0 的技术参考</span><span class="sxs-lookup"><span data-stu-id="b878b-118">Technical Reference for DaRT 8.0</span></span>](technical-reference-for-dart-80-new-ia.md)  

[<span data-ttu-id="b878b-119">Microsoft 诊断和恢复工具集（DaRT）用户应使用 Microsoft Defender Offline （WDO）进行恶意软件检测--></span><span class="sxs-lookup"><span data-stu-id="b878b-119">Microsoft Diagnostics and Recovery Toolset (DaRT) users should use Microsoft Defender Offline (WDO) for malware detection--></span></span>](use-windows-defender-offline-wdo-for-malware-protection-not-dart.md)

<a href="" id="troubleshooting-dart-8-0"></a>[<span data-ttu-id="b878b-120">DaRT 8.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="b878b-120">Troubleshooting DaRT 8.0</span></span>](troubleshooting-dart-80-dart-8.md)  

### <span data-ttu-id="b878b-121">详细信息</span><span class="sxs-lookup"><span data-stu-id="b878b-121">More Information</span></span>

<a href="" id="how-do-i-get-mdop"></a>[<span data-ttu-id="b878b-122">如何获取 MDOP</span><span class="sxs-lookup"><span data-stu-id="b878b-122">How Do I Get MDOP</span></span>](https://go.microsoft.com/fwlink/?LinkId=322049)  
<span data-ttu-id="b878b-123">获取有关如何下载 DaRT 的信息。</span><span class="sxs-lookup"><span data-stu-id="b878b-123">Get information about how to download DaRT.</span></span>

<a href="" id="release-notes-for-dart-8-0"></a>[<span data-ttu-id="b878b-124">DaRT 8.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="b878b-124">Release Notes for DaRT 8.0</span></span>](release-notes-for-dart-80--dart-8.md)  
<span data-ttu-id="b878b-125">查看适用于 DaRT 8.0 的已更新产品信息和已知问题。</span><span class="sxs-lookup"><span data-stu-id="b878b-125">View updated product information and known issues for DaRT 8.0.</span></span>

<a href="" id="mdop-techcenter-page"></a>[<span data-ttu-id="b878b-126">MDOP 技术中心页</span><span class="sxs-lookup"><span data-stu-id="b878b-126">MDOP TechCenter Page</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=225286)  
<span data-ttu-id="b878b-127">了解最新的 MDOP 信息和资源。</span><span class="sxs-lookup"><span data-stu-id="b878b-127">Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a>[<span data-ttu-id="b878b-128">MDOP 信息体验</span><span class="sxs-lookup"><span data-stu-id="b878b-128">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
<span data-ttu-id="b878b-129">查找 MDOP 技术的文档、视频和其他资源。</span><span class="sxs-lookup"><span data-stu-id="b878b-129">Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="b878b-130">您还可以[向我们发送反馈](mailto:MDOPDocs@microsoft.com)，或在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们的更新。</span><span class="sxs-lookup"><span data-stu-id="b878b-130">You can also [send us feedback](mailto:MDOPDocs@microsoft.com), or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

 

 





