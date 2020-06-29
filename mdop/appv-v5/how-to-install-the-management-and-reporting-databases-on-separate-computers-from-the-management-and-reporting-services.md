---
title: 如何在单独的计算机上从管理和报告服务安装管理和报告数据库
description: 如何在单独的计算机上从管理和报告服务安装管理和报告数据库
author: dansimp
ms.assetid: 02afd6d6-4c33-4c0b-bd88-ae167b786fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1522045fced411164ac4fd36af41d46ab61ad6f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798442"
---
# <span data-ttu-id="c652b-103">如何在单独的计算机上从管理和报告服务安装管理和报告数据库</span><span class="sxs-lookup"><span data-stu-id="c652b-103">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>


<span data-ttu-id="c652b-104">使用以下过程在不同计算机上安装数据库服务器和管理服务器。</span><span class="sxs-lookup"><span data-stu-id="c652b-104">Use the following procedure to install the database server and management server on different computers.</span></span> <span data-ttu-id="c652b-105">你计划用于安装数据库服务器的计算机必须运行受支持的 Microsoft SQL 版本，否则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="c652b-105">The computer you plan to install the database server on must be running a supported version of Microsoft SQL or the installation will fail.</span></span>

**<span data-ttu-id="c652b-106">注意</span><span class="sxs-lookup"><span data-stu-id="c652b-106">Note</span></span>**  
<span data-ttu-id="c652b-107">完成部署后，安装该服务的管理员将需要**MICROSOFT SQL Server 名称**、**实例名称**和**数据库名称**才能连接到这些数据库。</span><span class="sxs-lookup"><span data-stu-id="c652b-107">After you complete the deployment, the **Microsoft SQL Server name**, **instance name** and **database name** will be required by the administrator installing the service to be able to connect to these databases.</span></span>



**<span data-ttu-id="c652b-108">在单独的计算机上安装管理数据库和管理服务器</span><span class="sxs-lookup"><span data-stu-id="c652b-108">To install the management database and the management server on separate computers</span></span>**

1.  <span data-ttu-id="c652b-109">将 app-v 5.0 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="c652b-109">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="c652b-110">若要启动 app-v 5.0 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="c652b-110">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="c652b-111">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="c652b-111">Click **Install**.</span></span>

2.  <span data-ttu-id="c652b-112">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-112">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="c652b-113">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="c652b-113">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="c652b-114">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-114">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="c652b-115">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c652b-115">Click **Next**.</span></span>

4.  <span data-ttu-id="c652b-116">在 "**功能选择**" 页面上，选择要安装的组件，方法是选择 "**管理服务器数据库**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-116">On the **Feature Selection** page, select the components you want to install by selecting the **Management Server Database** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="c652b-117">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-117">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="c652b-118">在 "**新建管理服务器数据库" 页面**上，接受默认选择（如果适用），然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-118">On the initial **Create New Management Server Database page**, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="c652b-119">如果你使用的是自定义 SQL Server 实例，请选择 "**使用自定义实例**"，然后键入实例的名称。</span><span class="sxs-lookup"><span data-stu-id="c652b-119">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>

    <span data-ttu-id="c652b-120">如果您使用的是自定义数据库名称，请选择 "**自定义配置**"，然后键入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="c652b-120">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

7.  <span data-ttu-id="c652b-121">在 "**新建管理服务器数据库**" 页面上，选择 "**使用远程计算机**"，然后使用以下格式键入远程计算机帐户： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="c652b-121">On the next **Create New Management Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    **<span data-ttu-id="c652b-122">注意</span><span class="sxs-lookup"><span data-stu-id="c652b-122">Note</span></span>**  
    <span data-ttu-id="c652b-123">如果你计划在同一台计算机上部署管理服务器，必须选择 "**使用此本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-123">If you plan to deploy the management server on the same computer you must select **Use this local computer**.</span></span>



~~~
Specify the user name for the management server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**. Click **Next**.
~~~

8. <span data-ttu-id="c652b-124">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-124">To start the installation, click **Install**.</span></span>

**<span data-ttu-id="c652b-125">在单独的计算机上安装报表数据库和报表服务器</span><span class="sxs-lookup"><span data-stu-id="c652b-125">To install the reporting database and the reporting server on separate computers</span></span>**

1.  <span data-ttu-id="c652b-126">将 app-v 5.0 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="c652b-126">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="c652b-127">若要启动 app-v 5.0 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="c652b-127">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="c652b-128">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="c652b-128">Click **Install**.</span></span>

2.  <span data-ttu-id="c652b-129">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-129">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="c652b-130">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="c652b-130">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="c652b-131">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-131">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="c652b-132">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c652b-132">Click **Next**.</span></span>

4.  <span data-ttu-id="c652b-133">在 "**功能选择**" 页面上，选择要安装的组件，方法是选中 "**报表服务器数据库**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-133">On the **Feature Selection** page, select the components you want to install by selecting the **Reporting Server Database** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="c652b-134">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-134">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="c652b-135">在 "**创建新的报表服务器数据库**" 页面上，接受默认选择（如果适用），然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-135">On the initial **Create New Reporting Server Database** page, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="c652b-136">如果你使用的是自定义 SQL Server 实例，请选择 "**使用自定义实例**"，然后键入实例的名称。</span><span class="sxs-lookup"><span data-stu-id="c652b-136">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>

    <span data-ttu-id="c652b-137">如果您使用的是自定义数据库名称，请选择 "**自定义配置**"，然后键入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="c652b-137">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

7.  <span data-ttu-id="c652b-138">在 "**新建报表服务器数据库**" 页面上，选择 "**使用远程计算机**"，然后使用以下格式键入远程计算机帐户： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="c652b-138">On the next **Create New Reporting Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    **<span data-ttu-id="c652b-139">注意</span><span class="sxs-lookup"><span data-stu-id="c652b-139">Note</span></span>**  
    <span data-ttu-id="c652b-140">如果你计划在同一台计算机上部署报表服务器，必须选择 "**使用此本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-140">If you plan to deploy the reporting server on the same computer you must select **Use this local computer**.</span></span>



~~~
Specify the user name for the reporting server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**. Click **Next**.
~~~

8. <span data-ttu-id="c652b-141">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="c652b-141">To start the installation, click **Install**.</span></span>

**<span data-ttu-id="c652b-142">使用 App-v 5.0 数据库脚本安装管理和报告数据库</span><span class="sxs-lookup"><span data-stu-id="c652b-142">To install the management and reporting databases using App-V 5.0 database scripts</span></span>**

1.  <span data-ttu-id="c652b-143">将 app-v 5.0 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="c652b-143">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span>

2.  <span data-ttu-id="c652b-144">若要提取 app-v 5.0 数据库脚本，请打开命令提示符并指定保存安装文件的位置，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c652b-144">To extract the App-V 5.0 database scripts, open a command prompt and specify the location where the installation files are saved and run the following command:</span></span>

    <span data-ttu-id="c652b-145">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR = "InstallationExtractionLocation"**。</span><span class="sxs-lookup"><span data-stu-id="c652b-145">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR=”InstallationExtractionLocation”**.</span></span>

3.  <span data-ttu-id="c652b-146">提取完成后，若要访问 app-v 5.0 数据库脚本和说明自述文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c652b-146">After the extraction has been completed, to access the App-V 5.0 database scripts and instructions readme file:</span></span>

    -   <span data-ttu-id="c652b-147">App-v 5.0 管理数据库脚本和说明自述文件位于以下文件夹中： **InstallationExtractionLocation**  \\  **数据库脚本**  \\  **管理数据库**。</span><span class="sxs-lookup"><span data-stu-id="c652b-147">The App-V 5.0 Management Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Management Database**.</span></span>

    -   <span data-ttu-id="c652b-148">App-v 5.0 报告数据库脚本和说明自述文件位于以下文件夹中： **InstallationExtractionLocation**  \\  **数据库脚本**  \\  **报告数据库**。</span><span class="sxs-lookup"><span data-stu-id="c652b-148">The App-V 5.0 Reporting Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Reporting Database**.</span></span>

4.  <span data-ttu-id="c652b-149">对于每个数据库，将脚本复制到共享，然后按照自述文件中的说明进行修改。</span><span class="sxs-lookup"><span data-stu-id="c652b-149">For each database, copy the scripts to a share and modify them following the instructions in the readme file.</span></span>

    **<span data-ttu-id="c652b-150">注意</span><span class="sxs-lookup"><span data-stu-id="c652b-150">Note</span></span>**  
    <span data-ttu-id="c652b-151">有关修改脚本中包含的所需 Sid 的详细信息，请参阅[如何安装 App-v 数据库并使用 PowerShell 转换关联的安全标识符](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="c652b-151">For more information about modifying the required SIDs contained in the scripts see, [How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md).</span></span>



5.  <span data-ttu-id="c652b-152">在运行 Microsoft SQL Server 的计算机上运行脚本。</span><span class="sxs-lookup"><span data-stu-id="c652b-152">Run the scripts on the computer running Microsoft SQL Server.</span></span>

    <span data-ttu-id="c652b-153">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="c652b-153">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="c652b-154">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="c652b-154">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="c652b-155">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="c652b-155">Got an App-V issue?</span></span>** <span data-ttu-id="c652b-156">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="c652b-156">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="c652b-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="c652b-157">Related topics</span></span>


[<span data-ttu-id="c652b-158">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="c652b-158">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)









