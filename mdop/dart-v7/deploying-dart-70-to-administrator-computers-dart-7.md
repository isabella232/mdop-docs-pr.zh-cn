---
title: 将 DaRT 7.0 部署到管理员计算机
description: 将 DaRT 7.0 部署到管理员计算机
author: dansimp
ms.assetid: 8baf26aa-b168-463c-810f-a165918b9d9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96eda08e28b915e30d88aa57cb19562958848cf4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798108"
---
# <span data-ttu-id="53caf-103">将 DaRT 7.0 部署到管理员计算机</span><span class="sxs-lookup"><span data-stu-id="53caf-103">Deploying DaRT 7.0 to Administrator Computers</span></span>


<span data-ttu-id="53caf-104">开始部署 Microsoft 诊断和恢复工具集（DaRT）7之前，请查看你的环境的要求。</span><span class="sxs-lookup"><span data-stu-id="53caf-104">Before you begin the deployment of Microsoft Diagnostics and Recovery Toolset (DaRT)7, review the requirements for your environment.</span></span> <span data-ttu-id="53caf-105">这包括安装 DaRT 的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="53caf-105">This includes the hardware requirements for installing DaRT.</span></span> <span data-ttu-id="53caf-106">有关 DaRT 硬件和软件要求的详细信息，请参阅[dart 7.0 支持的配置](dart-70-supported-configurations-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="53caf-106">For more information about DaRT hardware and software requirements, see [DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md).</span></span>

<span data-ttu-id="53caf-107">本部分中的主题可用于帮助你基于你的环境和部署策略在你的企业中部署 DaRT。</span><span class="sxs-lookup"><span data-stu-id="53caf-107">The topics in this section can be used to help you deploy DaRT in your enterprise based on your environment and deployment strategy.</span></span>

## <span data-ttu-id="53caf-108">将 DaRT 7.0 部署到管理员计算机</span><span class="sxs-lookup"><span data-stu-id="53caf-108">Deploy DaRT 7.0 to administrator computers</span></span>


<span data-ttu-id="53caf-109">你可以使用适用于 DaRT 的 Windows Installer 文件在计算机上安装 DaRT，以便先创建 DaRT 恢复映像，然后对最终用户计算机进行故障排除和修复。</span><span class="sxs-lookup"><span data-stu-id="53caf-109">You can use the Windows Installer file for DaRT to install DaRT on a computer that you will use to first create the DaRT recovery image and then troubleshoot and fix end-user computers.</span></span> <span data-ttu-id="53caf-110">通常情况下，在组织中，你可能仅在管理员计算机上安装了创建 DaRT 恢复映像所需的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="53caf-110">Frequently, across an organization, you might install on the administrator computer only the DaRT functionality that you need to create a DaRT recovery image.</span></span> <span data-ttu-id="53caf-111">然后，在帮助台管理员的计算机上，你可能仅安装用于解决问题计算机（如 DaRT 远程连接查看器和崩溃分析器）所必须具备的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="53caf-111">Then, on a helpdesk administrator’s computer, you might install only the DaRT functionality that you must have to troubleshoot a problem computer, such as the DaRT Remote Connection Viewer and the Crash Analyzer.</span></span>

<span data-ttu-id="53caf-112">除了手动运行 Windows 安装程序文件以安装 DaRT 之外，还可以在命令提示符处安装 DaRT 以支持企业软件部署系统（如 SystemCenterConfigurationManager2012）。</span><span class="sxs-lookup"><span data-stu-id="53caf-112">In addition to manually running the Windows Installer file to install DaRT, you can also install DaRT at the command prompt to support enterprise software deployment systems such as SystemCenterConfigurationManager2012.</span></span>

[<span data-ttu-id="53caf-113">如何部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="53caf-113">How to Deploy DaRT 7.0</span></span>](how-to-deploy-dart-70.md)

## <span data-ttu-id="53caf-114">更改、修复或删除 DaRT 7。0</span><span class="sxs-lookup"><span data-stu-id="53caf-114">Change, repair, or remove DaRT 7.0</span></span>


<span data-ttu-id="53caf-115">你可以通过双击 DaRT 安装文件，然后单击与你要执行的操作对应的按钮或通过 Windows "控制面板" 来更改、修复或删除 DaRT 安装。</span><span class="sxs-lookup"><span data-stu-id="53caf-115">You can change, repair, or remove the DaRT installation by double-clicking the DaRT installation file and then clicking the button that corresponds to the action that you want to perform or through the Windows Control Panel.</span></span>

[<span data-ttu-id="53caf-116">如何更改、修复或删除 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="53caf-116">How to Change, Repair, or Remove DaRT 7.0</span></span>](how-to-change-repair-or-remove-dart-70.md)

## <span data-ttu-id="53caf-117">用于将 DaRT 7.0 部署到管理员计算机的其他资源</span><span class="sxs-lookup"><span data-stu-id="53caf-117">Other resources for Deploying the DaRT 7.0 to Administrator Computers</span></span>


-   [<span data-ttu-id="53caf-118">部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="53caf-118">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





