---
title: 如何卸载 MED-V 组件
description: 如何卸载 MED-V 组件
author: dansimp
ms.assetid: c121dd27-6b2f-4d41-a21a-c6e8608c5c41
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 514ec8227b858b34289ca2330f7cfb038bc4f00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798193"
---
# <span data-ttu-id="c2b42-103">如何卸载 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="c2b42-103">How to Uninstall the MED-V Components</span></span>


<span data-ttu-id="c2b42-104">在某些情况下，你可能需要从你的企业卸载 Microsoft 企业桌面虚拟化（MED-V）2.0 组件的全部或部分。</span><span class="sxs-lookup"><span data-stu-id="c2b42-104">Under certain circumstances, you might want to uninstall all or part of the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 components from your enterprise.</span></span> <span data-ttu-id="c2b42-105">例如，你已解决所有应用程序操作系统兼容性问题，或者你希望在你的企业中部署不同的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="c2b42-105">For example, you have resolved all application operating system compatibility issues, or you want to deploy a different MED-V workspace in your enterprise.</span></span>

<span data-ttu-id="c2b42-106">通常，你可以通过使用基于 Windows 的安装程序配置电子软件分发（ESD）系统以卸载 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="c2b42-106">Typically, you can configure your electronic software distribution (ESD) system to uninstall the MED-V components by using a Windows-based Installer.</span></span> <span data-ttu-id="c2b42-107">或者，您也可以手动卸载所有或部分 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="c2b42-107">Alternately, you can uninstall all or some MED-V components manually.</span></span>

<span data-ttu-id="c2b42-108">**重要提示** 必须先卸载任何已安装的 MED-V 主机代理，然后才能卸载 MED-V 主机代理。</span><span class="sxs-lookup"><span data-stu-id="c2b42-108">**Important** Before you can uninstall the MED-V Host Agent, you must first uninstall any installed MED-V workspace.</span></span>

 

<span data-ttu-id="c2b42-109">使用以下过程从您的企业版卸载 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="c2b42-109">Use the following procedures to uninstall the MED-V components from your enterprise.</span></span>

**<span data-ttu-id="c2b42-110">使用电子软件分发系统卸载 MED-V</span><span class="sxs-lookup"><span data-stu-id="c2b42-110">To uninstall MED-V using an electronic software distribution System</span></span>**

1.  <span data-ttu-id="c2b42-111">使用 ESD 系统分发一个脚本，该脚本为要卸载的每个 MED-V 工作区调用 uninstall.exe 的可执行程序。</span><span class="sxs-lookup"><span data-stu-id="c2b42-111">Use your ESD system to distribute a script that invokes the uninstall.exe executable program for every MED-V workspace that you want to uninstall.</span></span> <span data-ttu-id="c2b42-112">文件位于 C:\\ProgramData\\Microsoft\\Medv\\Workspace。</span><span class="sxs-lookup"><span data-stu-id="c2b42-112">The file is located at C:\\ProgramData\\Microsoft\\Medv\\Workspace.</span></span> <span data-ttu-id="c2b42-113">你可以设置一个标志以自动运行卸载可执行程序，以便最终用户不知道卸载。</span><span class="sxs-lookup"><span data-stu-id="c2b42-113">You can set a flag to run the uninstall executable program silently so that end users are unaware of the uninstallation.</span></span>

2.  <span data-ttu-id="c2b42-114">创建一个程序包，以便将 MED-V 主机代理安装文件分发到卸载了 MED-V 工作区的每台计算机。</span><span class="sxs-lookup"><span data-stu-id="c2b42-114">Create a package to distribute the MED-V Host Agent installation file to each computer on which a MED-V workspace was uninstalled.</span></span> <span data-ttu-id="c2b42-115">将程序包配置为在静默模式下运行卸载。</span><span class="sxs-lookup"><span data-stu-id="c2b42-115">Configure the package to run the uninstallation in silent mode.</span></span>

<span data-ttu-id="c2b42-116">ESD 客户端识别新程序包何时可用，并开始根据定义和要求卸载程序包。</span><span class="sxs-lookup"><span data-stu-id="c2b42-116">The ESD client recognizes when the new packages are available and starts to uninstall the packages per the definition and requirements.</span></span>

**<span data-ttu-id="c2b42-117">手动卸载 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="c2b42-117">To manually uninstall a MED-V workspace</span></span>**

1.  <span data-ttu-id="c2b42-118">在主计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-118">On the host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="c2b42-119">在 "**程序和功能**" 窗口中，选择要删除的 med-v 工作区，然后单击 "**卸载**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-119">In the **Programs and Features** window, select the MED-V workspace that you want to remove, and then click **Uninstall**.</span></span> <span data-ttu-id="c2b42-120">（MED-V 工作区名为 "MED-V-V 工作区- &lt;*工作区 \ _name* &gt; "）。</span><span class="sxs-lookup"><span data-stu-id="c2b42-120">(The MED-V workspace is named "MED-V Workspace - &lt;*workspace\_name*&gt;").</span></span> <span data-ttu-id="c2b42-121">将 &lt; 打开 "*工作区 \ _name* &gt; **安装向导**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-121">The &lt;*workspace\_name*&gt; **Setup Wizard** opens.</span></span>

3.  <span data-ttu-id="c2b42-122">在**设置向导**中，单击 "**下一步**"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-122">On the **Setup Wizard**, click **Next**, and then click **Remove**.</span></span>

4.  <span data-ttu-id="c2b42-123">如果你愿意，请选中复选框以删除主 VHD 磁盘和由 MED-V 创建的差异磁盘。</span><span class="sxs-lookup"><span data-stu-id="c2b42-123">If you prefer, select the check box to delete the master VHD disk and differencing disks created by MED-V.</span></span> <span data-ttu-id="c2b42-124">这不是必需的，但在卸载完成后将释放磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="c2b42-124">This is not required, but frees disk space after the uninstallation finishes.</span></span>

5.  <span data-ttu-id="c2b42-125">单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-125">Click **Remove**.</span></span>

    <span data-ttu-id="c2b42-126">**注意** 如果 MED-V 当前正在运行，则会出现一个对话框，提示您是否要将其关闭。</span><span class="sxs-lookup"><span data-stu-id="c2b42-126">**Note** If MED-V is currently running, a dialog box appears and prompts you whether you want to shut it down.</span></span> <span data-ttu-id="c2b42-127">单击 **"是"** 以继续卸载。</span><span class="sxs-lookup"><span data-stu-id="c2b42-127">Click **Yes** to continue with the uninstallation.</span></span> <span data-ttu-id="c2b42-128">单击 "**否**" 取消卸载。</span><span class="sxs-lookup"><span data-stu-id="c2b42-128">Click **No** to cancel the uninstallation.</span></span>

     

<span data-ttu-id="c2b42-129">或者，也可以通过运行 `uninstall.exe` 文件（通常位于 C:\\ProgramData\\Microsoft\\Medv\\Workspace. 上）来删除 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="c2b42-129">Alternately, you can remove a MED-V workspace by running the `uninstall.exe` file, typically located at C:\\ProgramData\\Microsoft\\Medv\\Workspace.</span></span>

**<span data-ttu-id="c2b42-130">手动卸载 MED-V 主机代理</span><span class="sxs-lookup"><span data-stu-id="c2b42-130">To manually uninstall the MED-V Host Agent</span></span>**

1.  <span data-ttu-id="c2b42-131">在 Windows 7 主机计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-131">On the Windows 7 host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="c2b42-132">在 "**程序和功能**" 窗口中，选择 " **med-v Host Agent**"，然后单击 "**卸载**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-132">In the **Programs and Features** window, select **MED-V Host Agent**, and then click **Uninstall**.</span></span>

    <span data-ttu-id="c2b42-133">Windows Installer 将删除 MED-V 主机代理。</span><span class="sxs-lookup"><span data-stu-id="c2b42-133">The Windows Installer removes the MED-V Host Agent.</span></span>

    <span data-ttu-id="c2b42-134">**注意** 如果您在卸载 MED-V 工作区之前尝试卸载 MED-V 主机代理，则会出现一个对话框，指明必须首先卸载 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="c2b42-134">**Note** If you try to uninstall the MED-V Host Agent before you uninstall the MED-V workspace, a dialog box appears that states that you must first uninstall the MED-V workspace.</span></span> <span data-ttu-id="c2b42-135">单击**确定**继续。</span><span class="sxs-lookup"><span data-stu-id="c2b42-135">Click **OK** to continue.</span></span>

     

**<span data-ttu-id="c2b42-136">手动卸载 MED-V 工作区包装程序</span><span class="sxs-lookup"><span data-stu-id="c2b42-136">To manually uninstall the MED-V Workspace Packager</span></span>**

1.  <span data-ttu-id="c2b42-137">在主计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-137">On the host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="c2b42-138">在 "**程序和功能**" 窗口中，选择 " **Med-v-V 工作区包装**程序"，然后单击 "**卸载**"。</span><span class="sxs-lookup"><span data-stu-id="c2b42-138">In the **Programs and Features** window, select **MED-V Workspace Packager**, and then click **Uninstall**.</span></span>

    <span data-ttu-id="c2b42-139">Windows 安装程序删除了 MED-V 工作区包装程序。</span><span class="sxs-lookup"><span data-stu-id="c2b42-139">The Windows Installer removes the MED-V Workspace Packager.</span></span>

    <span data-ttu-id="c2b42-140">**注意** 你可以随时卸载 MED-V 工作区包装程序，而不会影响任何已部署的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="c2b42-140">**Note** You can uninstall the MED-V Workspace Packager at any time without affecting any deployed MED-V workspaces.</span></span>

     

## <span data-ttu-id="c2b42-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="c2b42-141">Related topics</span></span>


[<span data-ttu-id="c2b42-142">部署 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="c2b42-142">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)

 

 





