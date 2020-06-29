---
title: 配置安装先决条件
description: 配置安装先决条件
author: dansimp
ms.assetid: ff9cf28a-3eac-4b6c-8ce9-bfc202f57947
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6cd9379804c45a2025064a6eecf363c010980369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802164"
---
# <span data-ttu-id="b465a-103">配置安装先决条件</span><span class="sxs-lookup"><span data-stu-id="b465a-103">Configure Installation Prerequisites</span></span>


<span data-ttu-id="b465a-104">以下说明是安装和使用 Microsoft 企业桌面虚拟化（MED-V）2.0 的先决条件：</span><span class="sxs-lookup"><span data-stu-id="b465a-104">The following instructions are prerequisites for installing and using Microsoft Enterprise Desktop Virtualization (MED-V) 2.0:</span></span>

[<span data-ttu-id="b465a-105">Windows 虚拟电脑</span><span class="sxs-lookup"><span data-stu-id="b465a-105">Windows Virtual PC</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7)

[<span data-ttu-id="b465a-106">Windows 虚拟电脑更新</span><span class="sxs-lookup"><span data-stu-id="b465a-106">Windows Virtual PC Update</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update)

[<span data-ttu-id="b465a-107">防病毒/备份软件配置</span><span class="sxs-lookup"><span data-stu-id="b465a-107">Antivirus/Backup Software Configuration</span></span>](#bkmk-antivirusbackupsoftwareconfiguration)

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7"></a><span data-ttu-id="b465a-108">如何安装和配置 Windows 虚拟 PC</span><span class="sxs-lookup"><span data-stu-id="b465a-108">How to Install and Configure Windows Virtual PC</span></span>


<span data-ttu-id="b465a-109">**重要提示** 如果主机上已存在虚拟 PC for Windows 的一个版本，则必须在安装 Windows 虚拟 PC 之前将其卸载。</span><span class="sxs-lookup"><span data-stu-id="b465a-109">**Important** If a version of Virtual PC for Windows already exists on the host computer, you must uninstall it before you install Windows Virtual PC.</span></span>

 

**<span data-ttu-id="b465a-110">安装 Windows 虚拟电脑</span><span class="sxs-lookup"><span data-stu-id="b465a-110">To install Windows Virtual PC</span></span>**

1.  <span data-ttu-id="b465a-111">从 Microsoft 下载中心下载[Windows 虚拟电脑](https://go.microsoft.com/fwlink/?LinkId=195918)（ https://go.microsoft.com/fwlink/?LinkId=195918) 。</span><span class="sxs-lookup"><span data-stu-id="b465a-111">Download [Windows Virtual PC](https://go.microsoft.com/fwlink/?LinkId=195918) from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195918).</span></span>

2.  <span data-ttu-id="b465a-112">在主机计算机上运行安装文件，然后按照向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="b465a-112">Run the installation file on the host computer, and follow the steps in the wizard.</span></span>

<span data-ttu-id="b465a-113">**重要提示** Windows 虚拟 PC 包含集成组件程序包，该程序包提供改进虚拟环境和物理计算机之间的交互的功能。</span><span class="sxs-lookup"><span data-stu-id="b465a-113">**Important** Windows Virtual PC includes the Integration Components package, which provides features that improve the interaction between the virtual environment and the physical computer.</span></span> <span data-ttu-id="b465a-114">例如，它允许你在主机和来宾计算机之间移动鼠标。</span><span class="sxs-lookup"><span data-stu-id="b465a-114">For example, it lets your mouse move between the host and the guest computers.</span></span> <span data-ttu-id="b465a-115">MED-V 需要安装集成组件程序包。</span><span class="sxs-lookup"><span data-stu-id="b465a-115">MED-V requires the installation of the Integration Components package.</span></span>

 

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update"></a><span data-ttu-id="b465a-116">如何安装和配置 Windows 虚拟 PC 更新</span><span class="sxs-lookup"><span data-stu-id="b465a-116">How to Install and Configure the Windows Virtual PC Update</span></span>


<span data-ttu-id="b465a-117">与文章 KB977206 相关联的 Microsoft 更新为没有硬件辅助虚拟化（HAV）技术的计算机启用 Windows XP 模式。</span><span class="sxs-lookup"><span data-stu-id="b465a-117">The Microsoft update associated with article KB977206 enables Windows XP Mode for computers without hardware-assisted virtualization (HAV) technology.</span></span> <span data-ttu-id="b465a-118">我们建议安装此更新，因为如果来宾操作系统中的集成组件程序包与主机上安装的 Windows Virtual 电脑版本不匹配，某些集成功能可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="b465a-118">We recommended that you install this update because some integration features might not work correctly if the Integration Components package in the guest operating system do not match the version of Windows Virtual PC that is installed on the host computer.</span></span>

<span data-ttu-id="b465a-119">**重要提示** 在运行 Windows 7 Service Pack 1 的主机上安装 MED-V 时，无需安装此更新。</span><span class="sxs-lookup"><span data-stu-id="b465a-119">**Important** You do not have to install this update when you are installing MED-V on host computers that are running Windows 7 with Service Pack 1.</span></span>

 

<span data-ttu-id="b465a-120">**提示** 除了此处列出的更新，建议你查看所有可用的 Windows 虚拟电脑更新，并针对你的环境应用相应的或必需的更新。</span><span class="sxs-lookup"><span data-stu-id="b465a-120">**Tip** In addition to the update listed here, we recommend that you review all available Windows Virtual PC updates and apply those updates that are appropriate or necessary for your environment.</span></span>

 

**<span data-ttu-id="b465a-121">安装 Windows 虚拟 PC 更新</span><span class="sxs-lookup"><span data-stu-id="b465a-121">To install the Windows Virtual PC Update</span></span>**

1.  <span data-ttu-id="b465a-122">从 Microsoft 下载中心下载所需的 Windows 虚拟 PC 更新。</span><span class="sxs-lookup"><span data-stu-id="b465a-122">Download the required Windows Virtual PC update from the Microsoft Download Center.</span></span>

    <span data-ttu-id="b465a-123">[32 位更新](https://go.microsoft.com/fwlink/?LinkId=195919)（ https://go.microsoft.com/fwlink/?LinkId=195919) 。</span><span class="sxs-lookup"><span data-stu-id="b465a-123">[32-bit Update](https://go.microsoft.com/fwlink/?LinkId=195919) (https://go.microsoft.com/fwlink/?LinkId=195919).</span></span>

    <span data-ttu-id="b465a-124">[64 位更新](https://go.microsoft.com/fwlink/?LinkId=195920)（ https://go.microsoft.com/fwlink/?LinkId=195920) 。</span><span class="sxs-lookup"><span data-stu-id="b465a-124">[64-bit Update](https://go.microsoft.com/fwlink/?LinkId=195920) (https://go.microsoft.com/fwlink/?LinkId=195920).</span></span>

2.  <span data-ttu-id="b465a-125">在提升模式下在主机计算机上运行安装文件，然后按照向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="b465a-125">Run the installation file on the host computer in elevated mode, and follow the steps in the wizard.</span></span>

    <span data-ttu-id="b465a-126">有关适用于 Windows 虚拟 PC 的修补程序包的详细信息，请参阅[文章 977206](https://go.microsoft.com/fwlink/?LinkId=195921) （ https://go.microsoft.com/fwlink/?LinkId=195921) 。</span><span class="sxs-lookup"><span data-stu-id="b465a-126">For more information about the hotfix package for Windows Virtual PC, see [article 977206](https://go.microsoft.com/fwlink/?LinkId=195921) (https://go.microsoft.com/fwlink/?LinkId=195921).</span></span>

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a><span data-ttu-id="b465a-127">如何配置防病毒/备份软件</span><span class="sxs-lookup"><span data-stu-id="b465a-127">How to Configure Antivirus/Backup Software</span></span>


<span data-ttu-id="b465a-128">为了防止防病毒活动影响虚拟桌面的性能，我们建议你可以从在主机计算机上运行的任何防病毒软件或备份进程中排除以下虚拟机文件类型：</span><span class="sxs-lookup"><span data-stu-id="b465a-128">To prevent antivirus activity from affecting the performance of the virtual desktop, we recommend, where you can, to exclude the following virtual machine file types from any antivirus or backup process that is running on the host computer:</span></span>

-   <span data-ttu-id="b465a-129">\*.VMC</span><span class="sxs-lookup"><span data-stu-id="b465a-129">\*.VMC</span></span>

-   <span data-ttu-id="b465a-130">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="b465a-130">\*.VUD</span></span>

-   <span data-ttu-id="b465a-131">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="b465a-131">\*.VSV</span></span>

-   <span data-ttu-id="b465a-132">\*..VHD</span><span class="sxs-lookup"><span data-stu-id="b465a-132">\*.VHD</span></span>

## <span data-ttu-id="b465a-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="b465a-133">Related topics</span></span>


[<span data-ttu-id="b465a-134">配置环境先决条件</span><span class="sxs-lookup"><span data-stu-id="b465a-134">Configure Environment Prerequisites</span></span>](configure-environment-prerequisites.md)

[<span data-ttu-id="b465a-135">高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="b465a-135">High-Level Architecture</span></span>](high-level-architecturemedv2.md)

[<span data-ttu-id="b465a-136">MED-V 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="b465a-136">MED-V 2.0 Supported Configurations</span></span>](med-v-20-supported-configurations.md)

 

 





