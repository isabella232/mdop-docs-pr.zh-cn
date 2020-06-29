---
title: 如何使用 PowerShell 修改客户端配置
description: 如何使用 PowerShell 修改客户端配置
author: dansimp
ms.assetid: c3a59592-bb0d-43b6-8f4e-44f3a2d5b7ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 368a0d12c12e10a623afad3f9040ae01cee6cb38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798389"
---
# <span data-ttu-id="aa719-103">如何使用 PowerShell 修改客户端配置</span><span class="sxs-lookup"><span data-stu-id="aa719-103">How to Modify Client Configuration by Using PowerShell</span></span>


<span data-ttu-id="aa719-104">使用以下过程配置 App-v 5.1 客户端配置。</span><span class="sxs-lookup"><span data-stu-id="aa719-104">Use the following procedure to configure the App-V 5.1 client configuration.</span></span>

**<span data-ttu-id="aa719-105">使用 PowerShell 修改 App-v 5.1 客户端配置</span><span class="sxs-lookup"><span data-stu-id="aa719-105">To modify App-V 5.1 client configuration using PowerShell</span></span>**

1.  <span data-ttu-id="aa719-106">若要使用 PowerShell 配置客户端设置，请使用**AppvClientConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa719-106">To configure the client settings using PowerShell, use the **Set-AppvClientConfiguration** cmdlet.</span></span> <span data-ttu-id="aa719-107">有关安装 PowerShell 的详细信息以及 cmdlet 的列表，请参阅[如何加载 PowerShell cmdlet 和获取 Cmdlet 帮助](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md)。</span><span class="sxs-lookup"><span data-stu-id="aa719-107">For more information about installing PowerShell, and a list of cmdlets see, [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md).</span></span>

2.  <span data-ttu-id="aa719-108">若要修改客户端配置，请打开 PowerShell 命令提示符，并使用任何必需的参数运行以下 cmdlet **Set AppvClientConfiguration** 。</span><span class="sxs-lookup"><span data-stu-id="aa719-108">To modify the client configuration, open a PowerShell Command prompt and run the following cmdlet **Set-AppvClientConfiguration** with any required parameters.</span></span> <span data-ttu-id="aa719-109">例如：</span><span class="sxs-lookup"><span data-stu-id="aa719-109">For example:</span></span>

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    <span data-ttu-id="aa719-110">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="aa719-110">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="aa719-111">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="aa719-111">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="aa719-112">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="aa719-112">Got an App-V issue?</span></span>** <span data-ttu-id="aa719-113">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="aa719-113">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="aa719-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="aa719-114">Related topics</span></span>


[<span data-ttu-id="aa719-115">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="aa719-115">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





