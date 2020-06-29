---
title: 使用部署包部署 MED-V 工作区
description: 使用部署包部署 MED-V 工作区
author: dansimp
ms.assetid: e07fa70a-1a9f-486f-9a86-b33593b234da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc16b32fd44e45606df5502fda2e580d404dbb19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803407"
---
# <span data-ttu-id="a6f29-103">使用部署包部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="a6f29-103">Deploying a MED-V Workspace Using a Deployment Package</span></span>


<span data-ttu-id="a6f29-104">部署程序包安装提供了一种方法，用于安装 MED-V 客户及其所有必需的先决条件以及由管理员预定义的任何设置。</span><span class="sxs-lookup"><span data-stu-id="a6f29-104">The deployment package installation provides a method of installing MED-V client together with all its required prerequisites as well as any settings predefined by the administrator.</span></span>

<span data-ttu-id="a6f29-105">使用部署程序包时，将通过共享网络或可移动媒体分发程序包。</span><span class="sxs-lookup"><span data-stu-id="a6f29-105">When using a deployment package, the package is distributed via a shared network or removable media.</span></span> <span data-ttu-id="a6f29-106">图像可以包含在程序包中，也可以单独分发。</span><span class="sxs-lookup"><span data-stu-id="a6f29-106">The image can be included in the package or can be distributed separately.</span></span>

<span data-ttu-id="a6f29-107">在创建部署程序包之前，请确保已创建准备好部署的 MED-V 映像。</span><span class="sxs-lookup"><span data-stu-id="a6f29-107">Before creating a deployment package, ensure that you have created a MED-V image ready for deployment.</span></span> <span data-ttu-id="a6f29-108">有关创建 MED-V 图像的详细信息，请参阅[创建 Med-v 图像](creating-a-med-v-image.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f29-108">For more information on creating a MED-V image, see [Creating a MED-V Image](creating-a-med-v-image.md).</span></span>

<span data-ttu-id="a6f29-109">准备好 MED-V 映像后，请考虑在你的环境中分发映像的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="a6f29-109">After the MED-V image is prepared, consider the best method for distributing the image in your environment.</span></span> <span data-ttu-id="a6f29-110">可以通过以下方式之一分发图像：</span><span class="sxs-lookup"><span data-stu-id="a6f29-110">The image can be distributed in one of the following ways:</span></span>

-   <span data-ttu-id="a6f29-111">通过 Web 下载上传到 Web 并进行分发，也可以选择使用 "剪裁传输技术"。</span><span class="sxs-lookup"><span data-stu-id="a6f29-111">Uploaded to the Web and distributed via Web download, optionally using Trim Transfer technology.</span></span>

-   <span data-ttu-id="a6f29-112">使用映像预分段进行分发。</span><span class="sxs-lookup"><span data-stu-id="a6f29-112">Distributed using image pre-staging.</span></span>

-   <span data-ttu-id="a6f29-113">包含在部署程序包中，并与所有其他 MED-V 组件一起分发。</span><span class="sxs-lookup"><span data-stu-id="a6f29-113">Included in the deployment package and distributed together with all the other MED-V components.</span></span>

<span data-ttu-id="a6f29-114">如果该图像将包含在程序包中，则不需要任何其他配置。</span><span class="sxs-lookup"><span data-stu-id="a6f29-114">If the image will be included in the package, no other configurations are necessary for the image.</span></span> <span data-ttu-id="a6f29-115">如果部署程序包中不包含该映像，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a6f29-115">If the image will not be included in the deployment package, do one of the following:</span></span>

-   <span data-ttu-id="a6f29-116">如果要通过 Web 部署映像，请将 MED-V 图像上载到图像 Web 分发服务器。</span><span class="sxs-lookup"><span data-stu-id="a6f29-116">If you are deploying the image via the Web, upload the MED-V image to the image Web distribution server.</span></span> <span data-ttu-id="a6f29-117">有关配置图像 Web 分发服务器的信息，请参阅[如何配置图像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f29-117">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span> <span data-ttu-id="a6f29-118">有关将图像上载到服务器的信息，请参阅[如何将 Med-v 图像上载到服务器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f29-118">For information on uploading an image to the server, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

-   <span data-ttu-id="a6f29-119">如果你是通过预暂存的映像部署映像，请配置前暂存文件夹，并将 MED-V 图像推送到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6f29-119">If you are deploying the image via image pre-staging, configure the pre-stage folder, and push the MED-V image to the folder.</span></span> <span data-ttu-id="a6f29-120">有关配置映像预暂存的详细信息，请参阅[如何配置映像预暂存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f29-120">For more information on configuring the image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

<span data-ttu-id="a6f29-121">**注意** 如果你使用的是映像预暂存，则在创建部署包之前配置图像预调试文件夹非常重要。</span><span class="sxs-lookup"><span data-stu-id="a6f29-121">**Note** If you are using image pre-staging, it is important to configure the image pre-stage folder prior to creating the deployment package.</span></span> <span data-ttu-id="a6f29-122">文件夹路径需要包含在部署程序包中。</span><span class="sxs-lookup"><span data-stu-id="a6f29-122">The folder path needs to be included in the deployment package.</span></span>

 

<span data-ttu-id="a6f29-123">最后，创建部署程序包。</span><span class="sxs-lookup"><span data-stu-id="a6f29-123">Finally, create the deployment package.</span></span> <span data-ttu-id="a6f29-124">有关创建部署包的详细信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f29-124">For more information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span> <span data-ttu-id="a6f29-125">程序包完成后，将其分配给部署。</span><span class="sxs-lookup"><span data-stu-id="a6f29-125">After the package is complete, distribute it for deployment.</span></span>

<span data-ttu-id="a6f29-126">分发部署包后，可以安装 MED-V 客户端并部署映像。</span><span class="sxs-lookup"><span data-stu-id="a6f29-126">After the deployment package is distributed, MED-V client can be installed and the image deployed.</span></span> <span data-ttu-id="a6f29-127">有关安装 MED-V 客户端的详细信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f29-127">For more information on installing MED-V client, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span> <span data-ttu-id="a6f29-128">有关部署映像的详细信息，请参阅[如何部署工作区映像](how-to-deploy-a-workspace-imagedeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f29-128">For more information on deploying the image, see [How to Deploy a Workspace Image](how-to-deploy-a-workspace-imagedeployment-package.md).</span></span>

 

 





