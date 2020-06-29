---
title: 如何安装和配置 MED-V 服务器组件
description: 如何安装和配置 MED-V 服务器组件
author: dansimp
ms.assetid: 2d3c5b15-df2c-4ab6-bf78-f47ef8ae7418
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4fb0cc5c9ffe76e987e316d0285f172dd0b76578
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804076"
---
# <span data-ttu-id="b0386-103">如何安装和配置 MED-V 服务器组件</span><span class="sxs-lookup"><span data-stu-id="b0386-103">How to Install and Configure the MED-V Server Component</span></span>


<span data-ttu-id="b0386-104">本部分介绍如何[安装](#bkmk-howtoinstallthemedvserver)和[配置](#bkmk-howtoconfigurethemedvserver)med-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="b0386-104">This section explains how to [install](#bkmk-howtoinstallthemedvserver) and [configure](#bkmk-howtoconfigurethemedvserver) the MED-V server.</span></span>

## <a href="" id="bkmk-howtoinstallthemedvserver"></a><span data-ttu-id="b0386-105">如何安装 MED-V 服务器</span><span class="sxs-lookup"><span data-stu-id="b0386-105">How to Install the MED-V Server</span></span>


**<span data-ttu-id="b0386-106">安装 MED-V 服务器</span><span class="sxs-lookup"><span data-stu-id="b0386-106">To install the MED-V server</span></span>**

1.  <span data-ttu-id="b0386-107">安装 MED-V 服务器 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="b0386-107">Install the MED-V Server .msi package.</span></span>

    <span data-ttu-id="b0386-108">"MED-V 服务器 .msi" 程序包称为 " *MED-V\_Server\_x.msi*"，其中 x 是版本号。</span><span class="sxs-lookup"><span data-stu-id="b0386-108">The MED-V Server .msi package is called *MED-V\_Server\_x.msi*, where x is the version number.</span></span>

    <span data-ttu-id="b0386-109">例如， *MED-V\_Server\_1.0.65.msi*。</span><span class="sxs-lookup"><span data-stu-id="b0386-109">For example, *MED-V\_Server\_1.0.65.msi*.</span></span>

2.  <span data-ttu-id="b0386-110">出现**InstallShield 向导 "欢迎**" 屏幕时，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-110">When the **InstallShield Wizard Welcome** screen appears, click **Next**.</span></span>

3.  <span data-ttu-id="b0386-111">在 "**许可协议**" 屏幕上，阅读许可协议，单击 **"我接受许可协议中的条款**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-111">On the **License Agreement** screen, read the license agreement, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

    <span data-ttu-id="b0386-112">显示 "**目标文件夹**" 屏幕，显示默认安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0386-112">The **Destination Folder** screen appears, with the default installation folder displayed.</span></span>

    <span data-ttu-id="b0386-113">默认安装文件夹为 *%Systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization\\*。</span><span class="sxs-lookup"><span data-stu-id="b0386-113">The default installation folder is *%systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization\\*.</span></span>

    -   <span data-ttu-id="b0386-114">若要更改应安装 MED-V 的文件夹，请单击 "**更改**"，然后浏览到现有文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0386-114">To change the folder where MED-V should be installed, click **Change** and browse to an existing folder.</span></span>

4.  <span data-ttu-id="b0386-115">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0386-115">Click **Next**.</span></span>

5.  <span data-ttu-id="b0386-116">在 "已**准备好安装程序**" 屏幕上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-116">On the **Ready to Install the Program** screen, click **Install**.</span></span>

    <span data-ttu-id="b0386-117">开始安装 MED-V 服务器。</span><span class="sxs-lookup"><span data-stu-id="b0386-117">The MED-V server installation starts.</span></span> <span data-ttu-id="b0386-118">这可能需要几分钟的时间，屏幕可能不会显示文本。</span><span class="sxs-lookup"><span data-stu-id="b0386-118">This can take several minutes, and the screen might not display text.</span></span> <span data-ttu-id="b0386-119">在安装过程中，将显示多个进度屏幕。</span><span class="sxs-lookup"><span data-stu-id="b0386-119">During installation, several progress screens appear.</span></span> <span data-ttu-id="b0386-120">如果出现一条消息，请按照提供的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b0386-120">If a message appears, follow the instructions provided.</span></span>

6.  <span data-ttu-id="b0386-121">当 " **InstallShield 向导完成**" 屏幕出现时，单击 "**完成**" 以完成该向导。</span><span class="sxs-lookup"><span data-stu-id="b0386-121">When the **InstallShield Wizard Completed** screen appears, click **Finish** to complete the wizard.</span></span>

**<span data-ttu-id="b0386-122">注意</span><span class="sxs-lookup"><span data-stu-id="b0386-122">Note</span></span>**  
<span data-ttu-id="b0386-123">如果要通过 Microsoft 远程桌面安装 MED-V 服务器，请使用以下语法： **mstsc/admin**。确保你的 RDP 会话定向到控制台。</span><span class="sxs-lookup"><span data-stu-id="b0386-123">If you are installing the MED-V server via Microsoft Remote Desktop, use the following syntax: **mstsc/admin**. Ensure that your RDP session is directed to the console.</span></span>



## <a href="" id="bkmk-howtoconfigurethemedvserver"></a><span data-ttu-id="b0386-124">如何配置 MED-V 服务器</span><span class="sxs-lookup"><span data-stu-id="b0386-124">How to Configure the MED-V Server</span></span>


<span data-ttu-id="b0386-125">可以配置以下服务器设置：</span><span class="sxs-lookup"><span data-stu-id="b0386-125">The following server settings can be configured:</span></span>

-   [<span data-ttu-id="b0386-126">连接</span><span class="sxs-lookup"><span data-stu-id="b0386-126">Connections</span></span>](#bkmk-configuringconnections)

-   [<span data-ttu-id="b0386-127">Images</span><span class="sxs-lookup"><span data-stu-id="b0386-127">Images</span></span>](#bkmk-configuringimages)

-   [<span data-ttu-id="b0386-128">权限</span><span class="sxs-lookup"><span data-stu-id="b0386-128">Permissions</span></span>](#bkmk-configuringpermissions)

-   [<span data-ttu-id="b0386-129">报告</span><span class="sxs-lookup"><span data-stu-id="b0386-129">Reports</span></span>](#bkmk-configuringreports)

### <a href="" id="bkmk-configuringconnections"></a><span data-ttu-id="b0386-130">配置连接</span><span class="sxs-lookup"><span data-stu-id="b0386-130">Configuring Connections</span></span>

**<span data-ttu-id="b0386-131">配置连接</span><span class="sxs-lookup"><span data-stu-id="b0386-131">To configure connections</span></span>**

1.  <span data-ttu-id="b0386-132">在 Windows "开始" 菜单上，选择 "**所有程序" &gt; med-v &gt; Med-v-v 服务器配置管理器**。</span><span class="sxs-lookup"><span data-stu-id="b0386-132">On the Windows Start menu, select **All Programs &gt; MED-V &gt; MED-V Server Configuration Manager**.</span></span>

    **<span data-ttu-id="b0386-133">注意</span><span class="sxs-lookup"><span data-stu-id="b0386-133">Note</span></span>**  
    <span data-ttu-id="b0386-134">注意：如果在服务器安装期间选中了 "**启动 Med-v Server 配置管理器**" 复选框，则 med-v 服务器配置管理器将在服务器安装完成后自动启动。</span><span class="sxs-lookup"><span data-stu-id="b0386-134">Note: If you selected the **Launch MED-V Server Configuration Manager** check box during the server installation, the MED-V server configuration manager starts automatically after the server installation is complete.</span></span>



~~~
The MED-V Server Configuration Manager appears.
~~~

2. <span data-ttu-id="b0386-135">在 "**连接**" 选项卡上，配置以下客户端连接设置：</span><span class="sxs-lookup"><span data-stu-id="b0386-135">On the **Connections** tab, configure the following client connections settings:</span></span>

   -   <span data-ttu-id="b0386-136">**启用未加密的连接（http），使用端口**—选中此复选框可使用指定的端口启用未加密的连接。</span><span class="sxs-lookup"><span data-stu-id="b0386-136">**Enable unencrypted connections (http), using port**—Select this check box to enable unencrypted connections using a specified port.</span></span> <span data-ttu-id="b0386-137">在 "端口" 框中，输入要接受未加密的连接（http）的服务器端口。</span><span class="sxs-lookup"><span data-stu-id="b0386-137">In the port box, enter the server port on which to accept unencrypted connections (http).</span></span>

   -   <span data-ttu-id="b0386-138">**启用加密连接（https），使用端口**-选中此复选框可使用指定的端口启用加密连接。</span><span class="sxs-lookup"><span data-stu-id="b0386-138">**Enable encrypted connections (https), using port**—Select this check box to enable encrypted connections using a specified port.</span></span> <span data-ttu-id="b0386-139">在 "端口" 框中，输入要接受加密连接的服务器端口（https）。</span><span class="sxs-lookup"><span data-stu-id="b0386-139">In the port box, enter the server port on which to accept encrypted connections (https).</span></span>

       <span data-ttu-id="b0386-140">Https 是可选配置，可以进行设置以确保 MED-V 服务器和 MED-V 客户端之间的安全事务。</span><span class="sxs-lookup"><span data-stu-id="b0386-140">Https is an optional configuration which can be set to ensure secure transactions between the MED-V server and MED-V clients.</span></span> <span data-ttu-id="b0386-141">若要配置 https，必须执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="b0386-141">To configure https, you must perform the following procedures:</span></span>

       -   <span data-ttu-id="b0386-142">在服务器上配置证书。</span><span class="sxs-lookup"><span data-stu-id="b0386-142">Configure a certificate on the server.</span></span>

       -   <span data-ttu-id="b0386-143">将服务器证书与使用 netsh 指定的端口相关联。</span><span class="sxs-lookup"><span data-stu-id="b0386-143">Associate the server certificate with the port specified using netsh.</span></span> <span data-ttu-id="b0386-144">有关信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="b0386-144">For information, see the following:</span></span>

           -   [<span data-ttu-id="b0386-145">超文本传输协议（HTTP）的 Netsh 命令</span><span class="sxs-lookup"><span data-stu-id="b0386-145">Netsh Commands for Hypertext Transfer Protocol (HTTP)</span></span>](https://go.microsoft.com/fwlink/?LinkId=183314)

           -   [<span data-ttu-id="b0386-146">如何：使用 SSL 证书配置端口</span><span class="sxs-lookup"><span data-stu-id="b0386-146">How to: Configure a Port with an SSL Certificate</span></span>](https://go.microsoft.com/fwlink/?LinkID=183315)

           -   [<span data-ttu-id="b0386-147">如何：使用 SSL 证书配置端口</span><span class="sxs-lookup"><span data-stu-id="b0386-147">How to: Configure a Port with an SSL Certificate</span></span>](https://msdn.microsoft.com/library/ms733791.aspx)

3. <span data-ttu-id="b0386-148">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0386-148">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringimages"></a><span data-ttu-id="b0386-149">配置图像</span><span class="sxs-lookup"><span data-stu-id="b0386-149">Configuring Images</span></span>

**<span data-ttu-id="b0386-150">配置图像</span><span class="sxs-lookup"><span data-stu-id="b0386-150">To configure images</span></span>**

1.  <span data-ttu-id="b0386-151">单击 "**图像**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0386-151">Click the **Images** tab.</span></span>

2.  <span data-ttu-id="b0386-152">配置以下映像管理设置：</span><span class="sxs-lookup"><span data-stu-id="b0386-152">Configure the following image management settings:</span></span>

    -   <span data-ttu-id="b0386-153">虚拟机**目录**-虚拟机目录（存储图像的目录）。</span><span class="sxs-lookup"><span data-stu-id="b0386-153">**VMs Directory**—The virtual machine directory (the directory where the images are stored).</span></span> <span data-ttu-id="b0386-154">此字段包含可从 MED-V 服务器访问的图像分发服务器上的图像目录的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="b0386-154">This field contains a UNC path to the image directory on the image distribution server that should be accessible from the MED-V server.</span></span>

    -   <span data-ttu-id="b0386-155">**VM URL**-存储图像的服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="b0386-155">**VMs URL**—The location of the server where the images are stored.</span></span>

3.  <span data-ttu-id="b0386-156">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0386-156">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringpermissions"></a><span data-ttu-id="b0386-157">配置权限</span><span class="sxs-lookup"><span data-stu-id="b0386-157">Configuring Permissions</span></span>

**<span data-ttu-id="b0386-158">配置权限</span><span class="sxs-lookup"><span data-stu-id="b0386-158">To configure permissions</span></span>**

1.  <span data-ttu-id="b0386-159">单击 "**权限**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0386-159">Click the **Permissions** tab.</span></span>

2.  <span data-ttu-id="b0386-160">提供了可供登录的所有用户的列表。</span><span class="sxs-lookup"><span data-stu-id="b0386-160">A list of all users who can log in is provided.</span></span> <span data-ttu-id="b0386-161">若要对用户应用 "读取" 和 "写入" 权限，请选中用户旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="b0386-161">To apply read and write permissions to a user, select the check box next to the user.</span></span> <span data-ttu-id="b0386-162">若要对用户应用只读权限，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="b0386-162">To apply read-only permissions to a user, clear the check box.</span></span>

3.  <span data-ttu-id="b0386-163">若要添加域用户或组，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-163">To add domain users or groups, click **Add**.</span></span>

    <span data-ttu-id="b0386-164">将显示 "**输入用户或组名称**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="b0386-164">The **Enter User or Group names** dialog box appears.</span></span>

    1.  <span data-ttu-id="b0386-165">通过执行下列操作之一选择 "域用户" 或 "组"：</span><span class="sxs-lookup"><span data-stu-id="b0386-165">Select domain users or groups by doing one of the following:</span></span>

        -   <span data-ttu-id="b0386-166">在 "**输入用户或组名称**" 字段中，键入域中存在的用户或组，或者在计算机上作为本地用户或组存在。</span><span class="sxs-lookup"><span data-stu-id="b0386-166">In the **Enter User or Group names** field, type a user or group that exists in the domain or exists as a local user or group on the computer.</span></span> <span data-ttu-id="b0386-167">然后单击 "**检查姓名**" 以将其解析为完整的现有名称。</span><span class="sxs-lookup"><span data-stu-id="b0386-167">Then click **Check Names** to resolve it to the full existent name.</span></span>

        -   <span data-ttu-id="b0386-168">单击 "**查找**" 以打开 "标准**选择用户或组**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="b0386-168">Click **Find** to open the standard **Select Users or Groups** dialog box.</span></span> <span data-ttu-id="b0386-169">然后选择 "域用户" 或 "组"。</span><span class="sxs-lookup"><span data-stu-id="b0386-169">Then select domain users or groups.</span></span>

    2.  <span data-ttu-id="b0386-170">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0386-170">Click **OK**.</span></span>

4.  <span data-ttu-id="b0386-171">若要删除域用户或组，请选择用户或组，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-171">To remove domain users or groups, select a user or group and click **Remove**.</span></span>

5.  <span data-ttu-id="b0386-172">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0386-172">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringreports"></a><span data-ttu-id="b0386-173">配置报表</span><span class="sxs-lookup"><span data-stu-id="b0386-173">Configuring Reports</span></span>

**<span data-ttu-id="b0386-174">配置报表</span><span class="sxs-lookup"><span data-stu-id="b0386-174">To configure reports</span></span>**

1.  <span data-ttu-id="b0386-175">单击 "**报表**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0386-175">Click the **Reports** tab.</span></span>

2.  <span data-ttu-id="b0386-176">若要支持报表，请选择 "**启用报表**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-176">To support reports, select **Enable reports**.</span></span>

3.  <span data-ttu-id="b0386-177">在 "**连接字符串**" 框中，输入 MSSQL 数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="b0386-177">In the **Connection String** box, enter a connection string for the MSSQL database.</span></span>

    -   <span data-ttu-id="b0386-178">当 SQL Server 安装在远程服务器上时，请使用以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="b0386-178">When SQL Server is installed on a remote server, use the following connection string:</span></span>

        `Data Source=<ServerName>;Initial Catalog=<DBName>;uid=sa;pwd=<Password>;`

        **<span data-ttu-id="b0386-179">注意</span><span class="sxs-lookup"><span data-stu-id="b0386-179">Note</span></span>**  
        <span data-ttu-id="b0386-180">注意：若要连接到 SQL Express，请使用：</span><span class="sxs-lookup"><span data-stu-id="b0386-180">Note: To connect to SQL Express, use:</span></span> `Data Source=<ServerName>\sqlexpress.`



4.  <span data-ttu-id="b0386-181">若要创建数据库，请单击 "**创建数据库**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-181">To create the database, click **Create Database**.</span></span>

5.  <span data-ttu-id="b0386-182">若要测试连接，请单击 "**测试连接**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-182">To test the connection, click **Test Connection**.</span></span>

6.  <span data-ttu-id="b0386-183">要配置数据库清除选项，请单击 "**清除选项**"。</span><span class="sxs-lookup"><span data-stu-id="b0386-183">To configure database clearing options, click **Clear Options**.</span></span>

    <span data-ttu-id="b0386-184">将显示 "**清除数据库选项**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="b0386-184">The **Clear Database Options** dialog box appears.</span></span>

    1.  <span data-ttu-id="b0386-185">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b0386-185">Choose one of the following options:</span></span>

        -   <span data-ttu-id="b0386-186">**清除早于**该时间的数据-清除早于指定天数的所有数据;在 "数字" 框中，输入天数。</span><span class="sxs-lookup"><span data-stu-id="b0386-186">**Clear data older than**—Clear all data older than the number of days specified; in the number box, enter a number of days.</span></span>

        -   <span data-ttu-id="b0386-187">**清除数据库中的所有数据**-清除数据库中的所有现有数据。</span><span class="sxs-lookup"><span data-stu-id="b0386-187">**Clear all data from database**—Clear all existent data in the database.</span></span>

        -   <span data-ttu-id="b0386-188">**删除数据库**-删除数据库。</span><span class="sxs-lookup"><span data-stu-id="b0386-188">**Drop database**—Delete the database.</span></span>

    2.  <span data-ttu-id="b0386-189">单击 **"确定"** 以应用更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="b0386-189">Click **OK** to apply changes and close the dialog box.</span></span>

7.  <span data-ttu-id="b0386-190">单击 **"确定"** 保存所做的更改，或单击 "**取消**" 关闭对话框而不保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b0386-190">Click **OK** to save the changes, or click **Cancel** to close the dialog box without saving changes.</span></span>

8.  <span data-ttu-id="b0386-191">如果出现提示，请重新启动 MED-V 服务器服务以将更改应用到网络设置。</span><span class="sxs-lookup"><span data-stu-id="b0386-191">If prompted, restart the MED-V server service to apply changes to the network settings.</span></span>

## <span data-ttu-id="b0386-192">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0386-192">Related topics</span></span>


[<span data-ttu-id="b0386-193">支持的配置</span><span class="sxs-lookup"><span data-stu-id="b0386-193">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="b0386-194">设计 MED-V 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="b0386-194">Design the MED-V Server Infrastructure</span></span>](design-the-med-v-server-infrastructure.md)









