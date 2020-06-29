---
title: 创建 MED-V 映像
description: 创建 MED-V 映像
author: dansimp
ms.assetid: 7cbbcd22-83f5-4b60-825f-781b4c6a2d36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de1c2cd87d85bbe2fc40b9007eba8f86d2ed6f60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798061"
---
# <span data-ttu-id="15a53-103">创建 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="15a53-103">Creating a MED-V Image</span></span>


## <span data-ttu-id="15a53-104">本部分内容</span><span class="sxs-lookup"><span data-stu-id="15a53-104">In This Section</span></span>


<span data-ttu-id="15a53-105">本部分介绍了如何在安装了 MED-V 客户端和 MED-V 管理应用程序的计算机上配置 MED-V 映像，并说明了以下内容：</span><span class="sxs-lookup"><span data-stu-id="15a53-105">This section describes how to configure a MED-V image on a computer on which the MED-V client and MED-V management application are installed, and explains the following:</span></span>

<a href="" id="how-to-create-and-test-a-med-v-image"></a>[<span data-ttu-id="15a53-106">如何创建和测试 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="15a53-106">How to Create and Test a MED-V Image</span></span>](how-to-create-and-test-a-med-v-image.md)  
<span data-ttu-id="15a53-107">介绍如何创建 MED-V 映像，然后在本地测试该映像。</span><span class="sxs-lookup"><span data-stu-id="15a53-107">Describes how to create a MED-V image, and then test the image locally.</span></span>

<a href="" id="how-to-pack-a-med-v-image"></a>[<span data-ttu-id="15a53-108">如何打包 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="15a53-108">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)  
<span data-ttu-id="15a53-109">介绍如何打包 MED-V 映像，以便可以将其添加到部署包或上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="15a53-109">Describes how to pack a MED-V image so that it can be added to a deployment package or uploaded to the server.</span></span>

<a href="" id="how-to-upload-a-med-v-image-to-the-server"></a>[<span data-ttu-id="15a53-110">如何将 MED-V 映像上传到服务器</span><span class="sxs-lookup"><span data-stu-id="15a53-110">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)  
<span data-ttu-id="15a53-111">介绍如何将 MED-V 图像上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="15a53-111">Describes how to upload a MED-V image to the server.</span></span>

<a href="" id="how-to-localize-a-med-v-image"></a>[<span data-ttu-id="15a53-112">如何本地化 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="15a53-112">How to Localize a MED-V Image</span></span>](how-to-localize-a-med-v-image.md)  
<span data-ttu-id="15a53-113">介绍如何通过提取或下载映像来本地化 MED-V 映像。</span><span class="sxs-lookup"><span data-stu-id="15a53-113">Describes how to localize a MED-V image either through extracting or downloading the image.</span></span>

<a href="" id="how-to-update-a-med-v-image"></a>[<span data-ttu-id="15a53-114">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="15a53-114">How to Update a MED-V Image</span></span>](how-to-update-a-med-v-image.md)  
<span data-ttu-id="15a53-115">介绍如何更新 MED-V 图像以创建新版本的图像。</span><span class="sxs-lookup"><span data-stu-id="15a53-115">Describes how to update a MED-V image to create a new version of the image.</span></span>

<a href="" id="how-to-delete-a-med-v-image"></a>[<span data-ttu-id="15a53-116">如何删除 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="15a53-116">How to Delete a MED-V Image</span></span>](how-to-delete-a-med-v-image.md)  
<span data-ttu-id="15a53-117">介绍如何删除 MED-V 图像。</span><span class="sxs-lookup"><span data-stu-id="15a53-117">Describes how to delete a MED-V image.</span></span>

<span data-ttu-id="15a53-118">**注意** 在配置 MED-V 映像后，计算机不应是域的一部分，因为在客户端上应在客户端上执行加入域过程，作为 MED-V 工作区设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="15a53-118">**Note** After the MED-V image is configured, the computer should not be part of a domain because the join domain procedure should be performed on the client after the deployment, as part of the MED-V workspace setup.</span></span>

 

 

 





