---
title: 如何在远程计算机上安装发布服务器
description: 如何在远程计算机上安装发布服务器
author: dansimp
ms.assetid: 37970706-54ff-4799-9485-b9b49fd50f37
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d711fa51ade856b3ac5880ba60a19315c358734
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798435"
---
# <span data-ttu-id="421cb-103">如何在远程计算机上安装发布服务器</span><span class="sxs-lookup"><span data-stu-id="421cb-103">How to Install the Publishing Server on a Remote Computer</span></span>


<span data-ttu-id="421cb-104">使用以下过程在单独的计算机上安装发布服务器。</span><span class="sxs-lookup"><span data-stu-id="421cb-104">Use the following procedure to install the publishing server on a separate computer.</span></span> <span data-ttu-id="421cb-105">在执行以下过程之前，请确保数据库和管理服务器可用。</span><span class="sxs-lookup"><span data-stu-id="421cb-105">Before you perform the following procedure, ensure the database and management server are available.</span></span>

**<span data-ttu-id="421cb-106">在单独的计算机上安装发布服务器</span><span class="sxs-lookup"><span data-stu-id="421cb-106">To install the publishing server on a separate computer</span></span>**

1. <span data-ttu-id="421cb-107">将 app-v 5.0 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="421cb-107">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="421cb-108">若要启动 app-v 5.0 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="421cb-108">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="421cb-109">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="421cb-109">Click **Install**.</span></span>

2. <span data-ttu-id="421cb-110">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="421cb-110">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3. <span data-ttu-id="421cb-111">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="421cb-111">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="421cb-112">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="421cb-112">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="421cb-113">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="421cb-113">Click **Next**.</span></span>

4. <span data-ttu-id="421cb-114">在**功能选择**页面上，选择 "**发布服务器**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="421cb-114">On the **Feature Selection** page, select the **Publishing Server** checkbox and click **Next**.</span></span>

5. <span data-ttu-id="421cb-115">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="421cb-115">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6. <span data-ttu-id="421cb-116">在 "**配置发布服务器配置**" 页面上，指定以下项目：</span><span class="sxs-lookup"><span data-stu-id="421cb-116">On the **Configure Publishing Server Configuration** page, specify the following items:</span></span>

   -   <span data-ttu-id="421cb-117">发布服务器将连接到的管理服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="421cb-117">The URL for the management service that the publishing server will connect to.</span></span> <span data-ttu-id="421cb-118">例如， **http://ManagementServerName:12345** 。</span><span class="sxs-lookup"><span data-stu-id="421cb-118">For example, **http://ManagementServerName:12345**.</span></span>

   -   <span data-ttu-id="421cb-119">指定要用于发布服务的网站名称。</span><span class="sxs-lookup"><span data-stu-id="421cb-119">Specify the website name that you want to use for the publishing service.</span></span> <span data-ttu-id="421cb-120">如果您没有自定义名称，请接受默认值。</span><span class="sxs-lookup"><span data-stu-id="421cb-120">Accept the default if you do not have a custom name.</span></span>

   -   <span data-ttu-id="421cb-121">对于**端口绑定**，请指定将由 app-v 5.0 使用的唯一端口号（例如**54321**）。</span><span class="sxs-lookup"><span data-stu-id="421cb-121">For the **Port Binding**, specify a unique port number that will be used by App-V 5.0, for example **54321**.</span></span>

7. <span data-ttu-id="421cb-122">在 "**准备安装**" 页面上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="421cb-122">On the **Ready to Install** page, click **Install**.</span></span>

8. <span data-ttu-id="421cb-123">安装完成后，发布服务器必须注册到管理服务器。</span><span class="sxs-lookup"><span data-stu-id="421cb-123">After the installation is complete, the publishing server must be registered with the management server.</span></span> <span data-ttu-id="421cb-124">在 App-v 5.0 管理控制台中，使用以下步骤注册服务器：</span><span class="sxs-lookup"><span data-stu-id="421cb-124">In the App-V 5.0 management console, use the following steps to register the server:</span></span>

   1.  <span data-ttu-id="421cb-125">打开 app-v 5.0 管理服务器控制台。</span><span class="sxs-lookup"><span data-stu-id="421cb-125">Open the App-V 5.0 management server console.</span></span>

   2.  <span data-ttu-id="421cb-126">在左窗格中，选择 "**服务器**"，然后选择 "**注册新服务器**"。</span><span class="sxs-lookup"><span data-stu-id="421cb-126">In the left pane, select **Servers**, and then select **Register New Server**.</span></span>

   3.  <span data-ttu-id="421cb-127">键入此服务器的名称和说明（如果需要），然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="421cb-127">Type the name of this server and a description (if required) and click **Add**.</span></span>

9. <span data-ttu-id="421cb-128">若要验证发布服务器是否正常运行，应将程序包导入管理服务器、将程序包 entitle 到 AD 组并发布程序包。</span><span class="sxs-lookup"><span data-stu-id="421cb-128">To verify if the publishing server is running correctly, you should import a package to the management server, entitle the package to an AD group, and publish the package.</span></span> <span data-ttu-id="421cb-129">使用 internet 浏览器打开以下 URL： <strong> http://publishingserver:pubport </strong> 。</span><span class="sxs-lookup"><span data-stu-id="421cb-129">Using an internet browser, open the following URL: <strong>http://publishingserver:pubport</strong>.</span></span> <span data-ttu-id="421cb-130">如果服务器运行的信息与以下内容类似，将显示：</span><span class="sxs-lookup"><span data-stu-id="421cb-130">If the server is running correctly information similar to the following will be displayed:</span></span>

   ```xml
   <Publishing Protocol="1.0">
     <Packages>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" VersionId="5d03c08f-51dc-4026-8cf9-15ebe3d65a72" PackageUrl="\\server\share\file.appv" />
     </Packages>
     <NoGroup>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" />
     </NoGroup>
   </Publishing>
   ```

   <span data-ttu-id="421cb-131">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="421cb-131">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="421cb-132">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="421cb-132">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="421cb-133">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="421cb-133">Got an App-V issue?</span></span>** <span data-ttu-id="421cb-134">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="421cb-134">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="421cb-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="421cb-135">Related topics</span></span>


[<span data-ttu-id="421cb-136">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="421cb-136">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

 

 





