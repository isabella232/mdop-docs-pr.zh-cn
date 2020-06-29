---
title: 如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置
description: 如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置
author: dansimp
ms.assetid: 79d03a2b-2586-4ca7-bbaa-bdeb0a694279
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cd257691bf223baa5e2919d83fdbf53d34f271ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798396"
---
# <span data-ttu-id="653dd-103">如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置</span><span class="sxs-lookup"><span data-stu-id="653dd-103">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span>


<span data-ttu-id="653dd-104">使用 "app-v 5.0 ADMX" 模板，使用 ADMX 模板和组策略配置 app-v 5.0 客户端设置。</span><span class="sxs-lookup"><span data-stu-id="653dd-104">Use the App-V 5.0 ADMX template to configure App-V 5.0 client settings using the ADMX Template and Group Policy.</span></span>

**<span data-ttu-id="653dd-105">使用组策略修改 App-v 5.0 客户端配置</span><span class="sxs-lookup"><span data-stu-id="653dd-105">To modify App-V 5.0 client configuration using Group Policy</span></span>**

1.  <span data-ttu-id="653dd-106">若要修改 app-v 5.0 客户端配置，请找到适用于 app-v 5.0 的**ADMXTemplate**文件。</span><span class="sxs-lookup"><span data-stu-id="653dd-106">To modify the App-V 5.0 client configuration, locate the **ADMXTemplate** files that are available with App-V 5.0.</span></span>

    <span data-ttu-id="653dd-107">**注意** 使用以下链接下载 app-v 5.0 **ADMX 模板**： <https://go.microsoft.com/fwlink/p/?LinkId=393941> 。</span><span class="sxs-lookup"><span data-stu-id="653dd-107">**Note** Use the following link to download the App-V 5.0 **ADMX Templates**: <https://go.microsoft.com/fwlink/p/?LinkId=393941>.</span></span>

     

2.  <span data-ttu-id="653dd-108">在管理组策略的计算机（通常为域控制器）上，将模板**admx**文件复制到以下目录： \*\* &lt; 安装驱动器 &gt; \\ Windows \\ PolicyDefinitions\*\*。</span><span class="sxs-lookup"><span data-stu-id="653dd-108">On the computer where you manage group Policy, typically the domain controller, copy the template **.admx** file to the following directory: **&lt;Installation Drive&gt; \\ Windows \\ PolicyDefinitions**.</span></span>

    <span data-ttu-id="653dd-109">接下来，在同一台计算机上，将**adml**文件复制到以下目录： \*\* &lt; InstallationDrive &gt; \\ Windows \\ PolicyDefinitions \ en-us\*\*。</span><span class="sxs-lookup"><span data-stu-id="653dd-109">Next, on the same computer, copy the **.adml** file to the following directory: **&lt;InstallationDrive&gt; \\ Windows \\ PolicyDefinitions \\ en-US**.</span></span>

3.  <span data-ttu-id="653dd-110">将文件复制到 "组策略管理控制台" 之后，若要修改与应用-v 5.0 客户端关联的策略，请浏览到 "**计算机配置**  /  **策略**"  /  **管理模板**  /  **系统**  /  **app-v**。</span><span class="sxs-lookup"><span data-stu-id="653dd-110">After you have copied the files open the Group Policy Management Console, to modify the policies associated with your App-V 5.0 clients browse to **Computer Configuration** / **Policies** / **Administrative Templates** / **System** / **App-V**.</span></span>

    <span data-ttu-id="653dd-111">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="653dd-111">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="653dd-112">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="653dd-112">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="653dd-113">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="653dd-113">Got an App-V issue?</span></span>** <span data-ttu-id="653dd-114">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="653dd-114">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="653dd-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="653dd-115">Related topics</span></span>


[<span data-ttu-id="653dd-116">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="653dd-116">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

[<span data-ttu-id="653dd-117">关于 Client 配置设置</span><span class="sxs-lookup"><span data-stu-id="653dd-117">About Client Configuration Settings</span></span>](about-client-configuration-settings.md)

 

 





