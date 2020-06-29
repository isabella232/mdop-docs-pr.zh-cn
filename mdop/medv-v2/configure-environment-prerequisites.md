---
title: 配置环境先决条件
description: 配置环境先决条件
author: dansimp
ms.assetid: 7379e8e5-1cb2-4b8e-8acc-5c04e26f8c91
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8d6fc3b81f6dafbe709dd904b9fba6124d2f6b6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803970"
---
# <span data-ttu-id="2754c-103">配置环境先决条件</span><span class="sxs-lookup"><span data-stu-id="2754c-103">Configure Environment Prerequisites</span></span>


<span data-ttu-id="2754c-104">在部署和运行 Microsoft 企业版桌面虚拟化（MED-V）2.0 之前，必须确保你的环境满足以下最低先决条件。</span><span class="sxs-lookup"><span data-stu-id="2754c-104">Before you can deploy and run Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you must ensure that your environment meets the following minimum prerequisites.</span></span>

**<span data-ttu-id="2754c-105">Windows 7</span><span class="sxs-lookup"><span data-stu-id="2754c-105">Windows 7</span></span>**

<span data-ttu-id="2754c-106">MED-V 主机代理和 MED-V 工作区包装程序仅在 Windows 7 或更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="2754c-106">The MED-V Host Agent and the MED-V Workspace Packager are only supported in Windows 7 or newer.</span></span>

**<span data-ttu-id="2754c-107">Windows XP SP3</span><span class="sxs-lookup"><span data-stu-id="2754c-107">Windows XP SP3</span></span>**

<span data-ttu-id="2754c-108">MED-V 来宾代理仅在 Windows XP SP3 中受支持。</span><span class="sxs-lookup"><span data-stu-id="2754c-108">The MED-V Guest Agent is only supported in Windows XP SP3.</span></span>

**<span data-ttu-id="2754c-109">.NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2754c-109">.NET Framework 3.5 SP1</span></span>**

<span data-ttu-id="2754c-110">MED-V 主机和来宾代理以及 MED-V 工作区包装程序需要 Microsoft .NET Framework 3.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="2754c-110">The MED-V Host and Guest agents and the MED-V Workspace Packager require the Microsoft .NET Framework 3.5 SP1.</span></span>

<span data-ttu-id="2754c-111">**重要提示** 你还必须安装更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) ，它解决了几个已知的应用程序兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="2754c-111">**Important** You must also install the update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950), which addresses several known application compatibility issues.</span></span>

 

<span data-ttu-id="2754c-112">**注意** 你必须手动将 .NET Framework 3.5 SP1 和更新 KB959209 安装到你准备用于 MED-V 的 Windows 虚拟 PC 映像中。</span><span class="sxs-lookup"><span data-stu-id="2754c-112">**Note** You must manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="2754c-113">但是，在主机上安装 Windows 7 时，默认情况下会包含 Microsoft .NET Framework 3.5 SP1 和更新。</span><span class="sxs-lookup"><span data-stu-id="2754c-113">However, by default, the Microsoft .NET Framework 3.5 SP1 and the update are included when you install Windows 7 on the host computer.</span></span>

 

**<span data-ttu-id="2754c-114">Active Directory 基础结构</span><span class="sxs-lookup"><span data-stu-id="2754c-114">An Active Directory Infrastructure</span></span>**

<span data-ttu-id="2754c-115">组策略提供对 Active Directory 环境中的操作系统、应用程序和用户设置的集中管理和配置。</span><span class="sxs-lookup"><span data-stu-id="2754c-115">Group Policy provides the centralized management and configuration of operating systems, applications, and users' settings in an Active Directory environment.</span></span>

## <span data-ttu-id="2754c-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="2754c-116">Related topics</span></span>


[<span data-ttu-id="2754c-117">配置安装先决条件</span><span class="sxs-lookup"><span data-stu-id="2754c-117">Configure Installation Prerequisites</span></span>](configure-installation-prerequisites.md)

[<span data-ttu-id="2754c-118">高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="2754c-118">High-Level Architecture</span></span>](high-level-architecturemedv2.md)

[<span data-ttu-id="2754c-119">MED-V 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="2754c-119">MED-V 2.0 Supported Configurations</span></span>](med-v-20-supported-configurations.md)

 

 





