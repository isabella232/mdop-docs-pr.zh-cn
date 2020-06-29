---
title: 如何安装 Sequencer
description: 如何安装 Sequencer
author: dansimp
ms.assetid: 2cd16427-a0ba-4870-82d1-3e3c79e1959b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 75a0f987fcc76d1ed92631085a4364ae6e06c9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801348"
---
# <span data-ttu-id="d8d1e-103">如何安装 Sequencer</span><span class="sxs-lookup"><span data-stu-id="d8d1e-103">How to Install the Sequencer</span></span>


<span data-ttu-id="d8d1e-104">Microsoft Application Virtualization （App-v） Sequencer 监视和记录应用程序的安装和设置过程，以便可以将应用程序作为虚拟应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="d8d1e-105">应在仅安装操作系统的计算机上安装 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-105">You should install the Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="d8d1e-106">或者，你可以在运行虚拟环境的计算机（例如 Microsoft 虚拟 PC）上安装 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-106">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="d8d1e-107">此方法非常有用，因为它更易于维护干净的顺序环境，可以使用最少的额外配置来重用。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-107">This method is useful because it is easier to maintain a clean sequencing environment that can be reused with minimal additional configuration.</span></span>

<span data-ttu-id="d8d1e-108">必须在用于对应用程序进行排序的计算机上具有管理权限，并且计算机必须连接到网络。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-108">You must have administrative rights on the computer you are using to sequence the application and the computer must be connected to the network.</span></span> <span data-ttu-id="d8d1e-109">计算机不得运行任何版本的应用程序虚拟化（app-v）客户端。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-109">The computer must not be running any version of the Application Virtualization (App-V) client.</span></span> <span data-ttu-id="d8d1e-110">使用 Sequencer 创建虚拟应用程序占用大量资源，因此在满足或超过推荐要求的计算机上安装 Sequencer 非常重要。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-110">Creating a virtual application using the Sequencer is very resource intensive, so it is important that you install the Sequencer on a computer that meets or exceeds the recommended requirements.</span></span> <span data-ttu-id="d8d1e-111">有关系统要求的详细信息，请参阅[Sequencer 硬件和软件要求](sequencer-hardware-and-software-requirements.md)。。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-111">For more information about the system requirements, see [Sequencer Hardware and Software Requirements](sequencer-hardware-and-software-requirements.md)..</span></span>

**<span data-ttu-id="d8d1e-112">安装 Microsoft Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="d8d1e-112">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="d8d1e-113">将 Microsoft Application Virtualization Sequencer 安装文件复制到要安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-113">Copy the Microsoft Application Virtualization Sequencer installation files to the computer that you want to install it on.</span></span>

2.  <span data-ttu-id="d8d1e-114">若要启动 Microsoft Application Virtualization Sequencer 安装向导，请选择 " **setup.exe**"。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-114">To start the Microsoft Application Virtualization Sequencer installation wizard, select **setup.exe**.</span></span> <span data-ttu-id="d8d1e-115">如果在安装之前未检测到**Microsoft Visual c + + SP1 可再发行程序包（x86）** ， **setup.exe**将安装该程序包。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-115">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, **setup.exe** will install it.</span></span>

3.  <span data-ttu-id="d8d1e-116">在 "**欢迎**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-116">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="d8d1e-117">在 "**许可协议**" 页面上，要接受许可协议的条款，请选择 **"我接受许可协议中的条款"**。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-117">On the **License Agreement** page, to accept the terms of the license agreement, select **I accept the terms in the license agreement**.</span></span> <span data-ttu-id="d8d1e-118">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-118">Click **Next**.</span></span>

5.  <span data-ttu-id="d8d1e-119">在 "**目标文件夹**" 页面上，要接受默认安装文件夹，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-119">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="d8d1e-120">若要指定其他目标文件夹，请单击 "**更改**"，然后指定将用于安装的安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-120">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="d8d1e-121">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-121">Click **Next**.</span></span>

6.  <span data-ttu-id="d8d1e-122">在 "已**准备好安装程序**" 页面上，若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-122">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="d8d1e-123">在 " **InstallShield 向导已完成**" 页面上，若要关闭安装向导并打开排序器，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-123">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the Sequencer, click **Finish**.</span></span> <span data-ttu-id="d8d1e-124">若要在不打开 Sequencer 的情况下关闭安装向导，请取消选中 **"启动程序"** ，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="d8d1e-124">To close the installation wizard without opening the Sequencer, deselect **Launch the program** and click **Finish**.</span></span>

## <span data-ttu-id="d8d1e-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="d8d1e-125">Related topics</span></span>


[<span data-ttu-id="d8d1e-126">配置 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="d8d1e-126">Configuring the Application Virtualization Sequencer</span></span>](configuring-the-application-virtualization-sequencer.md)

 

 





