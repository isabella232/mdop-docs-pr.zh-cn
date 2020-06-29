---
title: 如何更新 MED-V 映像
description: 如何更新 MED-V 映像
author: dansimp
ms.assetid: 61eacf50-3a00-4bb8-b2f3-7350a6467fa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f62cbd54d8593646460700a86ea48b5df4ce437
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798060"
---
# <span data-ttu-id="85a3d-103">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="85a3d-103">How to Update a MED-V Image</span></span>


## <span data-ttu-id="85a3d-104">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="85a3d-104">How to Update a MED-V Image</span></span>


<span data-ttu-id="85a3d-105">可以更新现有的 MED-V 映像，从而创建新版本的映像。</span><span class="sxs-lookup"><span data-stu-id="85a3d-105">An existing MED-V image can be updated, thereby creating a new version of the image.</span></span> <span data-ttu-id="85a3d-106">然后，可以在客户端计算机上部署新版本，替换现有的映像。</span><span class="sxs-lookup"><span data-stu-id="85a3d-106">The new version can then be deployed on client computers, replacing the existing image.</span></span>

<span data-ttu-id="85a3d-107">**注意** 在客户端上部署新版本时，它会覆盖现有图像。</span><span class="sxs-lookup"><span data-stu-id="85a3d-107">**Note** When a new version is deployed on the client, it overwrites the existing image.</span></span> <span data-ttu-id="85a3d-108">更新图像时，请确保不需要保存客户端上的数据。</span><span class="sxs-lookup"><span data-stu-id="85a3d-108">When updating an image, ensure that no data on the client needs to be saved.</span></span>

 

**<span data-ttu-id="85a3d-109">更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="85a3d-109">To update a MED-V image</span></span>**

1.  <span data-ttu-id="85a3d-110">在虚拟 PC2007 中打开现有图像。</span><span class="sxs-lookup"><span data-stu-id="85a3d-110">Open the existing image in Virtual PC2007.</span></span>

2.  <span data-ttu-id="85a3d-111">对图像进行所需的更改（如安装新软件）。</span><span class="sxs-lookup"><span data-stu-id="85a3d-111">Make the required changes to the image, updating the image (such as installing new software).</span></span>

3.  <span data-ttu-id="85a3d-112">关闭虚拟 PC2007。</span><span class="sxs-lookup"><span data-stu-id="85a3d-112">Close Virtual PC2007.</span></span>

4.  <span data-ttu-id="85a3d-113">测试图像。</span><span class="sxs-lookup"><span data-stu-id="85a3d-113">Test the image.</span></span>

5.  <span data-ttu-id="85a3d-114">在测试图像后，将其打包到本地存储库，使用与现有图像相同的名称。</span><span class="sxs-lookup"><span data-stu-id="85a3d-114">After the image is tested, pack it to the local repository, using the same name as the existing image.</span></span>

    <span data-ttu-id="85a3d-115">**注意** 如果将该图像命名为与现有版本不同的名称，将创建新的图像，而不是现有图像的新版本。</span><span class="sxs-lookup"><span data-stu-id="85a3d-115">**Note** If you name the image a different name than the existing version, a new image will be created rather than a new version of the existing image.</span></span>

     

6.  <span data-ttu-id="85a3d-116">将新版本上载到服务器或通过部署程序包分发。</span><span class="sxs-lookup"><span data-stu-id="85a3d-116">Upload the new version to the server or distribute it via a deployment package.</span></span>

## <span data-ttu-id="85a3d-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="85a3d-117">Related topics</span></span>


[<span data-ttu-id="85a3d-118">为 MED-V 创建虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="85a3d-118">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="85a3d-119">如何创建和测试 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="85a3d-119">How to Create and Test a MED-V Image</span></span>](how-to-create-and-test-a-med-v-image.md)

[<span data-ttu-id="85a3d-120">如何打包 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="85a3d-120">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)

[<span data-ttu-id="85a3d-121">如何将 MED-V 映像上传到服务器</span><span class="sxs-lookup"><span data-stu-id="85a3d-121">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)

[<span data-ttu-id="85a3d-122">更新 MED-V 工作区映像</span><span class="sxs-lookup"><span data-stu-id="85a3d-122">Updating a MED-V Workspace Image</span></span>](updating-a-med-v-workspace-image.md)

 

 





