---
title: 使用企业软件分发系统部署 MED-V 工作区
description: 使用企业软件分发系统部署 MED-V 工作区
author: dansimp
ms.assetid: 867faed6-74ce-4573-84be-8bf26e66c08c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb9ebbc0fb605f84c5a8e67fc77fd9be51b29ff4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803406"
---
# <span data-ttu-id="89da3-103">使用企业软件分发系统部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="89da3-103">Deploying a MED-V Workspace Using an Enterprise Software Distribution System</span></span>


<span data-ttu-id="89da3-104">MED-V 客户端可以使用企业软件分发系统（如 Microsoft System Center Configuration Manager）进行分发。</span><span class="sxs-lookup"><span data-stu-id="89da3-104">MED-V client can be distributed using an enterprise software distribution system, such as Microsoft System Center Configuration Manager.</span></span>

<span data-ttu-id="89da3-105">**注意** 如果 MED-V 是使用 Microsoft System Center Configuration Manager 安装的，则在为 MED-V 创建程序包时，请将 "运行模式" 设置为 "管理权限"。</span><span class="sxs-lookup"><span data-stu-id="89da3-105">**Note** If MED-V is installed by using Microsoft System Center Configuration Manager, when creating a package for MED-V, set the run mode to administrative rights.</span></span>

 

<span data-ttu-id="89da3-106">使用企业软件分发系统部署 MED-V 之前，请确保已创建一个 MED-V 映像供部署使用。</span><span class="sxs-lookup"><span data-stu-id="89da3-106">Before deploying MED-V using an enterprise software distribution system, ensure that you have created a MED-V image ready for deployment.</span></span> <span data-ttu-id="89da3-107">有关创建 MED-V 图像的详细信息，请参阅[创建 Med-v 图像](creating-a-med-v-image.md)。</span><span class="sxs-lookup"><span data-stu-id="89da3-107">For more information on creating a MED-V image, see [Creating a MED-V Image](creating-a-med-v-image.md).</span></span>

<span data-ttu-id="89da3-108">准备好 MED-V 映像后，请考虑在你的环境中分发映像的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="89da3-108">After the MED-V image is prepared, consider the best method for distributing the image in your environment.</span></span> <span data-ttu-id="89da3-109">可以通过以下方式之一分发图像：</span><span class="sxs-lookup"><span data-stu-id="89da3-109">The image can be distributed in one of the following ways:</span></span>

-   <span data-ttu-id="89da3-110">已上载到 Web 并通过 Web 下载分发，可选择利用修剪转移技术。</span><span class="sxs-lookup"><span data-stu-id="89da3-110">Uploaded to the Web and distributed via Web download, optionally utilizing Trim Transfer technology.</span></span>

-   <span data-ttu-id="89da3-111">使用映像预分段进行分发。</span><span class="sxs-lookup"><span data-stu-id="89da3-111">Distributed using image pre-staging.</span></span>

## <span data-ttu-id="89da3-112">通过 Web 部署图像</span><span class="sxs-lookup"><span data-stu-id="89da3-112">Deploying the Image via the Web</span></span>


<span data-ttu-id="89da3-113">如果要通过 Web 部署映像，请将 MED-V 图像上载到图像 Web 分发服务器。</span><span class="sxs-lookup"><span data-stu-id="89da3-113">If you are deploying the image via the Web, upload the MED-V image to an image Web distribution server.</span></span> <span data-ttu-id="89da3-114">有关配置图像 Web 分发服务器的信息，请参阅[如何配置图像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)。</span><span class="sxs-lookup"><span data-stu-id="89da3-114">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span> <span data-ttu-id="89da3-115">有关将图像上载到服务器的信息，请参阅[如何将 Med-v 图像上载到服务器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="89da3-115">For information on uploading an image to the server, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

## <span data-ttu-id="89da3-116">通过预暂存部署映像</span><span class="sxs-lookup"><span data-stu-id="89da3-116">Deploying the Image via Pre-staging</span></span>


<span data-ttu-id="89da3-117">如果你是通过预暂存的映像部署映像，请配置前暂存文件夹，并将 MED-V 图像推送到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="89da3-117">If you are deploying the image via image pre-staging, configure the pre-stage folder, and push the MED-V image to the folder.</span></span> <span data-ttu-id="89da3-118">有关配置映像预暂存的详细信息，请参阅[如何配置映像预暂存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="89da3-118">For more information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

<span data-ttu-id="89da3-119">**注意** 如果你使用的是映像预暂存，在推送客户端 .msi 程序包之前，请务必先配置图像预调试文件夹。</span><span class="sxs-lookup"><span data-stu-id="89da3-119">**Note** If you are using image pre-staging, it is important to configure the image pre-stage folder prior to pushing the client .msi package.</span></span> <span data-ttu-id="89da3-120">需要将文件夹路径包含在客户端 .msi 程序包中。</span><span class="sxs-lookup"><span data-stu-id="89da3-120">The folder path needs to be included in the client .msi package.</span></span>

 

<span data-ttu-id="89da3-121">最后，使用企业软件分发中心推送客户端 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="89da3-121">Finally, push the client .msi package using your enterprise software distribution center.</span></span> <span data-ttu-id="89da3-122">然后，可以安装 MED-V 并部署映像。</span><span class="sxs-lookup"><span data-stu-id="89da3-122">MED-V can then be installed and the image deployed.</span></span> <span data-ttu-id="89da3-123">有关安装 MED-V 客户端的详细信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientesds.md)。</span><span class="sxs-lookup"><span data-stu-id="89da3-123">For more information on installing MED-V client, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span> <span data-ttu-id="89da3-124">有关部署映像的详细信息，请参阅[如何部署工作区映像](how-to-deploy-a-workspace-imageesds.md)。</span><span class="sxs-lookup"><span data-stu-id="89da3-124">For more information on deploying the image, see [How to Deploy a Workspace Image](how-to-deploy-a-workspace-imageesds.md).</span></span>

 

 





