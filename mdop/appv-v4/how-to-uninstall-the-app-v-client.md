---
title: 如何卸载 App-V Client
description: 如何卸载 App-V Client
author: dansimp
ms.assetid: 07591270-9651-4bb5-a5b3-e0fc009bd9e2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: acb3f53b42027ff2c1b84fd2ab2bdde3c52f96de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801051"
---
# <span data-ttu-id="25d7c-103">如何卸载 App-V Client</span><span class="sxs-lookup"><span data-stu-id="25d7c-103">How to Uninstall the App-V Client</span></span>


<span data-ttu-id="25d7c-104">使用以下过程从计算机中卸载应用程序虚拟化客户端。</span><span class="sxs-lookup"><span data-stu-id="25d7c-104">Use the following procedure to uninstall the Application Virtualization Client from the computer.</span></span>

**<span data-ttu-id="25d7c-105">卸载应用程序虚拟化桌面客户端</span><span class="sxs-lookup"><span data-stu-id="25d7c-105">To uninstall the Application Virtualization Desktop Client</span></span>**

1.  <span data-ttu-id="25d7c-106">在 "控制面板" 中，双击 "**添加或删除程序**" （或者在 Windows Vista 中，单击 "**程序和功能**"，然后双击 " **Microsoft Application Virtualization 桌面客户端**"。</span><span class="sxs-lookup"><span data-stu-id="25d7c-106">In Control Panel, double-click **Add or Remove Programs** (or in Windows Vista, **Programs and Features**), and then double-click **Microsoft Application Virtualization Desktop Client**.</span></span>

2.  <span data-ttu-id="25d7c-107">在出现的对话框中，单击 **"是"** 以继续卸载过程。</span><span class="sxs-lookup"><span data-stu-id="25d7c-107">In the dialog box that appears, click **Yes** to continue with the uninstall process.</span></span>

    <span data-ttu-id="25d7c-108">**重要提示** 无法取消或中断卸载过程。</span><span class="sxs-lookup"><span data-stu-id="25d7c-108">**Important** The uninstall process cannot be canceled or interrupted.</span></span>

     

3.  <span data-ttu-id="25d7c-109">如果出现一条消息，指出必须关闭 Microsoft Application Virtualization 客户端任务栏应用程序才能继续操作，请右键单击通知区域中的 app-v 图标，然后选择 "**退出**" 以关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="25d7c-109">When a message stating that the Microsoft Application Virtualization Client Tray application must be closed before continuing appears, right-click the App-V icon in the notification area and select **Exit** to close the application.</span></span> <span data-ttu-id="25d7c-110">然后单击 "**重试**" 继续卸载过程。</span><span class="sxs-lookup"><span data-stu-id="25d7c-110">Then click **Retry** to continue with the uninstall process.</span></span>

    <span data-ttu-id="25d7c-111">**重要提示** 你可能会看到一条消息，指出正在使用一个或多个虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="25d7c-111">**Important** You might see a message stating that one or more virtual applications are in use.</span></span> <span data-ttu-id="25d7c-112">在继续之前，请关闭所有打开的应用程序并保存数据。</span><span class="sxs-lookup"><span data-stu-id="25d7c-112">Close any open applications and save your data before you continue.</span></span> <span data-ttu-id="25d7c-113">然后单击 **"确定"** 以继续卸载过程。</span><span class="sxs-lookup"><span data-stu-id="25d7c-113">Then click **OK** to continue with the uninstall process.</span></span>

     

4.  <span data-ttu-id="25d7c-114">进度栏显示剩余时间。</span><span class="sxs-lookup"><span data-stu-id="25d7c-114">A progress bar shows the time remaining.</span></span> <span data-ttu-id="25d7c-115">完成此步骤后，必须重新启动计算机，才能停止所有关联的驱动程序以完成卸载过程。</span><span class="sxs-lookup"><span data-stu-id="25d7c-115">When this step finishes, you must restart the computer so that all associated drivers can be stopped to complete the uninstall process.</span></span>

    <span data-ttu-id="25d7c-116">**注意** 卸载过程完成后，以下注册表项仍保留：</span><span class="sxs-lookup"><span data-stu-id="25d7c-116">**Note** The following registry keys remain after the uninstall process is complete:</span></span>

    -   <span data-ttu-id="25d7c-117">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid</span><span class="sxs-lookup"><span data-stu-id="25d7c-117">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid</span></span>

    -   <span data-ttu-id="25d7c-118">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4。5</span><span class="sxs-lookup"><span data-stu-id="25d7c-118">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5</span></span>

    -   <span data-ttu-id="25d7c-119">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard "客户端" = dword：00000000</span><span class="sxs-lookup"><span data-stu-id="25d7c-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard"Client"=dword:00000000</span></span>

    -   <span data-ttu-id="25d7c-120">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey</span><span class="sxs-lookup"><span data-stu-id="25d7c-120">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey</span></span>

     

## <span data-ttu-id="25d7c-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="25d7c-121">Related topics</span></span>


[<span data-ttu-id="25d7c-122">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="25d7c-122">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="25d7c-123">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="25d7c-123">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="25d7c-124">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="25d7c-124">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

 

 





