---
title: 如何将 DaRT 恢复映像作为远程分区进行部署
description: 如何将 DaRT 恢复映像作为远程分区进行部署
author: dansimp
ms.assetid: 06a5e250-b992-4f6a-ad74-e7715f9e96e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3cdb1313a64bacd652a5253c09f36fa792d0fa3c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798202"
---
# <span data-ttu-id="3d6c4-103">如何将 DaRT 恢复映像作为远程分区进行部署</span><span class="sxs-lookup"><span data-stu-id="3d6c4-103">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="3d6c4-104">在完成运行 Microsoft Diagnostics 和恢复工具集（DaRT）10恢复映像向导并创建恢复映像之后，你可以从 ISO 映像文件提取 boot.ini 文件，并将其部署为网络上的远程分区。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-104">After you have finished running the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

**<span data-ttu-id="3d6c4-105">将 DaRT 10 部署为远程分区</span><span class="sxs-lookup"><span data-stu-id="3d6c4-105">To deploy DaRT 10 as a remote partition</span></span>**

1.  <span data-ttu-id="3d6c4-106">从 DaRT ISO 映像文件提取启动 .wim 文件。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-106">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="3d6c4-107">通过使用贵公司装载映像的首选方法，装载在 "**创建启动映像**" 对话框中创建的 ISO 图像文件。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-107">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="3d6c4-108">打开 ISO 映像文件，并将装载的映像中的 \\sources 文件夹中的启动 .wim 文件复制到计算机上或外部驱动器上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-108">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="3d6c4-109">**注意** 如果刻录了恢复映像的 CD 或 DVD，则可以打开 CD 或 DVD 上的文件，并从 \\sources 文件夹中复制 boot.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-109">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="3d6c4-110">这使你可以跳过装入映像的需要。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-110">This lets you skip the need to mount the image.</span></span>

         

2.  <span data-ttu-id="3d6c4-111">将启动 .wim 文件部署到可从你的企业中的最终用户计算机访问的 WDS 服务器。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-111">Deploy the boot.wim file to a WDS server that can be accessed from end-user computers in your enterprise.</span></span>

3.  <span data-ttu-id="3d6c4-112">将 WDS 服务器配置为使用适用于 DaRT 的 boot.ini 文件，方法是遵循你的标准 WDS 部署过程。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-112">Configure the WDS server to use the boot.wim file for DaRT by following your standard WDS deployment procedures.</span></span>

<span data-ttu-id="3d6c4-113">有关如何将 DaRT 部署为远程分区的详细信息，请参阅[操作实例：使用 PXE](https://go.microsoft.com/fwlink/?LinkId=212108)和[Windows 部署服务入门指南](https://go.microsoft.com/fwlink/?LinkId=212106)部署映像。</span><span class="sxs-lookup"><span data-stu-id="3d6c4-113">For more information about how to deploy DaRT as a remote partition, see [Walkthrough: Deploy an Image by Using PXE](https://go.microsoft.com/fwlink/?LinkId=212108) and [Windows Deployment Services Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=212106).</span></span>

## <span data-ttu-id="3d6c4-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="3d6c4-114">Related topics</span></span>


[<span data-ttu-id="3d6c4-115">创建 DaRT 10 恢复映像</span><span class="sxs-lookup"><span data-stu-id="3d6c4-115">Creating the DaRT 10 Recovery Image</span></span>](creating-the-dart-10-recovery-image.md)

[<span data-ttu-id="3d6c4-116">部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="3d6c4-116">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-10.md)

[<span data-ttu-id="3d6c4-117">计划 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="3d6c4-117">Planning for DaRT 10</span></span>](planning-for-dart-10.md)

 

 





