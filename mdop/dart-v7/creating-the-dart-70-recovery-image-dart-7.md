---
title: 创建 DaRT 7.0 恢复映像
description: 创建 DaRT 7.0 恢复映像
author: dansimp
ms.assetid: ebb2ec58-0349-469d-a23f-3f944fe4c1fa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f19ff144cac61ca7ea5a8498f67caf8a99229d77
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803337"
---
# <span data-ttu-id="4a71d-103">创建 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="4a71d-103">Creating the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="4a71d-104">Microsoft 诊断和恢复工具集（DaRT）7包含在 Windows 中用于创建可启动的国际标准化组织（ISO）映像的**DaRT 恢复映像向导**。</span><span class="sxs-lookup"><span data-stu-id="4a71d-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes the **DaRT Recovery Image Wizard** that is used in Windows to create a bootable International Organization for Standardization (ISO) image.</span></span> <span data-ttu-id="4a71d-105">ISO 图像是表示 CD 的原始内容的文件。</span><span class="sxs-lookup"><span data-stu-id="4a71d-105">An ISO image is a file that represents the raw contents of a CD.</span></span>

## <span data-ttu-id="4a71d-106">使用 DaRT 恢复映像向导创建恢复映像</span><span class="sxs-lookup"><span data-stu-id="4a71d-106">Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>


<span data-ttu-id="4a71d-107">由 DaRT 恢复映像向导创建的 ISO 包含允许你启动到问题计算机的 DaRT 恢复映像，即使它可能不会启动。</span><span class="sxs-lookup"><span data-stu-id="4a71d-107">The ISO created by the DaRT Recovery Image Wizard contains the DaRT recovery image that lets you boot into a problem computer, even if it might otherwise not start.</span></span> <span data-ttu-id="4a71d-108">将计算机启动到 DaRT 后，您可以运行不同的 DaRT 工具来尝试诊断和修复计算机。</span><span class="sxs-lookup"><span data-stu-id="4a71d-108">After you boot the computer into DaRT, you can run the different DaRT tools to try to diagnose and repair the computer.</span></span>

<span data-ttu-id="4a71d-109">你可以将 ISO 写入可写 CD 或 DVD，将其保存到 USB 闪存驱动器，或将其保存为可用于从远程分区或恢复分区启动到 DaRT 的格式。</span><span class="sxs-lookup"><span data-stu-id="4a71d-109">You can write the ISO to a recordable CD or DVD, save it to a USB flash drive, or save it in a format that you can use to boot into DaRT from a remote partition or from a recovery partition.</span></span> <span data-ttu-id="4a71d-110">有关详细信息，请参阅[部署 DaRT 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="4a71d-110">For more information, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="4a71d-111">**注意** 如果你的计算机包含 CD-RW 驱动器，向导将提供将 ISO 映像刻录到空白 CD 或 DVD 的向导。</span><span class="sxs-lookup"><span data-stu-id="4a71d-111">**Note** If your computer includes a CD-RW drive, the wizard offers to burn the ISO image to a blank CD or DVD.</span></span> <span data-ttu-id="4a71d-112">如果你的计算机不包含向导支持的驱动器，你可以通过使用可刻录 CD 或 DVD 的大多数程序将 ISO 映像刻录到 CD 或 DVD 上。</span><span class="sxs-lookup"><span data-stu-id="4a71d-112">If your computer does not include a drive that is supported by the wizard, you can burn the ISO image onto a CD or DVD by using most programs that can burn a CD or DVD.</span></span>

 

<span data-ttu-id="4a71d-113">若要从 ISO 映像创建可启动 CD 或 DVD，您必须拥有：</span><span class="sxs-lookup"><span data-stu-id="4a71d-113">To create a bootable CD or DVD from the ISO image, you must have:</span></span>

-   <span data-ttu-id="4a71d-114">CD-RW 驱动器。</span><span class="sxs-lookup"><span data-stu-id="4a71d-114">A CD-RW drive.</span></span>

-   <span data-ttu-id="4a71d-115">可录制 CD 或 DVD （采用可刻录驱动器支持的格式）。</span><span class="sxs-lookup"><span data-stu-id="4a71d-115">A recordable CD or DVD (in a format supported by the recordable drive).</span></span>

-   <span data-ttu-id="4a71d-116">支持可刻录驱动器并支持直接将 ISO 映像刻录到 CD 或 DVD 的软件。</span><span class="sxs-lookup"><span data-stu-id="4a71d-116">Software that supports the recordable drive and supports burning an ISO image directly to CD or DVD.</span></span>

    <span data-ttu-id="4a71d-117">**重要提示** 在你打算支持的所有不同计算机上测试你创建的 CD 或 DVD，因为某些计算机无法从所有类型的可录制媒体启动。</span><span class="sxs-lookup"><span data-stu-id="4a71d-117">**Important** Test the CD or DVD that you create on all the different kinds of computers that you intend to support because some computers cannot start from all kinds of recordable media.</span></span>

     

<span data-ttu-id="4a71d-118">若要将 ISO 映像保存到 USB 闪存驱动器（UFD），您必须具备：</span><span class="sxs-lookup"><span data-stu-id="4a71d-118">To save the ISO image to a USB flash drive (UFD), you must have:</span></span>

-   <span data-ttu-id="4a71d-119">格式正确的 UFD。</span><span class="sxs-lookup"><span data-stu-id="4a71d-119">A correctly formatted UFD.</span></span>

-   <span data-ttu-id="4a71d-120">可用于装载 ISO 映像的程序。</span><span class="sxs-lookup"><span data-stu-id="4a71d-120">A program that you can use to mount the ISO image.</span></span>

[<span data-ttu-id="4a71d-121">如何使用 DaRT 恢复映像向导来创建恢复映像</span><span class="sxs-lookup"><span data-stu-id="4a71d-121">How to Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)

## <span data-ttu-id="4a71d-122">创建时间有限的恢复映像</span><span class="sxs-lookup"><span data-stu-id="4a71d-122">Create a Time Limited Recovery Image</span></span>


<span data-ttu-id="4a71d-123">你可以创建一个只能在生成特定天数后使用的 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="4a71d-123">You can create a DaRT recovery image that can only be used for a certain number of days after it is generated.</span></span> <span data-ttu-id="4a71d-124">若要执行此操作，必须在命令提示符处运行**DaRT 恢复映像向导**并指定天数。</span><span class="sxs-lookup"><span data-stu-id="4a71d-124">To do this, you must run the **DaRT Recovery Image Wizard** at a command prompt and specify the number of days.</span></span>

[<span data-ttu-id="4a71d-125">如何创建限期提供的恢复映像</span><span class="sxs-lookup"><span data-stu-id="4a71d-125">How to Create a Time Limited Recovery Image</span></span>](how-to-create-a-time-limited-recovery-image-dart-7.md)

## <span data-ttu-id="4a71d-126">用于创建 DaRT7 恢复映像的其他资源</span><span class="sxs-lookup"><span data-stu-id="4a71d-126">Other resources for creating the DaRT7 recovery image</span></span>


-   [<span data-ttu-id="4a71d-127">部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="4a71d-127">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





