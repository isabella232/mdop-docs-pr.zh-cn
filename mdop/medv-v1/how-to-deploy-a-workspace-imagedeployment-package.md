---
title: 如何部署工作区映像
description: 如何部署工作区映像
author: dansimp
ms.assetid: b2c77e0d-101d-4956-a27c-8beb0e4f262e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d691514691286c92bd62d6fda6666345e17eb9f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804083"
---
# <span data-ttu-id="c76b3-103">如何部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="c76b3-103">How to Deploy a Workspace Image</span></span>


<span data-ttu-id="c76b3-104">使用部署包时，可以通过以下方式之一将新映像部署到客户端计算机：</span><span class="sxs-lookup"><span data-stu-id="c76b3-104">When using a deployment package, a new image can be deployed onto client computers in one of the following ways:</span></span>

-   [<span data-ttu-id="c76b3-105">Web 下载</span><span class="sxs-lookup"><span data-stu-id="c76b3-105">Web download</span></span>](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [<span data-ttu-id="c76b3-106">映像预暂存</span><span class="sxs-lookup"><span data-stu-id="c76b3-106">Image pre-staging</span></span>](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

-   [<span data-ttu-id="c76b3-107">在部署程序包内部署映像</span><span class="sxs-lookup"><span data-stu-id="c76b3-107">Deploying the image inside the deployment package</span></span>](#bkmk-howtodeployaworkspaceimageusingadeploymentapackage)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a><span data-ttu-id="c76b3-108">如何通过 Web 部署工作区图像</span><span class="sxs-lookup"><span data-stu-id="c76b3-108">How to Deploy a Workspace Image via the Web</span></span>


**<span data-ttu-id="c76b3-109">通过 Web 部署工作区图像</span><span class="sxs-lookup"><span data-stu-id="c76b3-109">To deploy a workspace image via the Web</span></span>**

1.  <span data-ttu-id="c76b3-110">将 MED-V 图像上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="c76b3-110">Upload the MED-V image to the server.</span></span>

    <span data-ttu-id="c76b3-111">有关上载图像的信息，请参阅[如何将 Med-v 图像上载到服务器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-111">For information on uploading the image, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

2.  <span data-ttu-id="c76b3-112">创建一个部署程序包，并将服务器路径包含到该映像的位置。</span><span class="sxs-lookup"><span data-stu-id="c76b3-112">Create a deployment package, and include the server path to the location of the image.</span></span>

    <span data-ttu-id="c76b3-113">有关创建部署包的信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-113">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

3.  <span data-ttu-id="c76b3-114">将程序包部署到最终用户。</span><span class="sxs-lookup"><span data-stu-id="c76b3-114">Deploy the package to end users.</span></span>

    <span data-ttu-id="c76b3-115">有关部署程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-115">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="c76b3-116">MED-V 客户端首次安装并启动。</span><span class="sxs-lookup"><span data-stu-id="c76b3-116">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="c76b3-117">在首次启动时，客户端从客户端安装中指定的服务器地址下载映像。</span><span class="sxs-lookup"><span data-stu-id="c76b3-117">On first-time startup, the client downloads the image from the server address specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a><span data-ttu-id="c76b3-118">如何使用映像预转储部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="c76b3-118">How to Deploy a Workspace Image Using Image Pre-staging</span></span>


**<span data-ttu-id="c76b3-119">使用映像预暂存部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="c76b3-119">To deploy a workspace image using image pre-staging</span></span>**

1.  <span data-ttu-id="c76b3-120">创建一个图像预调试文件夹，并将图像推送到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="c76b3-120">Create an image pre-stage folder, and push the image to the folder.</span></span>

    <span data-ttu-id="c76b3-121">有关配置映像预暂存的信息，请参阅[如何配置映像预暂存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-121">For information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

2.  <span data-ttu-id="c76b3-122">创建部署程序包，并包含图像预调试文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="c76b3-122">Create a deployment package, and include the path to the image pre-stage folder.</span></span>

    <span data-ttu-id="c76b3-123">有关创建部署包的信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-123">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

3.  <span data-ttu-id="c76b3-124">将程序包部署到最终用户。</span><span class="sxs-lookup"><span data-stu-id="c76b3-124">Deploy the package to end users.</span></span>

    <span data-ttu-id="c76b3-125">有关部署程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-125">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="c76b3-126">MED-V 客户端首次安装并启动。</span><span class="sxs-lookup"><span data-stu-id="c76b3-126">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="c76b3-127">在首次启动时，客户端从客户端安装中指定的预安装文件夹中获取映像。</span><span class="sxs-lookup"><span data-stu-id="c76b3-127">On first-time startup, the client fetches the image from the pre-stage folder specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingadeploymentapackage"></a><span data-ttu-id="c76b3-128">如何使用部署包部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="c76b3-128">How to Deploy a Workspace Image Using a Deployment Package</span></span>


**<span data-ttu-id="c76b3-129">使用部署包部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="c76b3-129">To deploy a workspace image using a deployment package</span></span>**

1.  <span data-ttu-id="c76b3-130">创建一个部署程序包，并将该映像包含在程序包中。</span><span class="sxs-lookup"><span data-stu-id="c76b3-130">Create a deployment package, and include the image in the package.</span></span>

    <span data-ttu-id="c76b3-131">有关创建部署包的信息，请参阅[如何配置部署包](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-131">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

2.  <span data-ttu-id="c76b3-132">将程序包部署到最终用户。</span><span class="sxs-lookup"><span data-stu-id="c76b3-132">Deploy the package to end users.</span></span>

    <span data-ttu-id="c76b3-133">有关部署程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c76b3-133">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="c76b3-134">将图像作为软件包安装的一部分导入到主机。</span><span class="sxs-lookup"><span data-stu-id="c76b3-134">The image is imported to the host as part of the package installation.</span></span>

## <span data-ttu-id="c76b3-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="c76b3-135">Related topics</span></span>


[<span data-ttu-id="c76b3-136">如何配置映像 Web 分发服务器</span><span class="sxs-lookup"><span data-stu-id="c76b3-136">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

[<span data-ttu-id="c76b3-137">如何配置部署包</span><span class="sxs-lookup"><span data-stu-id="c76b3-137">How to Configure a Deployment Package</span></span>](how-to-configure-a-deployment-package.md)

 

 





