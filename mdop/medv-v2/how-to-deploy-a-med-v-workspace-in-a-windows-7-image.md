---
title: 如何在 Windows 7 映像中部署 MED-V 工作区
description: 如何在 Windows 7 映像中部署 MED-V 工作区
author: dansimp
ms.assetid: a83aba4e-8681-4906-9872-f431c0bb15f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49dd796d6f6af425b9000b595a0d828c3cb0035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804137"
---
# <span data-ttu-id="c392c-103">如何在 Windows 7 映像中部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="c392c-103">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>


<span data-ttu-id="c392c-104">你可以将所有 MED-V 组件安装到你在整个企业中分发的 Windows 7 映像中，就像使用 Windows 7 的任何全新安装一样。</span><span class="sxs-lookup"><span data-stu-id="c392c-104">You can install all the MED-V components into a Windows 7 image that you distribute throughout your enterprise just as you would any new installation of Windows 7.</span></span> <span data-ttu-id="c392c-105">最终用户通过单击您配置为启动 MED-V 的 "**开始**" 菜单快捷方式来完成 med-v 工作区的安装。</span><span class="sxs-lookup"><span data-stu-id="c392c-105">The end user then finishes the installation of the MED-V workspace by clicking a **Start** menu shortcut that you configure to start MED-V.</span></span> <span data-ttu-id="c392c-106">首次启动设置，最终用户按照说明完成配置。</span><span class="sxs-lookup"><span data-stu-id="c392c-106">First time setup starts and the end user follows the instructions to complete the configuration.</span></span>

<span data-ttu-id="c392c-107">以下部分提供了可帮助你使用 Windows 7 映像在整个企业中部署 MED-V 工作区的信息和说明。</span><span class="sxs-lookup"><span data-stu-id="c392c-107">The following section provides information and instructions to help you deploy the MED-V workspace throughout your enterprise by using a Windows 7 image.</span></span>

**<span data-ttu-id="c392c-108">在 Windows 7 映像中部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="c392c-108">To deploy a MED-V workspace in a Windows 7 image</span></span>**

1.  <span data-ttu-id="c392c-109">创建 Windows 7 的标准映像。</span><span class="sxs-lookup"><span data-stu-id="c392c-109">Create a standard image of Windows 7.</span></span> <span data-ttu-id="c392c-110">有关详细信息，请参阅[构建 Windows 7 的标准映像：分步指南](https://go.microsoft.com/fwlink/?LinkId=204843)（ https://go.microsoft.com/fwlink/?LinkId=204843) 。</span><span class="sxs-lookup"><span data-stu-id="c392c-110">For more information, see [Building a Standard Image of Windows 7: Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=204843) (https://go.microsoft.com/fwlink/?LinkId=204843).</span></span>

2.  <span data-ttu-id="c392c-111">在 Windows 7 映像中，安装 Windows 虚拟 PC 和 Windows 虚拟电脑更新。</span><span class="sxs-lookup"><span data-stu-id="c392c-111">In the Windows 7 image, install Windows Virtual PC and the Windows Virtual PC updates.</span></span> <span data-ttu-id="c392c-112">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="c392c-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

3.  <span data-ttu-id="c392c-113">使用 MED-V \ _HostAgent \ _Setup 安装文件安装 MED-V 主机代理。</span><span class="sxs-lookup"><span data-stu-id="c392c-113">Install the MED-V Host Agent by using the MED-V\_HostAgent\_Setup installation file.</span></span> <span data-ttu-id="c392c-114">有关详细信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="c392c-114">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

    <span data-ttu-id="c392c-115">**警告** 在安装 MED-V 主机代理之前，必须关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。</span><span class="sxs-lookup"><span data-stu-id="c392c-115">**Warning** Internet Explorer must be closed before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="c392c-116">您也可以通过在分发期间指定计算机重启来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c392c-116">You can also do this by specifying a computer restart during a distribution.</span></span>

     

4.  <span data-ttu-id="c392c-117">将 MED-V 工作区程序包文件复制到 Windows 7 映像。</span><span class="sxs-lookup"><span data-stu-id="c392c-117">Copy the MED-V workspace package files to the Windows 7 image.</span></span> <span data-ttu-id="c392c-118">MED-V 工作区程序包文件是 MED-V 工作区安装程序、medv 文件和使用**Med-v 工作区包装**程序创建的 setup.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="c392c-118">The MED-V workspace package files are the MED-V workspace installer, .medv file, and setup.exe file that you created by using the **MED-V Workspace Packager**.</span></span>

    <span data-ttu-id="c392c-119">**重要提示** Medv 和 setup.exe 文件必须与 MED-V 工作区安装程序位于同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c392c-119">**Important** The .medv and setup.exe file must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="c392c-120">然后，通过运行 setup.exe 安装 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="c392c-120">Then, install the MED-V workspace by running setup.exe.</span></span>

     

5.  <span data-ttu-id="c392c-121">在 "**开始**" 菜单上配置快捷方式以打开 med-v 工作区程序包安装。</span><span class="sxs-lookup"><span data-stu-id="c392c-121">Configure a shortcut on the **Start** menu to open the MED-V workspace package installation.</span></span>

    <span data-ttu-id="c392c-122">创建 setup.exe 文件的 "**开始**" 菜单快捷方式，最终用户可根据需要启动 med-v 安装。</span><span class="sxs-lookup"><span data-stu-id="c392c-122">Create a **Start** menu shortcut to the setup.exe file that lets the end user start a MED-V installation as required.</span></span>

6.  <span data-ttu-id="c392c-123">通过使用贵公司的标准映像部署过程，将 Windows 7 映像分发到企业中需要 MED-V 的计算机。</span><span class="sxs-lookup"><span data-stu-id="c392c-123">By using your company’s standard image deployment process, distribute the Windows 7 image to computers in your enterprise that require MED-V.</span></span>

<span data-ttu-id="c392c-124">当最终用户必须访问在 MED-V 工作区中发布的应用程序时，他们可以单击 "**开始**" 菜单快捷方式来安装 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="c392c-124">When the end user has to access an application published in the MED-V workspace, they can click the **Start** menu shortcut to install the MED-V workspace.</span></span> <span data-ttu-id="c392c-125">这将在首次设置时自动启动，并完成 MED-V 的配置。</span><span class="sxs-lookup"><span data-stu-id="c392c-125">This automatically starts first time setup and completes the configuration of MED-V.</span></span> <span data-ttu-id="c392c-126">第一次设置完成后，最终用户可以访问 "**开始**" 菜单上的 med-v 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c392c-126">After first time setup is complete, the end user can access the MED-V applications on the **Start** menu.</span></span>

## <span data-ttu-id="c392c-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="c392c-127">Related topics</span></span>


[<span data-ttu-id="c392c-128">MED-V 2.0 部署概述</span><span class="sxs-lookup"><span data-stu-id="c392c-128">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="c392c-129">如何通过电子软件分发系统部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="c392c-129">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

 

 





