---
title: 如何安装数据库
description: 如何安装数据库
author: dansimp
ms.assetid: 52e3a19d-b7cf-4f2c-8268-0f8361cc9766
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c5f42673c08744d17e1d2e0ef955ebed2848de18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801392"
---
# <span data-ttu-id="08413-103">如何安装数据库</span><span class="sxs-lookup"><span data-stu-id="08413-103">How to Install a Database</span></span>


<span data-ttu-id="08413-104">如果数据库尚不可用，则可以使用以下过程为应用程序虚拟化的基于服务器的部署安装数据库。</span><span class="sxs-lookup"><span data-stu-id="08413-104">You can use the following procedure to install a database for your server-based deployment of Application Virtualization if a database is not already available.</span></span> <span data-ttu-id="08413-105">通常情况下，在生产环境中，你将连接到现有数据库。</span><span class="sxs-lookup"><span data-stu-id="08413-105">Typically, in a production environment, you will connect to an existing database.</span></span>

<span data-ttu-id="08413-106">**重要提示** 若要安装数据库，必须使用具有相应权限的网络帐户。</span><span class="sxs-lookup"><span data-stu-id="08413-106">**Important** To install the database, you must use a network account with the appropriate permissions.</span></span> <span data-ttu-id="08413-107">如果你的组织要求只有数据库管理员才能创建和执行数据库升级，则提供允许执行此任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="08413-107">If your organization requires that only database administrators are allowed to create and conduct database upgrades, scripts are available that allow this task to be performed.</span></span>

 

**<span data-ttu-id="08413-108">安装数据库</span><span class="sxs-lookup"><span data-stu-id="08413-108">To install a database</span></span>**

1.  <span data-ttu-id="08413-109">导航到网络上应用程序虚拟化系统设置程序的位置，或者从网络运行此程序，或者将其目录复制到目标计算机，然后双击 " **Setup.exe**"。</span><span class="sxs-lookup"><span data-stu-id="08413-109">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

2.  <span data-ttu-id="08413-110">在 "**欢迎" 页面**上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-110">On the **Welcome Page**, click **Next**.</span></span>

3.  <span data-ttu-id="08413-111">在 "**许可协议**" 页面上，要接受许可协议，请选择 **"我接受许可条款和条件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-111">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and click **Next**.</span></span>

4.  <span data-ttu-id="08413-112">在 "**注册信息**" 页面上，指定**用户名**和**组织**信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-112">On the **Registering Information** page, specify the **User Name** and **Organization** information, and then click **Next**.</span></span>

5.  <span data-ttu-id="08413-113">在 "**安装类型**" 页面上，选择**自定义**，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-113">On the **Setup Type** page, select **Custom** and then click **Next**.</span></span>

6.  <span data-ttu-id="08413-114">在 "**自定义设置**" 页面上，取消选择 "**应用程序虚拟化服务器**除外"**下**的所有应用程序虚拟化系统组件，然后单击 "</span><span class="sxs-lookup"><span data-stu-id="08413-114">On the **Custom Setup** page, deselect all Application Virtualization System components except **Application Virtualization Server**, and then click **Next**.</span></span>

    <span data-ttu-id="08413-115">**注意** 如果计算机上已安装某个组件，请在 "**自定义设置**" 屏幕上取消选择该组件，它将自动卸载。</span><span class="sxs-lookup"><span data-stu-id="08413-115">**Note** If a component is already installed on the computer, by deselecting it on the **Custom Setup** screen it will automatically be uninstalled.</span></span>

     

7.  <span data-ttu-id="08413-116">在 "**数据库服务器**" 页面上，键入密码，分配安装路径，保存信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-116">On the **Database Server** page, type the passwords, assign an installation path, save the information, and click **Next**.</span></span>

8.  <span data-ttu-id="08413-117">选择数据库的名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-117">Select a name for the database, and then click **Next**.</span></span>

    <span data-ttu-id="08413-118">**注意** 如果在你尝试完成此步骤时显示错误25109，则你未正确设置安装数据库所需的权限。</span><span class="sxs-lookup"><span data-stu-id="08413-118">**Note** If error 25109 is displayed when you try to complete this step, you have incorrectly set up the permissions necessary to install the database.</span></span> <span data-ttu-id="08413-119">有关设置必要的 SQL 权限的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=132144> 。</span><span class="sxs-lookup"><span data-stu-id="08413-119">For details on setting up the necessary SQL permissions, please see <https://go.microsoft.com/fwlink/?LinkId=132144>.</span></span>

     

9.  <span data-ttu-id="08413-120">在 "**目录服务器**" 屏幕上，输入应用程序虚拟化服务器和管理 Web 服务将用于访问您的域控制器的域名和凭据，保存此信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-120">On the **Directory Server** screen, enter a domain name and credentials that Application Virtualization Servers and the Management Web Service will use to access your domain controller, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="08413-121">**注意** 安装将默认为当前计算机的域。</span><span class="sxs-lookup"><span data-stu-id="08413-121">**Note** The installation will default to the domain of the current computer.</span></span>

     

10. <span data-ttu-id="08413-122">在 "**管理员组**" 页面上，输入将具有管理员权限的组的名称，保存此信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-122">On the **Administrator Group** page, enter the name of a group that will have Administrator privileges, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="08413-123">**注意** 您也可以输入将具有管理权限的组名称的前几个字符，单击 "**下一步**"，然后在 "**选择管理员组**" 屏幕上，从生成的列表中选择组。</span><span class="sxs-lookup"><span data-stu-id="08413-123">**Note** You can also enter the first few characters of the name of a group that will have Administration privileges, click **Next**, and on the **Select Administrator Group** screen, select the group from the resulting list.</span></span> <span data-ttu-id="08413-124">然后保存此信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-124">Then save this information and click **Next**.</span></span>

     

11. <span data-ttu-id="08413-125">在 "**默认提供程序组**" 页面上，输入将控制对应用程序的访问的组的完整名称，保存此信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-125">On the **Default Provider Group** page, enter the complete name of a group that will control access to applications, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="08413-126">**注意** 你还可以输入将控制对应用程序的访问的组名称的前几个字符，单击 "**下一步**"，然后在 "**选择默认提供程序组**" 屏幕上，选择列表中的组。</span><span class="sxs-lookup"><span data-stu-id="08413-126">**Note** You can also enter the first few characters of the name of a group that will control access to applications, click **Next**, and on the **Select Default Provider Group** screen, select the group in the list.</span></span> <span data-ttu-id="08413-127">然后保存此信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="08413-127">Then save this information and click **Next**.</span></span>

     

12. <span data-ttu-id="08413-128">在 "**安装向导已完成**" 页面上，若要关闭向导，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="08413-128">On the **Installation Wizard Completed** page, to close the wizard, click **Finish**.</span></span>

    <span data-ttu-id="08413-129">**重要提示** 安装可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="08413-129">**Important** The installation can take a few minutes to finish.</span></span> <span data-ttu-id="08413-130">状态消息将在 Windows 桌面通知区域上方闪烁，指示安装是否成功。</span><span class="sxs-lookup"><span data-stu-id="08413-130">A status message will flash above the Windows desktop notification area, indicating whether the installation succeeded.</span></span>

     

## <span data-ttu-id="08413-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="08413-131">Related topics</span></span>


[<span data-ttu-id="08413-132">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="08413-132">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





