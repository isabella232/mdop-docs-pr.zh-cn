---
title: 如何部署工作区映像
description: 如何部署工作区映像
author: dansimp
ms.assetid: ccc8e89b-1625-4b58-837e-4c6d93d46070
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4cb16b0a4c278d135fdc9b737aa7a6e9b46115e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804081"
---
# <span data-ttu-id="7dea3-103">如何部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="7dea3-103">How to Deploy a Workspace Image</span></span>


<span data-ttu-id="7dea3-104">使用企业软件分发系统时，可通过以下方式之一将新映像部署到客户端计算机：</span><span class="sxs-lookup"><span data-stu-id="7dea3-104">When using an enterprise software distribution system, a new image can be deployed onto client computers in one of the following ways:</span></span>

-   [<span data-ttu-id="7dea3-105">Web 下载</span><span class="sxs-lookup"><span data-stu-id="7dea3-105">Web download</span></span>](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [<span data-ttu-id="7dea3-106">映像预暂存</span><span class="sxs-lookup"><span data-stu-id="7dea3-106">Image pre-staging</span></span>](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a><span data-ttu-id="7dea3-107">如何通过 Web 部署工作区图像</span><span class="sxs-lookup"><span data-stu-id="7dea3-107">How to Deploy a Workspace Image via the Web</span></span>


**<span data-ttu-id="7dea3-108">通过 Web 部署工作区图像</span><span class="sxs-lookup"><span data-stu-id="7dea3-108">To deploy a workspace image via the Web</span></span>**

1.  <span data-ttu-id="7dea3-109">将 MED-V 图像上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="7dea3-109">Upload the MED-V image to the server.</span></span>

    <span data-ttu-id="7dea3-110">有关上载图像的信息，请参阅[如何将 Med-v 图像上载到服务器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7dea3-110">For information on uploading the image, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

2.  <span data-ttu-id="7dea3-111">使用企业软件分发系统在用户的计算机上安装 MED-V 客户端 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="7dea3-111">Using your enterprise software distribution system, install the MED-V client .msi package on users’ computers.</span></span>

    <span data-ttu-id="7dea3-112">有关安装 MED-V 客户端 .msi 程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientesds.md)。</span><span class="sxs-lookup"><span data-stu-id="7dea3-112">For information on installing the MED-V client .msi package, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span>

    <span data-ttu-id="7dea3-113">MED-V 客户端首次安装并启动。</span><span class="sxs-lookup"><span data-stu-id="7dea3-113">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="7dea3-114">在首次启动时，客户端从客户端安装中指定的服务器地址下载映像。</span><span class="sxs-lookup"><span data-stu-id="7dea3-114">On first-time startup, the client downloads the image from the server address specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a><span data-ttu-id="7dea3-115">如何使用映像预转储部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="7dea3-115">How to Deploy a Workspace Image Using Image Pre-staging</span></span>


**<span data-ttu-id="7dea3-116">使用映像预暂存部署工作区映像</span><span class="sxs-lookup"><span data-stu-id="7dea3-116">To deploy a workspace image using image pre-staging</span></span>**

1.  <span data-ttu-id="7dea3-117">创建一个图像预调试文件夹，并将图像推送到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="7dea3-117">Create an image pre-stage folder, and push the image to the folder.</span></span>

    <span data-ttu-id="7dea3-118">有关配置映像预暂存的信息，请参阅[如何配置映像预暂存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="7dea3-118">For information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

2.  <span data-ttu-id="7dea3-119">使用企业软件分发系统在用户的计算机上安装 MED-V 客户端 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="7dea3-119">Using your enterprise software distribution system, install the MED-V client .msi package on users’ computers.</span></span>

    <span data-ttu-id="7dea3-120">有关安装 MED-V 客户端 .msi 程序包的信息，请参阅[如何安装 Med-v 客户端](how-to-install-med-v-clientesds.md)。</span><span class="sxs-lookup"><span data-stu-id="7dea3-120">For information on installing the MED-V client .msi package, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span>

    <span data-ttu-id="7dea3-121">MED-V 客户端首次安装并启动。</span><span class="sxs-lookup"><span data-stu-id="7dea3-121">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="7dea3-122">在首次启动时，客户端从客户端安装中指定的预安装文件夹中获取映像。</span><span class="sxs-lookup"><span data-stu-id="7dea3-122">On first-time startup, the client fetches the image from the pre-stage folder specified in the client installation.</span></span>

## <span data-ttu-id="7dea3-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="7dea3-123">Related topics</span></span>


[<span data-ttu-id="7dea3-124">如何配置映像 Web 分发服务器</span><span class="sxs-lookup"><span data-stu-id="7dea3-124">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

 

 





