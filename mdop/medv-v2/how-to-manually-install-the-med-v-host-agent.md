---
title: 如何手动安装 MED-V 主机代理
description: 如何手动安装 MED-V 主机代理
author: dansimp
ms.assetid: 4becc90b-6481-4e1f-a4d3-aec74c8821ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a7fb44b23a390cf394af2331152955afc2d8eba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798160"
---
# <span data-ttu-id="7f8c8-103">如何手动安装 MED-V 主机代理</span><span class="sxs-lookup"><span data-stu-id="7f8c8-103">How to Manually Install the MED-V Host Agent</span></span>


<span data-ttu-id="7f8c8-104">Microsoft 企业桌面虚拟化（MED-V）2.0 解决方案有两个独立但相关的组件： "MED-V 主机代理" 和 "来宾代理"。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-104">There are two separate but related components to the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution: the MED-V Host Agent and Guest Agent.</span></span> <span data-ttu-id="7f8c8-105">主机代理驻留在主机（运行 Windows 7 的用户计算机）上，并提供信道以与 MED-V 来宾（在主机计算机上运行的 MED-V 虚拟机）通信。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-105">The Host Agent resides on the host computer (a user’s computer that is running Windows 7) and provides a channel to communicate with the MED-V guest (the MED-V virtual machine running in the host computer).</span></span> <span data-ttu-id="7f8c8-106">它还提供某些与 MED-V 相关的功能，例如应用程序发布。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-106">It also provides certain MED-V related functionality, such as application publishing.</span></span>

<span data-ttu-id="7f8c8-107">通常情况下，使用贵公司的预配软件的首选方法部署和安装 MED-V 主机代理。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-107">Typically, you deploy and install the MED-V Host Agent by using your company’s preferred method of provisioning software.</span></span> <span data-ttu-id="7f8c8-108">但是，在你的企业内部署 MED-V 之前，你可能希望在本地安装主机代理以进行测试。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-108">However, before deploying MED-V across your enterprise, you might prefer to install the Host Agent locally for testing.</span></span> <span data-ttu-id="7f8c8-109">本部分提供了手动安装 MED-V 主机代理的分步说明。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-109">This section provides step-by-step instructions for manually installing the MED-V Host Agent.</span></span>

<span data-ttu-id="7f8c8-110">**注意** MED-V 来宾代理将在首次设置时自动安装。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-110">**Note** The MED-V Guest Agent is installed automatically during first time setup.</span></span>

 

<span data-ttu-id="7f8c8-111">**重要提示** 在安装 MED-V 主机代理之前关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-111">**Important** Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="7f8c8-112">您也可以通过在分发期间指定计算机重启来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-112">You can also do this by specifying a computer restart during a distribution.</span></span>

 

**<span data-ttu-id="7f8c8-113">安装 MED-V 主机代理</span><span class="sxs-lookup"><span data-stu-id="7f8c8-113">To install the MED-V Host Agent</span></span>**

1.  <span data-ttu-id="7f8c8-114">找到你在软件下载中收到的 MED-V 安装文件。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-114">Locate the MED-V installation files that you received as part of your software download.</span></span>

2.  <span data-ttu-id="7f8c8-115">双击 "MED-V \ _HostAgent \ _Setup 安装文件"。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-115">Double-click the MED-V\_HostAgent\_Setup installation file.</span></span>

    <span data-ttu-id="7f8c8-116">**Microsoft 企业桌面虚拟化（med-v） Host Agent 安装**向导随即打开。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-116">The **Microsoft Enterprise Desktop Virtualization (MED-V) Host Agent Setup** wizard opens.</span></span> <span data-ttu-id="7f8c8-117">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-117">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="7f8c8-118">接受 Microsoft 软件许可条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-118">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="7f8c8-119">选择用于安装 MED-V 主机代理的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-119">Select the destination folder for installing the MED-V Host Agent.</span></span> <span data-ttu-id="7f8c8-120">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-120">Click **Next**.</span></span>

5.  <span data-ttu-id="7f8c8-121">若要开始安装 Host Agent，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-121">To begin the Host Agent installation, click **Install**.</span></span>

6.  <span data-ttu-id="7f8c8-122">安装成功完成后，单击 "**完成**" 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-122">After the installation is completed successfully, click **Finish** to close the wizard.</span></span>

    <span data-ttu-id="7f8c8-123">若要验证主机代理的安装是否成功，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-123">To verify that the installation of the Host Agent was successful, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

<span data-ttu-id="7f8c8-124">**注意** 在安装 MED-V 工作区之前，MED-V 主机代理可以启动并运行，但不提供任何功能。</span><span class="sxs-lookup"><span data-stu-id="7f8c8-124">**Note** Until a MED-V workspace is installed, the MED-V Host Agent can be started and runs, but provides no functionality.</span></span>

 

## <span data-ttu-id="7f8c8-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f8c8-125">Related topics</span></span>


[<span data-ttu-id="7f8c8-126">如何通过电子软件分发系统部署 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="7f8c8-126">How to Deploy the MED-V Components Through an Electronic Software Distribution System</span></span>](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md)

[<span data-ttu-id="7f8c8-127">如何安装 MED-V 工作区包装程序</span><span class="sxs-lookup"><span data-stu-id="7f8c8-127">How to Install the MED-V Workspace Packager</span></span>](how-to-install-the-med-v-workspace-packager.md)

[<span data-ttu-id="7f8c8-128">如何卸载 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="7f8c8-128">How to Uninstall the MED-V Components</span></span>](how-to-uninstall-the-med-v-components.md)

 

 





