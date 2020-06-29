---
title: 如何在独立计算机上安装报告服务器并将其连接到数据库
description: 如何在独立计算机上安装报告服务器并将其连接到数据库
author: dansimp
ms.assetid: d186bdb7-e522-4124-bc6d-7d5a41ba8266
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f20f1ce16c3f0168d1c797efd816d4125c0f1f53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798432"
---
# <span data-ttu-id="02ed9-103">如何在独立计算机上安装报告服务器并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="02ed9-103">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>


<span data-ttu-id="02ed9-104">使用以下过程在独立计算机上安装报告服务器，并将其连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="02ed9-104">Use the following procedure to install the reporting server on a standalone computer and connect it to the database.</span></span>

**<span data-ttu-id="02ed9-105">重要提示</span><span class="sxs-lookup"><span data-stu-id="02ed9-105">Important</span></span>**  
<span data-ttu-id="02ed9-106">在执行以下过程之前，应阅读并了解[有关 app-v 5.0 的报告](about-app-v-50-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="02ed9-106">Before performing the following procedure you should read and understand [About App-V 5.0 Reporting](about-app-v-50-reporting.md).</span></span>



**<span data-ttu-id="02ed9-107">在独立计算机上安装报表服务器并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="02ed9-107">To install the reporting server on a standalone computer and connect it to the database</span></span>**

1.  <span data-ttu-id="02ed9-108">将 app-v 5.0 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="02ed9-108">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="02ed9-109">若要启动 app-v 5.0 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="02ed9-109">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="02ed9-110">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="02ed9-110">Click **Install**.</span></span>

2.  <span data-ttu-id="02ed9-111">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="02ed9-111">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="02ed9-112">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="02ed9-112">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="02ed9-113">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="02ed9-113">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="02ed9-114">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02ed9-114">Click **Next**.</span></span>

4.  <span data-ttu-id="02ed9-115">在 "**功能选择**" 页面上，选中 "**报表服务器**" 复选框，然后单击 "**下一步**"</span><span class="sxs-lookup"><span data-stu-id="02ed9-115">On the **Feature Selection** page, select the **Reporting Server** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="02ed9-116">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="02ed9-116">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="02ed9-117">在 "**配置现有报告数据库**" 页面上，选择 "**使用远程 SQL server**"，然后键入运行 Microsoft SQL server 的计算机的名称，例如**SqlServerMachine**。</span><span class="sxs-lookup"><span data-stu-id="02ed9-117">On the **Configure Existing Reporting Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL Server, for example **SqlServerMachine**.</span></span>

    **<span data-ttu-id="02ed9-118">注意</span><span class="sxs-lookup"><span data-stu-id="02ed9-118">Note</span></span>**  
    <span data-ttu-id="02ed9-119">如果 Microsoft SQL Server 部署在同一台服务器上，请选择 "**使用本地 SQL server**"。</span><span class="sxs-lookup"><span data-stu-id="02ed9-119">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this reporting server will use, for example **AppvReporting**.
~~~

7. <span data-ttu-id="02ed9-120">在 "**配置报表服务器配置**" 页面上。</span><span class="sxs-lookup"><span data-stu-id="02ed9-120">On the **Configure Reporting Server Configuration** page.</span></span>

   -   <span data-ttu-id="02ed9-121">指定要用于报告服务的网站名称。</span><span class="sxs-lookup"><span data-stu-id="02ed9-121">Specify the Website Name that you want to use for the Reporting Service.</span></span> <span data-ttu-id="02ed9-122">如果您没有自定义名称，则保留默认值不变。</span><span class="sxs-lookup"><span data-stu-id="02ed9-122">Leave the default unchanged if you do not have a custom name.</span></span>

   -   <span data-ttu-id="02ed9-123">对于**端口绑定**，请指定将由 app-v 5.0 使用的唯一端口号（例如**55555**）。</span><span class="sxs-lookup"><span data-stu-id="02ed9-123">For the **Port binding**, specify a unique port number that will be used by App-V 5.0, for example **55555**.</span></span> <span data-ttu-id="02ed9-124">你还应确保指定的端口未被其他网站使用。</span><span class="sxs-lookup"><span data-stu-id="02ed9-124">You should also ensure that the port specified is not being used by another website.</span></span>

8. <span data-ttu-id="02ed9-125">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="02ed9-125">Click **Install**.</span></span>

   <span data-ttu-id="02ed9-126">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="02ed9-126">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="02ed9-127">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="02ed9-127">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="02ed9-128">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="02ed9-128">Got an App-V issue?</span></span>** <span data-ttu-id="02ed9-129">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="02ed9-129">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="02ed9-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="02ed9-130">Related topics</span></span>


[<span data-ttu-id="02ed9-131">关于 App-V 5.0 报告</span><span class="sxs-lookup"><span data-stu-id="02ed9-131">About App-V 5.0 Reporting</span></span>](about-app-v-50-reporting.md)

[<span data-ttu-id="02ed9-132">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="02ed9-132">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

[<span data-ttu-id="02ed9-133">如何使用 PowerShell 在 App-V 5.0 Client 上启用报告</span><span class="sxs-lookup"><span data-stu-id="02ed9-133">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)









