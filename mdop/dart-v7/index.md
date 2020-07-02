---
title: 诊断和恢复工具集7管理员指南
description: 诊断和恢复工具集7管理员指南
author: dansimp
ms.assetid: bf89eccd-fc03-48ff-9019-a8640e11dd99
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 92cba6f364fc04e0113232c4682bcee8fe2bd73f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795387"
---
# <span data-ttu-id="ac254-103">诊断和恢复工具集7管理员指南</span><span class="sxs-lookup"><span data-stu-id="ac254-103">Diagnostics and Recovery Toolset 7 Administrator's Guide</span></span>


<span data-ttu-id="ac254-104">Microsoft 诊断和恢复工具集（DaRT）7让你可以诊断和修复无法启动的计算机，或者出现按预期启动问题的计算机。</span><span class="sxs-lookup"><span data-stu-id="ac254-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 lets you diagnose and repair a computer that cannot be started or that has problems starting as expected.</span></span> <span data-ttu-id="ac254-105">通过使用 DaRT，你可以恢复已不可用的最终用户计算机，诊断问题的可能原因，并快速修复无法启动或锁定的计算机。</span><span class="sxs-lookup"><span data-stu-id="ac254-105">By using DaRT, you can recover end-user computers that have become unusable, diagnose probable causes of issues, and quickly repair unbootable or locked-out computers.</span></span> <span data-ttu-id="ac254-106">如果需要，您还可以快速还原重要的丢失文件，并检测和删除恶意软件，即使计算机未联机。</span><span class="sxs-lookup"><span data-stu-id="ac254-106">When it is necessary, you can also quickly restore important lost files and detect and remove malware, even when the computer is not online.</span></span>

<span data-ttu-id="ac254-107">DaRT 是 Microsoft 桌面优化包（MDOP）的重要部分，可供软件保障客户使用的动态解决方案，可帮助降低软件安装成本，支持将应用程序作为服务提供，并帮助管理和控制企业桌面环境。</span><span class="sxs-lookup"><span data-stu-id="ac254-107">DaRT is an important part of the Microsoft Desktop Optimization Pack (MDOP), a dynamic solution available to Software Assurance customers that helps reduce software installation costs, enables delivery of applications as services, and helps manage and control enterprise desktop environments.</span></span>

<a href="" id="getting-started-with-dart-7-0"></a>[<span data-ttu-id="ac254-108">DaRT 7.0 入门</span><span class="sxs-lookup"><span data-stu-id="ac254-108">Getting Started with DaRT 7.0</span></span>](getting-started-with-dart-70-new-ia.md)  

<span data-ttu-id="ac254-109">[关于 DaRT 7.0](about-dart-70-new-ia.md) **|**[DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md) **|** 中的工具概述[适用于 DaRT 7.0 的辅助功能](accessibility-for-dart-70.md)</span><span class="sxs-lookup"><span data-stu-id="ac254-109">[About DaRT 7.0](about-dart-70-new-ia.md)**|**[Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md)**|**[Accessibility for DaRT 7.0](accessibility-for-dart-70.md)</span></span>

<a href="" id="planning-for-dart-7-0"></a>[<span data-ttu-id="ac254-110">计划 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="ac254-110">Planning for DaRT 7.0</span></span>](planning-for-dart-70-new-ia.md)  

<span data-ttu-id="ac254-111">[规划部署 DaRT 7.0](planning-to-deploy-dart-70.md) **|**[DaRT 7.0 支持的配置](dart-70-supported-configurations-dart-7.md) **|**[计划创建 DaRT 7.0 恢复映像](planning-to-create-the-dart-70-recovery-image.md) **|**[规划如何保存和部署 DaRT 7.0 恢复映像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md) **|**[DaRT 7.0 规划清单](dart-70-planning-checklist-dart-7.md)</span><span class="sxs-lookup"><span data-stu-id="ac254-111">[Planning to Deploy DaRT 7.0](planning-to-deploy-dart-70.md)**|**[DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md)**|**[Planning to Create the DaRT 7.0 Recovery Image](planning-to-create-the-dart-70-recovery-image.md)**|**[Planning How to Save and Deploy the DaRT 7.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)**|**[DaRT 7.0 Planning Checklist](dart-70-planning-checklist-dart-7.md)</span></span>

<a href="" id="deploying-dart-7-0"></a>[<span data-ttu-id="ac254-112">部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="ac254-112">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)  

<span data-ttu-id="ac254-113">[将 DaRT 7.0 部署到管理员计算机](deploying-dart-70-to-administrator-computers-dart-7.md) **|**[创建 DaRT 7.0 恢复映像](creating-the-dart-70-recovery-image-dart-7.md) **|**[部署 DaRT 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md) **|**[DaRT 7.0 部署清单](dart-70-deployment-checklist-dart-7.md)</span><span class="sxs-lookup"><span data-stu-id="ac254-113">[Deploying DaRT 7.0 to Administrator Computers](deploying-dart-70-to-administrator-computers-dart-7.md)**|**[Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md)**|**[Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md)**|**[DaRT 7.0 Deployment Checklist](dart-70-deployment-checklist-dart-7.md)</span></span>

<a href="" id="operations-for-dart-7-0"></a>[<span data-ttu-id="ac254-114">DaRT 7.0 的操作</span><span class="sxs-lookup"><span data-stu-id="ac254-114">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)  

<span data-ttu-id="ac254-115">[使用 DaRT 7.0](recovering-computers-using-dart-70-dart-7.md) **|** 恢复计算机[通过崩溃分析](diagnosing-system-failures-with-crash-analyzer--dart-7.md) **|** 程序诊断系统故障[针对 DaRT 7.0 的安全注意事项](security-considerations-for-dart-70-dart-7.md)</span><span class="sxs-lookup"><span data-stu-id="ac254-115">[Recovering Computers Using DaRT 7.0](recovering-computers-using-dart-70-dart-7.md)**|**[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-7.md)**|**[Security Considerations for DaRT 7.0](security-considerations-for-dart-70-dart-7.md)</span></span>

<a href="" id="troubleshooting-dart-7-0"></a>[<span data-ttu-id="ac254-116">DaRT 7.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="ac254-116">Troubleshooting DaRT 7.0</span></span>](troubleshooting-dart-70-new-ia.md)  

<a href="" id="technical-reference-for-dart-7-0"></a>[<span data-ttu-id="ac254-117">DaRT 7.0 的技术参考</span><span class="sxs-lookup"><span data-stu-id="ac254-117">Technical Reference for DaRT 7.0</span></span>](technical-reference-for-dart-70-new-ia.md)  

### <span data-ttu-id="ac254-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="ac254-118">More Information</span></span>

<a href="" id="release-notes-for-dart-7-0"></a>[<span data-ttu-id="ac254-119">DaRT 7.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="ac254-119">Release Notes for DaRT 7.0</span></span>](release-notes-for-dart-70-new-ia.md)  
<span data-ttu-id="ac254-120">查看适用于 DaRT 7 的已更新产品信息和已知问题。</span><span class="sxs-lookup"><span data-stu-id="ac254-120">View updated product information and known issues for DaRT 7.</span></span>

<a href="" id="mdop-techcenter-page"></a>[<span data-ttu-id="ac254-121">MDOP 技术中心页</span><span class="sxs-lookup"><span data-stu-id="ac254-121">MDOP TechCenter Page</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=225286)  
<span data-ttu-id="ac254-122">了解最新的 MDOP 信息和资源。</span><span class="sxs-lookup"><span data-stu-id="ac254-122">Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a>[<span data-ttu-id="ac254-123">MDOP 信息体验</span><span class="sxs-lookup"><span data-stu-id="ac254-123">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
<span data-ttu-id="ac254-124">查找 MDOP 技术的文档、视频和其他资源。</span><span class="sxs-lookup"><span data-stu-id="ac254-124">Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="ac254-125">您还可以在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们，[向我们发送反馈](mailto:MDOPDocs@microsoft.com)或了解更新。</span><span class="sxs-lookup"><span data-stu-id="ac254-125">You can also [send us feedback](mailto:MDOPDocs@microsoft.com) or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

 

 





