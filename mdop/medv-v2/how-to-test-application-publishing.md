---
title: 如何测试应用程序发布
description: 如何测试应用程序发布
author: dansimp
ms.assetid: 17ba2e12-50a0-4f41-8300-f61f09db9f6c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 8dffb4f79ac89c7d419b27640f4f05364bd69e5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804063"
---
# <span data-ttu-id="29408-103">如何测试应用程序发布</span><span class="sxs-lookup"><span data-stu-id="29408-103">How to Test Application Publishing</span></span>


<span data-ttu-id="29408-104">第一次测试完成后，你可以通过执行以下任务来验证应用程序发布功能是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="29408-104">After your test of first time setup finishes, you can verify that the application publishing functionality is working as expected by performing the following tasks.</span></span>

<a href="" id="bkmk-apppub"></a>**<span data-ttu-id="29408-105">测试应用程序发布</span><span class="sxs-lookup"><span data-stu-id="29408-105">To test application publishing</span></span>**

1.  <span data-ttu-id="29408-106">验证你指定用于发布的应用程序是否可见。</span><span class="sxs-lookup"><span data-stu-id="29408-106">Verify that the applications that you specified for publishing are visible.</span></span>

    <span data-ttu-id="29408-107">单击 "**开始**"，然后单击 "**所有程序**" 并搜索指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="29408-107">Click **Start** and then click **All Programs** and search for the specified applications.</span></span>

    <span data-ttu-id="29408-108">在某些情况下，你可能会在同一应用程序中安装两次，一次在一台主机上，一次在来宾上。</span><span class="sxs-lookup"><span data-stu-id="29408-108">In some cases, you might have the same application installed two times, one time on the host computer and one time on the guest.</span></span> <span data-ttu-id="29408-109">如果在主机 "**开始**" 菜单上将具有相同名称的已发布应用程序发布到同一位置，则它通过将虚拟机名称添加到快捷方式名称来区别于主机应用程序快捷方式。</span><span class="sxs-lookup"><span data-stu-id="29408-109">If a published application that has the same name is published to the same location on the host **Start** menu, it is distinguished from the host application shortcut by adding the virtual machine name to the shortcut name.</span></span> <span data-ttu-id="29408-110">例如，对于名为 "MEDVHost1" 的虚拟机，主机应用程序可能是 "记事本"，而发布的应用程序可能是 "Notepad （MEDVHost1）"。</span><span class="sxs-lookup"><span data-stu-id="29408-110">For example, for a virtual machine named “MEDVHost1”, a host application might be "Notepad" and a published application might be "Notepad (MEDVHost1)".</span></span>

2.  <span data-ttu-id="29408-111">验证应用程序是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="29408-111">Verify that the applications function as intended.</span></span>

    <span data-ttu-id="29408-112">在主机上，启动已发布的应用程序，并验证它们是否在来宾上的 Windows XP SP3 中打开。</span><span class="sxs-lookup"><span data-stu-id="29408-112">On the host computer, start the applications that you published and verify that they open in Windows XP SP3 on the guest.</span></span> <span data-ttu-id="29408-113">应用程序必须显示在主机桌面端的 Windows XP 风格的窗口中。</span><span class="sxs-lookup"><span data-stu-id="29408-113">The application must appear in a Windows XP-style window on the host computer desktop.</span></span>

3.  <span data-ttu-id="29408-114">如果适用，请验证文档重定向是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="29408-114">If applicable, verify that document redirection functions as intended.</span></span>

    <span data-ttu-id="29408-115">如果来宾上已发布的应用程序必须打开主机系统驱动器上的文件夹，请确保它可以打开指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="29408-115">If a published application on the guest has to open a folder on the host system drive, ensure that it can open the specified folder.</span></span>

    <span data-ttu-id="29408-116">**重要提示** 由于 Windows 虚拟 PC 不支持从已共享的文件夹创建共享，因此从共享文件夹（如位于网络上的 "我的文档" 文件夹）打开的任何文档都不会发生重定向。</span><span class="sxs-lookup"><span data-stu-id="29408-116">**Important** Because Windows Virtual PC does not support creating a share from a folder that is already shared, redirection does not occur for any documents that open from a shared folder, such as a My Documents folder that is located on the network.</span></span> <span data-ttu-id="29408-117">有关详细信息，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="29408-117">For more information, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="29408-118">验证已发布的应用程序已安装并正常运行后，你可以测试是否可以从 MED-V 工作区添加或删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="29408-118">After you have verified that published applications are installed and functioning correctly, you can test whether applications can be added or removed from the MED-V workspace.</span></span>

**<span data-ttu-id="29408-119">测试是否可以添加或删除应用程序</span><span class="sxs-lookup"><span data-stu-id="29408-119">To test that an application can be added or removed</span></span>**

1.  <span data-ttu-id="29408-120">从 MED-V 工作区添加或删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="29408-120">Add or remove an application from the MED-V workspace.</span></span>

    <span data-ttu-id="29408-121">有关如何从 MED-V 工作区添加和删除应用程序的信息，请参阅[管理部署到 Med-v 工作区的应用程序](managing-applications-deployed-to-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="29408-121">For information about how to add and remove applications from a MED-V workspace, see [Managing Applications Deployed to MED-V Workspaces](managing-applications-deployed-to-med-v-workspaces.md).</span></span>

2.  <span data-ttu-id="29408-122">如果添加了应用程序，请重复执行以下步骤[来测试应用程序发布](#bkmk-apppub)，以验证新应用程序是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="29408-122">If you added an application, repeat the steps in [To Test Application Publishing](#bkmk-apppub) to verify that the new application functions as intended.</span></span>

3.  <span data-ttu-id="29408-123">如果删除了应用程序，请单击 "**开始**"，然后单击 "**所有程序**"，验证删除的所有应用程序是否不再列出。</span><span class="sxs-lookup"><span data-stu-id="29408-123">If you removed an application, click **Start** and then click **All Programs** and verify that any applications that you removed are no longer listed.</span></span>

<span data-ttu-id="29408-124">**注意** 如果在验证应用程序发布设置时遇到任何问题，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="29408-124">**Note** If you encounter any problems when verifying your application publication settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="29408-125">在完成应用程序发布的测试后，可以测试其他 MED-V 工作区配置，以验证它们是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="29408-125">After you have completed testing application publishing, you can test other MED-V workspace configurations to verify that they function as intended.</span></span>

<span data-ttu-id="29408-126">在完成对 MED-V 工作区程序包的测试并验证它是否按预期运行后，你可以将 MED-V 工作区部署到你的企业。</span><span class="sxs-lookup"><span data-stu-id="29408-126">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="29408-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="29408-127">Related topics</span></span>

[<span data-ttu-id="29408-128">如何测试 URL 重定向</span><span class="sxs-lookup"><span data-stu-id="29408-128">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="29408-129">如何验证首次安装设置</span><span class="sxs-lookup"><span data-stu-id="29408-129">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="29408-130">部署 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="29408-130">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

 

 





