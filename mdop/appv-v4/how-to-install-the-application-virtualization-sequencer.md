---
title: 如何安装 Application Virtualization Sequencer
description: 如何安装 Application Virtualization Sequencer
author: dansimp
ms.assetid: 89cdf60d-18b0-4204-aa9f-b402610f8f0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a6fe03f2149504b6c34c70b2b82ce2ba0b55ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801364"
---
# <span data-ttu-id="b5b21-103">如何安装 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="b5b21-103">How to Install the Application Virtualization Sequencer</span></span>


<span data-ttu-id="b5b21-104">Microsoft Application Virtualization Sequencer 监视和记录应用程序的安装和设置过程，以便可以将应用程序作为虚拟应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="b5b21-104">The Microsoft Application Virtualization Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="b5b21-105">应在仅安装操作系统的计算机上安装 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="b5b21-105">You should install the Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="b5b21-106">或者，你可以在运行虚拟环境的计算机（例如 Microsoft 虚拟 PC）上安装 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="b5b21-106">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="b5b21-107">此方法非常有用，因为它更易于维护干净的顺序环境，可以使用最少的额外配置来重用。</span><span class="sxs-lookup"><span data-stu-id="b5b21-107">This method is useful because it is easier to maintain a clean sequencing environment that can be reused with minimal additional configuration.</span></span>

<span data-ttu-id="b5b21-108">你必须在用于对应用程序进行排序的计算机上拥有管理权限，并且计算机不得运行任何版本的应用程序虚拟化（app-v）客户端。</span><span class="sxs-lookup"><span data-stu-id="b5b21-108">You must have administrative rights on the computer you are using to sequence the application and the computer must not be running any version of the Application Virtualization (App-V) client.</span></span> <span data-ttu-id="b5b21-109">使用 Sequencer 创建虚拟应用程序占用大量资源，因此在满足或超过推荐要求的计算机上安装 Sequencer 非常重要。</span><span class="sxs-lookup"><span data-stu-id="b5b21-109">Creating a virtual application by using the Sequencer is very resource intensive, so it is important that you install the Sequencer on a computer that meets or exceeds the recommended requirements.</span></span> <span data-ttu-id="b5b21-110">在安全模式下运行 app-v sequencer 不受支持。</span><span class="sxs-lookup"><span data-stu-id="b5b21-110">Running the App-V sequencer in Safe Mode is not supported.</span></span> <span data-ttu-id="b5b21-111">有关系统要求的详细信息，请参阅[应用程序虚拟化系统要求](application-virtualization-system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5b21-111">For more information about the system requirements, see [Application Virtualization System Requirements](application-virtualization-system-requirements.md).</span></span>

<span data-ttu-id="b5b21-112">**重要提示** 对应用程序进行排序后，必须先在用于序列应用程序的计算机上重新安装操作系统和 Sequencer，然后才能正确地对新应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="b5b21-112">**Important** After you have sequenced an application, before you can properly sequence a new application you must reinstall the operating system and the Sequencer on the computer you are using to sequence applications.</span></span>

 

**<span data-ttu-id="b5b21-113">安装 Microsoft Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="b5b21-113">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="b5b21-114">将 Microsoft Application Virtualization Sequencer 安装文件复制到要安装它的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b5b21-114">Copy the Microsoft Application Virtualization Sequencer installation files to the computer that you want to install it on.</span></span>

2.  <span data-ttu-id="b5b21-115">若要启动 Microsoft Application Virtualization Sequencer 安装向导，请选择 " **setup.exe**"。</span><span class="sxs-lookup"><span data-stu-id="b5b21-115">To start the Microsoft Application Virtualization Sequencer installation wizard, select **setup.exe**.</span></span> <span data-ttu-id="b5b21-116">如果在安装之前未检测到**Microsoft Visual c + + SP1 可再发行程序包（x86）** ， **setup.exe**将安装该程序包。</span><span class="sxs-lookup"><span data-stu-id="b5b21-116">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, **setup.exe** will install it.</span></span>

3.  <span data-ttu-id="b5b21-117">在 "**欢迎**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b5b21-117">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="b5b21-118">在 "**许可协议**" 页面上，要接受许可协议的条款，请选择 **"我接受许可协议中的条款"**。</span><span class="sxs-lookup"><span data-stu-id="b5b21-118">On the **License Agreement** page, to accept the terms of the license agreement, select **I accept the terms in the license agreement**.</span></span> <span data-ttu-id="b5b21-119">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b5b21-119">Click **Next**.</span></span>

5.  <span data-ttu-id="b5b21-120">在 "**目标文件夹**" 页面上，要接受默认安装文件夹，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b5b21-120">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="b5b21-121">若要指定其他目标文件夹，请单击 "**更改**"，然后指定将用于安装的安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5b21-121">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="b5b21-122">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b5b21-122">Click **Next**.</span></span>

6.  <span data-ttu-id="b5b21-123">在 "已**准备好安装程序**" 页面上，若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="b5b21-123">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="b5b21-124">在 " **InstallShield 向导已完成**" 页面上，若要关闭安装向导并打开排序器，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b5b21-124">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the Sequencer, click **Finish**.</span></span> <span data-ttu-id="b5b21-125">若要在不打开 Sequencer 的情况下关闭安装向导，请取消选中 **"启动程序"** ，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b5b21-125">To close the installation wizard without opening the Sequencer, deselect **Launch the program** and click **Finish**.</span></span>

## <span data-ttu-id="b5b21-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="b5b21-126">Related topics</span></span>


[<span data-ttu-id="b5b21-127">如何升级 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="b5b21-127">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

[<span data-ttu-id="b5b21-128">Application Virtualization 部署要求</span><span class="sxs-lookup"><span data-stu-id="b5b21-128">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

 

 





