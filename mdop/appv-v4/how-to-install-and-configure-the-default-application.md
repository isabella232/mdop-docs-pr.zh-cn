---
title: 如何安装和配置默认应用程序
description: 如何安装和配置默认应用程序
author: dansimp
ms.assetid: 5c5d5ad1-af40-4f83-8234-39e972f2c29a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083de7a8ebf94bce0b41c0d3c3edf350a9aff38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801388"
---
# <span data-ttu-id="9080a-103">如何安装和配置默认应用程序</span><span class="sxs-lookup"><span data-stu-id="9080a-103">How to Install and Configure the Default Application</span></span>


<span data-ttu-id="9080a-104">默认应用程序作为安装的一部分提供，并在安装期间自动复制到 Microsoft Application Virtualization （app-v）管理服务器。</span><span class="sxs-lookup"><span data-stu-id="9080a-104">The default application is provided as part of the installation and is automatically copied to the Microsoft Application Virtualization (App-V) Management Server during installation.</span></span> <span data-ttu-id="9080a-105">它用于验证管理服务器是否已正确安装和配置，但必须将其发布到 Microsoft Application Virtualization （App-v）客户端，以便用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="9080a-105">It is used to verify that the Management Server was installed and configured correctly, but it has to be published to the Microsoft Application Virtualization (App-V) Client so that the user can access it.</span></span>

<span data-ttu-id="9080a-106">使用以下过程发布默认应用程序并将其流式传输。</span><span class="sxs-lookup"><span data-stu-id="9080a-106">Use the following procedures to publish the default application and to stream it.</span></span>

**<span data-ttu-id="9080a-107">发布默认应用程序</span><span class="sxs-lookup"><span data-stu-id="9080a-107">To publish the default application</span></span>**

1.  <span data-ttu-id="9080a-108">使用在安装期间指定的 App-v 管理员组成员的帐户登录到 App-v 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="9080a-108">Log on to the App-V Management Server by using an account that is a member of the App-V Administrators group specified during installation.</span></span>

2.  <span data-ttu-id="9080a-109">在 App-v 管理服务器上，单击 "**开始**"，单击 "**管理工具**"，然后单击 "**应用程序虚拟化管理控制台**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-109">On the App-V Management Server, click **Start**, click **Administrative Tools**, and then click **Application Virtualization Management Console**.</span></span>

3.  <span data-ttu-id="9080a-110">在 App-v 管理控制台中，单击 "**操作**"，然后单击 "**连接到应用程序虚拟化系统**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-110">In the App-V Management Console, click **Actions**, and then click **Connect to Application Virtualization System**.</span></span>

4.  <span data-ttu-id="9080a-111">在 "**配置连接**" 页面上，清除 "**使用安全连接**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="9080a-111">On the **Configure Connection** page, clear the **Use Secure Connection** check box.</span></span>

5.  <span data-ttu-id="9080a-112">在 " **Web 服务主机名**" 框中，键入 App-v 管理服务器的完全限定的域名（FQDN），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9080a-112">In the **Web Service Host Name** box, type the fully qualified domain name (FQDN) of the App-V Management Server, and then click **OK**.</span></span>

    <span data-ttu-id="9080a-113">**注意** 如果在管理服务器上安装了 Web 服务主机名称，还可以使用**localhost** 。</span><span class="sxs-lookup"><span data-stu-id="9080a-113">**Note** You can also use **localhost** for the Web Service Host name if it is installed on the Management Server.</span></span>

     

6.  <span data-ttu-id="9080a-114">在 App-v 管理控制台中，右键单击**服务器**节点，然后单击 "**系统选项**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-114">In the App-V Management Console, right-click the **Server** node, and click **System Options**.</span></span>

7.  <span data-ttu-id="9080a-115">在 "**常规**" 选项卡上的 "**默认内容路径**" 框中，输入安装期间在服务器上创建的内容文件夹的通用命名约定（UNC）路径;例如，\\ &lt; 服务器名 &gt; \\Content，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9080a-115">On the **General** tab, in the **Default Content Path** box, enter the Universal Naming Convention (UNC) path to the Content folder you created on the server during installation; for example, \\\\&lt;Server Name&gt;\\Content, and then click **OK**.</span></span>

    <span data-ttu-id="9080a-116">**重要提示** 使用服务器名称的 FQDN，以便客户端可以正确解析名称。</span><span class="sxs-lookup"><span data-stu-id="9080a-116">**Important** Use the FQDN for the server name so that the client can resolve the name correctly.</span></span>

     

8.  <span data-ttu-id="9080a-117">在 App-v 管理控制台中的 "导航" 窗格中，展开 "**服务器**" 节点，然后单击 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-117">In the App-V Management Console, in the navigation pane, expand the **Server** node, and then click **Applications**.</span></span>

9.  <span data-ttu-id="9080a-118">在 "主题" 窗格中，单击 "**默认应用程序**"，然后在 "**操作**" 窗格中单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-118">In the topic pane, click **Default Application**, and then, in the **Actions** pane, click **Properties**.</span></span>

10. <span data-ttu-id="9080a-119">在 "**属性**" 对话框中的 " **OSD 路径**" 框旁边，单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-119">In the **Properties** dialog box, next to the **OSD Path** box, click **Browse**.</span></span>

11. <span data-ttu-id="9080a-120">在 "**打开**" 对话框中，输入安装期间在服务器上创建的内容文件夹的 UNC 路径;例如，\\ &lt; 服务器名称 &gt; \\Content，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="9080a-120">In the **Open** dialog box, enter the UNC path to the Content folder you created on the server during installation; for example, \\\\&lt;Server Name&gt;\\Content, and press ENTER.</span></span> <span data-ttu-id="9080a-121">必须使用实际服务器名称，并且不能在此处使用**localhost** 。</span><span class="sxs-lookup"><span data-stu-id="9080a-121">You must use the actual server name and cannot use the **localhost** here.</span></span>

    <span data-ttu-id="9080a-122">**重要提示** 确保 " **OSD 路径**" 和 "**图标路径**" 框中的值为 UNC 格式（例如 \\ &lt; 服务器名称 &gt; \\Content\\DefaultApp.ico），并指向在安装服务器时创建的内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="9080a-122">**Important** Ensure that the values in both the **OSD Path** and **Icon Path** boxes are in UNC format (for example, \\\\&lt;Server Name&gt;\\Content\\DefaultApp.ico), and point to the Content folder you created when installing the server.</span></span> <span data-ttu-id="9080a-123">请勿使用**localhost**或包含驱动器号（如 c:\\program files Files\\..）的文件路径\\..内容.</span><span class="sxs-lookup"><span data-stu-id="9080a-123">Do not use **localhost** or a file path containing a drive letter such as C:\\Program Files\\..\\..\\Content.</span></span>

     

12. <span data-ttu-id="9080a-124">选择 "DefaultApp" 文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-124">Select the DefaultApp.osd file, and click **Open**.</span></span>

13. <span data-ttu-id="9080a-125">重复前面的步骤来配置图标路径。</span><span class="sxs-lookup"><span data-stu-id="9080a-125">Repeat the previous steps to configure the icon path.</span></span>

14. <span data-ttu-id="9080a-126">单击 "**访问权限**" 选项卡，然后确认 App-V 用户组是否有访问应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="9080a-126">Click the **Access Permissions** tab, and confirm that the App-V Users group has access permissions to the application.</span></span>

15. <span data-ttu-id="9080a-127">单击 "**快捷方式**" 选项卡，然后单击 "**发布到用户桌面**"。</span><span class="sxs-lookup"><span data-stu-id="9080a-127">Click the **Shortcuts** tab, and then click **Publish to User’s Desktop**.</span></span> <span data-ttu-id="9080a-128">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9080a-128">Click **OK**.</span></span>

16. <span data-ttu-id="9080a-129">打开 Windows 资源管理器，找到内容目录。</span><span class="sxs-lookup"><span data-stu-id="9080a-129">Open Windows Explorer, and locate the Content directory.</span></span>

17. <span data-ttu-id="9080a-130">双击 DefaultApp 文件，然后用记事本将其打开。</span><span class="sxs-lookup"><span data-stu-id="9080a-130">Double-click the DefaultApp.osd file, and open it with Notepad.</span></span>

18. <span data-ttu-id="9080a-131">找到包含**HREF**标记的行，并将其更改为以下代码：</span><span class="sxs-lookup"><span data-stu-id="9080a-131">Locate the line that contains the **HREF** tag, and change it to the following code:</span></span>

         `CODEBASEHREF=”RTSP://<FQDN of your server>:554/DefaultApp.sft”`

    <span data-ttu-id="9080a-132">或者，如果您使用的是 RTSPS：</span><span class="sxs-lookup"><span data-stu-id="9080a-132">Or, if you are using RTSPS:</span></span>

         `CODEBASEHREF=”RTSPS://<FQDN of your server>:322/DefaultApp.sft”`

19. <span data-ttu-id="9080a-133">关闭 DefaultApp 文件，然后保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="9080a-133">Close the DefaultApp.osd file, and save the changes.</span></span>

**<span data-ttu-id="9080a-134">流式传输默认应用程序</span><span class="sxs-lookup"><span data-stu-id="9080a-134">To stream the default application</span></span>**

1.  <span data-ttu-id="9080a-135">在安装了 App-v 客户端的计算机上，作为在服务器安装期间指定的应用程序虚拟化用户组成员的用户登录。</span><span class="sxs-lookup"><span data-stu-id="9080a-135">On the computer that has the App-V Client installed, log on as a user who is a member of the Application Virtualization Users group specified during server installation.</span></span>

2.  <span data-ttu-id="9080a-136">在桌面上，将显示**默认的应用程序虚拟化应用程序**快捷方式。</span><span class="sxs-lookup"><span data-stu-id="9080a-136">On the desktop, the **Default Application Virtualization Application** shortcut appears.</span></span> <span data-ttu-id="9080a-137">双击快捷方式以启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="9080a-137">Double-click the shortcut to start the application.</span></span>

3.  <span data-ttu-id="9080a-138">Windows 通知区域上方显示的状态栏，报告该应用程序正在启动。</span><span class="sxs-lookup"><span data-stu-id="9080a-138">A status bar, displayed above the Windows notification area, reports that the application is starting.</span></span> <span data-ttu-id="9080a-139">如果应用程序启动成功，将显示默认应用程序的标题屏幕。</span><span class="sxs-lookup"><span data-stu-id="9080a-139">If the application startup is successful, the title screen for the default application is displayed.</span></span> <span data-ttu-id="9080a-140">单击 **"确定"** 关闭该对话框。</span><span class="sxs-lookup"><span data-stu-id="9080a-140">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="9080a-141">您现在已确认 App V 系统正常运行。</span><span class="sxs-lookup"><span data-stu-id="9080a-141">You have now confirmed that the App-V system is running correctly.</span></span>

## <span data-ttu-id="9080a-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="9080a-142">Related topics</span></span>


[<span data-ttu-id="9080a-143">如何为基于服务器的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="9080a-143">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

 

 





