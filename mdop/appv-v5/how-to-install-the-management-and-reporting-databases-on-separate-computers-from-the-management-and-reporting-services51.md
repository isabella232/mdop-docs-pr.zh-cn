---
title: 如何在单独的计算机上从管理和报告服务安装管理和报告数据库
description: 如何在单独的计算机上从管理和报告服务安装管理和报告数据库
author: dansimp
ms.assetid: 2a67402e-3119-40ea-a247-24d166af1ced
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2332f674f10a9b60aa1cee814c6eac4ddbe4f5af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798444"
---
# <span data-ttu-id="138d2-103">如何在单独的计算机上从管理和报告服务安装管理和报告数据库</span><span class="sxs-lookup"><span data-stu-id="138d2-103">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>

<span data-ttu-id="138d2-104">使用以下过程在不同计算机上安装数据库服务器和管理服务器。</span><span class="sxs-lookup"><span data-stu-id="138d2-104">Use the following procedure to install the database server and management server on different computers.</span></span> <span data-ttu-id="138d2-105">你计划用于安装数据库服务器的计算机必须运行受支持的 Microsoft SQL 版本，否则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="138d2-105">The computer you plan to install the database server on must be running a supported version of Microsoft SQL or the installation will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="138d2-106">完成部署后，安装该服务的管理员将需要**MICROSOFT SQL Server 名称**、**实例名称**和**数据库名称**才能连接到这些数据库。</span><span class="sxs-lookup"><span data-stu-id="138d2-106">After you complete the deployment, the **Microsoft SQL Server name**, **instance name** and **database name** will be required by the administrator installing the service to be able to connect to these databases.</span></span>

## <span data-ttu-id="138d2-107">在单独的计算机上安装管理数据库和管理服务器</span><span class="sxs-lookup"><span data-stu-id="138d2-107">To install the management database and the management server on separate computers</span></span>

1. <span data-ttu-id="138d2-108">将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="138d2-108">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="138d2-109">若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="138d2-109">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="138d2-110">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="138d2-110">Click **Install**.</span></span>
1. <span data-ttu-id="138d2-111">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-111">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>
1. <span data-ttu-id="138d2-112">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="138d2-112">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="138d2-113">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-113">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="138d2-114">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="138d2-114">Click **Next**.</span></span>
1. <span data-ttu-id="138d2-115">在 "**功能选择**" 页面上，选择要安装的组件，方法是选择 "**管理服务器数据库**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-115">On the **Feature Selection** page, select the components you want to install by selecting the **Management Server Database** checkbox and click **Next**.</span></span>
1. <span data-ttu-id="138d2-116">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-116">On the **Installation Location** page, accept the default location and click **Next**.</span></span>
1. <span data-ttu-id="138d2-117">在 "**新建管理服务器数据库" 页面**上，接受默认选择（如果适用），然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-117">On the initial **Create New Management Server Database page**, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="138d2-118">如果您使用的是自定义 SQL Server 实例，请选择 "**使用自定义实例**"，然后键入实例的名称。</span><span class="sxs-lookup"><span data-stu-id="138d2-118">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.\</span></span>
    <span data-ttu-id="138d2-119">如果您使用的是自定义数据库名称，请选择 "**自定义配置**"，然后键入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="138d2-119">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

1. <span data-ttu-id="138d2-120">在 "**新建管理服务器数据库**" 页面上，选择 "**使用远程计算机**"，然后使用以下格式键入远程计算机帐户： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="138d2-120">On the next **Create New Management Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="138d2-121">如果你计划在同一台计算机上部署管理服务器，必须选择 "**使用此本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-121">If you plan to deploy the management server on the same computer you must select **Use this local computer**.</span></span>

1. <span data-ttu-id="138d2-122">使用以下格式为管理服务器**安装管理员**指定用户名称： **Domain\\AdministratorLoginName**。</span><span class="sxs-lookup"><span data-stu-id="138d2-122">Specify the user name for the management server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**.</span></span> <span data-ttu-id="138d2-123">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="138d2-123">Click **Next**.</span></span>
1. <span data-ttu-id="138d2-124">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-124">To start the installation, click **Install**.</span></span>

## <span data-ttu-id="138d2-125">在单独的计算机上安装报表数据库和报表服务器</span><span class="sxs-lookup"><span data-stu-id="138d2-125">To install the reporting database and the reporting server on separate computers</span></span>

1. <span data-ttu-id="138d2-126">将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="138d2-126">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="138d2-127">若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="138d2-127">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="138d2-128">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="138d2-128">Click **Install**.</span></span>
1. <span data-ttu-id="138d2-129">在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-129">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>
1. <span data-ttu-id="138d2-130">在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。**</span><span class="sxs-lookup"><span data-stu-id="138d2-130">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="138d2-131">若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-131">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="138d2-132">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="138d2-132">Click **Next**.</span></span>
1. <span data-ttu-id="138d2-133">在 "**功能选择**" 页面上，选择要安装的组件，方法是选中 "**报表服务器数据库**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-133">On the **Feature Selection** page, select the components you want to install by selecting the **Reporting Server Database** checkbox and click **Next**.</span></span>
1. <span data-ttu-id="138d2-134">在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-134">On the **Installation Location** page, accept the default location and click **Next**.</span></span>
1. <span data-ttu-id="138d2-135">在 "**创建新的报表服务器数据库**" 页面上，接受默认选择（如果适用），然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-135">On the initial **Create New Reporting Server Database** page, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="138d2-136">如果你使用的是自定义 SQL Server 实例，请选择 "**使用自定义实例**"，然后键入实例的名称。</span><span class="sxs-lookup"><span data-stu-id="138d2-136">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>
    <span data-ttu-id="138d2-137">如果您使用的是自定义数据库名称，请选择 "**自定义配置**"，然后键入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="138d2-137">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

1. <span data-ttu-id="138d2-138">在 "**新建报表服务器数据库**" 页面上，选择 "**使用远程计算机**"，然后使用以下格式键入远程计算机帐户： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="138d2-138">On the next **Create New Reporting Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="138d2-139">如果你计划在同一台计算机上部署报表服务器，必须选择 "**使用此本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-139">If you plan to deploy the reporting server on the same computer you must select **Use this local computer**.</span></span>

1. <span data-ttu-id="138d2-140">使用以下格式为 reporting server**安装管理员**指定用户名： **Domain\\AdministratorLoginName**。</span><span class="sxs-lookup"><span data-stu-id="138d2-140">Specify the user name for the reporting server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**.</span></span> <span data-ttu-id="138d2-141">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="138d2-141">Click **Next**.</span></span>
1. <span data-ttu-id="138d2-142">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="138d2-142">To start the installation, click **Install**.</span></span>

## <span data-ttu-id="138d2-143">使用 App-v 5.1 数据库脚本安装管理和报告数据库</span><span class="sxs-lookup"><span data-stu-id="138d2-143">To install the management and reporting databases using App-V 5.1 database scripts</span></span>

1. <span data-ttu-id="138d2-144">将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="138d2-144">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span>
1. <span data-ttu-id="138d2-145">若要提取 app-v 5.1 数据库脚本，请打开命令提示符并指定保存安装文件的位置，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="138d2-145">To extract the App-V 5.1 database scripts, open a command prompt and specify the location where the installation files are saved and run the following command:</span></span>

    <span data-ttu-id="138d2-146">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR = "InstallationExtractionLocation"**。</span><span class="sxs-lookup"><span data-stu-id="138d2-146">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR="InstallationExtractionLocation"**.</span></span>

1. <span data-ttu-id="138d2-147">提取完成后，若要访问 app-v 5.1 数据库脚本和说明自述文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="138d2-147">After the extraction has been completed, to access the App-V 5.1 database scripts and instructions readme file:</span></span>

    - <span data-ttu-id="138d2-148">App-v 5.1 管理数据库脚本和说明自述文件位于以下文件夹中： **InstallationExtractionLocation**  \\  **数据库脚本**  \\  **管理数据库**。</span><span class="sxs-lookup"><span data-stu-id="138d2-148">The App-V 5.1 Management Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Management Database**.</span></span>
    - <span data-ttu-id="138d2-149">App-v 5.1 报告数据库脚本和说明自述文件位于以下文件夹中： **InstallationExtractionLocation**  \\  **数据库脚本**  \\  **报告数据库**。</span><span class="sxs-lookup"><span data-stu-id="138d2-149">The App-V 5.1 Reporting Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Reporting Database**.</span></span>

1. <span data-ttu-id="138d2-150">对于每个数据库，将脚本复制到共享，然后按照自述文件中的说明进行修改。</span><span class="sxs-lookup"><span data-stu-id="138d2-150">For each database, copy the scripts to a share and modify them following the instructions in the readme file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="138d2-151">有关修改脚本中包含的所需 Sid 的详细信息，请参阅[如何使用 PowerShell 安装 App-v 数据库并转换关联的安全标识符](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md)。</span><span class="sxs-lookup"><span data-stu-id="138d2-151">For more information about modifying the required SIDs contained in the scripts, see [How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md).</span></span>

1. <span data-ttu-id="138d2-152">在运行 Microsoft SQL Server 的计算机上运行脚本。</span><span class="sxs-lookup"><span data-stu-id="138d2-152">Run the scripts on the computer running Microsoft SQL Server.</span></span>

**<span data-ttu-id="138d2-153">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="138d2-153">Got an App-V issue?</span></span>** <span data-ttu-id="138d2-154">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="138d2-154">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="138d2-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="138d2-155">Related topics</span></span>

[<span data-ttu-id="138d2-156">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="138d2-156">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)
