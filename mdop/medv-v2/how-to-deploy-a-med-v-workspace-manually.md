---
title: 如何手动部署 MED-V 工作区
description: 如何手动部署 MED-V 工作区
author: dansimp
ms.assetid: 94bfb209-2230-49b6-bb40-9c6ab088dbf4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f13d06e2232681f87df7a71b9a3ef3269b4f9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804136"
---
# <span data-ttu-id="22be1-103">如何手动部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="22be1-103">How to Deploy a MED-V Workspace Manually</span></span>


<span data-ttu-id="22be1-104">在某些情况下，你可能希望手动部署你的 MED-V 工作区，例如，如果你的公司不使用电子软件分发系统来部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="22be1-104">In some instances, you might want to deploy your MED-V workspace manually, for example, if your company does not use an electronic software distribution system to deploy applications.</span></span>

<span data-ttu-id="22be1-105">本部分提供了有关如何手动部署 MED-V 工作区的说明。</span><span class="sxs-lookup"><span data-stu-id="22be1-105">This section provides instruction about how to manually deploy a MED-V workspace.</span></span>

**<span data-ttu-id="22be1-106">手动部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="22be1-106">To deploy a MED-V workspace manually</span></span>**

1.  <span data-ttu-id="22be1-107">将所有必备应用程序和 MED-V 工作区程序包文件复制到共享驱动器或 DVD。</span><span class="sxs-lookup"><span data-stu-id="22be1-107">Copy all prerequisite applications and the MED-V workspace package files to a shared drive or to a DVD.</span></span> <span data-ttu-id="22be1-108">下面列出了所需的应用程序和文件。</span><span class="sxs-lookup"><span data-stu-id="22be1-108">The following is a list of the required applications and files.</span></span>

    -   <span data-ttu-id="22be1-109">**Windows 虚拟 PC**。</span><span class="sxs-lookup"><span data-stu-id="22be1-109">**Windows Virtual PC**.</span></span> <span data-ttu-id="22be1-110">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="22be1-110">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="22be1-111">**Windows 虚拟电脑添加和更新**。</span><span class="sxs-lookup"><span data-stu-id="22be1-111">**Windows Virtual PC Additions and Updates**.</span></span> <span data-ttu-id="22be1-112">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="22be1-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="22be1-113">**Med-v Host Agent 安装文件**-安装主机代理（med-v \ _HostAgent \ _Setup 安装文件）。</span><span class="sxs-lookup"><span data-stu-id="22be1-113">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span>

        **<span data-ttu-id="22be1-114">警告</span><span class="sxs-lookup"><span data-stu-id="22be1-114">Warning</span></span>**  
        <span data-ttu-id="22be1-115">在安装 MED-V 主机代理之前关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。</span><span class="sxs-lookup"><span data-stu-id="22be1-115">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="22be1-116">您也可以通过在分发期间指定计算机重启来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="22be1-116">You can also do this by specifying a computer restart during a distribution.</span></span>



~~~
-   **MED-V Workspace Installer, VHD, and Setup Executable** – created with the **MED-V Workspace Packager**. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    **Important**  
    The compressed VHD file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.
~~~



2. <span data-ttu-id="22be1-117">按列出的顺序安装以下。</span><span class="sxs-lookup"><span data-stu-id="22be1-117">Install the following in the order listed.</span></span> <span data-ttu-id="22be1-118">最终用户可以手动执行此任务，也可以创建脚本来安装以下内容：</span><span class="sxs-lookup"><span data-stu-id="22be1-118">The end user can perform this task manually or you can create a script to install the following:</span></span>

   -   <span data-ttu-id="22be1-119">Windows 虚拟电脑和 Windows 虚拟电脑的添加和更新。</span><span class="sxs-lookup"><span data-stu-id="22be1-119">Windows Virtual PC and the Windows Virtual PC additions and updates.</span></span> <span data-ttu-id="22be1-120">需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="22be1-120">A computer restart is required.</span></span>

   -   <span data-ttu-id="22be1-121">MED-V 主机代理。</span><span class="sxs-lookup"><span data-stu-id="22be1-121">The MED-V Host Agent.</span></span>

       **<span data-ttu-id="22be1-122">注意</span><span class="sxs-lookup"><span data-stu-id="22be1-122">Note</span></span>**  
       <span data-ttu-id="22be1-123">如果它正在运行，则必须重新启动 Internet Explorer，然后才能完成安装 MED-V Host Agent。</span><span class="sxs-lookup"><span data-stu-id="22be1-123">If it is running, Internet Explorer must be restarted before the installation of the MED-V Host Agent can finish.</span></span>



~~~
-   The MED-V workspace package.

    Install the MED-V workspace by running the setup.exe program that is included in the MED-V workspace package files.
~~~

3. <span data-ttu-id="22be1-124">首次安装完成。</span><span class="sxs-lookup"><span data-stu-id="22be1-124">Complete first time setup.</span></span>

   <span data-ttu-id="22be1-125">安装 MED-V 工作区后，您可以选择启动 MED-V。</span><span class="sxs-lookup"><span data-stu-id="22be1-125">After the MED-V workspace is installed, you have the option of starting MED-V.</span></span> <span data-ttu-id="22be1-126">这将启动 MED-V 主机代理。</span><span class="sxs-lookup"><span data-stu-id="22be1-126">This starts the MED-V Host Agent.</span></span> <span data-ttu-id="22be1-127">你可以在此时启动 MED-V，或者稍后启动 MED-V 主机代理以完成首次设置。</span><span class="sxs-lookup"><span data-stu-id="22be1-127">You can either start MED-V at that time, or start the MED-V Host Agent later to complete first time setup.</span></span>

   <span data-ttu-id="22be1-128">若要启动 MED-V 主机代理，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 主机代理**"。</span><span class="sxs-lookup"><span data-stu-id="22be1-128">To start the MED-V Host Agent, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

## <span data-ttu-id="22be1-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="22be1-129">Related topics</span></span>


[<span data-ttu-id="22be1-130">如何通过电子软件分发系统部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="22be1-130">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

[<span data-ttu-id="22be1-131">如何在 Windows 7 映像中部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="22be1-131">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)

[<span data-ttu-id="22be1-132">部署 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="22be1-132">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)









