---
title: 如何安装 Management Web Service
description: 如何安装 Management Web Service
author: dansimp
ms.assetid: cac296f5-8ca0-4ce7-afdb-859ae207d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b8cc1b4821cb4041d75003cf7e6ff592e1c5039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801352"
---
# <span data-ttu-id="c4d50-103">如何安装 Management Web Service</span><span class="sxs-lookup"><span data-stu-id="c4d50-103">How to Install the Management Web Service</span></span>


<span data-ttu-id="c4d50-104">使用以下过程，使用具有本地管理权限的登录帐户在网络上的目标计算机上安装应用程序虚拟化管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="c4d50-104">Use the following procedure to install the Application Virtualization Management Web Service on a target computer on the network, with a logon account having local administrative privileges.</span></span> <span data-ttu-id="c4d50-105">我们建议你在 Web 服务器上安装此组件，尽管这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="c4d50-105">Although it is not required, we recommended that you install this component on your Web server.</span></span>

**<span data-ttu-id="c4d50-106">安装管理 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c4d50-106">To install the Management Web Service</span></span>**

1.  <span data-ttu-id="c4d50-107">验证你的目标计算机上未安装应用程序虚拟化 Web 服务的以前版本。</span><span class="sxs-lookup"><span data-stu-id="c4d50-107">Verify that no previous versions of the Application Virtualization Web Service are installed on your target computer.</span></span>

2.  <span data-ttu-id="c4d50-108">导航到网络上应用程序虚拟化系统设置程序的位置，或者从网络运行此程序，或者将其目录复制到目标计算机，然后双击 " **Setup.exe**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-108">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

3.  <span data-ttu-id="c4d50-109">安装向导打开后，在 "**欢迎**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-109">After the Installation Wizard opens, on the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="c4d50-110">在 "**许可协议**" 页面上，要接受许可协议，请选择 **"我接受许可条款和条件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-110">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="c4d50-111">在 "**注册信息**" 页面上，指定**用户名**和组织信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-111">On the **Registration Information** page, specify the **User Name** and organization information, and then click **Next**.</span></span>

6.  <span data-ttu-id="c4d50-112">在 "**安装类型**" 页面上，单击 "**自定义**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-112">On the **Setup Type** page, click **Custom**, and then click **Next**.</span></span>

    <span data-ttu-id="c4d50-113">**注意** 如果这不是您在此计算机上安装的第一个组件，则会显示 "**程序维护**" 页面。</span><span class="sxs-lookup"><span data-stu-id="c4d50-113">**Note** If this is not the first component you installed on this computer, the **Program Maintenance** page is displayed.</span></span> <span data-ttu-id="c4d50-114">在 "**程序维护**" 页面上，单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-114">On the **Program Maintenance** page, click **Modify**.</span></span>

     

7.  <span data-ttu-id="c4d50-115">在 "**自定义设置**" 页面上，清除 "应用**Virt 管理服务**" 之外的所有 Application Virtualization System 组件，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-115">On the **Custom Setup** page, clear all Application Virtualization System components except **App Virt Management Service**, and then click **Next**.</span></span>

    <span data-ttu-id="c4d50-116">**注意** 如果计算机上已安装某个组件，请在 "**自定义设置**" 页面上将其清除，您将自动卸载该组件。</span><span class="sxs-lookup"><span data-stu-id="c4d50-116">**Note** If a component is already installed on the computer, by clearing it on the **Custom Setup** page, you will automatically uninstall it.</span></span>

     

8.  <span data-ttu-id="c4d50-117">在 "**数据库服务器**" 页面上，单击 "**连接到可用数据库**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-117">On the **Database Server** page, click **Connect to available database**, and then click **Next**.</span></span>

    <span data-ttu-id="c4d50-118">**注意** 在生产环境中，Microsoft 假定你将连接到现有数据库。</span><span class="sxs-lookup"><span data-stu-id="c4d50-118">**Note** In a production environment, Microsoft assumes that you will connect to an existing database.</span></span> <span data-ttu-id="c4d50-119">如果要安装数据库，请参阅[如何安装数据库](how-to-install-a-database.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d50-119">If you want to install a database, see [How to Install a Database](how-to-install-a-database.md).</span></span> <span data-ttu-id="c4d50-120">安装数据库后，请继续执行步骤13。</span><span class="sxs-lookup"><span data-stu-id="c4d50-120">After installing the database, continue with step 13.</span></span>

     

9.  <span data-ttu-id="c4d50-121">在 "**数据库服务器类型**" 页面上，从列表中选择数据库类型，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-121">On the **Database Server Type** page, select a database type from the list, and then click **Next**.</span></span>

10. <span data-ttu-id="c4d50-122">在 "**数据库服务器位置**" 页面上，从可用服务器列表中选择一个数据库服务器，或通过选中 "**使用以下主机名**" 复选框并在 "**服务器名称**" 和 "**端口号**" 框中输入信息，然后单击 "**下一步**" 来添加服务器。</span><span class="sxs-lookup"><span data-stu-id="c4d50-122">On the **Database Server Location** page, select a database server from the list of available servers or add a server by selecting the **Use the following host name** check box and entering information in the **Server Name** and **Port Number** boxes, and then click **Next**.</span></span>

11. <span data-ttu-id="c4d50-123">在 "**选择数据库**" 页面上，选择所需的数据库，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-123">On the **Select Database** page, select the database you want, and then click **Next**.</span></span>

12. <span data-ttu-id="c4d50-124">在 "**数据库用户配置**" 页面上，输入管理 Web 服务将用于访问数据存储的凭据，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-124">On the **Database User Configuration** page, enter the credentials that the Management Web Service will use to access the data store, and then click **Next**.</span></span>

13. <span data-ttu-id="c4d50-125">在 "**准备修改程序**" 页面上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-125">On the **Ready to Modify the Program** page, click **Install**.</span></span>

    <span data-ttu-id="c4d50-126">**注意** 如果这是你安装的第一个组件，则会显示 "**准备安装程序**" 页面。</span><span class="sxs-lookup"><span data-stu-id="c4d50-126">**Note** If this is the first component you install, the **Ready to Install the Program** page is displayed.</span></span> <span data-ttu-id="c4d50-127">在页面上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-127">On the page, click **Install**.</span></span>

     

14. <span data-ttu-id="c4d50-128">在 "**安装向导已完成**" 页面上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="c4d50-128">On the **Installation Wizard Completed** page, click **Finish**.</span></span>

## <span data-ttu-id="c4d50-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="c4d50-129">Related topics</span></span>


[<span data-ttu-id="c4d50-130">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="c4d50-130">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





