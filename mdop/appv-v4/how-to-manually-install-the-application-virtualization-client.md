---
title: 如何手动安装 Application Virtualization Client
description: 如何手动安装 Application Virtualization Client
author: dansimp
ms.assetid: bb67f70b-d525-4317-b254-e4f084c717ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cb41b5e51bd33c377b17c088e97cb54f1a57685
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801275"
---
# <span data-ttu-id="20bf0-103">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="20bf0-103">How to Manually Install the Application Virtualization Client</span></span>

<span data-ttu-id="20bf0-104">存在两种类型的应用程序虚拟化客户端组件：应用程序虚拟化桌面客户端，用于在台式计算机上安装，以及用于远程桌面服务（以前称为终端服务）的应用程序虚拟化客户端，可在远程桌面会话主机（RD 会话主机）服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="20bf0-104">There are two types of Application Virtualization Client components: the Application Virtualization Desktop Client, which is designed for installation on desktop computers, and the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services), which you can install on Remote Desktop Session Host (RD Session Host) servers .</span></span> <span data-ttu-id="20bf0-105">虽然两个客户端安装程序不同，但你可以使用以下过程在单个桌面计算机上手动安装应用程序虚拟化桌面客户端，或者在单个 RD 会话主机服务器上手动安装远程桌面服务的应用程序虚拟化客户端。</span><span class="sxs-lookup"><span data-stu-id="20bf0-105">Although the two client installer programs are different, you can use the following procedure to manually install either the Application Virtualization Desktop Client on a single desktop computer or the Application Virtualization Client for Remote Desktop Services on a single RD Session Host server.</span></span> <span data-ttu-id="20bf0-106">在生产环境中，你很可能会在具有自动脚本安装过程的多台桌面计算机上安装应用程序虚拟化桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="20bf0-106">In a production environment, you most likely will install the Application Virtualization Desktop Client on multiple desktop computers with an automated scripted installation process.</span></span> <span data-ttu-id="20bf0-107">有关如何使用脚本安装过程安装多个客户端的信息，请参阅[如何使用命令行安装客户端](how-to-install-the-client-by-using-the-command-line-new.md)。</span><span class="sxs-lookup"><span data-stu-id="20bf0-107">For information about how to install multiple clients by using a scripted installation process, see [How to Install the Client by Using the Command Line](how-to-install-the-client-by-using-the-command-line-new.md).</span></span>

**<span data-ttu-id="20bf0-108">注意</span><span class="sxs-lookup"><span data-stu-id="20bf0-108">Note</span></span>**  
1. <span data-ttu-id="20bf0-109">如果要为 RD 会话主机服务器上的远程桌面服务软件安装 Application Virtualization 客户端，建议与 RD 会话主机服务器有打开的 RDP 或 ICA 客户端会话的用户，他们必须保存其工作并关闭其会话。</span><span class="sxs-lookup"><span data-stu-id="20bf0-109">If you are installing the Application Virtualization Client for Remote Desktop Services software on a RD Session Host server, advise users who have an open RDP or ICA client session with the RD Session Host server that they must save their work and close their sessions.</span></span> <span data-ttu-id="20bf0-110">在远程桌面会话中，你可以手动安装客户端。</span><span class="sxs-lookup"><span data-stu-id="20bf0-110">In a Remote Desktop session, you can install the client the client manually.</span></span> <span data-ttu-id="20bf0-111">有关升级客户端的详细信息，请参阅[如何升级应用程序虚拟化客户端](how-to-upgrade-the-application-virtualization-client.md)。</span><span class="sxs-lookup"><span data-stu-id="20bf0-111">For more information about upgrading the client, see [How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md).</span></span>

2. <span data-ttu-id="20bf0-112">如果用户计算机上的任何配置取决于客户端安装路径，请注意应用程序虚拟化（app-v）4.5 客户端使用的安装文件夹与以前的版本不同。</span><span class="sxs-lookup"><span data-stu-id="20bf0-112">If you have any configuration on the user’s computer that depends on the client install path, note that the Application Virtualization (App-V) 4.5 client uses a different install folder than previous versions.</span></span> <span data-ttu-id="20bf0-113">默认情况下，应用程序虚拟化（app-v）4.5 客户端的全新安装将安装到 \\Program Files\\Microsoft Application Virtualization Client 文件夹。</span><span class="sxs-lookup"><span data-stu-id="20bf0-113">By default, a new install of the Application Virtualization (App-V) 4.5 client will install to the \\Program Files\\Microsoft Application Virtualization Client folder.</span></span> <span data-ttu-id="20bf0-114">如果已安装早期版本的客户端，则安装 app-v 客户端会将升级到现有安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="20bf0-114">If an earlier version of the client is already installed, installing the App-V client will perform an upgrade into the existing installation folder.</span></span>

**<span data-ttu-id="20bf0-115">注意</span><span class="sxs-lookup"><span data-stu-id="20bf0-115">Note</span></span>**  
<span data-ttu-id="20bf0-116">对于 app-v 版本4.6 和更高版本，当安装了 App-v 客户端时，SFTLDR.DLL 安装在 Windows\\system32 目录中。</span><span class="sxs-lookup"><span data-stu-id="20bf0-116">For App-V version 4.6 and later, when the App-V client is installed, SFTLDR.DLL is installed in the Windows\\system32 directory.</span></span> <span data-ttu-id="20bf0-117">如果在64位系统上安装了 app-v 客户端，SFTLDR\_WOW64.DLL 将安装在 Windows\\SysWOW64 目录中。</span><span class="sxs-lookup"><span data-stu-id="20bf0-117">If the App-V client is installed on a 64-bit system, SFTLDR\_WOW64.DLL is installed in the Windows\\SysWOW64 directory.</span></span>

**<span data-ttu-id="20bf0-118">手动安装应用程序虚拟化桌面客户端</span><span class="sxs-lookup"><span data-stu-id="20bf0-118">To manually install Application Virtualization Desktop Client</span></span>**

1. <span data-ttu-id="20bf0-119">获取正确的安装程序存档文件并将其保存到计算机后，请确保使用拥有计算机管理员权限的帐户登录，然后双击文件以展开存档。</span><span class="sxs-lookup"><span data-stu-id="20bf0-119">After you have obtained the correct installer archive file and saved it to your computer, make sure you are logged on with an account having administrator rights on the computer and double-click the file to expand the archive.</span></span>

2. <span data-ttu-id="20bf0-120">选择要在其中保存文件的文件夹，然后在将文件复制到该文件夹后打开该文件夹。</span><span class="sxs-lookup"><span data-stu-id="20bf0-120">Choose the folder in which to save the files, and then open the folder after the files have been copied to it.</span></span>

3. <span data-ttu-id="20bf0-121">查看发行说明（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="20bf0-121">Review the Release Notes if appropriate.</span></span>

4. <span data-ttu-id="20bf0-122">通过浏览找到 setup.exe 文件，然后双击 "setup.exe" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="20bf0-122">Browse to find the setup.exe file, and double-click setup.exe to start the installation.</span></span>

5. <span data-ttu-id="20bf0-123">该向导将检查系统以确保安装了所有必备软件，如果缺少以下任何软件，向导将自动提示您安装它们：</span><span class="sxs-lookup"><span data-stu-id="20bf0-123">The wizard checks the system to ensure that all prerequisite software is installed, and if any of the following are missing, the wizard will automatically prompt you to install them:</span></span>

    - <span data-ttu-id="20bf0-124">Microsoft Visual c + + 2005 SP1 可再发行程序包（x86）</span><span class="sxs-lookup"><span data-stu-id="20bf0-124">Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)</span></span>

    - <span data-ttu-id="20bf0-125">Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）</span><span class="sxs-lookup"><span data-stu-id="20bf0-125">Microsoft Core XML Services (MSXML) 6.0 SP1 (x86)</span></span>

    - <span data-ttu-id="20bf0-126">Microsoft 应用程序错误报告</span><span class="sxs-lookup"><span data-stu-id="20bf0-126">Microsoft Application Error Reporting</span></span>

    **<span data-ttu-id="20bf0-127">注意</span><span class="sxs-lookup"><span data-stu-id="20bf0-127">Note</span></span>**  
    <span data-ttu-id="20bf0-128">对于 app-v 版本4.6 和更高版本，向导还将安装 Microsoft Visual c + + 2008 SP1 可再发行程序包（x86）。</span><span class="sxs-lookup"><span data-stu-id="20bf0-128">For App-V version 4.6 and later, the wizard will also install Microsoft Visual C++ 2008 SP1 Redistributable Package (x86).</span></span>

    <span data-ttu-id="20bf0-129">有关安装 Microsoft Visual c + + 2008 SP1 可再发行程序包（x86）的详细信息，请参阅 [https://go.microsoft.com/fwlink/?LinkId=150700](https://go.microsoft.com/fwlink/?LinkId=150700) 。</span><span class="sxs-lookup"><span data-stu-id="20bf0-129">For more information about installing Microsoft Visual C++ 2008 SP1 Redistributable Package (x86), see [https://go.microsoft.com/fwlink/?LinkId=150700](https://go.microsoft.com/fwlink/?LinkId=150700).</span></span>

    <span data-ttu-id="20bf0-130">如果出现提示，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-130">If prompted, click **Install**.</span></span> <span data-ttu-id="20bf0-131">显示安装进度，状态从 "已**挂起**" 更改为 "**正在安装**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-131">Installation progress is displayed, and the status changes from **Pending** to **Installing**.</span></span> <span data-ttu-id="20bf0-132">已成功完成每个步骤，安装状态更改为 "**成功**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-132">Installation status changes to **Succeeded** as each step is completed successfully.</span></span>

6. <span data-ttu-id="20bf0-133">当显示 " **Microsoft Application Virtualization 桌面客户端-InstallShield 向导**" 时，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-133">When the **Microsoft Application Virtualization Desktop Client – InstallShield Wizard** is displayed, click **Next**.</span></span>

7. <span data-ttu-id="20bf0-134">将显示 "**许可协议**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="20bf0-134">The **License Agreement** screen is displayed.</span></span> <span data-ttu-id="20bf0-135">阅读许可协议，如果同意，请单击 "**我接受许可协议中的条款"** ，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-135">Read the license agreement, and if you agree, click **I accept the terms in the license agreement** and then click **Next**.</span></span>

   <span data-ttu-id="20bf0-136">（可选）您可以单击该按钮阅读隐私声明。</span><span class="sxs-lookup"><span data-stu-id="20bf0-136">Optionally, you can click the button to read the Privacy Statement.</span></span> <span data-ttu-id="20bf0-137">您必须连接到互联网才能访问隐私声明。</span><span class="sxs-lookup"><span data-stu-id="20bf0-137">You must be connected to the Internet to access the Privacy Statement.</span></span>

8. <span data-ttu-id="20bf0-138">在 "**安装类型**" 屏幕上，选择 "设置类型"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-138">On the **Setup Type** screen, select the setup type.</span></span> <span data-ttu-id="20bf0-139">单击 "**典型**" 使用默认程序值，或者单击 "**自定义**" （如果要在安装期间配置程序设置）。</span><span class="sxs-lookup"><span data-stu-id="20bf0-139">Click **Typical** to use the default program values, or click **Custom** if you want to configure the program settings during installation.</span></span>

9. <span data-ttu-id="20bf0-140">如果您选择 "**典型**"，下一个屏幕显示已**准备好安装该程序**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-140">If you choose **Typical**, the next screen displays **Ready to Install the Program**.</span></span> <span data-ttu-id="20bf0-141">单击 "**安装**" 以开始安装。</span><span class="sxs-lookup"><span data-stu-id="20bf0-141">Click **Install** to begin the installation.</span></span>

10. <span data-ttu-id="20bf0-142">如果选择 "**自定义**"，将显示 "**目标文件夹**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="20bf0-142">If you choose **Custom**, the **Destination Folder** screen appears.</span></span>

11. <span data-ttu-id="20bf0-143">在 "**目标文件夹**" 屏幕上，单击 "**下一步**" 接受默认文件夹，或单击 "**更改**" 以显示 "**更改当前目标文件夹**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="20bf0-143">On the **Destination Folder** screen, click **Next** to accept the default folder or click **Change** to display the **Change Current Destination Folder** screen.</span></span> <span data-ttu-id="20bf0-144">通过浏览找到或，在 "**文件夹名称**" 字段中，输入目标文件夹，单击 **"确定**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-144">Browse to or, in the **Folder Name** field, enter the destination folder, click **OK**, and then click **Next**.</span></span>

12. <span data-ttu-id="20bf0-145">在 "**应用程序虚拟化数据位置**" 屏幕上，单击 "**下一步**" 接受默认数据位置或完成以下操作以更改存储数据的位置：</span><span class="sxs-lookup"><span data-stu-id="20bf0-145">On the **Application Virtualization Data Location** screen, click **Next** to accept the default data locations or complete the following actions to change where the data is stored:</span></span>

    1. <span data-ttu-id="20bf0-146">单击 "**更改**"，然后浏览到 "或"，在 "**全局数据位置**" 字段中，输入全局数据位置的目标文件夹，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-146">Click **Change**, and then browse to or, in the **Global Data Location** field, enter the destination folder for the global data location, and click **OK**.</span></span> <span data-ttu-id="20bf0-147">全局数据目录是应用程序虚拟化桌面客户端缓存由计算机上的所有用户共享的数据的位置，如 OSD 文件和 SFT 文件数据。</span><span class="sxs-lookup"><span data-stu-id="20bf0-147">The Global Data Directory is where the Application Virtualization Desktop Client caches data shared by all users on the computer, like OSD files and SFT file data.</span></span>

    2. <span data-ttu-id="20bf0-148">如果要更改要使用的驱动器号，请从下拉列表中选择首选驱动器号。</span><span class="sxs-lookup"><span data-stu-id="20bf0-148">If you want to change the drive letter to be used, select the preferred drive letter from the drop-down list.</span></span>

    3. <span data-ttu-id="20bf0-149">如果要更改数据位置，请在 "特定于用户的**数据位置**" 字段中输入用于存储特定于用户的数据的新路径。</span><span class="sxs-lookup"><span data-stu-id="20bf0-149">Enter a new path to store the user-specific data in the **User-specific Data Location** field if you want to change the data location.</span></span> <span data-ttu-id="20bf0-150">用户数据目录是应用程序虚拟化桌面客户端存储特定于用户的信息（如虚拟化应用程序的个人设置）的位置。</span><span class="sxs-lookup"><span data-stu-id="20bf0-150">The User Data Directory is where the Application Virtualization Desktop Client stores user-specific information, like personal settings for virtualized applications.</span></span>

       **<span data-ttu-id="20bf0-151">注意</span><span class="sxs-lookup"><span data-stu-id="20bf0-151">Note</span></span>**  
       <span data-ttu-id="20bf0-152">此路径对于每个用户都必须是不同的，因此它应包含特定于用户的环境变量或映射的驱动器或将解析为每个用户的唯一路径的其他内容。</span><span class="sxs-lookup"><span data-stu-id="20bf0-152">This path must be different for every user, so it should include a user-specific environment variable or a mapped drive or something else that will resolve to a unique path for each user.</span></span>

    4. <span data-ttu-id="20bf0-153">完成更改后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-153">When you have finished making the changes, click **Next**.</span></span>

13. <span data-ttu-id="20bf0-154">在 "**缓存大小" 设置**屏幕上，可以接受或更改默认缓存大小。</span><span class="sxs-lookup"><span data-stu-id="20bf0-154">On the **Cache Size Settings** screen, you can accept or change the default cache size.</span></span> <span data-ttu-id="20bf0-155">单击下列单选按钮之一，选择如何管理缓存空间：</span><span class="sxs-lookup"><span data-stu-id="20bf0-155">Click one of the following radio buttons to choose how to manage the cache space:</span></span>

    1. <span data-ttu-id="20bf0-156">**使用最大缓存大小**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-156">**Use maximum cache size**.</span></span> <span data-ttu-id="20bf0-157">在 "**最大大小（MB）** " 字段中输入一个介于100到1048576（1 TB）之间的数值，以指定缓存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="20bf0-157">Enter a numeric value from 100–1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache.</span></span>

    2. <span data-ttu-id="20bf0-158">**使用可用磁盘空间阈值**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-158">**Use free disk space threshold**.</span></span> <span data-ttu-id="20bf0-159">输入一个数字值以指定应用程序虚拟化客户端必须在磁盘上保留的可用磁盘空间量（以 MB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="20bf0-159">Enter a numeric value to specify the amount of free disk space, in MB, that the Application Virtualization Client must leave available on the disk.</span></span> <span data-ttu-id="20bf0-160">这允许缓存增长，直到可用磁盘空间量达到此限制。</span><span class="sxs-lookup"><span data-stu-id="20bf0-160">This allows the cache to grow until the amount of free disk space reaches this limit.</span></span> <span data-ttu-id="20bf0-161">"**剩余可用磁盘空间**" 中显示的值表示当前未使用的磁盘空间量。</span><span class="sxs-lookup"><span data-stu-id="20bf0-161">The value shown in **Free disk space remaining** indicates how much disk space is currently unused.</span></span>

    **<span data-ttu-id="20bf0-162">重要提示</span><span class="sxs-lookup"><span data-stu-id="20bf0-162">Important</span></span>**  
    <span data-ttu-id="20bf0-163">若要确保缓存为所有可能部署的程序包分配了足够的空间，请在配置客户端时使用 "**使用可用磁盘空间阈值**" 设置，以便缓存可以根据需要增长。</span><span class="sxs-lookup"><span data-stu-id="20bf0-163">To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="20bf0-164">或者，提前确定应用 V 缓存所需的磁盘空间量，并在安装时设置相应的缓存大小。</span><span class="sxs-lookup"><span data-stu-id="20bf0-164">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span> <span data-ttu-id="20bf0-165">有关缓存空间管理功能的详细信息，请参阅 Microsoft Application Virtualization （App-v）操作指南中的**如何使用缓存空间管理功能**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-165">For more information about the cache space management feature, in the Microsoft Application Virtualization (App-V) Operations Guide, see **How to Use the Cache Space Management Feature**.</span></span>

    <span data-ttu-id="20bf0-166">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="20bf0-166">Click **Next** to continue.</span></span>

14. <span data-ttu-id="20bf0-167">在 "**运行时程序包策略配置**" 屏幕的以下部分中，你可以更改影响应用程序虚拟化客户端在运行时的行为方式的参数：</span><span class="sxs-lookup"><span data-stu-id="20bf0-167">In the following sections of the **Runtime Package Policy Configuration** screen, you can change the parameters that affect how the Application Virtualization client behaves during runtime:</span></span>

    1. <span data-ttu-id="20bf0-168">**应用程序源根目录**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-168">**Application Source Root**.</span></span> <span data-ttu-id="20bf0-169">指定 SFT 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="20bf0-169">Specifies the location of SFT files.</span></span> <span data-ttu-id="20bf0-170">如果使用，将替代 OSD 文件中基本代码 HREF URL 的协议、服务器和端口部分。</span><span class="sxs-lookup"><span data-stu-id="20bf0-170">If used, overrides the protocol, server, and port portions of the CODEBASE HREF URL in the OSD file.</span></span>

    2. <span data-ttu-id="20bf0-171">**应用程序授权**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-171">**Application Authorization**.</span></span> <span data-ttu-id="20bf0-172">当**需要用户授权**的情况下，即使已选中缓存，用户也必须连接到服务器并至少验证其凭据一次，然后才允许它们开始每个虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="20bf0-172">When **Require User authorization even when cached** is checked, users are required to connect to a server and validate their credentials at least once before they are allowed to start each virtual application.</span></span>

    3. <span data-ttu-id="20bf0-173">**允许从文件进行流处理**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-173">**Allow streaming from file**.</span></span> <span data-ttu-id="20bf0-174">指示是否将启用文件的流处理，无论**应用程序源根**字段的使用方式如何。</span><span class="sxs-lookup"><span data-stu-id="20bf0-174">Indicates whether streaming from file will be enabled, regardless of how the **Application Source Root** field is used.</span></span> <span data-ttu-id="20bf0-175">如果未选中，则禁用 "从文件进行流处理"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-175">If not checked, streaming from files is disabled.</span></span> <span data-ttu-id="20bf0-176">如果**应用程序源根目录**包含窗体 \\\\server\\share. 中的 UNC 路径，则必须选中此项。</span><span class="sxs-lookup"><span data-stu-id="20bf0-176">This must be checked if **Application Source Root** contains a UNC path in the form \\\\server\\share.</span></span>

    4. <span data-ttu-id="20bf0-177">**自动加载应用程序**。</span><span class="sxs-lookup"><span data-stu-id="20bf0-177">**Automatically Load Application**.</span></span> <span data-ttu-id="20bf0-178">控制应用程序的自动后台加载的时间和方式。</span><span class="sxs-lookup"><span data-stu-id="20bf0-178">Controls when and how automatic background loading of applications occurs.</span></span>

       **<span data-ttu-id="20bf0-179">注意</span><span class="sxs-lookup"><span data-stu-id="20bf0-179">Note</span></span>**  
       <span data-ttu-id="20bf0-180">在安装与只读缓存（例如，使用 VDI 服务器实现）时，如果要将应用程序与只读缓存一起使用，请将**要自动加载的应用程序**设置为**不自动加载应用程序**，以防止客户端尝试更新只读缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="20bf0-180">When you install the App-V client to use with a read-only cache, for example, with a VDI server implementation, set **What applications to Auto Load** to **Do not automatically load applications** to prevent the client from trying to update applications in the read-only cache.</span></span>

    <span data-ttu-id="20bf0-181">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="20bf0-181">Click **Next** to continue.</span></span>

15. <span data-ttu-id="20bf0-182">如果要定义发布服务器，请在 "**发布服务器**" 屏幕上选中 "**立即设置发布服务器**" 复选框，或者单击 "**下一步**" （如果要稍后完成此操作）。</span><span class="sxs-lookup"><span data-stu-id="20bf0-182">On the **Publishing Server** screen, select the **Set up a Publishing Server now** check box if you want to define a publishing server, or click **Next** if you want to complete this later.</span></span> <span data-ttu-id="20bf0-183">若要定义发布服务器，请指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="20bf0-183">To define a publishing server, specify the following information:</span></span>

    1. <span data-ttu-id="20bf0-184">**显示名称**-输入要为服务器显示的名称。</span><span class="sxs-lookup"><span data-stu-id="20bf0-184">**Display Name**—Enter the name you want to display for the server.</span></span>

    2. <span data-ttu-id="20bf0-185">**类型**—从服务器类型的下拉列表中选择服务器类型。</span><span class="sxs-lookup"><span data-stu-id="20bf0-185">**Type**—Select the server type from the drop-down list of server types.</span></span>

    3. <span data-ttu-id="20bf0-186">**主机名**和**端口**-在对应字段中输入主机名和端口。</span><span class="sxs-lookup"><span data-stu-id="20bf0-186">**Host Name** and **Port**—Enter the host name and the port in the corresponding fields.</span></span> <span data-ttu-id="20bf0-187">在下拉列表中选择服务器类型时，"端口" 字段将自动填充标准端口号。</span><span class="sxs-lookup"><span data-stu-id="20bf0-187">When you select a server type in the drop-down list, the port field will automatically fill with the standard port numbers.</span></span> <span data-ttu-id="20bf0-188">若要更改端口号，请单击列表中的服务器类型，并根据需要更改端口号。</span><span class="sxs-lookup"><span data-stu-id="20bf0-188">To change a port number, click the server type in the list and change the port number according to your needs.</span></span>

    4. <span data-ttu-id="20bf0-189">**路径**-如果已选择 "**标准 HTTP 服务器**" 或 "**增强的安全 http 服务器**"，则必须输入包含此字段中的发布数据的 XML 文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="20bf0-189">**Path**—If you have selected either **Standard HTTP Server** or **Enhanced Security HTTP Server**, you must enter the complete path to the XML file containing publishing data in this field.</span></span> <span data-ttu-id="20bf0-190">如果选择 "**应用程序虚拟化服务器**" 或 "**增强的安全应用程序虚拟化服务器**"，则此字段不处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="20bf0-190">If you select either **Application Virtualization Server** or **Enhanced Security Application Virtualization Server**, this field is not active.</span></span>

    5. <span data-ttu-id="20bf0-191">**当用户登录时自动联系此服务器以更新设置**-如果你希望在用户登录到应用程序虚拟化客户端上的帐户时自动查询此服务器，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="20bf0-191">**Automatically contact this server to update settings when a user logs in**—Select this check box if you want this server to be queried automatically when users log in to their account on the Application Virtualization Client.</span></span>

    6. <span data-ttu-id="20bf0-192">完成配置步骤后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-192">When finished with the configuration steps, click **Next**.</span></span>

16. <span data-ttu-id="20bf0-193">在 "已**准备好安装程序**" 屏幕上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-193">On the **Ready to Install the Program** screen, click **Install**.</span></span> <span data-ttu-id="20bf0-194">显示安装进度的屏幕。</span><span class="sxs-lookup"><span data-stu-id="20bf0-194">A screen is displayed that shows the progress of the installation.</span></span>

17. <span data-ttu-id="20bf0-195">在 "**安装向导完成**" 屏幕上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="20bf0-195">On the **Install Wizard Completed** screen, click **Finish**.</span></span>

    **<span data-ttu-id="20bf0-196">注意</span><span class="sxs-lookup"><span data-stu-id="20bf0-196">Note</span></span>**  
    <span data-ttu-id="20bf0-197">如果安装因任何原因而失败，您可能需要重新启动计算机，然后再次尝试安装。</span><span class="sxs-lookup"><span data-stu-id="20bf0-197">If the installation fails for any reason, you might need to restart the computer before trying the install again.</span></span>

## <span data-ttu-id="20bf0-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="20bf0-198">Related topics</span></span>

[<span data-ttu-id="20bf0-199">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="20bf0-199">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="20bf0-200">独立传递方案概述</span><span class="sxs-lookup"><span data-stu-id="20bf0-200">Stand-Alone Delivery Scenario Overview</span></span>](stand-alone-delivery-scenario-overview.md)
