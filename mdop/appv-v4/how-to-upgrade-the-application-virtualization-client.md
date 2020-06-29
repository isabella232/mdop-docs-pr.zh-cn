---
title: 如何升级 Application Virtualization Client
description: 如何升级 Application Virtualization Client
author: dansimp
ms.assetid: 2a75d8b5-da88-456c-85bb-f5bd3d470f7f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9748fbdba7c8d2777a06c93295e4582be784dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801023"
---
# <span data-ttu-id="c2c03-103">如何升级 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="c2c03-103">How to Upgrade the Application Virtualization Client</span></span>


<span data-ttu-id="c2c03-104">你可以使用以下过程来升级应用程序虚拟化（app-v）桌面客户端或远程桌面服务的 app-v 客户端（以前称为 "终端服务"）。</span><span class="sxs-lookup"><span data-stu-id="c2c03-104">You can use the following procedures to upgrade the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="c2c03-105">通过在以前安装的旧版本上安装新版本来升级客户端。</span><span class="sxs-lookup"><span data-stu-id="c2c03-105">You upgrade the client by installing a new version over the previously installed older version.</span></span> <span data-ttu-id="c2c03-106">升级客户端时，安装程序软件会自动为虚拟应用程序保留和迁移用户设置。</span><span class="sxs-lookup"><span data-stu-id="c2c03-106">When you upgrade the clients, the installer software automatically preserves and migrates the user’s settings for virtual applications.</span></span> <span data-ttu-id="c2c03-107">需要管理员权限才能运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="c2c03-107">Administrative rights are required to run the setup program.</span></span>

<span data-ttu-id="c2c03-108">**注意** 在升级到应用程序虚拟化（app-v）4.5 或更高版本时，将更改 HKCU 注册表项的权限。</span><span class="sxs-lookup"><span data-stu-id="c2c03-108">**Note** During the upgrade to Application Virtualization (App-V)4.5 or later versions, the permissions to the HKCU registry key are changed.</span></span> <span data-ttu-id="c2c03-109">因此，用户将丢失以前设置的用户配置，如用户配置的断开模式设置。</span><span class="sxs-lookup"><span data-stu-id="c2c03-109">Because of this, users will lose user configurations that were set previously, such as user-configured Disconnected Mode settings.</span></span> <span data-ttu-id="c2c03-110">如果用户未受到限制通过权限锁定配置客户端用户界面行为，则用户可以在发布刷新后重置这些首选项。</span><span class="sxs-lookup"><span data-stu-id="c2c03-110">If the user is not actively restricted from configuring client user interface behavior through a permission lockdown, the user can reset these preferences after a publishing refresh.</span></span>

 

<span data-ttu-id="c2c03-111">**重要提示** 当升级到版本4.6 或 App-v 客户端的更高版本时，必须使用适用于计算机操作系统、32位或64位的正确安装程序。</span><span class="sxs-lookup"><span data-stu-id="c2c03-111">**Important** When upgrading to version4.6 or a later version of the App-V Client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="c2c03-112">如果你使用了错误的安装程序，安装将失败，并且将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c2c03-112">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

 

**<span data-ttu-id="c2c03-113">升级应用程序虚拟化桌面客户端</span><span class="sxs-lookup"><span data-stu-id="c2c03-113">To upgrade the Application Virtualization Desktop Client</span></span>**

1.  <span data-ttu-id="c2c03-114">关闭所有虚拟应用程序，右键单击 Windows 桌面通知区域中显示的 app-v 桌面客户端图标，然后选择 "**退出**" 以关闭现有客户端。</span><span class="sxs-lookup"><span data-stu-id="c2c03-114">Shut down all virtual applications, right-click the App-V Desktop Client icon displayed in the Windows desktop notification area, and select **Exit** to shut down the existing client.</span></span>

2.  <span data-ttu-id="c2c03-115">获取正确的安装程序存档文件并将其保存到计算机后，双击它以展开存档。</span><span class="sxs-lookup"><span data-stu-id="c2c03-115">After you have obtained the correct installer archive file and saved it to your computer, double-click it to expand the archive.</span></span>

3.  <span data-ttu-id="c2c03-116">通过浏览找到 setup.exe 文件，然后双击 "setup.exe" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="c2c03-116">Browse to find the setup.exe file, and double-click setup.exe to start the installation.</span></span>

4.  <span data-ttu-id="c2c03-117">该向导将检查系统以确保安装了所有必备软件，如果缺少任何必备软件，系统将提示您安装以下任何内容：</span><span class="sxs-lookup"><span data-stu-id="c2c03-117">The wizard checks the system to ensure that all prerequisite software is installed and will prompt you to install any of the following, if missing:</span></span>

    -   <span data-ttu-id="c2c03-118">Microsoft VisualC + + 2005SP1 可再发行程序包（x86）</span><span class="sxs-lookup"><span data-stu-id="c2c03-118">Microsoft VisualC++2005SP1 Redistributable Package (x86)</span></span>

    -   <span data-ttu-id="c2c03-119">Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）</span><span class="sxs-lookup"><span data-stu-id="c2c03-119">Microsoft Core XML Services (MSXML)6.0SP1 (x86)</span></span>

    -   <span data-ttu-id="c2c03-120">Microsoft 应用程序错误报告</span><span class="sxs-lookup"><span data-stu-id="c2c03-120">Microsoft Application Error Reporting</span></span>

    <span data-ttu-id="c2c03-121">**注意** 对于版本4.6 和更高版本，向导还将安装以下软件必备：</span><span class="sxs-lookup"><span data-stu-id="c2c03-121">**Note** For version4.6 and higher, the wizard will also install the following software prerequisite:</span></span>

    -   <span data-ttu-id="c2c03-122">Microsoft VisualC + + 2008SP1 可再发行程序包（x86）</span><span class="sxs-lookup"><span data-stu-id="c2c03-122">Microsoft VisualC++2008SP1 Redistributable Package (x86)</span></span>

     

5.  <span data-ttu-id="c2c03-123">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="c2c03-123">Click **Install**.</span></span> <span data-ttu-id="c2c03-124">显示安装进度，状态从 "已**挂起**" 更改为 "**正在安装**"。</span><span class="sxs-lookup"><span data-stu-id="c2c03-124">Installation progress is displayed, and the status changes from **Pending** to **Installing**.</span></span> <span data-ttu-id="c2c03-125">已成功完成每个步骤，安装状态更改为 "**成功**"。</span><span class="sxs-lookup"><span data-stu-id="c2c03-125">Installation status changes to **Succeeded** as each step is completed successfully.</span></span>

6.  <span data-ttu-id="c2c03-126">当出现 "**应用程序虚拟化桌面客户端**" 对话框时，显示一条消息，指出计算机上已找到旧版本的客户端，请单击 "**下一步**" 以升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="c2c03-126">When the **Application Virtualization Desktop Client** dialog appears and displays a message stating that an older version of the client has been found on the computer, click **Next** to upgrade to the new version.</span></span>

7.  <span data-ttu-id="c2c03-127">当显示 "**许可协议**" 屏幕时，请阅读许可协议，如果同意，请单击 **"我接受许可协议中的条款**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c2c03-127">When the **License Agreement** screen is displayed, read the license agreement, and if you agree, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

8.  <span data-ttu-id="c2c03-128">当 InstallShield 向导显示 "**准备升级程序**" 对话框屏幕时，单击 "**升级**" 开始升级。</span><span class="sxs-lookup"><span data-stu-id="c2c03-128">When the InstallShield Wizard displays the **Ready to Upgrade the Program** dialog screen, click **Upgrade** to begin the upgrade.</span></span> <span data-ttu-id="c2c03-129">下一个屏幕指示正在安装客户端。</span><span class="sxs-lookup"><span data-stu-id="c2c03-129">The next screen indicates that the client is being installed.</span></span>

    <span data-ttu-id="c2c03-130">**警告** 如果您未在步骤1中关闭客户端程序，您可能会看到显示 **"正在使用**的警告" 中的文件。</span><span class="sxs-lookup"><span data-stu-id="c2c03-130">**Warning** If you did not shut down the client program in step 1, you might see a **Files In Use** warning displayed.</span></span> <span data-ttu-id="c2c03-131">如果发生这种情况，请右键单击桌面通知区域中显示的 app-v 客户端图标，然后选择 "**退出**" 以关闭现有客户端。</span><span class="sxs-lookup"><span data-stu-id="c2c03-131">If this happens, right-click the App-V Client icon displayed in the desktop notification area and select **Exit** to shut down the existing client.</span></span> <span data-ttu-id="c2c03-132">然后单击 "**重试**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="c2c03-132">Then click **Retry** to continue.</span></span>

     

9.  <span data-ttu-id="c2c03-133">安装成功完成后，系统将提示您重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="c2c03-133">When the installation completes successfully, you will be prompted to restart the computer.</span></span> <span data-ttu-id="c2c03-134">您需要重新启动计算机才能完成安装。</span><span class="sxs-lookup"><span data-stu-id="c2c03-134">You need to restart the computer to complete the installation.</span></span>

    <span data-ttu-id="c2c03-135">**小心** 如果升级因任何原因而失败，则需要重新启动计算机，然后再次尝试升级。</span><span class="sxs-lookup"><span data-stu-id="c2c03-135">**Caution** If the upgrade fails for any reason, you will need to restart the computer before attempting the upgrade again.</span></span>

     

**<span data-ttu-id="c2c03-136">使用命令行升级应用程序虚拟化客户端</span><span class="sxs-lookup"><span data-stu-id="c2c03-136">To upgrade the Application Virtualization Client by Using the Command Line</span></span>**

1.  <span data-ttu-id="c2c03-137">如果使用 setup.msi 程序升级 app-v 客户端，请确保已安装任何必需的必备软件。</span><span class="sxs-lookup"><span data-stu-id="c2c03-137">If upgrading the App-V client using the setup.msi program, ensure that any necessary prerequisite software has been installed.</span></span>

    **<span data-ttu-id="c2c03-138">重要提示</span><span class="sxs-lookup"><span data-stu-id="c2c03-138">Important</span></span>**  
    -   <span data-ttu-id="c2c03-139">对于应用程序-V 客户端的版本4.6 和更高版本，setup.msi 程序将检查系统并将失败，并出现一条错误消息，指示如果未安装必备软件，安装无法继续。</span><span class="sxs-lookup"><span data-stu-id="c2c03-139">For version4.6 and later of the App-V client, the setup.msi program checks the system and will fail with an error message indicating that installation cannot continue if prerequisite software is not installed.</span></span>

    -   <span data-ttu-id="c2c03-140">对于 app-v 版本4.6，无法在升级期间使用命令行参数，将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c2c03-140">For App-V version4.6, command-line parameters cannot be used during an upgrade and will be ignored.</span></span>

     

2.  <span data-ttu-id="c2c03-141">下面的命令行示例使用 setup.msi 文件升级 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="c2c03-141">The following command-line example uses the setup.msi file to upgrade the App-V Client.</span></span> <span data-ttu-id="c2c03-142">你将需要使用正确的客户端安装程序，具体取决于你是升级 app-v 桌面客户端还是远程桌面服务的 app-v 客户端（以前称为 "终端服务"）。</span><span class="sxs-lookup"><span data-stu-id="c2c03-142">You will need to use the correct client installer program depending on whether you are upgrading the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span>

    **<span data-ttu-id="c2c03-143">msiexec.exe/i "setup.msi"</span><span class="sxs-lookup"><span data-stu-id="c2c03-143">msiexec.exe /i "setup.msi"</span></span>**

    <span data-ttu-id="c2c03-144">**重要提示** 只有当值包含空格时，才需要使用引号。</span><span class="sxs-lookup"><span data-stu-id="c2c03-144">**Important** The quotation marks are required only when the value contains a space.</span></span> <span data-ttu-id="c2c03-145">为了保持一致性，上述示例中的所有实例都显示为带有引号。</span><span class="sxs-lookup"><span data-stu-id="c2c03-145">For consistency, all instances in the preceding example are shown as having quotation marks.</span></span>

     

**<span data-ttu-id="c2c03-146">为远程桌面服务升级应用程序虚拟化客户端</span><span class="sxs-lookup"><span data-stu-id="c2c03-146">To upgrade the Application Virtualization Client for Remote Desktop Services</span></span>**

1.  <span data-ttu-id="c2c03-147">按照组织的标准策略在远程桌面会话主机（RDSession Host）服务器上安装或升级应用程序。</span><span class="sxs-lookup"><span data-stu-id="c2c03-147">Follow your organization’s standard policies for installing or upgrading applications on the Remote Desktop Session Host (RDSession Host) server.</span></span> <span data-ttu-id="c2c03-148">如果系统是场的一部分，请从服务器场中删除 RDSession 主机。</span><span class="sxs-lookup"><span data-stu-id="c2c03-148">If the system is part of a farm, remove the RDSession Host from the server farm.</span></span>

2.  <span data-ttu-id="c2c03-149">若要升级远程桌面服务（以前称为终端服务）的 app-v 客户端，你必须使用命令行，因为你无法在 RDSession 主机上手动升级客户端。</span><span class="sxs-lookup"><span data-stu-id="c2c03-149">To upgrade the App-V Client for Remote Desktop Services (formerly Terminal Services), you must use the command line because you cannot upgrade the client manually on the RDSession Host.</span></span>

    <span data-ttu-id="c2c03-150">**注意** 在 app-v 版本4.6 和更高版本中，除了使用命令行升级客户端外，你还可以使用远程桌面会话。</span><span class="sxs-lookup"><span data-stu-id="c2c03-150">**Note** In App-V version 4.6 and later, in addition to using the command line to upgrade the client, you can also use a Remote Desktop session.</span></span> <span data-ttu-id="c2c03-151">启动远程桌面会话时无需任何特殊参数。</span><span class="sxs-lookup"><span data-stu-id="c2c03-151">No special parameters are required to start the Remote Desktop session.</span></span>

     

3.  <span data-ttu-id="c2c03-152">客户端完成远程桌面服务升级后，重新启动并登录到 RDSession 主机。</span><span class="sxs-lookup"><span data-stu-id="c2c03-152">After the Client for Remote Desktop Services upgrade is complete, restart and log in to the RDSession Host.</span></span>

4.  <span data-ttu-id="c2c03-153">重新启动系统后，将服务器添加到服务器场。</span><span class="sxs-lookup"><span data-stu-id="c2c03-153">After the system is restarted, add the server to the server farm.</span></span>

    <span data-ttu-id="c2c03-154">**小心** 如果升级因任何原因而失败，则需要重新启动计算机，然后再次尝试升级。</span><span class="sxs-lookup"><span data-stu-id="c2c03-154">**Caution** If the upgrade fails for any reason, you will need to restart the computer before attempting the upgrade again.</span></span>

     

## <span data-ttu-id="c2c03-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="c2c03-155">Related topics</span></span>


[<span data-ttu-id="c2c03-156">Application Virtualization 部署和升级注意事项</span><span class="sxs-lookup"><span data-stu-id="c2c03-156">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

 

 





