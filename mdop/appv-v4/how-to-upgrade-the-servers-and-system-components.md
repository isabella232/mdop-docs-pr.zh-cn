---
title: 如何升级服务器和系统组件
description: 如何升级服务器和系统组件
author: dansimp
ms.assetid: 7d8374fe-5897-452e-923e-556a854b2024
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 61f8742a2f5e3c17083a77b839dfbee85ea00e24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798968"
---
# <span data-ttu-id="67293-103">如何升级服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="67293-103">How to Upgrade the Servers and System Components</span></span>


<span data-ttu-id="67293-104">使用以下过程升级在所有应用程序虚拟化系统计算机上安装的软件组件。</span><span class="sxs-lookup"><span data-stu-id="67293-104">Use the following procedure to upgrade software components installed on all Application Virtualization System computers.</span></span> <span data-ttu-id="67293-105">升级后，应用程序虚拟化系统服务将在每台计算机上自动重启。</span><span class="sxs-lookup"><span data-stu-id="67293-105">Application Virtualization System services will be restarted automatically on each computer after it has been upgraded.</span></span>

**<span data-ttu-id="67293-106">注意</span><span class="sxs-lookup"><span data-stu-id="67293-106">Note</span></span>**  
-   <span data-ttu-id="67293-107">升级过程将停止所有应用程序虚拟化系统服务，从而导致系统停止服务。</span><span class="sxs-lookup"><span data-stu-id="67293-107">The upgrade process stops all Application Virtualization System services, thereby taking the system out of service.</span></span> <span data-ttu-id="67293-108">在开始升级过程之前，应关闭用户会话，并且你应该停止环境中的所有应用程序虚拟化服务器服务。</span><span class="sxs-lookup"><span data-stu-id="67293-108">User sessions should be shut down before you begin the upgrade process, and you should stop all Application Virtualization Server services in your environment.</span></span>

-   <span data-ttu-id="67293-109">如果你有多个服务器共享对应用程序虚拟化数据库的访问，则所有这些服务器都必须在数据库升级时脱机。</span><span class="sxs-lookup"><span data-stu-id="67293-109">If you have more than one server that is sharing access to the Application Virtualization database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="67293-110">你应遵循数据库升级的正常业务做法，但强烈建议你先在测试服务器上使用数据库的备份副本测试数据库升级。</span><span class="sxs-lookup"><span data-stu-id="67293-110">You should follow your normal business practices for the database upgrade, but it is highly advisable that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="67293-111">然后，你应该选择其中一个服务器进行首次升级，这将升级数据库架构。</span><span class="sxs-lookup"><span data-stu-id="67293-111">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="67293-112">成功升级生产数据库后，您可以升级其他服务器。</span><span class="sxs-lookup"><span data-stu-id="67293-112">After the production database has been successfully upgraded, you can upgrade the other servers.</span></span>

-   <span data-ttu-id="67293-113">仅可从 Microsoft Application Virtualization （app-v）4.1 或 4.1 SP1 升级到 Microsoft Application Virtualization （app-v）4.5。</span><span class="sxs-lookup"><span data-stu-id="67293-113">You can upgrade to Microsoft Application Virtualization (App-V)4.5 only from Microsoft Application Virtualization (App-V)4.1 or4.1 SP1.</span></span> <span data-ttu-id="67293-114">App-v 4.0 及更早版本必须先卸载或升级到4.1 或 4.1 SP1，然后再升级到 app-v 4.5。</span><span class="sxs-lookup"><span data-stu-id="67293-114">App-V4.0 and earlier must be uninstalled or upgraded to4.1 or4.1 SP1 before upgrading to App-V4.5.</span></span>

 

**<span data-ttu-id="67293-115">升级应用程序虚拟化系统计算机上的软件组件</span><span class="sxs-lookup"><span data-stu-id="67293-115">To upgrade software components on Application Virtualization System computers</span></span>**

1.  <span data-ttu-id="67293-116">导航到网络上安装程序的位置，或者从网络运行此程序，或者将其目录复制到目标计算机，然后双击 Setup.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="67293-116">Navigate to the location of the Setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the Setup.exe file.</span></span>

2.  <span data-ttu-id="67293-117">在安装向导的 "**欢迎**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-117">On the **Welcome** page of the Installation Wizard, click **Next**.</span></span>

3.  <span data-ttu-id="67293-118">在 "**许可协议**" 页面上，阅读 "许可协议"，选中 "**我接受许可协议中的条款**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-118">On the **License Agreement** page, read the license agreement, check **I accept the terms in the license agreement**, and click **Next**.</span></span>

4.  <span data-ttu-id="67293-119">当**已安装的软件**页面打开并显示已安装的应用程序虚拟化系统组件的列表和每个组件的版本时，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-119">When the **Installed Software** page opens and displays a list of the installed Application Virtualization System components and the version of each component, click **Next**.</span></span>

5.  <span data-ttu-id="67293-120">在 "**会话丢失警告**" 页面上，阅读显示的消息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-120">On the **Session Loss Warning** page, read the displayed message and click **Next**.</span></span>

6.  <span data-ttu-id="67293-121">在 "**连接到配置数据库**" 页面上，查看页面上的内容，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-121">On the **Connect to Configuration Database** page, review the content on the page and click **Next**.</span></span>

7.  <span data-ttu-id="67293-122">如果显示 "**需要数据库升级**" 页面，则需要数据库升级。</span><span class="sxs-lookup"><span data-stu-id="67293-122">If the **Database Upgrade Required** page is displayed, a database upgrade is required.</span></span> <span data-ttu-id="67293-123">输入数据库管理凭据，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-123">Enter the database administrative credentials, and then click **Next**.</span></span> <span data-ttu-id="67293-124">如果此页面未显示，请跳到步骤9。</span><span class="sxs-lookup"><span data-stu-id="67293-124">If this page is not displayed, skip to Step 9.</span></span>

8.  <span data-ttu-id="67293-125">在 "**备份配置数据库**" 页面上，选中相应的框以执行备份并将其导出到现有位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-125">On the **Backup Configuration Database** page, check the appropriate boxes to perform the backup and export it to an existing location, and then click **Next**.</span></span>

    <span data-ttu-id="67293-126">**重要提示** 如果你希望能够在升级失败的情况下回退到以前的版本，请确保选中 "**对配置数据库执行备份**" 框，否则将丢失配置数据。</span><span class="sxs-lookup"><span data-stu-id="67293-126">**Important** If you want to be able to roll back to the previous version in the event of an upgrade failure, make sure you check the **Perform a backup of the configuration database** box, or you will lose the configuration data.</span></span>

    <span data-ttu-id="67293-127">当您想要使用 VSS 还原数据库时，必须首先停止管理服务器上的 App-v 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="67293-127">When you want to restore a database with VSS, you must first stop the App-V Server Service on the Management Server.</span></span> <span data-ttu-id="67293-128">如果有多个服务器连接到同一个数据库，则应在每个管理服务器上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="67293-128">This should be done on every Management server if there is more than one server connected to the same database.</span></span>

     

9.  <span data-ttu-id="67293-129">在第一个 "**程序包验证**" 页面上，阅读内容，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-129">On the first **Package Validation** page, read the content and then click **Next**.</span></span>

10. <span data-ttu-id="67293-130">在 "第二个**程序包验证**" 页面上，你可以选择在记事本窗口中显示程序包验证的详细信息。</span><span class="sxs-lookup"><span data-stu-id="67293-130">On the second **Package Validation** page, you have the option of displaying the details of the package validation in a Notepad window.</span></span> <span data-ttu-id="67293-131">若要查看详细信息，请单击 "**详细信息**";否则，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-131">To see the details, click **Details**; otherwise, click **Next**.</span></span>

11. <span data-ttu-id="67293-132">在 "**准备好升级程序"** 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="67293-132">On the **Ready to Upgrade the Program** page, click **Next**.</span></span>

12. <span data-ttu-id="67293-133">在 "**安装向导已完成**" 页面上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="67293-133">On the **Installation Wizard Completed** page, click **Finish**.</span></span>

13. <span data-ttu-id="67293-134">在安装了应用程序虚拟化管理控制台或应用程序虚拟化服务器软件组件的所有其他计算机上重复步骤1至12。</span><span class="sxs-lookup"><span data-stu-id="67293-134">Repeat steps 1–12 on all other computers where you installed the Application Virtualization Management Console or the Application Virtualization Server software component.</span></span>

    <span data-ttu-id="67293-135">升级数据存储区后，您可以恢复正常操作。</span><span class="sxs-lookup"><span data-stu-id="67293-135">After upgrading the data store, you can resume normal operation.</span></span> <span data-ttu-id="67293-136">（升级任何服务器或 App-v 管理 Web 服务时，将升级数据存储。）</span><span class="sxs-lookup"><span data-stu-id="67293-136">(The data store is upgraded when you upgrade any server or the App-V Management Web Service.)</span></span>

## <span data-ttu-id="67293-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="67293-137">Related topics</span></span>


[<span data-ttu-id="67293-138">Application Virtualization 部署和升级注意事项</span><span class="sxs-lookup"><span data-stu-id="67293-138">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

 

 





