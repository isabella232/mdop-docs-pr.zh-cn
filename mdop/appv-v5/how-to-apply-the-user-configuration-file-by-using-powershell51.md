---
title: 如何使用 PowerShell 应用用户配置文件
description: 如何使用 PowerShell 应用用户配置文件
author: dansimp
ms.assetid: 986e638c-4a0c-4a7e-be73-f4615e8b8000
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97b3db253993d6d855384ee5d9771a7f9ff5b64d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798543"
---
# <span data-ttu-id="7db3a-103">如何使用 PowerShell 应用用户配置文件</span><span class="sxs-lookup"><span data-stu-id="7db3a-103">How to Apply the User Configuration File by Using PowerShell</span></span>


<span data-ttu-id="7db3a-104">当程序包发布到特定用户并确定该程序包的运行方式时，将应用动态用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="7db3a-104">The dynamic user configuration file is applied when a package is published to a specific user and determines how the package will run.</span></span>

<span data-ttu-id="7db3a-105">使用以下过程指定特定于用户的配置文件。</span><span class="sxs-lookup"><span data-stu-id="7db3a-105">Use the following procedure to specify a user-specific configuration file.</span></span> <span data-ttu-id="7db3a-106">下面的过程基于示例：</span><span class="sxs-lookup"><span data-stu-id="7db3a-106">The following procedure is based on the example:</span></span>

**<span data-ttu-id="7db3a-107">c:\\Packages\\Contoso\\MyApp.appv</span><span class="sxs-lookup"><span data-stu-id="7db3a-107">c:\\Packages\\Contoso\\MyApp.appv</span></span>**

**<span data-ttu-id="7db3a-108">应用用户配置文件</span><span class="sxs-lookup"><span data-stu-id="7db3a-108">To apply a user Configuration file</span></span>**

1.  <span data-ttu-id="7db3a-109">若要使用 PowerShell 控制台将程序包添加到计算机，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7db3a-109">To add the package to the computer using the PowerShell console type the following command:</span></span>

    <span data-ttu-id="7db3a-110">**AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**。</span><span class="sxs-lookup"><span data-stu-id="7db3a-110">**Add-AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**.</span></span>

2.  <span data-ttu-id="7db3a-111">使用以下命令将程序包发布到用户并指定已更新的动态用户配置文件：</span><span class="sxs-lookup"><span data-stu-id="7db3a-111">Use the following command to publish the package to the user and specify the updated the dynamic user configuration file:</span></span>

    **<span data-ttu-id="7db3a-112">发布-AppVClientPackage $pkg-DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span><span class="sxs-lookup"><span data-stu-id="7db3a-112">Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span></span>**

    <span data-ttu-id="7db3a-113">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="7db3a-113">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="7db3a-114">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="7db3a-114">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="7db3a-115">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="7db3a-115">Got an App-V issue?</span></span>** <span data-ttu-id="7db3a-116">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="7db3a-116">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="7db3a-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="7db3a-117">Related topics</span></span>


[<span data-ttu-id="7db3a-118">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="7db3a-118">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





