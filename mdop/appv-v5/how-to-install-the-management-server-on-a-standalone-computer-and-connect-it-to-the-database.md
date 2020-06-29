---
title: 如何在独立计算机上安装 Management Server 并将其连接到数据库
description: 如何在独立计算机上安装 Management Server 并将其连接到数据库
author: dansimp
ms.assetid: 95281287-cb56-4117-befd-854268ea147c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 86f384e88b85101855287bb428e75376f7974219
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798443"
---
# <span data-ttu-id="8c3bf-103">如何在独立计算机上安装 Management Server 并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="8c3bf-103">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>


<span data-ttu-id="8c3bf-104">使用以下过程在独立计算机上安装管理服务器，并将其连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-104">Use the following procedure to install the management server on a standalone computer and connect it to the database.</span></span>

**<span data-ttu-id="8c3bf-105">在独立计算机上安装管理服务器并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="8c3bf-105">To install the management server on a standalone computer and connect it to the database</span></span>**

1.  <span data-ttu-id="8c3bf-106">将 app-v 5.0 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-106">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="8c3bf-107">若要启动 app-v 5.0 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-107">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="8c3bf-108">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-108">Click **Install**.</span></span>

2.  <span data-ttu-id="8c3bf-109">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-109">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="8c3bf-110">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="8c3bf-110">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="8c3bf-111">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-111">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="8c3bf-112">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-112">Click **Next**.</span></span>

4.  <span data-ttu-id="8c3bf-113">在**功能选择**页面上，选中 "**管理服务器**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-113">On the **Feature Selection** page, select the **Management Server** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="8c3bf-114">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-114">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="8c3bf-115">在 "**配置现有管理数据库**" 页面上，选择 "**使用远程 SQL Server**"，然后键入运行 Microsoft sql sql 的计算机的计算机名称，例如**SqlServerMachine**。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-115">On the **Configure Existing Management Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL SQL, for example **SqlServerMachine**.</span></span>

    **<span data-ttu-id="8c3bf-116">注意</span><span class="sxs-lookup"><span data-stu-id="8c3bf-116">Note</span></span>**  
    <span data-ttu-id="8c3bf-117">如果 Microsoft SQL Server 部署在同一台服务器上，请选择 "**使用本地 SQL server**"。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-117">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this management server will use, for example **AppvManagement**.
~~~

7. <span data-ttu-id="8c3bf-118">在 "**配置管理服务器配置**" 页面上，指定将连接到管理控制台（例如**MyDomain\\MyUser**或**MyDomain\\AdminGroup**）的广告组或帐户。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-118">On the **Configure Management Server Configuration** page, specify the AD group or account that will connect to the management console for administrative purposes for example **MyDomain\\MyUser** or **MyDomain\\AdminGroup**.</span></span> <span data-ttu-id="8c3bf-119">将启用你指定的帐户或 AD 组，以便通过管理控制台管理服务器。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-119">The account or AD group you specify will be enabled to manage the server through the management console.</span></span> <span data-ttu-id="8c3bf-120">安装后，你可以使用管理控制台添加其他用户或组</span><span class="sxs-lookup"><span data-stu-id="8c3bf-120">You can add additional users or groups using the management console after installation</span></span>

   <span data-ttu-id="8c3bf-121">指定要用于管理服务的**网站名称**。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-121">Specify the **Website Name** that you want to use for the management service.</span></span> <span data-ttu-id="8c3bf-122">如果您没有自定义名称，请接受默认值。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-122">Accept the default if you do not have a custom name.</span></span> <span data-ttu-id="8c3bf-123">对于**端口绑定**，请指定要使用的唯一端口号，例如**12345**。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-123">For the **Port Binding**, specify a unique port number to be used, for example **12345**.</span></span>

8. <span data-ttu-id="8c3bf-124">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-124">Click **Install**.</span></span>

9. <span data-ttu-id="8c3bf-125">若要确认安装程序已成功完成，请打开 web 浏览器，然后键入以下 URL： http://managementserver:portnumber/Console.html 如果安装成功，您应该看到**Silverlight 管理控制台**出现，并且不显示任何错误消息或警告。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-125">To confirm that the setup has completed successfully, open a web browser, and type the following URL: http://managementserver:portnumber/Console.html if the installation was successful you should see the **Silverlight Management Console** appear without any error messages or warnings being displayed.</span></span>

   <span data-ttu-id="8c3bf-126">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="8c3bf-126">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="8c3bf-127">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-127">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="8c3bf-128">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="8c3bf-128">Got an App-V issue?</span></span>** <span data-ttu-id="8c3bf-129">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="8c3bf-129">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="8c3bf-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="8c3bf-130">Related topics</span></span>


[<span data-ttu-id="8c3bf-131">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="8c3bf-131">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)









