---
title: 部署 DaRT 7.0 恢复映像
description: 部署 DaRT 7.0 恢复映像
author: dansimp
ms.assetid: 6bba7bff-800f-44e4-bcfc-e143115607ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cef626e50bf1049529c51afca5e536b03b3d915d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798100"
---
# <span data-ttu-id="3c66e-103">部署 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="3c66e-103">Deploying the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="3c66e-104">创建包含 Microsoft Diagnostics 和恢复工具集（DaRT）7恢复映像的国际标准化组织（ISO）文件后，您可以在整个企业中部署 DaRT 恢复映像，以便最终用户和支持人员的代理可以使用该映像。</span><span class="sxs-lookup"><span data-stu-id="3c66e-104">After you have created the International Organization for Standardization (ISO) file that contains the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image, you can deploy the DaRT recovery image throughout your enterprise so that it is available to end users and helpdesk agents.</span></span> <span data-ttu-id="3c66e-105">你可以使用四种受支持的方法来部署 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="3c66e-105">There are four supported methods that you can use to deploy the DaRT recovery image.</span></span>

-   <span data-ttu-id="3c66e-106">将 ISO 图像文件刻录到 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="3c66e-106">Burn the ISO image file to a CD or DVD</span></span>

-   <span data-ttu-id="3c66e-107">将 ISO 图像文件的内容保存到 USB 闪存驱动器（UFD）</span><span class="sxs-lookup"><span data-stu-id="3c66e-107">Save the contents of the ISO image file to a USB Flash Drive (UFD)</span></span>

-   <span data-ttu-id="3c66e-108">从 ISO 映像提取启动 .wim 文件，并将其部署为可供最终用户计算机使用的远程分区</span><span class="sxs-lookup"><span data-stu-id="3c66e-108">Extract the boot.wim file from the ISO image and deploy as a remote partition that is available to end-user computers</span></span>

-   <span data-ttu-id="3c66e-109">从 ISO 映像提取启动 .wim 文件，并在新的 Windows 7 安装的恢复分区中部署</span><span class="sxs-lookup"><span data-stu-id="3c66e-109">Extract the boot.wim file from the ISO image and deploy in the recovery partition of a new Windows 7 installation</span></span>

<span data-ttu-id="3c66e-110">**重要提示** **DaRT 恢复映像向导**仅提供刻录 CD 或 DVD 的选项。</span><span class="sxs-lookup"><span data-stu-id="3c66e-110">**Important** The **DaRT Recovery Image Wizard** only provides the option to burn a CD or DVD.</span></span> <span data-ttu-id="3c66e-111">保存和部署恢复映像的所有其他方法都需要执行其他步骤，这些步骤涉及 DaRT 中未包含的工具。</span><span class="sxs-lookup"><span data-stu-id="3c66e-111">All other methods of saving and deploying the recovery image require additional steps that involve tools that are not included in DaRT.</span></span> <span data-ttu-id="3c66e-112">本部分提供了有关这些其他方法的一些指南和链接。</span><span class="sxs-lookup"><span data-stu-id="3c66e-112">Some guidance and links for these other methods are provided in this section.</span></span>

 

## <span data-ttu-id="3c66e-113">使用 USB 闪存驱动器部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="3c66e-113">Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>


<span data-ttu-id="3c66e-114">在完成运行 DaRT 恢复映像向导后，您可以使用中的工具 <https://go.microsoft.com/fwlink/?LinkId=218888> 将 ISO 映像文件复制到 USB 闪存驱动器（UFD）。</span><span class="sxs-lookup"><span data-stu-id="3c66e-114">After you have finished running the DaRT Recovery Image Wizard, you can use the tool at <https://go.microsoft.com/fwlink/?LinkId=218888> to copy the ISO image file to a USB flash drive (UFD).</span></span>

[<span data-ttu-id="3c66e-115">如何使用 U 盘部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="3c66e-115">How to Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>](how-to-deploy-the-dart-recovery-image-using-a-usb-flash-drive-dart-7.md)

## <span data-ttu-id="3c66e-116">将 DaRT 恢复映像部署为恢复分区的一部分</span><span class="sxs-lookup"><span data-stu-id="3c66e-116">Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="3c66e-117">在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件提取 boot.ini 文件，并将其部署为 Windows 7 映像中的恢复分区。</span><span class="sxs-lookup"><span data-stu-id="3c66e-117">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 7 image.</span></span>

[<span data-ttu-id="3c66e-118">如何将 DaRT 恢复映像作为恢复分区的一部分进行部署</span><span class="sxs-lookup"><span data-stu-id="3c66e-118">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-7.md)

## <span data-ttu-id="3c66e-119">将 DaRT 恢复映像部署为远程分区</span><span class="sxs-lookup"><span data-stu-id="3c66e-119">Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="3c66e-120">在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件中提取 boot.ini 文件，并将其部署为网络上的远程分区。</span><span class="sxs-lookup"><span data-stu-id="3c66e-120">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

[<span data-ttu-id="3c66e-121">如何将 DaRT 恢复映像作为远程分区进行部署</span><span class="sxs-lookup"><span data-stu-id="3c66e-121">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-7.md)

## <span data-ttu-id="3c66e-122">用于维护部署 DaRT 恢复映像的其他资源</span><span class="sxs-lookup"><span data-stu-id="3c66e-122">Other resources for maintaining Deploying the DaRT Recovery Image</span></span>


-   [<span data-ttu-id="3c66e-123">部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="3c66e-123">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





