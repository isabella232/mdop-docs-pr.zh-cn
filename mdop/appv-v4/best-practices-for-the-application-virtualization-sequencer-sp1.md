---
title: 适用于 Application Virtualization Sequencer 的最佳做法
description: 适用于 Application Virtualization Sequencer 的最佳做法
author: dansimp
ms.assetid: 95e5e216-864f-41a1-90d4-b8d7e1eb42a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859514fb34185a339c7f2c2734f331e5a99d050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803080"
---
# <span data-ttu-id="d5972-103">适用于 Application Virtualization Sequencer 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d5972-103">Best Practices for the Application Virtualization Sequencer</span></span>


<span data-ttu-id="d5972-104">本主题提供运行 Microsoft Application Virtualization （app-v） Sequencer 的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="d5972-104">This topic provides best practices for running the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="d5972-105">在你的环境中规划和使用 Sequencer 时，请查看并考虑以下建议。</span><span class="sxs-lookup"><span data-stu-id="d5972-105">Review and consider the following recommendations when planning and using the Sequencer in your environment.</span></span>

## <span data-ttu-id="d5972-106">计算机配置最佳做法排序</span><span class="sxs-lookup"><span data-stu-id="d5972-106">Sequencing Computer Configuration Best Practices</span></span>


<span data-ttu-id="d5972-107">配置运行 App-v Sequencer 的计算机时，应考虑以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="d5972-107">The following best practices should be considered when configuring the computer running the App-V Sequencer:</span></span>

-   **<span data-ttu-id="d5972-108">在具有类似配置且运行的操作系统比目标计算机较早版本的计算机上的顺序。</span><span class="sxs-lookup"><span data-stu-id="d5972-108">Sequence on a computer that has a similar configuration and that is running an earlier version of the operating system than the target computers.</span></span>**

    <span data-ttu-id="d5972-109">确保运行 Sequencer 的计算机运行的是早期版本的操作系统，而不是目标计算机。</span><span class="sxs-lookup"><span data-stu-id="d5972-109">Ensure that the computer that is running the Sequencer is running an earlier version of the operating system than the target computers.</span></span> <span data-ttu-id="d5972-110">这包括服务包和更新版本。</span><span class="sxs-lookup"><span data-stu-id="d5972-110">This includes the service pack and update versions.</span></span> <span data-ttu-id="d5972-111">例如，如果目标计算机运行的是 WindowsVista 和 WindowsXP，则应在运行 WindowsXP 的计算机上序列化应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5972-111">For example, if the target computers are running WindowsVista and WindowsXP, you should sequence applications on a computer that is running WindowsXP.</span></span> <span data-ttu-id="d5972-112">在一个操作系统上进行排序并不保证在不同操作系统上运行虚拟化应用程序的功能，具体取决于特定应用程序和操作系统。</span><span class="sxs-lookup"><span data-stu-id="d5972-112">The ability to sequence on one operating system and run the virtualized application on a different operating system is not guaranteed, and depends on the particular application and operating system.</span></span> <span data-ttu-id="d5972-113">如果遇到问题，可能会要求你在与应用 V 客户端运行的操作系统环境相同的操作系统环境上进行序列化。</span><span class="sxs-lookup"><span data-stu-id="d5972-113">If you encounter issues, you may be required to sequence on the same operating system environment as the one on which the App-V client is running.</span></span>

-   **<span data-ttu-id="d5972-114">配置运行具有多个分区的 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="d5972-114">Configure the computer running the Sequencer with multiple partitions.</span></span>**

    <span data-ttu-id="d5972-115">应将运行 Sequencer 的计算机配置为至少两个主分区。</span><span class="sxs-lookup"><span data-stu-id="d5972-115">You should configure the computer running the Sequencer with at least two primary partitions.</span></span> <span data-ttu-id="d5972-116">第一个分区（**C：**）应包含操作系统，并且应使用 NTFS 文件系统设置其格式。</span><span class="sxs-lookup"><span data-stu-id="d5972-116">The first partition (**C:**) should contain the operating system, and it should be formatted using the NTFS file system.</span></span> <span data-ttu-id="d5972-117">第二个分区（**Q：**）用作虚拟应用程序安装的目标路径，还应使用 NTFS 文件系统进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="d5972-117">The second partition (**Q:**) is used as the destination path for the virtual application installation and should also be formatted using the NTFS file system.</span></span>

-   **<span data-ttu-id="d5972-118">配置具有足够的可用磁盘空间的 temp 目录。</span><span class="sxs-lookup"><span data-stu-id="d5972-118">Configure the temp directory with enough free disk space.</span></span>**

    <span data-ttu-id="d5972-119">排序器使用 **% TMP%** 或 **% TEMP%** 目录和**暂存**目录在排序期间存储临时文件。</span><span class="sxs-lookup"><span data-stu-id="d5972-119">The Sequencer uses the **%TMP%** or **%TEMP%** directory and the **Scratch** directory to store temporary files during sequencing.</span></span> <span data-ttu-id="d5972-120">你应该在运行 Sequencer 的计算机上配置这些目录，其可用磁盘空间相当于估计的应用程序安装要求。</span><span class="sxs-lookup"><span data-stu-id="d5972-120">You should configure these directories on the computer running the Sequencer with free disk space equivalent to the estimated application installation requirements.</span></span> <span data-ttu-id="d5972-121">你可以通过打开 Sequencer 控制台并选择 "**工具**"、"**选项**"，然后选择 "**路径**" 选项卡来验证**暂存**目录的位置。在排序期间，配置临时目录和**暂存**目录在不同的硬驱分区上可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="d5972-121">You can verify the location of the **Scratch** directory by opening the Sequencer console and selecting **Tools**, **Options**, and then selecting the **Paths** tab. Configuring the temp directories and the **Scratch** directory on different hard drive partitions can improve performance during sequencing.</span></span>

-   **<span data-ttu-id="d5972-122">使用 Microsoft VirtualPC 序列应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5972-122">Sequence applications by using Microsoft VirtualPC.</span></span>**

    <span data-ttu-id="d5972-123">你将多个应用程序序列数超过一次。</span><span class="sxs-lookup"><span data-stu-id="d5972-123">You will sequence most applications more than once.</span></span> <span data-ttu-id="d5972-124">为了帮助实现此操作，你应该考虑在虚拟环境中运行的计算机上的排序。</span><span class="sxs-lookup"><span data-stu-id="d5972-124">To help facilitate this, you should consider sequencing on a computer running in a virtual environment.</span></span> <span data-ttu-id="d5972-125">这将允许你在运行 Sequencer 的计算机上对应用程序进行排序，并使用最少的重新配置还原到干净状态。</span><span class="sxs-lookup"><span data-stu-id="d5972-125">This will allow you to sequence an application and revert to a clean state, with minimal reconfiguration, on the computer that is running the Sequencer.</span></span>

    <span data-ttu-id="d5972-126">如果你在你的环境中运行 Microsoft Hyper-v，则运行它的 Hyper-v 虚拟计算机将运行 app-v 排序器：</span><span class="sxs-lookup"><span data-stu-id="d5972-126">If you are running Microsoft Hyper-V in your environment the App-V sequencer will run when the Hyper-V virtual computer it is running on is:</span></span>

    -   <span data-ttu-id="d5972-127">暂停和恢复。</span><span class="sxs-lookup"><span data-stu-id="d5972-127">paused and resumed.</span></span>

    -   <span data-ttu-id="d5972-128">已保存和还原其状态。</span><span class="sxs-lookup"><span data-stu-id="d5972-128">has its state saved and restored.</span></span>

    -   <span data-ttu-id="d5972-129">另存为快照并被还原。</span><span class="sxs-lookup"><span data-stu-id="d5972-129">saved as a snapshot and is restored.</span></span>

    -   <span data-ttu-id="d5972-130">作为实时迁移的一部分迁移到其他硬件。</span><span class="sxs-lookup"><span data-stu-id="d5972-130">migrated to different hardware as part of a live migration.</span></span>

-   **<span data-ttu-id="d5972-131">在对新应用程序进行排序之前，请关闭其他正在运行的程序。</span><span class="sxs-lookup"><span data-stu-id="d5972-131">Before you sequence a new application, shut down other running programs.</span></span>**

    <span data-ttu-id="d5972-132">通常在顺序计算机上运行的进程和计划任务可能会减慢排序过程，并导致在排序期间收集不相关的数据。</span><span class="sxs-lookup"><span data-stu-id="d5972-132">Processes and scheduled tasks that normally run on the sequencing computer can slow down the sequencing process and cause irrelevant data to be gathered during sequencing.</span></span> <span data-ttu-id="d5972-133">开始先后顺序之前，应关闭所有不需要的应用程序和程序。</span><span class="sxs-lookup"><span data-stu-id="d5972-133">All unnecessary applications and programs should be shut down before you begin sequencing.</span></span>

-   **<span data-ttu-id="d5972-134">在运行终端服务的计算机上的顺序</span><span class="sxs-lookup"><span data-stu-id="d5972-134">Sequence on a computer that is running Terminal Services</span></span>**

    <span data-ttu-id="d5972-135">在安装 sequencer 之前，不应在运行终端服务的计算机上配置安装模式。</span><span class="sxs-lookup"><span data-stu-id="d5972-135">You should not configure the install mode on a computer that is running Terminal Services before you install the sequencer.</span></span>

## <span data-ttu-id="d5972-136">排序最佳做法</span><span class="sxs-lookup"><span data-stu-id="d5972-136">Sequencing Best Practices</span></span>


<span data-ttu-id="d5972-137">在对新应用程序进行排序时，应考虑以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="d5972-137">The following best practices should be considered when sequencing a new application:</span></span>

-   

    <span data-ttu-id="d5972-138">**注意** 如果您运行的是 app-v 4.6 SP1，则无需按8.3 命名约定的目录进行排序。</span><span class="sxs-lookup"><span data-stu-id="d5972-138">**Note** If you are running App-V 4.6 SP1 you do not need to sequence to a directory that follows the 8.3 naming convention.</span></span>

     

-   **<span data-ttu-id="d5972-139">序列到遵循8.3 命名约定的唯一目录。</span><span class="sxs-lookup"><span data-stu-id="d5972-139">Sequence to a unique directory that follows the 8.3 naming convention.</span></span>**

    <span data-ttu-id="d5972-140">应将所有应用程序序列化到遵守8.3 命名约定的目录中。</span><span class="sxs-lookup"><span data-stu-id="d5972-140">You should sequence all applications to a directory that follows the 8.3 naming convention.</span></span> <span data-ttu-id="d5972-141">指定的目录名不能超过八个字符，后跟三个字符的文件名扩展名，例如**Q:\\MYAPP。ABC**。</span><span class="sxs-lookup"><span data-stu-id="d5972-141">The specified directory name cannot contain more than eight characters, followed by a three-character file name extension—for example, **Q:\\MYAPP.ABC**.</span></span>

-   **<span data-ttu-id="d5972-142">序列到驱动器根目录的目标文件夹，而不是子目录。</span><span class="sxs-lookup"><span data-stu-id="d5972-142">Sequence to a destination folder on the root of the drive, not to a subdirectory.</span></span>**

    <span data-ttu-id="d5972-143">如果应用程序套件有多个部分，请将每个应用程序安装到主目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="d5972-143">If the application suite has multiple parts, install each application to a subdirectory of the main directory.</span></span> <span data-ttu-id="d5972-144">例如，如果程序包中包含一个应用程序和一个客户端，请将**Q:\\AppSuite**用作主目录并将主应用程序序列化到**Q:\\AppSuite\\Main**，并将客户端序列化到**Q:\\AppSuite\\Client**。</span><span class="sxs-lookup"><span data-stu-id="d5972-144">For example, if a package contains an application along with a client, use **Q:\\AppSuite** as the main directory and sequence the main application to **Q:\\AppSuite\\Main**, and sequence the client to **Q:\\AppSuite\\Client**.</span></span>

-   **<span data-ttu-id="d5972-145">在安装阶段配置和测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5972-145">Configure and test the application during the installation phase.</span></span>**

    <span data-ttu-id="d5972-146">完成应用程序的安装通常需要执行不属于应用程序安装过程的多个手动步骤。</span><span class="sxs-lookup"><span data-stu-id="d5972-146">Completing the installation of an application often requires performing several manual steps that are not part of the application installation process.</span></span> <span data-ttu-id="d5972-147">这些步骤可能涉及配置到数据库的连接或复制更新的文件。</span><span class="sxs-lookup"><span data-stu-id="d5972-147">These steps can involve configuring a connection to a database or copying updated files.</span></span> <span data-ttu-id="d5972-148">应在安装阶段执行这些配置，然后运行该应用程序以确保其正常工作。</span><span class="sxs-lookup"><span data-stu-id="d5972-148">You should perform these configurations during the installation phase and then run the application to make sure it works.</span></span>

-   **<span data-ttu-id="d5972-149">如果需要，请多次运行该应用程序，直至程序稳定。</span><span class="sxs-lookup"><span data-stu-id="d5972-149">Run the application, multiple times if necessary, until the program is stable.</span></span>**

    <span data-ttu-id="d5972-150">在安装期间，你应该多次运行该应用程序，以确保所有关联的注册和对话框配置均已完成。</span><span class="sxs-lookup"><span data-stu-id="d5972-150">You should run the application multiple times during the installation to ensure all associated registration and dialog box configurations have been completed.</span></span> <span data-ttu-id="d5972-151">在安装期间多次打开应用程序将确保仅将相关的应用程序功能加载到**主功能块**中。</span><span class="sxs-lookup"><span data-stu-id="d5972-151">Opening the application multiple times during installation will ensure that only the relevant application features are loaded into the **primary feature block**.</span></span>

-   **<span data-ttu-id="d5972-152">禁用与应用程序相关联的所有自动更新功能。</span><span class="sxs-lookup"><span data-stu-id="d5972-152">Disable all automatic update features associated with the application.</span></span>**

    <span data-ttu-id="d5972-153">某些应用程序能够在安装期间自动检查最新的更新。</span><span class="sxs-lookup"><span data-stu-id="d5972-153">Some applications have the ability to check for the latest updates automatically during installation.</span></span> <span data-ttu-id="d5972-154">若要协助虚拟应用程序包的版本控制，应在排序期间禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="d5972-154">To assist with versioning of virtual application packages, you should disable this feature during sequencing.</span></span> <span data-ttu-id="d5972-155">如果存在必需的更新，则应该对安装了相关更新的新虚拟应用程序包进行排序。</span><span class="sxs-lookup"><span data-stu-id="d5972-155">If there are required updates, you should sequence a new virtual application package with the associated updates installed.</span></span>

## <span data-ttu-id="d5972-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="d5972-156">Related topics</span></span>


[<span data-ttu-id="d5972-157">规划 Application Virtualization System 部署</span><span class="sxs-lookup"><span data-stu-id="d5972-157">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





