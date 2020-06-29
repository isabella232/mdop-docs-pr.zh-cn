---
title: 如何使用 PowerShell 应用用户配置文件
description: 如何使用 PowerShell 应用用户配置文件
author: dansimp
ms.assetid: f7d7c595-4fdd-4096-b53d-9eead111c339
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 95ae5840f5eee04a29431716a956ddec7d0487aa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798545"
---
# <span data-ttu-id="edd6b-103">如何使用 PowerShell 应用用户配置文件</span><span class="sxs-lookup"><span data-stu-id="edd6b-103">How to Apply the User Configuration File by Using PowerShell</span></span>


<span data-ttu-id="edd6b-104">当程序包发布到特定用户并确定该程序包的运行方式时，将应用动态用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="edd6b-104">The dynamic user configuration file is applied when a package is published to a specific user and determines how the package will run.</span></span>

<span data-ttu-id="edd6b-105">使用以下过程指定特定于用户的配置文件。</span><span class="sxs-lookup"><span data-stu-id="edd6b-105">Use the following procedure to specify a user-specific configuration file.</span></span> <span data-ttu-id="edd6b-106">下面的过程基于示例：</span><span class="sxs-lookup"><span data-stu-id="edd6b-106">The following procedure is based on the example:</span></span>

**<span data-ttu-id="edd6b-107">c:\\Packages\\Contoso\\MyApp.appv</span><span class="sxs-lookup"><span data-stu-id="edd6b-107">c:\\Packages\\Contoso\\MyApp.appv</span></span>**

**<span data-ttu-id="edd6b-108">应用用户配置文件</span><span class="sxs-lookup"><span data-stu-id="edd6b-108">To apply a user Configuration file</span></span>**

1.  <span data-ttu-id="edd6b-109">若要使用 PowerShell 控制台将程序包添加到计算机，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="edd6b-109">To add the package to the computer using the PowerShell console type the following command:</span></span>

    <span data-ttu-id="edd6b-110">**AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**。</span><span class="sxs-lookup"><span data-stu-id="edd6b-110">**Add-AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**.</span></span>

2.  <span data-ttu-id="edd6b-111">使用以下命令将程序包发布到用户并指定已更新的动态用户配置文件：</span><span class="sxs-lookup"><span data-stu-id="edd6b-111">Use the following command to publish the package to the user and specify the updated the dynamic user configuration file:</span></span>

    **<span data-ttu-id="edd6b-112">发布-AppVClientPackage $pkg-DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span><span class="sxs-lookup"><span data-stu-id="edd6b-112">Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span></span>**

    <span data-ttu-id="edd6b-113">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="edd6b-113">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="edd6b-114">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="edd6b-114">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="edd6b-115">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="edd6b-115">Got an App-V issue?</span></span>** <span data-ttu-id="edd6b-116">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="edd6b-116">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="edd6b-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="edd6b-117">Related topics</span></span>


[<span data-ttu-id="edd6b-118">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="edd6b-118">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





