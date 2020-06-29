---
title: 如何安装 Application Virtualization Streaming Server
description: 如何安装 Application Virtualization Streaming Server
author: dansimp
ms.assetid: a3065257-fb5a-4d92-98f8-7ef996c61db9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4e4f8421ef1c0e60a7df92d41be98a5d2bc0132
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801372"
---
# <span data-ttu-id="7d7fb-103">如何安装 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="7d7fb-103">How to Install the Application Virtualization Streaming Server</span></span>


<span data-ttu-id="7d7fb-104">应用程序虚拟化流服务器将其应用程序发布到客户端。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-104">The Application Virtualization Streaming Server publishes its applications to clients.</span></span> <span data-ttu-id="7d7fb-105">在负载平衡环境（这是一种典型的大型部署）中，服务器组中的所有服务器应流出相同的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-105">In a load-balanced environment, which is typical of large deployments, all servers in a server group should stream the same applications.</span></span> <span data-ttu-id="7d7fb-106">如果应用程序虚拟化流服务器要流处理不同的应用程序，请将服务器分配给不同的服务器组。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-106">If Application Virtualization Streaming Servers are to stream different applications, assign the servers to different server groups.</span></span> <span data-ttu-id="7d7fb-107">在这种情况下，你可能还必须增加服务器组的容量。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-107">In this case, you might also have to increase a server group's capacity.</span></span>

<span data-ttu-id="7d7fb-108">如果已使用具有本地管理权限的登录帐户在网络上指定目标计算机，则可以使用以下过程来安装应用程序虚拟化流服务器并将其分配到相应的服务器组。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-108">If you have designated a target computer on the network, with a logon account having local administrative privileges, you can use the following procedure to install the Application Virtualization Streaming Server and assign it to the appropriate server group.</span></span>

<span data-ttu-id="7d7fb-109">**注意** 安装向导可以创建一个服务器组记录（如果不存在），以及此组中的应用程序虚拟化流服务器成员身份记录。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-109">**Note** The Installation Wizard can create a server group record, if one does not exist, and a record of the Application Virtualization Streaming Server membership in this group.</span></span>

 

<span data-ttu-id="7d7fb-110">完成安装过程后，重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-110">After you complete the installation process, restart the server.</span></span>

**<span data-ttu-id="7d7fb-111">安装应用程序虚拟化流服务器</span><span class="sxs-lookup"><span data-stu-id="7d7fb-111">To install an Application Virtualization Streaming Server</span></span>**

1.  <span data-ttu-id="7d7fb-112">验证你的目标计算机上未安装应用程序虚拟化流服务器的早期版本。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-112">Verify that no earlier versions of the Application Virtualization Streaming Server are installed on your target computer.</span></span>

    <span data-ttu-id="7d7fb-113">**重要提示** 请确保此计算机上未安装 app-v 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-113">**Important** Make sure that the App-V Management Server is not installed on this computer.</span></span> <span data-ttu-id="7d7fb-114">这两种产品不能安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-114">The two products cannot be installed on the same computer.</span></span>

     

2.  <span data-ttu-id="7d7fb-115">导航到网络上应用程序虚拟化系统设置程序的位置，或者从网络运行此程序，或者将其目录复制到目标计算机，然后双击**Setup.exe**文件。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-115">Navigate to the location of the Application Virtualization System Setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the **Setup.exe** file.</span></span>

3.  <span data-ttu-id="7d7fb-116">在 "**欢迎**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-116">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="7d7fb-117">在 "**许可协议**" 页面上，要接受许可条款，请选择 **"我接受许可条款和条件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-117">On the **License Agreement** page, to accept the license terms, select **I accept the licensing terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="7d7fb-118">在 "**客户信息**" 页面上，指定**用户名称**和组织，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-118">On the **Customer Information** page, specify the **User name** and the organization, and then click **Next**.</span></span>

6.  <span data-ttu-id="7d7fb-119">在 "**安装路径**" 页面上，单击 "**浏览**"，指定要安装流式服务器的位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-119">On the **Installation Path** page, click **Browse**, specify the location where you want to install the Streaming Server, and then click **Next**.</span></span>

7.  <span data-ttu-id="7d7fb-120">在 "**连接安全模式**" 页面上，从下拉列表中选择所需的证书，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-120">On the **Connection Security Mode** page, select the desired certificate from the drop-down list, and then click **Next**.</span></span>

    <span data-ttu-id="7d7fb-121">**注意** "**安全连接模式**" 设置要求服务器从公钥基础结构中为其预配服务器证书。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-121">**Note** The **Secure Connection Mode** setting requires the server to have a server certificate provisioned to it from a public key infrastructure.</span></span> <span data-ttu-id="7d7fb-122">如果服务器上未安装服务器证书，则此选项不可用且无法选中。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-122">If a server certificate is not installed on the server, this option is unavailable and cannot be selected.</span></span> <span data-ttu-id="7d7fb-123">您必须授予网络服务帐户对正在使用的证书的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-123">You must grant the Network Service account read access to the certificate being used.</span></span>

     

8.  <span data-ttu-id="7d7fb-124">在 " **TCP 端口配置**" 页面上，要使用标准端口（554），请选择 "**使用默认端口（554）**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-124">On the **TCP Port Configuration** page, to use the standard port (554), select **Use default port (554)**.</span></span> <span data-ttu-id="7d7fb-125">若要指定自定义端口，请选择 "**使用自定义端口**"，在提供的字段中指定端口号，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-125">To specify a custom port, select **Use custom port**, specify the port number in the field provided, and then click **Next**.</span></span>

    <span data-ttu-id="7d7fb-126">**注意** 如果在不安全的情况下安装服务器，则可以使用默认端口（554），也可以定义自定义端口。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-126">**Note** When you install the server in a nonsecure scenario, you can use the default port (554), or you can define a custom port.</span></span>

     

9.  <span data-ttu-id="7d7fb-127">在 "**内容根**" 页面上，指定将保存 SFT 文件的目标计算机上的位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-127">On the **Content Root** page, specify the location on the target computer where SFT files will be saved, and then click **Next**.</span></span>

    <span data-ttu-id="7d7fb-128">**注意** 如果虚拟应用程序流服务器的 HTTP 或 RTSP 端口已分配，系统将提示你选择新的端口。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-128">**Note** If the HTTP or RTSP port for the Virtual Application Streaming Server is already allocated, you will be prompted to select a new port.</span></span> <span data-ttu-id="7d7fb-129">指定所需的端口，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-129">Specify the desired port, and then click **Next**.</span></span>

     

10. <span data-ttu-id="7d7fb-130">在 "**高级设置**" 屏幕上，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="7d7fb-130">On the **Advanced Setting** screen, enter the following information:</span></span>

    1.  **<span data-ttu-id="7d7fb-131">最大客户端连接数</span><span class="sxs-lookup"><span data-stu-id="7d7fb-131">Max client connections</span></span>**

    2.  **<span data-ttu-id="7d7fb-132">连接超时（秒）</span><span class="sxs-lookup"><span data-stu-id="7d7fb-132">Connection timeout (sec)</span></span>**

    3.  **<span data-ttu-id="7d7fb-133">RTSP 线程池大小</span><span class="sxs-lookup"><span data-stu-id="7d7fb-133">RTSP thread pool size</span></span>**

    4.  **<span data-ttu-id="7d7fb-134">RTSP 超时（秒）</span><span class="sxs-lookup"><span data-stu-id="7d7fb-134">RTSP timeout (sec)</span></span>**

    5.  **<span data-ttu-id="7d7fb-135">核心流程数</span><span class="sxs-lookup"><span data-stu-id="7d7fb-135">Number of core processes</span></span>**

    6.  **<span data-ttu-id="7d7fb-136">核心超时（秒）</span><span class="sxs-lookup"><span data-stu-id="7d7fb-136">Core timeout (sec)</span></span>**

    7.  **<span data-ttu-id="7d7fb-137">启用用户身份验证</span><span class="sxs-lookup"><span data-stu-id="7d7fb-137">Enable User authentication</span></span>**

    8.  **<span data-ttu-id="7d7fb-138">启用用户授权</span><span class="sxs-lookup"><span data-stu-id="7d7fb-138">Enable User authorization</span></span>**

    9.  **<span data-ttu-id="7d7fb-139">缓存块大小（KB）</span><span class="sxs-lookup"><span data-stu-id="7d7fb-139">Cache block size (KB)</span></span>**

    10. **<span data-ttu-id="7d7fb-140">最大缓存大小（MB）</span><span class="sxs-lookup"><span data-stu-id="7d7fb-140">Maximum cache size (MB)</span></span>**

    <span data-ttu-id="7d7fb-141">**注意** App-v 流服务器使用 NTFS 文件系统权限控制对内容共享下的应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-141">**Note** The App-V Streaming Server uses NTFS file system permissions to control access to the applications under the Content share.</span></span> <span data-ttu-id="7d7fb-142">使用 "**启用用户身份验证**"，并**启用 "用户授权**" 以控制服务器是否检查并强制执行这些访问控制列表（acl）。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-142">Use **Enable User authentication** and **Enable User authorization** to control whether the server checks and enforces those access control lists (ACLs) or not.</span></span>

     

11. <span data-ttu-id="7d7fb-143">在 "已**准备好安装程序**" 页面上，若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-143">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

12. <span data-ttu-id="7d7fb-144">在**安装向导完成**的屏幕上，若要关闭向导，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-144">On the **Installation Wizard Completed** screen, to close the wizard, click **Finish**.</span></span>

    <span data-ttu-id="7d7fb-145">**重要提示** 安装过程可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-145">**Important** The installation can take several minutes to finish.</span></span> <span data-ttu-id="7d7fb-146">状态消息将在 Windows 桌面通知区域上方闪烁，指示安装成功。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-146">A status message will flash above the Windows desktop notification area, indicating that the installation succeeded.</span></span>

    <span data-ttu-id="7d7fb-147">出现提示时，不需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-147">It is not required to restart the computer when you are prompted.</span></span> <span data-ttu-id="7d7fb-148">但是，为了优化系统性能，我们建议重启。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-148">However, to optimize system performance, we recommend a restart.</span></span>

     

13. <span data-ttu-id="7d7fb-149">对每个必须安装的虚拟应用程序服务器重复步骤1至12。</span><span class="sxs-lookup"><span data-stu-id="7d7fb-149">Repeat Steps 1–12 for each Virtual Application Server that you have to install.</span></span>

## <span data-ttu-id="7d7fb-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="7d7fb-150">Related topics</span></span>


[<span data-ttu-id="7d7fb-151">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="7d7fb-151">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





