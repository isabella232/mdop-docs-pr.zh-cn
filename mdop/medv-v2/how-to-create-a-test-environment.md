---
title: 如何创建测试环境
description: 如何创建测试环境
author: dansimp
ms.assetid: a0db2299-16f3-4516-8769-7d55ca4a1e98
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ee2ab131f6003b56cce7a60ffea1cd00b067fae3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804138"
---
# <span data-ttu-id="e7086-103">如何创建测试环境</span><span class="sxs-lookup"><span data-stu-id="e7086-103">How to Create a Test Environment</span></span>


<span data-ttu-id="e7086-104">下面是一些可帮助你创建测试环境的步骤和说明，可用于在整个企业中部署你的 MED-V 工作区程序包之前进行本地测试。</span><span class="sxs-lookup"><span data-stu-id="e7086-104">The following are some steps and instructions to help you create a test environment that you can use to test your MED-V workspace package locally before deploying it throughout your enterprise.</span></span> <span data-ttu-id="e7086-105">本部分提供了有关如何手动或通过使用电子软件分发系统创建测试环境的指南。</span><span class="sxs-lookup"><span data-stu-id="e7086-105">This section provides guidance about how to create a test environment, either manually or by using an electronic software distribution system.</span></span>

**<span data-ttu-id="e7086-106">使用 ESD 创建测试环境</span><span class="sxs-lookup"><span data-stu-id="e7086-106">To create a test environment by using an ESD</span></span>**

1.  <span data-ttu-id="e7086-107">使用贵公司在整个企业中部署软件的方法将以下必要组件部署到测试计算机。</span><span class="sxs-lookup"><span data-stu-id="e7086-107">Use your company’s method of deploying software throughout the enterprise to deploy the following necessary components to a test computer.</span></span> <span data-ttu-id="e7086-108">按以下顺序安装：</span><span class="sxs-lookup"><span data-stu-id="e7086-108">Install them in the following order:</span></span>

    -   <span data-ttu-id="e7086-109">**Windows 虚拟电脑**–如果尚未安装。</span><span class="sxs-lookup"><span data-stu-id="e7086-109">**Windows Virtual PC** – if not already installed.</span></span> <span data-ttu-id="e7086-110">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="e7086-110">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="e7086-111">**Windows 虚拟 PC 的添加和更新**-如果尚未安装。</span><span class="sxs-lookup"><span data-stu-id="e7086-111">**Windows Virtual PC Additions and Updates**– if not already installed.</span></span> <span data-ttu-id="e7086-112">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="e7086-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="e7086-113">**Med-v Host Agent 安装文件**-安装主机代理（med-v \ _HostAgent \ _Setup 安装文件）。</span><span class="sxs-lookup"><span data-stu-id="e7086-113">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="e7086-114">有关详细信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="e7086-114">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

    -   <span data-ttu-id="e7086-115">**Med-v 工作区安装程序、VHD 和安装可执行文件**-在**Med-v 工作区包装**程序中创建。</span><span class="sxs-lookup"><span data-stu-id="e7086-115">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="e7086-116">有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="e7086-116">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        <span data-ttu-id="e7086-117">**重要提示** VHD 和设置可执行程序必须与 MED-V 工作区安装程序位于同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e7086-117">**Important** The VHD and Setup executable program must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="e7086-118">然后，通过运行 setup.exe 安装 MED-V 工作区安装程序。</span><span class="sxs-lookup"><span data-stu-id="e7086-118">Then, install the MED-V workspace installer by running setup.exe.</span></span>

         

2.  <span data-ttu-id="e7086-119">在测试计算机上安装所有组件后，运行 MED-V 主机代理首次启动设置。</span><span class="sxs-lookup"><span data-stu-id="e7086-119">After all of the components are installed on the test computer, run the MED-V Host Agent to start first time setup.</span></span>

    <span data-ttu-id="e7086-120">单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。</span><span class="sxs-lookup"><span data-stu-id="e7086-120">Click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

    <span data-ttu-id="e7086-121">**注意** 如果您无法在测试计算机上物理运行 MED-V 主机代理，则首次重新启动计算机时，安装程序将自动启动。</span><span class="sxs-lookup"><span data-stu-id="e7086-121">**Note** If you cannot physically run the MED-V Host Agent on the test computer, first time setup starts automatically the next time that the computer restarts.</span></span>

     

<span data-ttu-id="e7086-122">首次启动时，可能需要十分钟或更长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="e7086-122">First time setup starts and can take ten minutes or more to finish.</span></span>

<span data-ttu-id="e7086-123">有关在首次运行设置时测试配置设置的信息，请参阅[如何首次验证](how-to-verify-first-time-setup-settings.md)设置。</span><span class="sxs-lookup"><span data-stu-id="e7086-123">For information about testing your configuration settings when first time setup is running, see [How to Verify First Time Setup Settings](how-to-verify-first-time-setup-settings.md).</span></span>

**<span data-ttu-id="e7086-124">手动创建测试环境</span><span class="sxs-lookup"><span data-stu-id="e7086-124">To create a test environment manually</span></span>**

1.  <span data-ttu-id="e7086-125">在包含 MED-V 先决条件的本地测试环境（如带有添加和更新的 Windows 虚拟 PC）中安装 MED-V 主机代理。</span><span class="sxs-lookup"><span data-stu-id="e7086-125">Install the MED-V Host Agent in a local test environment that includes MED-V prerequisites, such as Windows Virtual PC with additions and updates.</span></span> <span data-ttu-id="e7086-126">有关信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="e7086-126">For information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

2.  <span data-ttu-id="e7086-127">将 MED-V 工作区文件复制到你的测试环境。</span><span class="sxs-lookup"><span data-stu-id="e7086-127">Copy the MED-V workspace files to your test environment.</span></span> <span data-ttu-id="e7086-128">MED-V 工作区文件位于您在**Med-v 工作区包装**程序中指定的目标文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e7086-128">The MED-V workspace files are located in the destination folder that you specified in the **MED-V Workspace Packager**.</span></span>

    <span data-ttu-id="e7086-129">**重要提示** VHD 和设置可执行程序必须与 MED-V 工作区安装程序位于测试环境的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e7086-129">**Important** The VHD and Setup executable program must be in the same folder on your test environment as the MED-V workspace installer.</span></span>

     

3.  <span data-ttu-id="e7086-130">通过运行 setup.exe 安装 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="e7086-130">Install the MED-V workspace by running setup.exe.</span></span>

4.  <span data-ttu-id="e7086-131">通过运行 MED-V Host Agent 开始首次设置。</span><span class="sxs-lookup"><span data-stu-id="e7086-131">Start first time setup by running the MED-V Host Agent.</span></span>

    <span data-ttu-id="e7086-132">单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。</span><span class="sxs-lookup"><span data-stu-id="e7086-132">Click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

<span data-ttu-id="e7086-133">首次设置启动时，可能需要几分钟才能完成，具体取决于指定 VHD 的大小。</span><span class="sxs-lookup"><span data-stu-id="e7086-133">First time setup starts and might take several minutes to complete, depending on the size of the VHD specified.</span></span>

<span data-ttu-id="e7086-134">现在，你可以为你为 MED-V 工作区指定的配置、应用程序发布和 URL 重定向测试不同的设置。</span><span class="sxs-lookup"><span data-stu-id="e7086-134">You are now ready to test the different settings for configuration, application publishing, and URL redirection that you specified for your MED-V workspace.</span></span>

<span data-ttu-id="e7086-135">**注意** 默认情况下，MED-V 会覆盖来宾中的屏幕锁定策略。</span><span class="sxs-lookup"><span data-stu-id="e7086-135">**Note** By default, MED-V overrides the screen lock policy in the guest.</span></span> <span data-ttu-id="e7086-136">但是，这不会造成安全问题，因为主机仍然采用屏幕锁定策略。</span><span class="sxs-lookup"><span data-stu-id="e7086-136">However, this does not pose a security problem because the host computer still honors the screen lock policy.</span></span>

 

## <span data-ttu-id="e7086-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="e7086-137">Related topics</span></span>


[<span data-ttu-id="e7086-138">如何验证首次安装设置</span><span class="sxs-lookup"><span data-stu-id="e7086-138">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="e7086-139">如何测试应用程序发布</span><span class="sxs-lookup"><span data-stu-id="e7086-139">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="e7086-140">如何测试 URL 重定向</span><span class="sxs-lookup"><span data-stu-id="e7086-140">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

 

 





