---
title: 如何安装 Management Console
description: 如何安装 Management Console
author: dansimp
ms.assetid: 586d99c8-bca6-42e2-a39c-a696053142f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48f4f69753794cf8099df36828e0502e98414b31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801363"
---
# <span data-ttu-id="6aa0f-103">如何安装 Management Console</span><span class="sxs-lookup"><span data-stu-id="6aa0f-103">How to Install the Management Console</span></span>


<span data-ttu-id="6aa0f-104">你可以使用以下过程在网络上的目标计算机上安装应用程序虚拟化管理控制台。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-104">You can use the following procedure to install the Application Virtualization Management Console on a target computer on the network.</span></span> <span data-ttu-id="6aa0f-105">您必须使用在目标计算机上具有管理员权限的网络帐户。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-105">You must use a network account that has administrator privileges on the target computer.</span></span> <span data-ttu-id="6aa0f-106">你可以使用该控制台配置和管理应用程序虚拟化系统平台。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-106">You can use the console to configure and manage the Application Virtualization System Platform.</span></span>

<span data-ttu-id="6aa0f-107">在完成此过程之前，必须在此计算机或其他计算机上安装应用程序虚拟化管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-107">Before you can complete this procedure, you must install the Application Virtualization Management Web Service on this or a different computer.</span></span> <span data-ttu-id="6aa0f-108">管理 Web 服务允许你访问数据存储和域控制器。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-108">The Management Web Service allows you to access the data store and the domain controller.</span></span> <span data-ttu-id="6aa0f-109">有关安装 Web 服务的详细信息，请参阅[如何安装管理 Web 服务](how-to-install-the-management-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-109">For more information about installing the Web service, see [How to Install the Management Web Service](how-to-install-the-management-web-service.md).</span></span>

**<span data-ttu-id="6aa0f-110">安装管理控制台</span><span class="sxs-lookup"><span data-stu-id="6aa0f-110">To install the Management Console</span></span>**

1.  <span data-ttu-id="6aa0f-111">验证目标计算机上未安装以前版本的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-111">Verify that no previous versions of the Management Console are installed on the target computer.</span></span>

2.  <span data-ttu-id="6aa0f-112">导航到网络上应用程序虚拟化系统设置程序的位置，或者从网络运行此程序，或者将其目录复制到目标计算机，然后双击 " **Setup.exe**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-112">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

3.  <span data-ttu-id="6aa0f-113">在 "**欢迎" 页面**上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-113">On the **Welcome Page**, click **Next**.</span></span>

4.  <span data-ttu-id="6aa0f-114">在 "**许可协议**" 页面上，要接受许可协议，请选择 **"我接受许可条款和条件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-114">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="6aa0f-115">在 "**注册信息**" 页面上，指定**用户名**和**组织**信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-115">On the **Registration Information** page, specify the **User Name** and **Organization** information, and then click **Next**.</span></span>

6.  <span data-ttu-id="6aa0f-116">在 "**安装类型**" 页面上，单击 "**自定义**"，然后单击 "**下一步**"</span><span class="sxs-lookup"><span data-stu-id="6aa0f-116">On the **Setup Type** page, click **Custom** and then click **Next**.</span></span>

7.  <span data-ttu-id="6aa0f-117">在 "**自定义设置**" 页面上，取消选择 "**管理控制台**" 以外的所有应用程序虚拟化系统组件，然后单击 "**下一步**</span><span class="sxs-lookup"><span data-stu-id="6aa0f-117">On the **Custom Setup** page, deselect all Application Virtualization System components except **Management Console**, and then click **Next**.</span></span>

    <span data-ttu-id="6aa0f-118">**注意** 如果计算机上已安装某个组件，请在 "自定义设置" 屏幕上将其取消选中，它将自动卸载。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-118">**Note** If a component is already installed on the computer, by deselecting it on the Custom Setup screen, it will automatically be uninstalled.</span></span>

     

8.  <span data-ttu-id="6aa0f-119">在 "**准备修改程序"** 屏幕上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-119">On the **Ready to Modify the Program** screen, click **Install**.</span></span>

    <span data-ttu-id="6aa0f-120">**注意** 如果这是你安装的第一个组件，则会显示 "**准备安装程序**" 页面。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-120">**Note** If this is the first component you install, the **Ready to Install the Program** page is displayed.</span></span> <span data-ttu-id="6aa0f-121">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-121">To start the installation, click **Install**.</span></span>

     

9.  <span data-ttu-id="6aa0f-122">在 "**安装向导已完成**" 屏幕上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-122">On the **Installation Wizard Completed** screen, click **Finish**.</span></span> <span data-ttu-id="6aa0f-123">单击 **"** 确定" 以重新启动计算机并完成安装。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-123">Click **Okay** to restart the computer and complete the installation.</span></span>

10. <span data-ttu-id="6aa0f-124">在 Windows "控制面板" 中，双击 "**管理工具**"，然后单击 "**应用程序虚拟化管理控制台**" 以显示管理控制台。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-124">In the Windows Control Panel, double-click **Administrative Tools** and then click **Application Virtualization Management Console** to display the Management Console.</span></span>

11. <span data-ttu-id="6aa0f-125">单击 "**连接**" 图标，或右键单击 "**应用程序虚拟化系统**" 容器，然后单击 "**连接到应用程序虚拟化系统**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-125">Click the **Connect** icon, or right-click the **Application Virtualization Systems** container, and then click **Connect to Application Virtualization System**.</span></span>

12. <span data-ttu-id="6aa0f-126">在 "**连接到应用程序虚拟化系统**" 屏幕上，输入管理 Web 服务计算机的主机名和端口，更改安全信息和登录凭据（如有必要），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-126">On the **Connect to Application Virtualization System** screen, enter the host name and port of the Management Web Service computer, change the security information and login credentials if necessary, and then click **OK**.</span></span>

13. <span data-ttu-id="6aa0f-127">连接到管理 Web 服务计算机后，单击 "**控制台**" 菜单上的 "**文件**"，然后单击 "**退出**"。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-127">After connecting to the Management Web Service computer, click **File** on the **Console** menu, and then click **Exit**.</span></span> <span data-ttu-id="6aa0f-128">单击 **"是"** 保存控制台设置。</span><span class="sxs-lookup"><span data-stu-id="6aa0f-128">Click **Yes** to save console settings.</span></span>

## <span data-ttu-id="6aa0f-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="6aa0f-129">Related topics</span></span>


[<span data-ttu-id="6aa0f-130">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="6aa0f-130">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





