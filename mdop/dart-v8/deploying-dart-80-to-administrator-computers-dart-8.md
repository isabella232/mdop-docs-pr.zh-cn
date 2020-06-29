---
title: 将 DaRT 8.0 部署到管理员计算机
description: 将 DaRT 8.0 部署到管理员计算机
author: dansimp
ms.assetid: f918ead8-742e-464a-8bf6-1fcedde66cae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0ab001f612f2257ecbd77c39319cc99c17d36197
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803505"
---
# <span data-ttu-id="a69ab-103">将 DaRT 8.0 部署到管理员计算机</span><span class="sxs-lookup"><span data-stu-id="a69ab-103">Deploying DaRT 8.0 to Administrator Computers</span></span>


<span data-ttu-id="a69ab-104">开始部署 Microsoft 诊断和恢复工具集（DaRT）8.0 之前，请查看你的环境的要求。</span><span class="sxs-lookup"><span data-stu-id="a69ab-104">Before you begin the deployment of Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0, review the requirements for your environment.</span></span> <span data-ttu-id="a69ab-105">这包括安装 DaRT 8.0 的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="a69ab-105">This includes the hardware requirements for installing DaRT 8.0.</span></span> <span data-ttu-id="a69ab-106">有关 DaRT 硬件和软件要求的详细信息，请参阅[dart 8.0 支持的配置](dart-80-supported-configurations-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="a69ab-106">For more information about DaRT hardware and software requirements, see [DaRT 8.0 Supported Configurations](dart-80-supported-configurations-dart-8.md).</span></span>

<span data-ttu-id="a69ab-107">本部分中的主题可用于帮助你基于你的环境和部署策略在你的企业中部署 DaRT。</span><span class="sxs-lookup"><span data-stu-id="a69ab-107">The topics in this section can be used to help you deploy DaRT in your enterprise based on your environment and deployment strategy.</span></span>

## <span data-ttu-id="a69ab-108">部署 DaRT 8。0</span><span class="sxs-lookup"><span data-stu-id="a69ab-108">Deploy DaRT 8.0</span></span>


<span data-ttu-id="a69ab-109">你可以使用适用于 DaRT 的 Windows Installer 文件在计算机上安装 DaRT，以便先创建 DaRT 恢复映像，然后对最终用户计算机进行故障排除和修复。</span><span class="sxs-lookup"><span data-stu-id="a69ab-109">You can use the Windows Installer file for DaRT to install DaRT on a computer that you will use to first create the DaRT recovery image and then troubleshoot and fix end-user computers.</span></span> <span data-ttu-id="a69ab-110">通常情况下，在组织中，你可能仅在管理员计算机上安装了创建 DaRT 恢复映像所需的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="a69ab-110">Frequently, across an organization, you might install on the administrator computer only the DaRT functionality that you need to create a DaRT recovery image.</span></span> <span data-ttu-id="a69ab-111">然后，在技术支持管理员的计算机上，你可能仅安装用于解决问题计算机（如 DaRT 远程连接查看器和崩溃分析器）所必须具备的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="a69ab-111">Then, on a help desk administrator’s computer, you might install only the DaRT functionality that you must have to troubleshoot a problem computer, such as the DaRT Remote Connection Viewer and the Crash Analyzer.</span></span>

<span data-ttu-id="a69ab-112">除了手动运行 Windows 安装程序文件以安装 DaRT 之外，还可以在命令提示符处安装 DaRT 以支持企业软件部署系统（如 SystemCenterConfigurationManager2012）。</span><span class="sxs-lookup"><span data-stu-id="a69ab-112">In addition to manually running the Windows Installer file to install DaRT, you can also install DaRT at the command prompt to support enterprise software deployment systems such as SystemCenterConfigurationManager2012.</span></span>

[<span data-ttu-id="a69ab-113">如何部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="a69ab-113">How to Deploy DaRT 8.0</span></span>](how-to-deploy-dart-80-dart-8.md)

## <span data-ttu-id="a69ab-114">更改、修复或删除 DaRT 8。0</span><span class="sxs-lookup"><span data-stu-id="a69ab-114">Change, repair, or remove DaRT 8.0</span></span>


<span data-ttu-id="a69ab-115">你可以通过双击 DaRT 安装文件，然后单击与你要执行的操作对应的按钮或通过 Windows "控制面板" 来更改、修复或删除 DaRT 安装。</span><span class="sxs-lookup"><span data-stu-id="a69ab-115">You can change, repair, or remove the DaRT installation by double-clicking the DaRT installation file and then clicking the button that corresponds to the action that you want to perform or through the Windows Control Panel.</span></span>

[<span data-ttu-id="a69ab-116">如何更改、修复或删除 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="a69ab-116">How to Change, Repair, or Remove DaRT 8.0</span></span>](how-to-change-repair-or-remove-dart-80-dart-8.md)

## <span data-ttu-id="a69ab-117">如何获取 DaRT 8。0</span><span class="sxs-lookup"><span data-stu-id="a69ab-117">How to get DaRT 8.0</span></span>


<span data-ttu-id="a69ab-118">若要获取 DaRT 软件，请参阅[如何获取 MDOP](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="a69ab-118">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="a69ab-119">用于将 DaRT 8.0 部署到管理员计算机的其他资源</span><span class="sxs-lookup"><span data-stu-id="a69ab-119">Other resources for deploying the DaRT 8.0 to administrator computers</span></span>


[<span data-ttu-id="a69ab-120">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="a69ab-120">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

 

 





