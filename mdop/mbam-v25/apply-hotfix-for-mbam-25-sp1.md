---
title: 在 MBAM 2.5 SP1 上应用修补程序
description: 在 MBAM 2.5 SP1 上应用修补程序
ms.author: dansimp
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: ea564d93a3eec6a46ec7d4c1be0f794abba9c93e
ms.sourcegitcommit: 8ecbf818a6ff2ddafd80b93614c01256484737ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "11014986"
---
# <span data-ttu-id="28fa0-103">在 MBAM 2.5 SP1 上应用修补程序</span><span class="sxs-lookup"><span data-stu-id="28fa0-103">Applying hotfixes on MBAM 2.5 SP1</span></span>
<span data-ttu-id="28fa0-104">本主题介绍在 MBAM) Server 2.5 SP1 中应用用于 Microsoft BitLocker 管理和监视 (修补程序的过程</span><span class="sxs-lookup"><span data-stu-id="28fa0-104">This topic describes the process for applying the hotfixes for Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>

### <span data-ttu-id="28fa0-105">开始之前，请下载 Microsoft BitLocker 管理和监视 (的最新修复程序 MBAM) Server 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="28fa0-105">Before you begin, download the latest hotfix of Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>
[<span data-ttu-id="28fa0-106">桌面优化包</span><span class="sxs-lookup"><span data-stu-id="28fa0-106">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> <span data-ttu-id="28fa0-107">有关修补程序版本的详细信息，请参阅 [MBAM 版本图](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)。</span><span class="sxs-lookup"><span data-stu-id="28fa0-107">For more information about the hotfix releases, see the [MBAM version chart](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart).</span></span>

#### <span data-ttu-id="28fa0-108">为现有 MBAM 环境更新 MBAM 服务器的步骤</span><span class="sxs-lookup"><span data-stu-id="28fa0-108">Steps to update the MBAM Server for existing MBAM environment</span></span> 
1. <span data-ttu-id="28fa0-109">删除 MBAM 服务器功能 (通过打开 MBAM 服务器配置工具，然后选择 "删除功能") 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="28fa0-109">Remove MBAM server feature (do this by opening the MBAM Server Configuration Tool, then selecting Remove Features).</span></span>
2. <span data-ttu-id="28fa0-110">从 "控制面板" 中删除 MDOP MBAM |程序和功能。</span><span class="sxs-lookup"><span data-stu-id="28fa0-110">Remove MDOP MBAM from Control Panel | Programs and Features.</span></span>
3. <span data-ttu-id="28fa0-111">安装 MBAM 2.5 SP1 RTM 服务器组件。</span><span class="sxs-lookup"><span data-stu-id="28fa0-111">Install MBAM 2.5 SP1 RTM server components.</span></span>
4. <span data-ttu-id="28fa0-112">安装 lastest MBAM 2.5 SP1 累积修补程序。</span><span class="sxs-lookup"><span data-stu-id="28fa0-112">Install lastest MBAM 2.5 SP1 hotfix rollup.</span></span>
5. <span data-ttu-id="28fa0-113">使用 MBAM 服务器配置器配置 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="28fa0-113">Configure MBAM features using MBAM Server Configurator.</span></span>

#### <span data-ttu-id="28fa0-114">安装新的 MBAM 2.5 SP1 server 修补程序的步骤</span><span class="sxs-lookup"><span data-stu-id="28fa0-114">Steps to install the new MBAM 2.5 SP1 server hotfix</span></span>
<span data-ttu-id="28fa0-115">有关 [新的服务器安装](deploying-the-mbam-25-server-infrastructure.md)，请参阅文档。</span><span class="sxs-lookup"><span data-stu-id="28fa0-115">Refer to the document for [new server installation](deploying-the-mbam-25-server-infrastructure.md).</span></span>
