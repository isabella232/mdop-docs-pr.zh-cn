---
title: 为 UE-V 1.0 部署 UE-V 设置位置模板
description: 为 UE-V 1.0 部署 UE-V 设置位置模板
author: dansimp
ms.assetid: 7e0cc553-14f7-40fa-828a-281c8d2d1934
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b276fb9d6c0b3749f9818483869dfe98bbc147c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804105"
---
# <span data-ttu-id="ec4d8-103">为 UE-V 1.0 部署 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="ec4d8-103">Deploying UE-V Settings Location Templates for UE-V 1.0</span></span>


<span data-ttu-id="ec4d8-104">Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义用户体验虚拟化捕获和应用的设置。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by User Experience Virtualization.</span></span> <span data-ttu-id="ec4d8-105">UE-V 包含一组标准模板以及一个工具，即 UE-V 生成器，该生成器允许你创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-105">UE-V includes a set of standard templates, as well as a tool, the UE-V Generator, which allows you to create custom settings location templates.</span></span> <span data-ttu-id="ec4d8-106">创建设置位置模板后，应对其进行测试以确保应用程序设置在测试环境中正确漫游。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-106">After you create a settings location template, you should test it to ensure that the application settings roam correctly in a test environment.</span></span> <span data-ttu-id="ec4d8-107">然后，您可以安全地将设置位置模板部署到企业中的计算机。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-107">You can then safely deploy the settings location template to computers in the enterprise.</span></span>

<span data-ttu-id="ec4d8-108">可以使用企业软件分发（ESD）、组策略首选项或通过配置 UE-V 设置模板目录来部署设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-108">Settings location templates can be deployed by using enterprise software distribution (ESD), Group Policy preferences, or by configuring a UE-V settings template catalog.</span></span> <span data-ttu-id="ec4d8-109">使用 ESD 或组策略部署的模板必须通过 UE-V WMI 或 PowerShell 注册。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-109">Templates that are deployed by using an ESD or Group Policy must be registered through UE-V WMI or PowerShell.</span></span> <span data-ttu-id="ec4d8-110">存储在设置模板目录位置的模板由 UE-V agent 自动注册。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-110">Templates that are stored in the settings template catalog location are automatically registered by the UE-V agent.</span></span>

## <span data-ttu-id="ec4d8-111">使用设置模板目录路径部署设置位置模板</span><span class="sxs-lookup"><span data-stu-id="ec4d8-111">Deploy the settings location templates with a settings template catalog path</span></span>


<span data-ttu-id="ec4d8-112">可以使用以下方法定义 UE-V 设置位置模板目录路径：组策略、代理安装命令行参数、WMI 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-112">The UE-V settings location template catalog path can be defined by using the following methods: Group Policy, the agent install command-line parameters, WMI, or PowerShell.</span></span> <span data-ttu-id="ec4d8-113">定义模板目录路径后，UE-V agent 将从该位置检索新的或更新的模板。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-113">After the template catalog path has been defined, the UE-V agent retrieves the new or updated templates from this location.</span></span> <span data-ttu-id="ec4d8-114">UE-V agent 每天检查此位置一次，并根据在此文件夹中找到的模板更新其同步行为。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-114">The UE-V agent checks this location once each day and updates its synchronization behavior based on the templates found in this folder.</span></span> <span data-ttu-id="ec4d8-115">自上次检查以来，在此文件夹中添加或更新的模板由 UE-V agent 注册。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-115">Templates that have been added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="ec4d8-116">UE-V agent 还将注销已从此文件夹中删除的模板。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-116">The UE-V agent also unregisters templates that have been removed from this folder.</span></span> <span data-ttu-id="ec4d8-117">任务计划程序每天注册和注销一次模板。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-117">Templates are registered and unregistered one time per day by the task scheduler.</span></span>

**<span data-ttu-id="ec4d8-118">使用设置模板目录路径部署 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="ec4d8-118">To use settings template catalog path to deploy UE-V settings location templates</span></span>**

1.  <span data-ttu-id="ec4d8-119">导航到定义为设置模板目录的网络共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-119">Navigate to the network share folder that is defined as the settings template catalog.</span></span>

2.  <span data-ttu-id="ec4d8-120">在设置模板目录中添加、删除或更新设置位置模板，以反映 UE-V 计算机的所需 UE-V agent 模板配置。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-120">Add, remove, or update settings location templates in the settings template catalog to reflect the desired UE-V agent template configuration for UE-V computers.</span></span>

3.  <span data-ttu-id="ec4d8-121">计算机上的模板根据对设置模板目录的更改每天更新。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-121">Templates on computers are updated daily based on changes to the settings template catalog.</span></span>

4.  <span data-ttu-id="ec4d8-122">打开提升的命令提示符并导航到 **% program files%\\Microsoft 用户体验虚拟化 \\ agent \ &lt; x86 或 x64 &gt; **，然后运行**ApplySettingsTemplateCatalog.exe**以手动更新运行 ue-v Agent 的计算机上的模板。</span><span class="sxs-lookup"><span data-stu-id="ec4d8-122">Open an elevated command prompt and navigate to **%program files%\\Microsoft user Experience Virtualization \\ Agent \\ &lt;x86 or x64 &gt;**, and then run **ApplySettingsTemplateCatalog.exe** to manually update templates on a computer that runs the UE-V agent.</span></span>

## <span data-ttu-id="ec4d8-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="ec4d8-123">Related topics</span></span>


[<span data-ttu-id="ec4d8-124">Microsoft 用户体验虚拟化 (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="ec4d8-124">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="ec4d8-125">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="ec4d8-125">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="ec4d8-126">规划要使用 UE-V 1.0 同步的应用程序</span><span class="sxs-lookup"><span data-stu-id="ec4d8-126">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

 

 





