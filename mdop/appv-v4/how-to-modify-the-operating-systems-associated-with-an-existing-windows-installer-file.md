---
title: 如何修改与现有 Windows Installer 文件关联的操作系统
description: 如何修改与现有 Windows Installer 文件关联的操作系统
author: dansimp
ms.assetid: 0633f7e2-aebf-4e00-be02-35bc59dec420
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63184852f996cbe09b476f456f7c2b509549f4fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801223"
---
# <span data-ttu-id="c3366-103">如何修改与现有 Windows Installer 文件关联的操作系统</span><span class="sxs-lookup"><span data-stu-id="c3366-103">How to Modify the Operating Systems Associated With an Existing Windows Installer File</span></span>


<span data-ttu-id="c3366-104">使用以下过程修改与使用 App-v 排序器创建的现有 Windows Installer （**MSI**）文件相关联的操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="c3366-104">Use the following procedure to modify the operating system versions associated with an existing Windows Installer (**MSI**) file that was created by using the App-V Sequencer.</span></span>

**<span data-ttu-id="c3366-105">修改现有 Windows Installer 文件的操作系统</span><span class="sxs-lookup"><span data-stu-id="c3366-105">To modify the operating systems of an existing Windows Installer file</span></span>**

1.  <span data-ttu-id="c3366-106">在仅安装了操作系统的环境中的计算机上安装 app-v Sequencer。</span><span class="sxs-lookup"><span data-stu-id="c3366-106">Install the App-V Sequencer on a computer in your environment that has only the operating system installed.</span></span> <span data-ttu-id="c3366-107">或者，你可以在运行虚拟环境的计算机（例如 Microsoft 虚拟 PC）上安装 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="c3366-107">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="c3366-108">此方法非常有用，因为它更易于维护可使用最少的额外配置的干净的顺序环境。</span><span class="sxs-lookup"><span data-stu-id="c3366-108">This method is useful because it is easier to maintain a clean sequencing environment that you can reuse with minimal additional configuration.</span></span> <span data-ttu-id="c3366-109">有关安装 app-v Sequencer 的详细信息，请参阅[如何安装 Sequencer](how-to-install-the-sequencer.md)。</span><span class="sxs-lookup"><span data-stu-id="c3366-109">For more information about installing the App-V Sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer.md).</span></span>

2.  <span data-ttu-id="c3366-110">将包含要修改的 Windows Installer 文件的整个虚拟应用程序包复制到运行 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="c3366-110">Copy the entire virtual application package that contains the Windows Installer file you want to modify to the computer running the Sequencer.</span></span>

3.  <span data-ttu-id="c3366-111">若要修改 Windows installer 文件，请打开 Sequencer 控制台，选择 "**程序包**  /  **打开**"，然后浏览到保存与 Windows Installer 文件关联的虚拟应用程序包的位置。</span><span class="sxs-lookup"><span data-stu-id="c3366-111">To modify the Windows Installer file, open the Sequencer console, select **Package** / **Open**, and then browse to the location where the virtual application package associated with the Windows Installer file is saved.</span></span>

4.  <span data-ttu-id="c3366-112">若要添加或删除操作系统，请选择 Sequencer 控制台中的 "**部署**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c3366-112">To add or remove operating systems, select the **Deployment** tab in the Sequencer console.</span></span> <span data-ttu-id="c3366-113">若要指定将与 Windows Installer 文件相关联的其他操作系统，请选择所需操作系统，然后单击指向**所选**操作系统列表控件的箭头。</span><span class="sxs-lookup"><span data-stu-id="c3366-113">To specify additional operating systems that will be associated with the Windows Installer file, select the desired operating system, and then click the arrow that points to the **Selected** operating system list control.</span></span>

    <span data-ttu-id="c3366-114">若要删除操作系统关联，请选择要删除的操作系统，然后单击指向**可用**操作系统列表控件的箭头。</span><span class="sxs-lookup"><span data-stu-id="c3366-114">To remove an operating system association, select the operating system you want to remove, and then click the arrow that points to the **Available** operating system list control.</span></span>

5.  <span data-ttu-id="c3366-115">若要创建将与虚拟应用程序包关联的新 Windows 安装程序，请选择 "**生成 Microsoft Windows installer （MSI）程序包**"。</span><span class="sxs-lookup"><span data-stu-id="c3366-115">To create a new Windows Installer that will be associated with the virtual application package, select **Generate Microsoft Windows Installer (MSI) Package**.</span></span> <span data-ttu-id="c3366-116">或者，你可以选择 "**工具**  /  **创建 MSI**"。</span><span class="sxs-lookup"><span data-stu-id="c3366-116">Alternatively, you can select **Tools** / **Create MSI**.</span></span>

    <span data-ttu-id="c3366-117">**注意** 如果选择 "**工具** / **创建 MSI** " 以创建新的 Windows Installer 文件，则可以跳过此过程的**步骤 6** 。</span><span class="sxs-lookup"><span data-stu-id="c3366-117">**Note** If you select **Tools** / **Create MSI** to create a new Windows Installer file, you can skip **Step 6** of this procedure.</span></span>

     

6.  <span data-ttu-id="c3366-118">若要保存虚拟应用程序包，请选择 "**打包**  /  **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c3366-118">To save the virtual application package, select **Package** / **Save**.</span></span>

## <span data-ttu-id="c3366-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="c3366-119">Related topics</span></span>


[<span data-ttu-id="c3366-120">Application Virtualization Sequencer 的任务</span><span class="sxs-lookup"><span data-stu-id="c3366-120">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





