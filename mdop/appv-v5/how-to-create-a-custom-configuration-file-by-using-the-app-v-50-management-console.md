---
title: 如何使用 App-V 5.0 Management Console 创建自定义配置文件
description: 如何使用 App-V 5.0 Management Console 创建自定义配置文件
author: dansimp
ms.assetid: 0d1f6768-be30-4682-8eeb-aa95918b24c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d54e68caa380025b2ff6f3ea79d30f275b589b30
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798518"
---
# <span data-ttu-id="5a1bd-103">如何使用 App-V 5.0 Management Console 创建自定义配置文件</span><span class="sxs-lookup"><span data-stu-id="5a1bd-103">How to Create a Custom Configuration File by Using the App-V 5.0 Management Console</span></span>


<span data-ttu-id="5a1bd-104">你可以使用动态配置为特定用户自定义 app-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-104">You can use a dynamic configuration to customize an App-V 5.0 package for a specific user.</span></span> <span data-ttu-id="5a1bd-105">但是，必须首先创建动态用户配置（.xml）文件或动态部署配置文件，然后才能使用这些文件。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-105">However, you must first create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use the files.</span></span> <span data-ttu-id="5a1bd-106">文件的创建是一个高级手动操作。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-106">Creation of the file is an advanced manual operation.</span></span> <span data-ttu-id="5a1bd-107">有关动态用户配置文件的一般信息，请参阅[关于 app-v 5.0 动态配置](about-app-v-50-dynamic-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-107">For general information about dynamic user configuration files, see, [About App-V 5.0 Dynamic Configuration](about-app-v-50-dynamic-configuration.md).</span></span>

<span data-ttu-id="5a1bd-108">使用以下过程，使用 App-v 5.0 管理控制台创建动态用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-108">Use the following procedure to create a Dynamic User Configuration file by using the App-V 5.0 Management console.</span></span>

**<span data-ttu-id="5a1bd-109">创建动态用户配置文件</span><span class="sxs-lookup"><span data-stu-id="5a1bd-109">To create a Dynamic User Configuration file</span></span>**

1.  <span data-ttu-id="5a1bd-110">右键单击要查看的程序包的名称，然后选择 "**编辑 active directory 访问权限**" 以查看分配给给定用户组的配置。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-110">Right-click the name of the package that you want to view and select **Edit active directory access** to view the configuration that is assigned to a given user group.</span></span> <span data-ttu-id="5a1bd-111">或者，选择该程序包，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-111">Alternatively, select the package, and click **Edit**.</span></span>

2.  <span data-ttu-id="5a1bd-112">通过使用**具有 Access 的广告实体**的列表，选择要自定义的广告组。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-112">Using the list of **AD Entities with Access**, select the AD group that you want to customize.</span></span> <span data-ttu-id="5a1bd-113">从下拉列表中选择 "**自定义**" （如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-113">Select **Custom** from the drop-down list, if it is not already selected.</span></span> <span data-ttu-id="5a1bd-114">将显示名为**Edit**的链接。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-114">A link named **Edit** will be displayed.</span></span>

3.  <span data-ttu-id="5a1bd-115">单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-115">Click **Edit**.</span></span> <span data-ttu-id="5a1bd-116">将显示分配给 AD 组的动态用户配置。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-116">The Dynamic User Configuration that is assigned to the AD Group will be displayed.</span></span>

4.  <span data-ttu-id="5a1bd-117">单击 "**高级**"，然后单击 "**导出配置**"。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-117">Click **Advanced**, and then click **Export Configuration**.</span></span> <span data-ttu-id="5a1bd-118">键入文件名，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-118">Type in a filename and click **Save**.</span></span> <span data-ttu-id="5a1bd-119">现在，你可以编辑文件来为用户配置程序包。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-119">Now you can edit the file to configure a package for a user.</span></span>

    <span data-ttu-id="5a1bd-120">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="5a1bd-120">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="5a1bd-121">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-121">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="5a1bd-122">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="5a1bd-122">Got an App-V issue?</span></span>** <span data-ttu-id="5a1bd-123">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="5a1bd-123">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="5a1bd-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="5a1bd-124">Related topics</span></span>


[<span data-ttu-id="5a1bd-125">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="5a1bd-125">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





