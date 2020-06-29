---
title: 如何安装 Sequencer （App-v 4.6 SP1）
description: 如何安装 Sequencer （App-v 4.6 SP1）
author: dansimp
ms.assetid: fe8eb876-28fb-46ae-b592-da055107e639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 611564e861d65dcd357c58732fb60dab21c05abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801351"
---
# <span data-ttu-id="78294-103">如何安装 Sequencer （App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="78294-103">How to Install the Sequencer (App-V 4.6 SP1)</span></span>


<span data-ttu-id="78294-104">Microsoft Application Virtualization （App-v） Sequencer 监视和记录应用程序的安装和设置过程，以便可以将应用程序作为虚拟应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="78294-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="78294-105">应在仅安装操作系统的计算机上安装 app-v 排序器。</span><span class="sxs-lookup"><span data-stu-id="78294-105">You should install the App-V Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="78294-106">或者，你可以在虚拟环境（如虚拟计算机）上运行的计算机上安装 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="78294-106">Alternatively, you can install the Sequencer on a computer running in a virtual environment, for example, a virtual computer.</span></span> <span data-ttu-id="78294-107">此方法非常有用，因为它更易于维护可使用最少的额外配置的干净的顺序环境。</span><span class="sxs-lookup"><span data-stu-id="78294-107">This method is useful because it is easier to maintain a clean sequencing environment that you can reuse with minimal additional configuration.</span></span>

<span data-ttu-id="78294-108">你必须在用于对应用程序进行序列化的计算机上拥有管理凭据，并且计算机不得运行任何版本的 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="78294-108">You must have administrative credentials on the computer you are using to sequence the application, and the computer must not be running any version of App-V client.</span></span> <span data-ttu-id="78294-109">使用 App-v Sequencer 创建虚拟应用程序需要多个操作，因此在满足或超过[应用虚拟化 Sequencer 硬件和软件要求](application-virtualization-sequencer-hardware-and-software-requirements.md)的计算机上安装 Sequencer 非常重要。</span><span class="sxs-lookup"><span data-stu-id="78294-109">Creating a virtual application by using the App-V Sequencer requires multiple operations, so it is important that you install the Sequencer on a computer that meets or exceeds the [Application Virtualization Sequencer Hardware and Software Requirements](application-virtualization-sequencer-hardware-and-software-requirements.md).</span></span>

**<span data-ttu-id="78294-110">注意</span><span class="sxs-lookup"><span data-stu-id="78294-110">Note</span></span>**  
<span data-ttu-id="78294-111">在安全模式下运行 app-v sequencer 不受支持。</span><span class="sxs-lookup"><span data-stu-id="78294-111">Running the App-V sequencer in Safe Mode is not supported.</span></span>



**<span data-ttu-id="78294-112">安装 Microsoft Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="78294-112">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="78294-113">将 Microsoft Application Virtualization Sequencer 安装文件复制到要在其上安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="78294-113">Copy the Microsoft Application Virtualization Sequencer installation files to the computer on which you want to install it.</span></span>

2.  <span data-ttu-id="78294-114">若要启动 Microsoft Application Virtualization Sequencer 安装向导，请双击 " **Setup.exe**"。</span><span class="sxs-lookup"><span data-stu-id="78294-114">To start the Microsoft Application Virtualization Sequencer installation wizard, double-click **Setup.exe**.</span></span> <span data-ttu-id="78294-115">如果在安装之前未检测到**Microsoft Visual c + + SP1 可再发行程序包（x86）** ，请单击 "**安装**" 以安装所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="78294-115">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, click **Install** to install the required prerequisite.</span></span>

3.  <span data-ttu-id="78294-116">若要继续安装，请在 "**欢迎**" 页面上单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="78294-116">To continue the installation, on the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="78294-117">在 "**许可协议**" 页面上，要接受许可协议的条款，请单击 **"我接受许可协议中的条款**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="78294-117">On the **License Agreement** page, to accept the terms of the license agreement, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

5.  <span data-ttu-id="78294-118">在 "**目标文件夹**" 页面上，要接受默认安装文件夹，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="78294-118">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="78294-119">若要指定其他目标文件夹，请单击 "**更改**"，然后指定将用于安装的安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="78294-119">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="78294-120">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78294-120">Click **Next**.</span></span>

6.  <span data-ttu-id="78294-121">在 "**虚拟驱动器**" 页面上，要将应用程序虚拟化默认驱动器**Q:\\** （默认）配置为运行所有序列化应用程序的驱动器，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="78294-121">On the **Virtual Drive** page, to configure the Application Virtualization default drive **Q:\\** (default) as the drive that all sequenced applications will run from, click **Next**.</span></span> <span data-ttu-id="78294-122">如果要指定不同的驱动器号，请使用列表并选择要使用的驱动器号，方法是选择相应的驱动器号，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="78294-122">If you want to specify a different drive letter, use the list and select the drive letter that you want to use by selecting the appropriate drive letter, and then click **Next**.</span></span>

    **<span data-ttu-id="78294-123">重要提示</span><span class="sxs-lookup"><span data-stu-id="78294-123">Important</span></span>**  
    <span data-ttu-id="78294-124">通过此步骤指定的 Application Virtualization 驱动器号是虚拟应用程序将从目标计算机上运行的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="78294-124">The Application Virtualization drive letter specified with this step is the drive letter that virtual applications will be run from on target computers.</span></span> <span data-ttu-id="78294-125">指定的驱动器号必须可用，并且当前未在运行 App-v client 的计算机上使用。</span><span class="sxs-lookup"><span data-stu-id="78294-125">The drive letter specified must be available, and not currently in use on the computers running the App-V client.</span></span> <span data-ttu-id="78294-126">如果指定的驱动器已在使用，则虚拟应用程序将在目标计算机上失败。</span><span class="sxs-lookup"><span data-stu-id="78294-126">If the specified drive is already in use, the virtual application fails on the target computer.</span></span>



7.  <span data-ttu-id="78294-127">在 "已**准备好安装程序**" 页面上，若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="78294-127">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

8.  <span data-ttu-id="78294-128">在 " **InstallShield 向导已完成**" 页面上，若要关闭安装向导并打开 app-v 排序器，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="78294-128">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the App-V Sequencer, click **Finish**.</span></span> <span data-ttu-id="78294-129">若要在不打开 Sequencer 的情况下关闭安装向导，请清除 "**启动程序**"，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="78294-129">To close the installation wizard without opening the Sequencer, clear **Launch the program**, and then click **Finish**.</span></span>

    **<span data-ttu-id="78294-130">注意</span><span class="sxs-lookup"><span data-stu-id="78294-130">Note</span></span>**  
    <span data-ttu-id="78294-131">如果在运行虚拟环境的计算机（例如虚拟机）上安装了 app-v Sequencer，现在必须拍摄快照。</span><span class="sxs-lookup"><span data-stu-id="78294-131">If you installed the App-V Sequencer on a computer running a virtual environment, for example a virtual machine, you must now take a snapshot.</span></span> <span data-ttu-id="78294-132">对应用程序进行排序后，你可以还原到此映像，以便对下一个应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="78294-132">After you sequence an application, you can revert to this image, so you can sequence the next application.</span></span>



~~~
When you uninstall the Sequencer, the following registry keys are not removed from the computer that the Sequencer was installed on. Additionally, you must restart the computer after you have uninstalled the Sequencer so that all associated drivers can be stopped and the operation can be completed.

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey**
~~~

## <span data-ttu-id="78294-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="78294-133">Related topics</span></span>


[<span data-ttu-id="78294-134">配置 Application Virtualization Sequencer (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="78294-134">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)









