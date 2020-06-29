---
title: 如何验证首次安装设置
description: 如何验证首次安装设置
author: dansimp
ms.assetid: e8a07d4c-5786-4455-ac43-2deac4042efd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859d627ec90fbc26d18019062d5e316f907cec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798192"
---
# <span data-ttu-id="a3444-103">如何验证首次安装设置</span><span class="sxs-lookup"><span data-stu-id="a3444-103">How to Verify First Time Setup Settings</span></span>


<span data-ttu-id="a3444-104">测试首次设置运行或完成后，你可以通过执行以下任务来验证你在 MED-V 工作区中配置的设置。</span><span class="sxs-lookup"><span data-stu-id="a3444-104">While your test of first time setup is running or after it finishes, you can verify the settings that you configured in your MED-V workspace by performing the following tasks.</span></span>

<span data-ttu-id="a3444-105">**注意** 有关如何在部署后监视整个企业中首次设置成功完成的信息，请参阅[监视 Med-v 工作区部署](monitoring-med-v-workspace-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="a3444-105">**Note** For information about how to monitor the successful completion of first time setup throughout your enterprise after deployment, see [Monitoring MED-V Workspace Deployments](monitoring-med-v-workspace-deployments.md).</span></span>

 

**<span data-ttu-id="a3444-106">首次设置时验证设置</span><span class="sxs-lookup"><span data-stu-id="a3444-106">To verify settings during first time setup</span></span>**

1.  <span data-ttu-id="a3444-107">首次运行安装程序时，请验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="a3444-107">While first time setup is running, verify the following:</span></span>

    <span data-ttu-id="a3444-108">如果你指定了**无人参与**模式，请验证是否在首次运行设置时未显示虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a3444-108">If you specified **Unattended** mode, verify that the virtual machine does not appear when first time setup is running.</span></span>

    <span data-ttu-id="a3444-109">如果指定了参与模式，请验证虚拟机是否显示，以及是否显示需要用户输入的所有字段。</span><span class="sxs-lookup"><span data-stu-id="a3444-109">If you specified attended mode, verify that the virtual machine appears and that all fields that require user input are displayed.</span></span>

2.  <span data-ttu-id="a3444-110">你还可以通过在首次设置运行时查看虚拟机来监视第一次完成的设置过程。</span><span class="sxs-lookup"><span data-stu-id="a3444-110">You can also monitor the complete first time setup process by viewing the virtual machine when first time setup is running.</span></span> <span data-ttu-id="a3444-111">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="a3444-111">To do this, follow these steps:</span></span>

    1.  <span data-ttu-id="a3444-112">打开 Windows 虚拟 PC 控制台。</span><span class="sxs-lookup"><span data-stu-id="a3444-112">Open the Windows Virtual PC Console.</span></span>

        <span data-ttu-id="a3444-113">单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc**"，然后单击 " **windows 虚拟 pc**"。</span><span class="sxs-lookup"><span data-stu-id="a3444-113">Click **Start**, click **All Programs**, click **Windows Virtual PC**, and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="a3444-114">如果尚未运行 MED-V，请启动它。</span><span class="sxs-lookup"><span data-stu-id="a3444-114">Start MED-V if it is not already running.</span></span>

        <span data-ttu-id="a3444-115">如果在短时间内尚不存在，则会在虚拟机列表中显示一个虚拟机，其中包含已部署的 MED-V 工作区的名称。</span><span class="sxs-lookup"><span data-stu-id="a3444-115">If not already present, in a short time, a virtual machine with the name of the deployed MED-V workspace appears in the list of virtual machines.</span></span>

    3.  <span data-ttu-id="a3444-116">双击 "MED-V 虚拟机" 将其打开。</span><span class="sxs-lookup"><span data-stu-id="a3444-116">Double-click the MED-V virtual machine to open it.</span></span>

        <span data-ttu-id="a3444-117">你可以在设置 MED-V 虚拟机时看到它，并且你可以对最小化安装过程进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="a3444-117">You can observe the MED-V virtual machine when it is being set up, and you can troubleshoot the Mini-Setup procedure.</span></span> <span data-ttu-id="a3444-118">验证不同屏幕中的信息，例如配置网络设置、计算机域加入信息、来宾代理配置、设置个人设置和关机。</span><span class="sxs-lookup"><span data-stu-id="a3444-118">Verify the information in the different screens as they go by, such as configuring networking settings, computer domain join information, configuring of the Guest Agent, set up of personal settings, and shutdown.</span></span>

    4.  <span data-ttu-id="a3444-119">当首次设置完成时，虚拟机将自动关闭。</span><span class="sxs-lookup"><span data-stu-id="a3444-119">The virtual machine closes automatically when first time setup finishes.</span></span>

        <span data-ttu-id="a3444-120">**注意** 你可以随时关闭虚拟机窗口，并且首次继续安装。</span><span class="sxs-lookup"><span data-stu-id="a3444-120">**Note** You can close the virtual machine window at any time and first time setup continues.</span></span>

         

**<span data-ttu-id="a3444-121">首次设置完成后验证设置</span><span class="sxs-lookup"><span data-stu-id="a3444-121">To verify settings after first time setup finishes</span></span>**

1.  <span data-ttu-id="a3444-122">确保首次安装成功完成。</span><span class="sxs-lookup"><span data-stu-id="a3444-122">Ensure that first time setup finished successfully.</span></span>

2.  <span data-ttu-id="a3444-123">验证 MED-V 工作区是否设置正确。</span><span class="sxs-lookup"><span data-stu-id="a3444-123">Verify that the MED-V workspace is set up correctly.</span></span>

    1.  <span data-ttu-id="a3444-124">打开 Windows 虚拟 PC 控制台。</span><span class="sxs-lookup"><span data-stu-id="a3444-124">Open the Windows Virtual PC Console.</span></span>

        <span data-ttu-id="a3444-125">单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc**"，然后单击 " **windows 虚拟 pc**"。</span><span class="sxs-lookup"><span data-stu-id="a3444-125">Click **Start**, click **All Programs**, click **Windows Virtual PC**, and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="a3444-126">双击已安装的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="a3444-126">Double-click your installed MED-V workspace.</span></span>

        <span data-ttu-id="a3444-127">如果 MED-V 工作区已经在运行虚拟应用程序，系统可能会提示你关闭该应用程序，然后才能打开虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a3444-127">If the MED-V workspace is already running a virtual application, you might be prompted to close the application before you can open the virtual machine.</span></span>

    3.  <span data-ttu-id="a3444-128">在 MED-V 工作区中，右键单击 **"我的电脑**"，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="a3444-128">In the MED-V workspace, right-click **My Computer**, and then click **Properties**.</span></span>

    4.  <span data-ttu-id="a3444-129">验证 MED-V 工作区是否加入了正确的域。</span><span class="sxs-lookup"><span data-stu-id="a3444-129">Verify that the MED-V workspace joined the correct domain.</span></span> <span data-ttu-id="a3444-130">如果适用于你的组织，请通过指定两个不同的域来测试域加入，以验证来宾域是否被主机域重写。</span><span class="sxs-lookup"><span data-stu-id="a3444-130">If applicable to your organization, test domain joining by specifying two different domains to verify that the guest domain is overridden by the host domain.</span></span>

    5.  <span data-ttu-id="a3444-131">验证 MED-V 工作区是否加入了您指定的域组织单位。</span><span class="sxs-lookup"><span data-stu-id="a3444-131">Verify that the MED-V workspace joined the domain organizational unit that you specified.</span></span>

    6.  <span data-ttu-id="a3444-132">如果你指定了计算机名称掩码，请验证新计算机名称是否与指定的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="a3444-132">If you specified the computer name mask, verify that the new computer name matches what was specified.</span></span>

3.  <span data-ttu-id="a3444-133">验证指定的区域设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="a3444-133">Verify that the locale settings that you specified are correct.</span></span>

    1.  <span data-ttu-id="a3444-134">在 MED-V 工作区中，单击 "**开始**"，然后单击 "**控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="a3444-134">In the MED-V workspace, click **Start** and then click **Control Panel**.</span></span>

    2.  <span data-ttu-id="a3444-135">验证指定的配置设置，例如 "**日期和时间**" 以及 "**区域和语言**"。</span><span class="sxs-lookup"><span data-stu-id="a3444-135">Verify your specified configuration settings, for example, **Date and Time** and **Regional and Language**.</span></span>

<span data-ttu-id="a3444-136">**注意** 如果您在验证首次设置设置时遇到任何问题，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="a3444-136">**Note** If you encounter any problems when verifying your first time setup settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

 

<span data-ttu-id="a3444-137">验证你的首次设置是否正确后，你可以测试其他 MED-V 工作区配置，以验证它们是否按预期运行，例如应用程序发布和 URL 重定向。</span><span class="sxs-lookup"><span data-stu-id="a3444-137">After you have verified that your first time setup settings are correct, you can test other MED-V workspace configurations to verify that they function as intended, such as application publishing and URL redirection.</span></span>

<span data-ttu-id="a3444-138">完成 MED-V 工作区程序包的所有测试并验证它是否按预期运行后，你可以将 MED-V 工作区部署到你的企业。</span><span class="sxs-lookup"><span data-stu-id="a3444-138">After you have completed all testing of your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="a3444-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="a3444-139">Related topics</span></span>


[<span data-ttu-id="a3444-140">如何测试应用程序发布</span><span class="sxs-lookup"><span data-stu-id="a3444-140">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="a3444-141">如何测试 URL 重定向</span><span class="sxs-lookup"><span data-stu-id="a3444-141">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="a3444-142">部署 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="a3444-142">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

[<span data-ttu-id="a3444-143">管理 MED-V 工作区设置</span><span class="sxs-lookup"><span data-stu-id="a3444-143">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





