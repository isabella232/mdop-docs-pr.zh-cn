---
title: 部署 DaRT 恢复映像
description: 部署 DaRT 恢复映像
author: dansimp
ms.assetid: df5cb54a-be8c-4ed2-89ea-d3c67c2ef4d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e445873324f005455ba3c96319847dea8ba761ae
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803503"
---
# <span data-ttu-id="393ac-103">部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="393ac-103">Deploying the DaRT Recovery Image</span></span>


<span data-ttu-id="393ac-104">创建包含 Microsoft Diagnostics 和恢复工具集（DaRT）8.0 恢复映像的国际标准化组织（ISO）文件后，您可以在整个企业中部署 DaRT 8.0 恢复映像，以供最终用户和技术支持人员使用。</span><span class="sxs-lookup"><span data-stu-id="393ac-104">After you have created the International Organization for Standardization (ISO) file that contains the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image, you can deploy the DaRT 8.0 recovery image throughout your enterprise so that it is available to end users and help desk workers.</span></span> <span data-ttu-id="393ac-105">你可以使用四种受支持的方法来部署 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="393ac-105">There are four supported methods that you can use to deploy the DaRT recovery image.</span></span> <span data-ttu-id="393ac-106">若要查看每种方法的优点和缺点，请参阅[规划如何保存和部署 DaRT 8.0 恢复映像](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="393ac-106">To review the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="393ac-107">使用 DaRT 恢复映像向导将 ISO 图像文件刻录到 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="393ac-107">Burn the ISO image file to a CD or DVD by using the DaRT Recovery Image wizard</span></span>

<span data-ttu-id="393ac-108">使用 DaRT 恢复映像向导将 ISO 图像文件的内容保存到 USB 闪存驱动器（UFD）</span><span class="sxs-lookup"><span data-stu-id="393ac-108">Save the contents of the ISO image file to a USB Flash Drive (UFD) by using the DaRT Recovery Image wizard</span></span>

<span data-ttu-id="393ac-109">从 ISO 映像提取启动 .wim 文件，并将其部署为可供最终用户计算机使用的远程分区</span><span class="sxs-lookup"><span data-stu-id="393ac-109">Extract the boot.wim file from the ISO image and deploy as a remote partition that is available to end-user computers</span></span>

<span data-ttu-id="393ac-110">从 ISO 映像提取启动 .wim 文件，并在新的 Windows 8 安装的恢复分区中部署</span><span class="sxs-lookup"><span data-stu-id="393ac-110">Extract the boot.wim file from the ISO image and deploy in the recovery partition of a new Windows 8 installation</span></span>

<span data-ttu-id="393ac-111">**重要提示** **DaRT 恢复映像向导**提供将映像刻录到 CD、DVD 或 UFD 的选项，但保存和部署恢复映像的其他方法需要额外的步骤，这些步骤涉及 DaRT 中未包含的工具。</span><span class="sxs-lookup"><span data-stu-id="393ac-111">**Important** The **DaRT Recovery Image Wizard** provides the option to burn the image to a CD, DVD or UFD, but the other methods of saving and deploying the recovery image require additional steps that involve tools that are not included in DaRT.</span></span> <span data-ttu-id="393ac-112">本部分提供了有关这些其他方法的一些指南和链接。</span><span class="sxs-lookup"><span data-stu-id="393ac-112">Some guidance and links for these other methods are provided in this section.</span></span>

 

## <span data-ttu-id="393ac-113">将 DaRT 恢复映像部署为恢复分区的一部分</span><span class="sxs-lookup"><span data-stu-id="393ac-113">Deploy the DaRT recovery image as part of a recovery partition</span></span>


<span data-ttu-id="393ac-114">在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件提取 boot.ini 文件，并将其作为 Windows 8 映像中的恢复分区进行部署。</span><span class="sxs-lookup"><span data-stu-id="393ac-114">After you have finished running the DaRT Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 8 image.</span></span>

[<span data-ttu-id="393ac-115">如何将 DaRT 恢复映像作为恢复分区的一部分进行部署</span><span class="sxs-lookup"><span data-stu-id="393ac-115">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-8.md)

## <span data-ttu-id="393ac-116">将 DaRT 恢复映像部署为远程分区</span><span class="sxs-lookup"><span data-stu-id="393ac-116">Deploy the DaRT recovery image as a remote partition</span></span>


<span data-ttu-id="393ac-117">你可以在中央网络启动服务器（如 Windows 部署服务）上托管恢复映像，并允许用户或支持人员将映像流式传输到计算机按需传输。</span><span class="sxs-lookup"><span data-stu-id="393ac-117">You can host the recovery image on a central network boot server, such as Windows Deployment Services, and allow users or support staff to stream the image to computers on demand.</span></span>

[<span data-ttu-id="393ac-118">如何将 DaRT 恢复映像作为远程分区进行部署</span><span class="sxs-lookup"><span data-stu-id="393ac-118">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-8.md)

## <span data-ttu-id="393ac-119">用于部署 DaRT 恢复映像的其他资源</span><span class="sxs-lookup"><span data-stu-id="393ac-119">Other resources for deploying the DaRT recovery image</span></span>


[<span data-ttu-id="393ac-120">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="393ac-120">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

 

 





