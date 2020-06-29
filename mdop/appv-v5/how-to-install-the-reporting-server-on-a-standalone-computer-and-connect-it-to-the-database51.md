---
title: 如何在独立计算机上安装报告服务器并将其连接到数据库
description: 如何在独立计算机上安装报告服务器并将其连接到数据库
author: dansimp
ms.assetid: 11f07750-4045-4c8d-a583-7d70c9e9aa7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67866714ff6ae60097d9b368fd0eaf361b08eec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798429"
---
# <span data-ttu-id="18929-103">如何在独立计算机上安装报告服务器并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="18929-103">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>

<span data-ttu-id="18929-104">使用以下过程在独立计算机上安装报告服务器，并将其连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="18929-104">Use the following procedure to install the reporting server on a standalone computer and connect it to the database.</span></span>

<span data-ttu-id="18929-105">**重要提示**在执行以下过程之前，应阅读并了解[有关 app-v 5.1 的报告](about-app-v-51-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="18929-105">**Important** Before performing the following procedure you should read and understand [About App-V 5.1 Reporting](about-app-v-51-reporting.md).</span></span>

## <span data-ttu-id="18929-106">在独立计算机上安装报表服务器并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="18929-106">To install the reporting server on a standalone computer and connect it to the database</span></span>

1. <span data-ttu-id="18929-107">将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="18929-107">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="18929-108">若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="18929-108">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="18929-109">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="18929-109">Click **Install**.</span></span>

2. <span data-ttu-id="18929-110">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18929-110">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3. <span data-ttu-id="18929-111">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="18929-111">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="18929-112">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="18929-112">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="18929-113">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18929-113">Click **Next**.</span></span>

4. <span data-ttu-id="18929-114">在 "**功能选择**" 页面上，选中 "**报表服务器**" 复选框，然后单击 "**下一步**"</span><span class="sxs-lookup"><span data-stu-id="18929-114">On the **Feature Selection** page, select the **Reporting Server** checkbox and click **Next**.</span></span>

5. <span data-ttu-id="18929-115">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18929-115">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6. <span data-ttu-id="18929-116">在 "**配置现有报告数据库**" 页面上，选择 "**使用远程 SQL server**"，然后键入运行 Microsoft SQL server 的计算机的名称，例如**SqlServerMachine**。</span><span class="sxs-lookup"><span data-stu-id="18929-116">On the **Configure Existing Reporting Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL Server, for example **SqlServerMachine**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="18929-117">如果 Microsoft SQL Server 部署在同一台服务器上，请选择 "**使用本地 SQL server**"。</span><span class="sxs-lookup"><span data-stu-id="18929-117">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>

    <span data-ttu-id="18929-118">对于 SQL Server 实例，请选择 "**使用默认实例"**。</span><span class="sxs-lookup"><span data-stu-id="18929-118">For the SQL Server Instance, select **Use the default instance**.</span></span> <span data-ttu-id="18929-119">如果你使用的是自定义 Microsoft SQL Server 实例，则必须选择 "**使用自定义实例**"，然后键入实例的名称。</span><span class="sxs-lookup"><span data-stu-id="18929-119">If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.</span></span>

    <span data-ttu-id="18929-120">指定此报表服务器将使用的**SQL Server 数据库名称**，例如**AppvReporting**。</span><span class="sxs-lookup"><span data-stu-id="18929-120">Specify the **SQL Server Database name** that this reporting server will use, for example **AppvReporting**.</span></span>

7. <span data-ttu-id="18929-121">在 "**配置报表服务器配置**" 页面上。</span><span class="sxs-lookup"><span data-stu-id="18929-121">On the **Configure Reporting Server Configuration** page.</span></span>

   - <span data-ttu-id="18929-122">指定要用于报告服务的网站名称。</span><span class="sxs-lookup"><span data-stu-id="18929-122">Specify the Website Name that you want to use for the Reporting Service.</span></span> <span data-ttu-id="18929-123">如果您没有自定义名称，则保留默认值不变。</span><span class="sxs-lookup"><span data-stu-id="18929-123">Leave the default unchanged if you do not have a custom name.</span></span>

   - <span data-ttu-id="18929-124">对于**端口绑定**，请指定将由 app-v 5.1 使用的唯一端口号（例如**55555**）。</span><span class="sxs-lookup"><span data-stu-id="18929-124">For the **Port binding**, specify a unique port number that will be used by App-V 5.1, for example **55555**.</span></span> <span data-ttu-id="18929-125">你还应确保指定的端口未被其他网站使用。</span><span class="sxs-lookup"><span data-stu-id="18929-125">You should also ensure that the port specified is not being used by another website.</span></span>

8. <span data-ttu-id="18929-126">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="18929-126">Click **Install**.</span></span>

**<span data-ttu-id="18929-127">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="18929-127">Got an App-V issue?</span></span>** <span data-ttu-id="18929-128">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="18929-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="18929-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="18929-129">Related topics</span></span>

[<span data-ttu-id="18929-130">关于 App-V 5.1 报告</span><span class="sxs-lookup"><span data-stu-id="18929-130">About App-V 5.1 Reporting</span></span>](about-app-v-51-reporting.md)

[<span data-ttu-id="18929-131">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="18929-131">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="18929-132">如何使用 PowerShell 在 App-V 5.1 Client 上启用报告</span><span class="sxs-lookup"><span data-stu-id="18929-132">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)
