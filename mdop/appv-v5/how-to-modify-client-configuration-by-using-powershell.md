---
title: 如何使用 PowerShell 修改客户端配置
description: 如何使用 PowerShell 修改客户端配置
author: dansimp
ms.assetid: 53ccb2cf-ef81-4310-a853-efcb395f006e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d3173944abfe2c2b3d30aa9654dae81f204a32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798393"
---
# <span data-ttu-id="a9710-103">如何使用 PowerShell 修改客户端配置</span><span class="sxs-lookup"><span data-stu-id="a9710-103">How to Modify Client Configuration by Using PowerShell</span></span>


<span data-ttu-id="a9710-104">使用以下过程配置 App-v 5.0 客户端配置。</span><span class="sxs-lookup"><span data-stu-id="a9710-104">Use the following procedure to configure the App-V 5.0 client configuration.</span></span>

**<span data-ttu-id="a9710-105">使用 PowerShell 修改 App-v 5.0 客户端配置</span><span class="sxs-lookup"><span data-stu-id="a9710-105">To modify App-V 5.0 client configuration using PowerShell</span></span>**

1.  <span data-ttu-id="a9710-106">若要使用 PowerShell 配置客户端设置，请使用**AppvClientConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9710-106">To configure the client settings using PowerShell, use the **Set-AppvClientConfiguration** cmdlet.</span></span>

2.  <span data-ttu-id="a9710-107">若要修改客户端配置，请打开 PowerShell 命令提示符，并使用任何必需的参数运行以下 cmdlet **Set AppvClientConfiguration** 。</span><span class="sxs-lookup"><span data-stu-id="a9710-107">To modify the client configuration, open a PowerShell Command prompt and run the following cmdlet **Set-AppvClientConfiguration** with any required parameters.</span></span> <span data-ttu-id="a9710-108">例如：</span><span class="sxs-lookup"><span data-stu-id="a9710-108">For example:</span></span>

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    <span data-ttu-id="a9710-109">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="a9710-109">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a9710-110">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="a9710-110">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a9710-111">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="a9710-111">Got an App-V issue?</span></span>** <span data-ttu-id="a9710-112">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="a9710-112">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a9710-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="a9710-113">Related topics</span></span>


[<span data-ttu-id="a9710-114">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="a9710-114">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





