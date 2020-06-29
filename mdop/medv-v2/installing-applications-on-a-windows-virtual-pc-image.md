---
title: 在 Windows Virtual PC 映像上安装应用程序
description: 在 Windows Virtual PC 映像上安装应用程序
author: dansimp
ms.assetid: 32651eff-e3c6-4ef4-947d-2beddc695eac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bf73fec0b33b37c2553dfe6f923917aa926b8e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804047"
---
# <span data-ttu-id="8f50e-103">在 Windows Virtual PC 映像上安装应用程序</span><span class="sxs-lookup"><span data-stu-id="8f50e-103">Installing Applications on a Windows Virtual PC Image</span></span>


<span data-ttu-id="8f50e-104">创建用于 Microsoft 企业桌面虚拟化（MED-V）2.0 的 Windows 虚拟电脑映像后，你可以在运行 MED-V （如电子软件分发（ESD）系统和防病毒软件）的情况下安装其他有用的组件。</span><span class="sxs-lookup"><span data-stu-id="8f50e-104">After you have created a Windows Virtual PC image for use with Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you can install other components that are helpful when running MED-V, such as an electronic software distribution (ESD) system and antivirus software.</span></span>

<span data-ttu-id="8f50e-105">以下部分提供的信息可帮助你在 MED-V 映像上安装软件。</span><span class="sxs-lookup"><span data-stu-id="8f50e-105">The following section provides information to help you install software on the MED-V image.</span></span>

<span data-ttu-id="8f50e-106">**小心** 若要在部署后轻松使用 MED-V 工作区管理，我们建议你将在 MED-V 映像上安装的组件数限制为所需的组件或在使用 MED-V 时有用的组件。</span><span class="sxs-lookup"><span data-stu-id="8f50e-106">**Caution** For ease of MED-V workspace management after deployment, we recommend that you limit the number of components that you install on the MED-V image to those components that are required or that are helpful when using MED-V.</span></span> <span data-ttu-id="8f50e-107">例如，虽然它们不是运行 MED-V 所必需的，但你可以安装 ESD 系统，以便稍后将应用程序安装到 MED-V 工作区和防病毒软件中，以便在映像上进行安全保护。</span><span class="sxs-lookup"><span data-stu-id="8f50e-107">For example, although they are not required to run MED-V, you can install an ESD system to use later for installing applications to a MED-V workspace and antivirus software for security on the image.</span></span>

 

**<span data-ttu-id="8f50e-108">在 MED-V 映像上安装软件</span><span class="sxs-lookup"><span data-stu-id="8f50e-108">Installing Software on a MED-V Image</span></span>**

1.  <span data-ttu-id="8f50e-109">如果当前未在运行，请打开你的 MED-V 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="8f50e-109">If it is not currently running, open your MED-V virtual machine.</span></span>

    1.  <span data-ttu-id="8f50e-110">单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc** "，然后单击 " **windows 虚拟 pc**"。</span><span class="sxs-lookup"><span data-stu-id="8f50e-110">Click **Start**, click **All Programs**, click **Windows Virtual PC** and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="8f50e-111">双击 "MED-V 虚拟机"。</span><span class="sxs-lookup"><span data-stu-id="8f50e-111">Double-click your MED-V virtual machine.</span></span>

2.  <span data-ttu-id="8f50e-112">从虚拟机操作系统内，找到要安装的软件的安装文件。</span><span class="sxs-lookup"><span data-stu-id="8f50e-112">From inside the virtual machine operating system, locate the installation files for the software that you want to install.</span></span>

3.  <span data-ttu-id="8f50e-113">按照软件供应商提供的安装说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8f50e-113">Follow the installation instructions that are provided by the software vendor.</span></span>

    <span data-ttu-id="8f50e-114">**注意** 安装完成后，你可能需要关闭并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="8f50e-114">**Note** After installation is complete, you might have to close and then restart the virtual machine.</span></span>

     

<span data-ttu-id="8f50e-115">对于要在 MED-V 映像上安装的任何软件或应用程序，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="8f50e-115">Repeat these steps for any software or application that you want to install on the MED-V image.</span></span> <span data-ttu-id="8f50e-116">我们建议你限制在映像上预安装的应用程序数。</span><span class="sxs-lookup"><span data-stu-id="8f50e-116">We recommend that you limit the number of applications that you preinstall on the image.</span></span> <span data-ttu-id="8f50e-117">在映像上安装应用程序和其他软件的建议过程是立即预安装 ESD 系统，稍后再使用它将软件部署到映像。</span><span class="sxs-lookup"><span data-stu-id="8f50e-117">The recommended process for installing applications and other software on the image is to preinstall an ESD system now and to use it later to deploy software to the image.</span></span> <span data-ttu-id="8f50e-118">或者，也可以使用组策略或 App-v 在 MED-V 工作区中添加或删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f50e-118">Alternately, you can also use Group Policy or App-V to add or remove applications on a MED-V workspace.</span></span> <span data-ttu-id="8f50e-119">有关详细信息，请参阅[管理部署到 Med-v 工作区的应用程序](managing-applications-deployed-to-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="8f50e-119">For more information, see [Managing Applications Deployed to MED-V Workspaces](managing-applications-deployed-to-med-v-workspaces.md).</span></span>

<span data-ttu-id="8f50e-120">有关如何在虚拟映像上安装软件的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8f50e-120">For more information about how to install software on a virtual image, see the following articles:</span></span>

-   <span data-ttu-id="8f50e-121">[发布和使用虚拟应用程序](https://go.microsoft.com/fwlink/?LinkId=195926)（ https://go.microsoft.com/fwlink/?LinkId=195926) 。</span><span class="sxs-lookup"><span data-stu-id="8f50e-121">[Publish and Use Virtual Applications](https://go.microsoft.com/fwlink/?LinkId=195926) (https://go.microsoft.com/fwlink/?LinkId=195926).</span></span>

-   <span data-ttu-id="8f50e-122">[Windows 虚拟电脑帮助](https://go.microsoft.com/fwlink/?LinkId=182378)（ https://go.microsoft.com/fwlink/?LinkId=182378) 。</span><span class="sxs-lookup"><span data-stu-id="8f50e-122">[Windows Virtual PC Help](https://go.microsoft.com/fwlink/?LinkId=182378) (https://go.microsoft.com/fwlink/?LinkId=182378).</span></span>

<span data-ttu-id="8f50e-123">在你安装了 MED-V 映像上所需的所有软件后，你的映像已准备好进行打包。</span><span class="sxs-lookup"><span data-stu-id="8f50e-123">After you have installed all of the software that you want on the MED-V image, your image is ready to be packaged.</span></span>

## <span data-ttu-id="8f50e-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="8f50e-124">Related topics</span></span>


[<span data-ttu-id="8f50e-125">为 MED-V 配置 Windows Virtual PC 映像</span><span class="sxs-lookup"><span data-stu-id="8f50e-125">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="8f50e-126">准备 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="8f50e-126">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)

 

 





