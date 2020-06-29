---
title: 如何安装 Application Virtualization Management Server
description: 如何安装 Application Virtualization Management Server
author: dansimp
ms.assetid: 8184be79-8c27-4328-a3c1-183791b5556c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfd06ee1d2448990d5a740f3d59b0e5e4b45be4d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801387"
---
# <span data-ttu-id="4c9a3-103">如何安装 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="4c9a3-103">How to Install Application Virtualization Management Server</span></span>


<span data-ttu-id="4c9a3-104">应用程序虚拟化管理服务器将其应用程序发布到客户端。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-104">The Application Virtualization Management Server publishes its applications to clients.</span></span> <span data-ttu-id="4c9a3-105">在负载平衡环境（这是一种典型的大型部署）中，服务器组中的所有服务器应流出相同的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-105">In a load-balanced environment, which is typical of large deployments, all servers in a server group should stream the same applications.</span></span> <span data-ttu-id="4c9a3-106">如果应用程序虚拟化管理服务器要发布不同的应用程序，请将服务器分配给不同的服务器组。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-106">If Application Virtualization Management Servers are to publish different applications, assign the servers to different server groups.</span></span> <span data-ttu-id="4c9a3-107">在这种情况下，你还可能需要增加服务器组的容量。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-107">In this case, you also might need to increase a server group's capacity.</span></span>

<span data-ttu-id="4c9a3-108">如果已使用具有本地管理员权限的登录帐户在网络上指定目标计算机，则可以使用以下过程来安装应用程序虚拟化管理服务器并将其分配到相应的服务器组。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-108">If you have designated a target computer on the network, with a login account having local Administrator privileges, you can use the following procedure to install the Application Virtualization Management Server and assign it to the appropriate server group.</span></span>

**<span data-ttu-id="4c9a3-109">注意</span><span class="sxs-lookup"><span data-stu-id="4c9a3-109">Note</span></span>**  
<span data-ttu-id="4c9a3-110">安装向导可以创建一个服务器组记录（如果不存在），以及此组中应用程序虚拟化管理服务器成员身份的记录。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-110">The Installation Wizard can create a server group record, if one does not exist, as well as a record of the Application Virtualization Management Server's membership in this group.</span></span>



<span data-ttu-id="4c9a3-111">完成安装过程后，重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-111">After you complete the installation process, reboot the server.</span></span>

**<span data-ttu-id="4c9a3-112">安装应用程序虚拟化管理服务器</span><span class="sxs-lookup"><span data-stu-id="4c9a3-112">To install an Application Virtualization Management Server</span></span>**

1.  <span data-ttu-id="4c9a3-113">验证和（如有必要）卸载已安装在目标计算机上的应用程序虚拟化管理服务器的以前版本。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-113">Verify and, if necessary, uninstall previous versions of the Application Virtualization Management Server that are installed on the target computer.</span></span>

2.  <span data-ttu-id="4c9a3-114">若要打开**Microsoft Application Virtualization 管理服务器安装**向导，请导航到网络上应用程序虚拟化系统**setup.exe**程序的位置，或者从网络运行此程序，或者将其目录复制到目标计算机，然后双击**Setup.exe**文件。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-114">To open the **Microsoft Application Virtualization Management Server installation** wizard, navigate to the location of the Application Virtualization System **setup.exe** program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the **Setup.exe** file.</span></span>

3.  <span data-ttu-id="4c9a3-115">在 "**欢迎**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-115">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="4c9a3-116">在 "**许可协议**" 页面上，阅读许可协议，若要接受许可协议，请选择 **"我接受许可条款和条件"**。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-116">On the **License Agreement** page, read the license agreement and, to accept the license agreement, select **I accept the license terms and conditions**.</span></span> <span data-ttu-id="4c9a3-117">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-117">Click **Next**.</span></span>

5.  <span data-ttu-id="4c9a3-118">在 "**注册信息**" 页面上，必须输入用户名和**组织**名称。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-118">On the **Registering Information** page, you must enter the user name and the **Organization**.</span></span> <span data-ttu-id="4c9a3-119">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-119">Click **Next**.</span></span>

6.  <span data-ttu-id="4c9a3-120">在 "**安装类型**" 页面上，选择 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-120">On the **Setup Type** page, select **Custom**.</span></span> <span data-ttu-id="4c9a3-121">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-121">Click **Next**.</span></span> <span data-ttu-id="4c9a3-122">在 "**自定义设置**" 页面上，取消选择 "**应用程序虚拟化服务器**除外"**下**的所有应用程序虚拟化系统组件，然后单击 "</span><span class="sxs-lookup"><span data-stu-id="4c9a3-122">On the **Custom Setup** page, deselect all Application Virtualization System components except **Application Virtualization Server**, and then click **Next**.</span></span>

    **<span data-ttu-id="4c9a3-123">注意</span><span class="sxs-lookup"><span data-stu-id="4c9a3-123">Caution</span></span>**  
    <span data-ttu-id="4c9a3-124">如果计算机上已安装某个组件，则在 "**自定义设置**" 窗口中取消选中该组件时，将自动卸载该组件。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-124">If a component is already installed on the computer, when you deselect it in the **Custom Setup** window, the component is automatically uninstalled.</span></span>



7.  <span data-ttu-id="4c9a3-125">在 "**配置数据库**" 页面上，从可用服务器列表中选择一个数据库服务器，或通过选择 "**使用以下主机名**" 并指定**服务器名称**和**端口号**数据来添加服务器。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-125">On the **Configuration Database** page, select a database server from the list of available servers or add a server by selecting **Use the following host name** and specifying the **Server Name** and **Port Number** data.</span></span> <span data-ttu-id="4c9a3-126">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-126">Click **Next**.</span></span>

    **<span data-ttu-id="4c9a3-127">注意</span><span class="sxs-lookup"><span data-stu-id="4c9a3-127">Note</span></span>**  
    <span data-ttu-id="4c9a3-128">应用程序虚拟化管理服务器不支持区分大小写的 SQL。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-128">The Application Virtualization Management Server does not support case sensitive SQL.</span></span>



~~~
If a database is available, click the radio button, select the database from the list, and then click **Next**. Setup will upgrade it to this newer version. If the name does not appear in the list, enter the name in the space provided.

**Note**  
When naming a server, do not use the backslash character (/) in the server name.

If you need to install a database, see [How to Install a Database](how-to-install-a-database.md). If you would like to create a new database for this version, select **Create a new database** and specify the name that will be assigned to the new database. You can also specify a new location for the database by selecting the check box and entering the path.
~~~



8. <span data-ttu-id="4c9a3-129">在 "**连接安全模式**" 页面上，从下拉列表中选择所需的证书。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-129">On the **Connection Security Mode** page, select the desired certificate from the drop-down list.</span></span> <span data-ttu-id="4c9a3-130">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-130">Click **Next**.</span></span>

   **<span data-ttu-id="4c9a3-131">注意</span><span class="sxs-lookup"><span data-stu-id="4c9a3-131">Note</span></span>**  
   <span data-ttu-id="4c9a3-132">"**安全连接模式**" 设置要求服务器从公钥基础结构中为其预配服务器证书。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-132">The **Secure Connection Mode** setting requires the server to have a server certificate provisioned to it from a public key infrastructure.</span></span> <span data-ttu-id="4c9a3-133">如果服务器上未安装服务器证书，则此选项不可用且无法选中。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-133">If a server certificate is not installed on the server, this option is unavailable and cannot be selected.</span></span> <span data-ttu-id="4c9a3-134">您必须授予网络服务帐户对正在使用的证书的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-134">You must grant the Network Service account read access to the certificate being used.</span></span>



9. <span data-ttu-id="4c9a3-135">在 " **TCP 端口配置**" 页面上，要使用默认端口（554），请选择 "**使用默认端口（554）**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-135">On the **TCP Port Configuration** page, to use the default port (554), select **Use default port (554)**.</span></span> <span data-ttu-id="4c9a3-136">若要指定自定义端口，请选择 "**使用自定义端口**" 并指定将使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-136">To specify a custom port, select **Use custom port** and specify the port number that will be used.</span></span> <span data-ttu-id="4c9a3-137">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-137">Click **Next**.</span></span>

   **<span data-ttu-id="4c9a3-138">注意</span><span class="sxs-lookup"><span data-stu-id="4c9a3-138">Note</span></span>**  
   <span data-ttu-id="4c9a3-139">在不安全的环境中安装服务器时，可以使用默认端口（554），也可以定义自定义端口。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-139">When you install the server in a nonsecure environment, you can use the default port (554) or you can define a custom port.</span></span>



10. <span data-ttu-id="4c9a3-140">在 "**管理员组**" 页面上，在 "**组名称**" 中指定授权管理此服务器的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-140">On the **Administrator Group** page, specify the name of the security group authorized to manage this server in **Group Name**.</span></span> <span data-ttu-id="4c9a3-141">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-141">Click **Next**.</span></span> <span data-ttu-id="4c9a3-142">确认指定的组，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-142">Confirm the group specified and click **Next**.</span></span>

11. <span data-ttu-id="4c9a3-143">在 "**默认提供程序组**" 页面上，指定默认提供程序组的名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-143">On the **Default Provider Group** page, specify the name of the default provider group, and then click **Next**.</span></span>

12. <span data-ttu-id="4c9a3-144">在 "**内容路径**" 页面上，指定将保存 SFT 文件的目标计算机上的位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-144">On the **Content Path** page, specify the location on the target computer where SFT files will be saved, and then click **Next**.</span></span>

   **<span data-ttu-id="4c9a3-145">注意</span><span class="sxs-lookup"><span data-stu-id="4c9a3-145">Note</span></span>**  
   <span data-ttu-id="4c9a3-146">如果管理服务器的 HTTP 或 RTSP 端口已分配，系统将提示你选择新端口。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-146">If the HTTP or RTSP port for the Management Server is already allocated, you will be prompted to choose a new port.</span></span> <span data-ttu-id="4c9a3-147">选择所需的端口，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-147">Select the desired port, and then click **Next**.</span></span>



13. <span data-ttu-id="4c9a3-148">在 "已**准备好安装程序**" 页面上，若要安装应用程序虚拟化管理服务器，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-148">On the **Ready to Install the Program** page, to install the Application Virtualization Management Server, click **Install**.</span></span>

   **<span data-ttu-id="4c9a3-149">注意</span><span class="sxs-lookup"><span data-stu-id="4c9a3-149">Note</span></span>**  
   <span data-ttu-id="4c9a3-150">如果在尝试完成此步骤时显示错误25120，则需要启用 IIS**管理脚本和工具**。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-150">If error 25120 is displayed when you try to complete this step, you need to enable IIS **Management Scripts and Tools**.</span></span> <span data-ttu-id="4c9a3-151">若要启用此 Windows 功能，请打开 "**程序和功能**" 控制面板，选择 **"打开或关闭 Windows 功能**"，然后导航到 " **Internet 信息服务"。**</span><span class="sxs-lookup"><span data-stu-id="4c9a3-151">To enable this Windows feature, open the **Programs and Features** control panel, select **Turn Windows features on or off**, and navigate to **Internet Information Services.**</span></span>

   <span data-ttu-id="4c9a3-152">在 " **Web 管理工具**" 下，启用**IIS 管理脚本和工具**。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-152">Under **Web Management Tools**, enable **IIS Management Scripts and Tools**.</span></span>



14. <span data-ttu-id="4c9a3-153">在**安装向导完成**的屏幕上，若要关闭向导，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-153">On the **Installation Wizard Completed** screen, to close the wizard, click **Finish**.</span></span>

   **<span data-ttu-id="4c9a3-154">重要提示</span><span class="sxs-lookup"><span data-stu-id="4c9a3-154">Important</span></span>**  
   <span data-ttu-id="4c9a3-155">安装可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-155">The installation can take a few minutes to finish.</span></span> <span data-ttu-id="4c9a3-156">状态消息将在 Windows 桌面通知区域上方闪烁，指示安装成功。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-156">A status message will flash above the Windows desktop notification area, indicating that the installation succeeded.</span></span>

   <span data-ttu-id="4c9a3-157">出现提示时，不需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-157">It is not necessary to reboot the computer when prompted.</span></span> <span data-ttu-id="4c9a3-158">但是，为了优化系统性能，建议重新启动。</span><span class="sxs-lookup"><span data-stu-id="4c9a3-158">However, to optimize system performance, a reboot is recommended.</span></span>



## <span data-ttu-id="4c9a3-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="4c9a3-159">Related topics</span></span>


[<span data-ttu-id="4c9a3-160">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="4c9a3-160">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)









