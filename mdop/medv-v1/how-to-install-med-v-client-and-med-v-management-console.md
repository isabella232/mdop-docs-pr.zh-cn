---
title: 如何安装 MED-V 客户端和 MED-V 管理控制台
description: 如何安装 MED-V 客户端和 MED-V 管理控制台
author: dansimp
ms.assetid: 8a5f3010-3a50-487e-99d8-e352e5cb51c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a486cc7cf5534171f80b08dc93742e03cd4a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804077"
---
# <span data-ttu-id="fdfd4-103">如何安装 MED-V 客户端和 MED-V 管理控制台</span><span class="sxs-lookup"><span data-stu-id="fdfd4-103">How to Install MED-V Client and MED-V Management Console</span></span>


<span data-ttu-id="fdfd4-104">客户端 .msi 程序包中包含以下 MED-V 组件：</span><span class="sxs-lookup"><span data-stu-id="fdfd4-104">The following MED-V components are included in the client .msi package:</span></span>

-   <span data-ttu-id="fdfd4-105">MED-V 客户端-必须安装在客户端计算机上才能运行 MED-V 工作区的 MED-V 软件。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-105">MED-V client—The MED-V software that must be installed on client computers for running MED-V workspaces.</span></span>

-   <span data-ttu-id="fdfd4-106">MED-V 管理控制台-管理员可用于创建和维护图像、MED-V 工作区和策略的管理工具。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-106">MED-V management console—The administrative tool that administrators can use to create and maintain images, MED-V workspaces, and policies.</span></span>

<span data-ttu-id="fdfd4-107">MED-V 管理控制台和 MED-V 客户端都是从 MED-V 客户端安装的。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-107">The MED-V management console and the MED-V client are both installed from the MED-V client .msi package.</span></span> <span data-ttu-id="fdfd4-108">但是，不使用 MED-V 管理控制台即可独立安装 MED-V 客户端，方法是清除安装期间的 "**安装 Med-v 管理应用程序**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-108">The MED-V client, however, can be installed independently without the MED-V management console by clearing the **Install the MED-V Management application** check box during installation.</span></span>

**<span data-ttu-id="fdfd4-109">注意</span><span class="sxs-lookup"><span data-stu-id="fdfd4-109">Note</span></span>**  
<span data-ttu-id="fdfd4-110">MED-V 客户端和 MED-V 管理控制台只能安装在基于 Windows 7、Windows Vista 和 Windows XP 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-110">The MED-V client and MED-V management console can only be installed on Windows 7-, Windows Vista-, and Windows XP-based computers.</span></span> <span data-ttu-id="fdfd4-111">不能在服务器产品上安装它们。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-111">They cannot be installed on server products.</span></span>



**<span data-ttu-id="fdfd4-112">注意</span><span class="sxs-lookup"><span data-stu-id="fdfd4-112">Note</span></span>**  
<span data-ttu-id="fdfd4-113">不要使用 Windows **runas**命令安装 med-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-113">Do not install the MED-V client using the Windows **runas** command.</span></span>



**<span data-ttu-id="fdfd4-114">安装 MED-V 客户端</span><span class="sxs-lookup"><span data-stu-id="fdfd4-114">To install the MED-V client</span></span>**

1.  <span data-ttu-id="fdfd4-115">以具有本地计算机上的本地管理员权限的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-115">Log in as a user with local administrator rights on the local computer.</span></span>

2.  <span data-ttu-id="fdfd4-116">运行 MED-V .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-116">Run the MED-V .msi package.</span></span>

    <span data-ttu-id="fdfd4-117">MED-V 程序包称为 " *MED-V\_x.msi*"，其中*x*是版本号。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-117">The MED-V .msi package is called *MED-V\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="fdfd4-118">例如， *MED-V\_1.0.65.msi*。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-118">For example, *MED-V\_1.0.65.msi*.</span></span>

3.  <span data-ttu-id="fdfd4-119">出现**InstallShield 向导 "欢迎**" 屏幕时，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-119">When the **InstallShield Wizard Welcome** screen appears, click **Next**.</span></span>

4.  <span data-ttu-id="fdfd4-120">在 "**许可协议**" 屏幕上，阅读许可协议，单击 **"我接受许可协议中的条款**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-120">On the **License Agreement** screen, read the license agreement, click **I accept the terms in the license agreement**, and click **Next**.</span></span>

    <span data-ttu-id="fdfd4-121">显示 "**目标文件夹**" 屏幕，显示默认安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-121">The **Destination Folder** screen appears, with the default installation folder displayed.</span></span>

    <span data-ttu-id="fdfd4-122">默认安装文件夹是安装操作系统的目录。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-122">The default installation folder is the directory where the operating system is installed.</span></span>

    -   <span data-ttu-id="fdfd4-123">若要更改应安装 MED-V 的文件夹，请单击 "**更改**"，然后通过浏览找到现有文件夹。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-123">To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.</span></span>

5.  <span data-ttu-id="fdfd4-124">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-124">Click **Next**.</span></span>

6.  <span data-ttu-id="fdfd4-125">在 " **Med-v 设置**" 屏幕上，配置 med-v 安装，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fdfd4-125">On the **MED-V Settings** screen, configure the MED-V installation as follows:</span></span>

    -   <span data-ttu-id="fdfd4-126">选中 "**安装 med-v 管理应用程序**" 复选框以在安装中包含管理组件。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-126">Select the **Install the MED-V management application** check box to include the management component in the installation.</span></span>

        **<span data-ttu-id="fdfd4-127">注意</span><span class="sxs-lookup"><span data-stu-id="fdfd4-127">Note</span></span>**  
        <span data-ttu-id="fdfd4-128">企业桌面虚拟化管理员应安装 MED-V 管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-128">Enterprise Desktop Virtualization administrators should install the MED-V management application.</span></span> <span data-ttu-id="fdfd4-129">配置桌面映像和 MED-V 工作区需要此应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-129">This application is required for configuring desktop images and MED-V workspaces.</span></span>



~~~
-   Select the **Load MED-V when Windows starts** check box to start MED-V automatically on startup.

-   Select the **Add a MED-V shortcut to my desktop** check box to create a MED-V shortcut on your desktop.

-   In the **Server address** field, type the server address.

-   In the **Server port** field, type the server's port.

-   Select the **Server requires encrypted connections (https)** check box to work with https.

-   The default virtual machine images folder is displayed. The default installation folder is *%systemdrive%\\MED-V Images\\*. To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.
~~~

7. <span data-ttu-id="fdfd4-130">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-130">Click **Next**.</span></span>

8. <span data-ttu-id="fdfd4-131">在 "已**准备好安装程序**" 屏幕上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-131">On the **Ready to Install the Program** screen, click **Install**.</span></span>

   <span data-ttu-id="fdfd4-132">开始安装 MED-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-132">The MED-V client installation starts.</span></span> <span data-ttu-id="fdfd4-133">这可能需要几分钟的时间，屏幕可能不会显示文本。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-133">This can take several minutes, and the screen might not display text.</span></span> <span data-ttu-id="fdfd4-134">在安装过程中，将显示多个进度屏幕。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-134">During installation, several progress screens appear.</span></span> <span data-ttu-id="fdfd4-135">如果出现一条消息，请按照提供的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-135">If a message appears, follow the instructions provided.</span></span>

   <span data-ttu-id="fdfd4-136">成功安装后，将显示 " **InstallShield 向导已完成**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-136">Upon successful installation, the **InstallShield Wizard Completed** screen appears.</span></span>

9. <span data-ttu-id="fdfd4-137">单击 "**完成**" 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="fdfd4-137">Click **Finish** to close the wizard.</span></span>

## <span data-ttu-id="fdfd4-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="fdfd4-138">Related topics</span></span>


[<span data-ttu-id="fdfd4-139">支持的配置</span><span class="sxs-lookup"><span data-stu-id="fdfd4-139">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="fdfd4-140">安装和升级清单</span><span class="sxs-lookup"><span data-stu-id="fdfd4-140">Installation and Upgrade Checklists</span></span>](installation-and-upgrade-checklists.md)









