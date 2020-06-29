---
title: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
description: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
author: dansimp
ms.assetid: 07c5d539-51d9-4759-adc7-72b40d5d7bb3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e3647d684f64a0635e2875314498bde841204369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803557"
---
# <span data-ttu-id="d0d86-103">如何将 DaRT 恢复映像作为恢复分区的一部分进行部署</span><span class="sxs-lookup"><span data-stu-id="d0d86-103">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="d0d86-104">在完成运行 Microsoft Diagnostics 和恢复工具集（DaRT）8.0 恢复映像向导并创建恢复映像之后，你可以从 ISO 映像文件提取 boot.ini 文件，并将其作为 Windows 8 映像中的恢复分区进行部署。</span><span class="sxs-lookup"><span data-stu-id="d0d86-104">After you have finished running the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 8 image.</span></span> <span data-ttu-id="d0d86-105">建议使用分区，因为阻止 Windows 操作系统启动的任何损坏问题也会阻止恢复映像启动。</span><span class="sxs-lookup"><span data-stu-id="d0d86-105">A partition is recommended, because any corruption issues that prevent the Windows operating system from starting would also prevent the recovery image from starting.</span></span> <span data-ttu-id="d0d86-106">单独的分区还无需提供两次 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="d0d86-106">A separate partition also eliminates the need to provide the BitLocker recovery key twice.</span></span> <span data-ttu-id="d0d86-107">考虑隐藏分区以防止用户在其上存储文件。</span><span class="sxs-lookup"><span data-stu-id="d0d86-107">Consider hiding the partition to prevent users from storing files on it.</span></span>

**<span data-ttu-id="d0d86-108">在 Windows 8 映像的恢复分区中部署 DaRT</span><span class="sxs-lookup"><span data-stu-id="d0d86-108">To deploy DaRT in the recovery partition of a Windows 8 image</span></span>**

1.  <span data-ttu-id="d0d86-109">在 Windows 8 映像中创建一个等于或大于使用**DaRT 8.0 恢复映像向导**创建的 ISO 映像文件大小的目标分区。</span><span class="sxs-lookup"><span data-stu-id="d0d86-109">Create a target partition in your Windows 8 image that is equal to or greater than the size of the ISO image file that you created by using the **DaRT 8.0 Recovery Image wizard**.</span></span>

    <span data-ttu-id="d0d86-110">DaRT 分区所需的最小大小是500MB，以适应 DaRT 中的远程连接功能。</span><span class="sxs-lookup"><span data-stu-id="d0d86-110">The minimum size required for a DaRT partition is 500MB to accommodate the remote connection functionality in DaRT.</span></span>

2.  <span data-ttu-id="d0d86-111">从 DaRT ISO 映像文件提取启动 .wim 文件。</span><span class="sxs-lookup"><span data-stu-id="d0d86-111">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="d0d86-112">使用贵公司的首选方法，装载您在 "**创建启动映像**" 页面上创建的 ISO 映像文件。</span><span class="sxs-lookup"><span data-stu-id="d0d86-112">Using your company’s preferred method, mount the ISO image file that you created on the **Create Startup Image** page.</span></span>

    2.  <span data-ttu-id="d0d86-113">打开 ISO 映像文件，并将装载的映像中的 \\sources 文件夹中的启动 .wim 文件复制到计算机上或外部驱动器上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="d0d86-113">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="d0d86-114">**注意** 如果你刻录了恢复映像的 CD、DVD 或 USB，则可以打开可移动媒体上的文件并从 \\sources 文件夹中复制 boot.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="d0d86-114">**Note** If you burned a CD, DVD, or USB of the recovery image, you can open the files on the removable media and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="d0d86-115">如果复制 boot.ini 文件，则无需装载映像。</span><span class="sxs-lookup"><span data-stu-id="d0d86-115">If you copy boot.wim file, you don’t need to mount the image.</span></span>

         

3.  <span data-ttu-id="d0d86-116">使用 boot.ini 文件创建可启动的恢复分区，方法是使用贵公司用于创建自定义 Windows RE 映像的标准方法。</span><span class="sxs-lookup"><span data-stu-id="d0d86-116">Use the boot.wim file to create a bootable recovery partition by using your company’s standard method for creating a custom Windows RE image.</span></span>

    <span data-ttu-id="d0d86-117">有关如何创建或自定义恢复分区的详细信息，请参阅[自定义 WINDOWS RE 体验](https://go.microsoft.com/fwlink/?LinkId=214222)。</span><span class="sxs-lookup"><span data-stu-id="d0d86-117">For more information about how to create or customize a recovery partition, see [Customizing the Windows RE Experience](https://go.microsoft.com/fwlink/?LinkId=214222).</span></span>

4.  <span data-ttu-id="d0d86-118">将 Windows 8 映像中的目标分区替换为恢复分区。</span><span class="sxs-lookup"><span data-stu-id="d0d86-118">Replace the target partition in your Windows 8 image with the recovery partition.</span></span>

    <span data-ttu-id="d0d86-119">有关如何部署恢复解决方案以在系统发生故障时重新安装工厂映像的详细信息，请参阅[部署系统恢复映像](https://go.microsoft.com/fwlink/?LinkId=214221)。</span><span class="sxs-lookup"><span data-stu-id="d0d86-119">For more information about how to deploy a recovery solution to reinstall the factory image in the event of a system failure, see [Deploy a System Recovery Image](https://go.microsoft.com/fwlink/?LinkId=214221).</span></span>

## <span data-ttu-id="d0d86-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="d0d86-120">Related topics</span></span>


[<span data-ttu-id="d0d86-121">创建 DaRT 8.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="d0d86-121">Creating the DaRT 8.0 Recovery Image</span></span>](creating-the-dart-80-recovery-image-dart-8.md)

[<span data-ttu-id="d0d86-122">部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="d0d86-122">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-8.md)

[<span data-ttu-id="d0d86-123">计划 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="d0d86-123">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

 

 





