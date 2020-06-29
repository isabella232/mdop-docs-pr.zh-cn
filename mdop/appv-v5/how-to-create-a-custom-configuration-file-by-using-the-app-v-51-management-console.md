---
title: 如何使用 App-V 5.1 Management Console 创建自定义配置文件
description: 如何使用 App-V 5.1 Management Console 创建自定义配置文件
author: dansimp
ms.assetid: f5ab426a-f49a-47b3-93f3-b9d60aada8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 282207b5424442950e88c40a372194e9def768cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798517"
---
# <span data-ttu-id="65e70-103">如何使用 App-V 5.1 Management Console 创建自定义配置文件</span><span class="sxs-lookup"><span data-stu-id="65e70-103">How to Create a Custom Configuration File by Using the App-V 5.1 Management Console</span></span>


<span data-ttu-id="65e70-104">你可以使用动态配置为特定用户自定义 app-v 5.1 程序包。</span><span class="sxs-lookup"><span data-stu-id="65e70-104">You can use a dynamic configuration to customize an App-V 5.1 package for a specific user.</span></span> <span data-ttu-id="65e70-105">但是，必须首先创建动态用户配置（.xml）文件或动态部署配置文件，然后才能使用这些文件。</span><span class="sxs-lookup"><span data-stu-id="65e70-105">However, you must first create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use the files.</span></span> <span data-ttu-id="65e70-106">文件的创建是一个高级手动操作。</span><span class="sxs-lookup"><span data-stu-id="65e70-106">Creation of the file is an advanced manual operation.</span></span> <span data-ttu-id="65e70-107">有关动态用户配置文件的一般信息，请参阅[关于 app-v 5.1 动态配置](about-app-v-51-dynamic-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="65e70-107">For general information about dynamic user configuration files, see, [About App-V 5.1 Dynamic Configuration](about-app-v-51-dynamic-configuration.md).</span></span>

<span data-ttu-id="65e70-108">使用以下过程，使用 App-v 5.1 管理控制台创建动态用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="65e70-108">Use the following procedure to create a Dynamic User Configuration file by using the App-V 5.1 Management console.</span></span>

**<span data-ttu-id="65e70-109">创建动态用户配置文件</span><span class="sxs-lookup"><span data-stu-id="65e70-109">To create a Dynamic User Configuration file</span></span>**

1.  <span data-ttu-id="65e70-110">右键单击要查看的程序包的名称，然后选择 "**编辑 active directory 访问权限**" 以查看分配给给定用户组的配置。</span><span class="sxs-lookup"><span data-stu-id="65e70-110">Right-click the name of the package that you want to view and select **Edit active directory access** to view the configuration that is assigned to a given user group.</span></span> <span data-ttu-id="65e70-111">或者，选择该程序包，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="65e70-111">Alternatively, select the package, and click **Edit**.</span></span>

2.  <span data-ttu-id="65e70-112">通过使用**具有 Access 的广告实体**的列表，选择要自定义的广告组。</span><span class="sxs-lookup"><span data-stu-id="65e70-112">Using the list of **AD Entities with Access**, select the AD group that you want to customize.</span></span> <span data-ttu-id="65e70-113">从下拉列表中选择 "**自定义**" （如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="65e70-113">Select **Custom** from the drop-down list, if it is not already selected.</span></span> <span data-ttu-id="65e70-114">将显示名为**Edit**的链接。</span><span class="sxs-lookup"><span data-stu-id="65e70-114">A link named **Edit** will be displayed.</span></span>

3.  <span data-ttu-id="65e70-115">单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="65e70-115">Click **Edit**.</span></span> <span data-ttu-id="65e70-116">将显示分配给 AD 组的动态用户配置。</span><span class="sxs-lookup"><span data-stu-id="65e70-116">The Dynamic User Configuration that is assigned to the AD Group will be displayed.</span></span>

4.  <span data-ttu-id="65e70-117">单击 "**高级**"，然后单击 "**导出配置**"。</span><span class="sxs-lookup"><span data-stu-id="65e70-117">Click **Advanced**, and then click **Export Configuration**.</span></span> <span data-ttu-id="65e70-118">键入文件名，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="65e70-118">Type in a filename and click **Save**.</span></span> <span data-ttu-id="65e70-119">现在，你可以编辑文件来为用户配置程序包。</span><span class="sxs-lookup"><span data-stu-id="65e70-119">Now you can edit the file to configure a package for a user.</span></span>

    **<span data-ttu-id="65e70-120">注意</span><span class="sxs-lookup"><span data-stu-id="65e70-120">Note</span></span>**  
    <span data-ttu-id="65e70-121">若要在 Windows Server 上运行时导出配置，必须禁用 "IE 增强的安全配置"。</span><span class="sxs-lookup"><span data-stu-id="65e70-121">To export a configuration while running on Windows Server, you must disable "IE Enhanced Security Configuration".</span></span> <span data-ttu-id="65e70-122">如果启用了此功能，并将其设置为 "阻止下载"，则不能从 App-v 服务器下载任何内容。</span><span class="sxs-lookup"><span data-stu-id="65e70-122">If this is enabled and set to block downloads, you cannot download anything from the App-V Server.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="65e70-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="65e70-123">Related topics</span></span>


[<span data-ttu-id="65e70-124">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="65e70-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









