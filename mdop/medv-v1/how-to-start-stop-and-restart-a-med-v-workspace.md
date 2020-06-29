---
title: 如何启动、停止和重启 MED-V 工作区
description: 如何启动、停止和重启 MED-V 工作区
author: dansimp
ms.assetid: 54ce139c-8f32-499e-944b-72f123ebfd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2739ace085a4d57d333daf7872e01a7712a7fbd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803825"
---
# <span data-ttu-id="07bde-103">如何启动、停止和重启 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="07bde-103">How to Start, Stop, and Restart a MED-V Workspace</span></span>


**<span data-ttu-id="07bde-104">启动 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="07bde-104">To start a MED-V workspace</span></span>**

1.  <span data-ttu-id="07bde-105">在通知区域中，右键单击 MED-V 图标。</span><span class="sxs-lookup"><span data-stu-id="07bde-105">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="07bde-106">在子菜单上，单击 "**启动工作区**"。</span><span class="sxs-lookup"><span data-stu-id="07bde-106">On the submenu, click **Start Workspace**.</span></span>

    -   <span data-ttu-id="07bde-107">如果计算机上运行有多个 MED-V 工作区，则会显示 "**工作区选择**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="07bde-107">If there are multiple MED-V workspaces running on the computer, the **Workspace Selection** window appears.</span></span>

        1.  <span data-ttu-id="07bde-108">选择 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="07bde-108">Select a MED-V workspace.</span></span>

        2.  <span data-ttu-id="07bde-109">选中 "**启动所选工作区而不询问我**" 复选框，以在下次启动客户端时跳过此窗口，并自动打开所选的 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="07bde-109">Select the **Start the selected Workspace without asking me** check box to skip this window the next time the client is started and to automatically open the selected MED-V workspace.</span></span>

        3.  <span data-ttu-id="07bde-110">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07bde-110">Click **OK**.</span></span>

    <span data-ttu-id="07bde-111">将显示 "**启动工作区身份验证**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="07bde-111">The **Start Workspace Authentication** window appears.</span></span>

    -   <span data-ttu-id="07bde-112">如果计算机上有多个 MED-V 工作区，并且您选择使用指定的 MED-V 工作区，则会出现下图所示的窗口。</span><span class="sxs-lookup"><span data-stu-id="07bde-112">If there are several MED-V workspaces on the computer and you have opted to use a specified MED-V workspace, the window shown in the following figure appears.</span></span>

        ![](images/medv-logon.gif)

    -   <span data-ttu-id="07bde-113">如果计算机上只有一个 MED-V 工作区，则 "启动上次使用的工作区" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="07bde-113">If there is only one MED-V workspace on the computer, the “Start last used Workspace” option is unavailable.</span></span>

3.  <span data-ttu-id="07bde-114">键入您的域用户凭据。</span><span class="sxs-lookup"><span data-stu-id="07bde-114">Type in your domain user credentials.</span></span>

    <span data-ttu-id="07bde-115">**注意** 第一次启动 med-v 工作区时，用户名应采用以下格式： &lt; 域名 &gt; \\ &lt; 用户名 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="07bde-115">**Note** The first time a MED-V workspace is started, the user name should be in the following format: &lt;domain name&gt;\\&lt;user name&gt;.</span></span>

     

4.  <span data-ttu-id="07bde-116">选择 **"保存我的密码"** 以在会话之间保存密码。</span><span class="sxs-lookup"><span data-stu-id="07bde-116">Select **Save my password** to save your password between sessions.</span></span>

    <span data-ttu-id="07bde-117">**注意** 若要启用 "保存密码" 功能，必须在 ClientSettings.xml 文件中将 EnableSavePassword 属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="07bde-117">**Note** To enable the save password feature, the EnableSavePassword attribute must be set to True in the ClientSettings.xml file.</span></span> <span data-ttu-id="07bde-118">可在*Servers\\Configuration Server\\*文件夹中找到该文件。</span><span class="sxs-lookup"><span data-stu-id="07bde-118">The file can be found in the *Servers\\Configuration Server\\* folder.</span></span>

     

5.  <span data-ttu-id="07bde-119">清除 "**启动上次使用的工作区**" 复选框以选择其他 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="07bde-119">Clear the **Start last used workspace** check box to choose a different MED-V workspace.</span></span>

6.  <span data-ttu-id="07bde-120">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07bde-120">Click **OK**.</span></span>

    <span data-ttu-id="07bde-121">将显示多个状态屏幕，具体取决于 MED-V 工作区配置。</span><span class="sxs-lookup"><span data-stu-id="07bde-121">Several status screens appear depending on the MED-V workspace configuration.</span></span>

    <span data-ttu-id="07bde-122">将显示 "**启动工作区**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="07bde-122">The **Starting Workspace** screen appears.</span></span>

**<span data-ttu-id="07bde-123">重新启动 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="07bde-123">To restart a MED-V workspace</span></span>**

1.  <span data-ttu-id="07bde-124">当客户端运行时，在通知区域中，右键单击 MED-V 图标。</span><span class="sxs-lookup"><span data-stu-id="07bde-124">When the client is running, in the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="07bde-125">在子菜单上，单击 "**重新启动工作区**"。</span><span class="sxs-lookup"><span data-stu-id="07bde-125">On the submenu, click **Restart Workspace**.</span></span>

    <span data-ttu-id="07bde-126">将重新启动 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="07bde-126">The MED-V workspace is restarted.</span></span>

    -   <span data-ttu-id="07bde-127">在永久性的 MED-V 工作区中，虚拟机将关闭，然后重新启动。</span><span class="sxs-lookup"><span data-stu-id="07bde-127">In a persistent MED-V workspace, the virtual machine is shut down and then restarted.</span></span>

    -   <span data-ttu-id="07bde-128">在 revertible MED-V 工作区中，虚拟机实际上不会关闭;而是返回到其原始状态。</span><span class="sxs-lookup"><span data-stu-id="07bde-128">In a revertible MED-V workspace, the virtual machine does not actually shut down; instead, it returns to its original state.</span></span>

**<span data-ttu-id="07bde-129">停止 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="07bde-129">To stop a MED-V workspace</span></span>**

1.  <span data-ttu-id="07bde-130">在通知区域中，右键单击 MED-V 图标。</span><span class="sxs-lookup"><span data-stu-id="07bde-130">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="07bde-131">在子菜单上，单击 "**停止工作区**"。</span><span class="sxs-lookup"><span data-stu-id="07bde-131">On the submenu, click **Stop Workspace**.</span></span>

    <span data-ttu-id="07bde-132">MED-V 工作区已停止。</span><span class="sxs-lookup"><span data-stu-id="07bde-132">The MED-V workspace is stopped.</span></span>

## <span data-ttu-id="07bde-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="07bde-133">Related topics</span></span>


[<span data-ttu-id="07bde-134">如何启动和退出 MED-V 客户端</span><span class="sxs-lookup"><span data-stu-id="07bde-134">How to Start and Exit the MED-V Client</span></span>](how-to-start-and-exit-the-med-v-client.md)

 

 





