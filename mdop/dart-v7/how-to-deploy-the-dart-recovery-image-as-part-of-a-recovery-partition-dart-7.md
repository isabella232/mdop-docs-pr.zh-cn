---
title: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
description: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
author: dansimp
ms.assetid: 462f2d08-f03b-4a07-b2d3-c69205dc6f70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e75c3f9e58d784c13003feb84001f89c4607115d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803392"
---
# <span data-ttu-id="dcb37-103">如何将 DaRT 恢复映像作为恢复分区的一部分进行部署</span><span class="sxs-lookup"><span data-stu-id="dcb37-103">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="dcb37-104">在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件提取 boot.ini 文件，并将其部署为 Windows 7 映像中的恢复分区。</span><span class="sxs-lookup"><span data-stu-id="dcb37-104">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 7 image.</span></span>

**<span data-ttu-id="dcb37-105">在 Windows 7 映像的恢复分区中部署 DaRT</span><span class="sxs-lookup"><span data-stu-id="dcb37-105">To deploy DaRT in the recovery partition of a Windows 7 image</span></span>**

1.  <span data-ttu-id="dcb37-106">在 Windows 7 映像中创建一个等于或大于使用**DaRT 恢复映像向导**创建的 ISO 映像文件大小的目标分区。</span><span class="sxs-lookup"><span data-stu-id="dcb37-106">Create a target partition in your Windows 7 image that is equal to or greater than the size of the ISO image file that you created by using the **DaRT Recovery Image Wizard**.</span></span>

    <span data-ttu-id="dcb37-107">DaRT 分区所需的最小大小约为300MB。</span><span class="sxs-lookup"><span data-stu-id="dcb37-107">The minimum size required for a DaRT partition is approximately 300MB.</span></span> <span data-ttu-id="dcb37-108">但是，我们建议450MB 以满足 DaRT 中的远程连接功能。</span><span class="sxs-lookup"><span data-stu-id="dcb37-108">However, we recommend 450MB to accommodate for the remote connection functionality in DaRT.</span></span>

2.  <span data-ttu-id="dcb37-109">从 DaRT ISO 映像文件提取启动 .wim 文件。</span><span class="sxs-lookup"><span data-stu-id="dcb37-109">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="dcb37-110">通过使用贵公司装载映像的首选方法，装载在 "**创建启动映像**" 对话框中创建的 ISO 图像文件。</span><span class="sxs-lookup"><span data-stu-id="dcb37-110">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="dcb37-111">打开 ISO 映像文件，并将装载的映像中的 \\sources 文件夹中的启动 .wim 文件复制到计算机上或外部驱动器上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="dcb37-111">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="dcb37-112">**注意** 如果刻录了恢复映像的 CD 或 DVD，则可以打开 CD 或 DVD 上的文件，并从 \\sources 文件夹中复制 boot.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="dcb37-112">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="dcb37-113">这使你可以跳过装入映像的需要。</span><span class="sxs-lookup"><span data-stu-id="dcb37-113">This lets you skip the need to mount the image.</span></span>

         

3.  <span data-ttu-id="dcb37-114">使用 boot.ini 文件创建可启动的恢复分区，方法是使用贵公司用于创建自定义 Windows RE 映像的标准方法。</span><span class="sxs-lookup"><span data-stu-id="dcb37-114">Use the boot.wim file to create a bootable recovery partition by using your company’s standard method for creating a custom Windows RE image.</span></span>

    <span data-ttu-id="dcb37-115">有关如何创建或自定义恢复分区的详细信息，请参阅[自定义 WINDOWS RE 体验](https://go.microsoft.com/fwlink/?LinkId=214222)。</span><span class="sxs-lookup"><span data-stu-id="dcb37-115">For more information about how to create or customize a recovery partition, see [Customizing the Windows RE Experience](https://go.microsoft.com/fwlink/?LinkId=214222).</span></span>

4.  <span data-ttu-id="dcb37-116">将 Windows 7 映像中的目标分区替换为恢复分区。</span><span class="sxs-lookup"><span data-stu-id="dcb37-116">Replace the target partition in your Windows 7 image with the recovery partition.</span></span>

<span data-ttu-id="dcb37-117">在 Windows 7 映像准备就绪后，使用贵公司的标准映像部署过程将映像分发到企业中的计算机。</span><span class="sxs-lookup"><span data-stu-id="dcb37-117">After your Windows 7 image is ready, distribute the image to computers in your enterprise by using your company’s standard image deployment process.</span></span> <span data-ttu-id="dcb37-118">有关如何创建 Windows 7 映像的详细信息，请参阅[构建 windows 7 的标准映像：分步指南](https://go.microsoft.com/fwlink/?LinkId=212103)。</span><span class="sxs-lookup"><span data-stu-id="dcb37-118">For more information about how to create a Windows 7 image, see [Building a Standard Image of Windows 7: Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=212103).</span></span>

<span data-ttu-id="dcb37-119">有关如何部署恢复解决方案以在系统发生故障时重新安装工厂映像的详细信息，请参阅[部署系统恢复映像](https://go.microsoft.com/fwlink/?LinkId=214221)。</span><span class="sxs-lookup"><span data-stu-id="dcb37-119">For more information about how to deploy a recovery solution to reinstall the factory image in the event of a system failure, see [Deploy a System Recovery Image](https://go.microsoft.com/fwlink/?LinkId=214221).</span></span>

## <span data-ttu-id="dcb37-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="dcb37-120">Related topics</span></span>


[<span data-ttu-id="dcb37-121">部署 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="dcb37-121">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





