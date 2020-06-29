---
title: 更新 MED-V 工作区映像
description: 更新 MED-V 工作区映像
author: dansimp
ms.assetid: 1b9c4a73-3487-43d2-98e3-43dbc79e10e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60a5d12622e0cb7012c6d0a22124d63c085f6d0a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803851"
---
# <span data-ttu-id="423a6-103">更新 MED-V 工作区映像</span><span class="sxs-lookup"><span data-stu-id="423a6-103">Updating a MED-V Workspace Image</span></span>


<span data-ttu-id="423a6-104">可通过以下方式之一更新图像：</span><span class="sxs-lookup"><span data-stu-id="423a6-104">An image can be updated in one of the following ways:</span></span>

-   <span data-ttu-id="423a6-105">可以使用企业软件分发系统将更新推送到来宾操作系统。</span><span class="sxs-lookup"><span data-stu-id="423a6-105">The update can be pushed to the guest operating system using your enterprise software distribution system.</span></span>

-   <span data-ttu-id="423a6-106">更新可以上载到图像 Web 分发服务器，然后由客户端下载并应用于 MED-V 映像。</span><span class="sxs-lookup"><span data-stu-id="423a6-106">The update can be uploaded to the image Web distribution server, and then downloaded by the client and applied to the MED-V image.</span></span>

-   <span data-ttu-id="423a6-107">可以更新和重新部署 MED-V 基本图像。</span><span class="sxs-lookup"><span data-stu-id="423a6-107">The MED-V base image can be updated and redeployed.</span></span>

## <a href="" id="bkmk-howtoupdateamedvimageusinganesd"></a><span data-ttu-id="423a6-108">如何使用企业软件分发系统更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="423a6-108">How to Update a MED-V Image Using an Enterprise Software Distribution System</span></span>


**<span data-ttu-id="423a6-109">使用企业软件分发系统更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="423a6-109">To update a MED-V image using an enterprise software distribution system</span></span>**

-   <span data-ttu-id="423a6-110">请参阅您正在使用的系统的文档。</span><span class="sxs-lookup"><span data-stu-id="423a6-110">Refer to the documentation of the system you are using.</span></span>

## <a href="" id="bkmk-howtoupdateamedvimageusingwebdownload"></a><span data-ttu-id="423a6-111">如何使用 Web 下载更新 MED-V 图像</span><span class="sxs-lookup"><span data-stu-id="423a6-111">How to Update a MED-V Image Using Web Download</span></span>


**<span data-ttu-id="423a6-112">使用 Web 下载更新 MED-V 图像</span><span class="sxs-lookup"><span data-stu-id="423a6-112">To update a MED-V image using Web download</span></span>**

1.  <span data-ttu-id="423a6-113">在 MED-V 管理的 "**虚拟机**" 选项卡上，确保将以下设置应用到与正在更新的 med-v 映像相关联的 med-v 工作区策略：</span><span class="sxs-lookup"><span data-stu-id="423a6-113">In MED-V management, on the **Virtual Machine** tab, ensure that the following settings are applied to the MED-V workspace policies that are associated with the MED-V image being updated:</span></span>

    -   <span data-ttu-id="423a6-114">选中 "**新版本可用时的建议更新**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="423a6-114">The **Suggest update when a new version is available** check box is selected.</span></span>

    -   <span data-ttu-id="423a6-115">（可选）**在 "下载此工作区的图像**" 复选框处于选中状态时，客户端应使用 "剪裁传输"。</span><span class="sxs-lookup"><span data-stu-id="423a6-115">Optionally, the **Clients should use Trim Transfer when downloading images for this Workspace** check box is selected.</span></span>

    <span data-ttu-id="423a6-116">有关详细信息，请参阅[如何将虚拟机设置应用到 Med-v 工作区](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)。</span><span class="sxs-lookup"><span data-stu-id="423a6-116">For more information, see [How to Apply Virtual Machine Settings to a MED-V Workspace](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md).</span></span>

2.  <span data-ttu-id="423a6-117">将图像更新上载到图像 Web 分发服务器。</span><span class="sxs-lookup"><span data-stu-id="423a6-117">Upload the image update to the image Web distribution server.</span></span>

    <span data-ttu-id="423a6-118">具有需要更新的图像的所有客户端都将自动下载更新，并将其应用到映像。</span><span class="sxs-lookup"><span data-stu-id="423a6-118">All clients with images that need to be updated automatically download the update and apply it to the image.</span></span>

## <a href="" id="bkmk-howtoupdateamedvbaseimage"></a><span data-ttu-id="423a6-119">如何更新 MED-V 基本图像</span><span class="sxs-lookup"><span data-stu-id="423a6-119">How to Update a MED-V Base Image</span></span>


**<span data-ttu-id="423a6-120">更新 MED-V 基本图像</span><span class="sxs-lookup"><span data-stu-id="423a6-120">To update a MED-V base image</span></span>**

1.  <span data-ttu-id="423a6-121">在虚拟 PC2007 中打开现有图像。</span><span class="sxs-lookup"><span data-stu-id="423a6-121">Open the existing image in Virtual PC2007.</span></span>

2.  <span data-ttu-id="423a6-122">对图像进行所需的更改（如安装新软件）。</span><span class="sxs-lookup"><span data-stu-id="423a6-122">Make the required changes to the image, updating the image (such as installing new software).</span></span>

3.  <span data-ttu-id="423a6-123">关闭虚拟 PC2007。</span><span class="sxs-lookup"><span data-stu-id="423a6-123">Close Virtual PC2007.</span></span>

4.  <span data-ttu-id="423a6-124">测试图像。</span><span class="sxs-lookup"><span data-stu-id="423a6-124">Test the image.</span></span>

5.  <span data-ttu-id="423a6-125">在测试图像后，将其打包到本地存储库，使用与现有图像相同的名称。</span><span class="sxs-lookup"><span data-stu-id="423a6-125">After the image is tested, pack it to the local repository, using the same name as the existing image.</span></span>

    <span data-ttu-id="423a6-126">**注意** 如果将该图像命名为与现有版本不同的名称，将创建新的图像，而不是现有图像的新版本。</span><span class="sxs-lookup"><span data-stu-id="423a6-126">**Note** If you name the image a different name than the existing version, a new image will be created rather than a new version of the existing image.</span></span>

     

6.  <span data-ttu-id="423a6-127">将新版本上载到服务器，将其推送到 "图像预调试" 文件夹，或通过部署包分发。</span><span class="sxs-lookup"><span data-stu-id="423a6-127">Upload the new version to the server, push it to the image pre-stage folder, or distribute it via a deployment package.</span></span>

## <span data-ttu-id="423a6-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="423a6-128">Related topics</span></span>


[<span data-ttu-id="423a6-129">创建 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="423a6-129">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)

[<span data-ttu-id="423a6-130">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="423a6-130">How to Update a MED-V Image</span></span>](how-to-update-a-med-v-image.md)

[<span data-ttu-id="423a6-131">配置 MED-V 工作区策略</span><span class="sxs-lookup"><span data-stu-id="423a6-131">Configuring MED-V Workspace Policies</span></span>](configuring-med-v-workspace-policies.md)

[<span data-ttu-id="423a6-132">如何配置映像 Web 分发服务器</span><span class="sxs-lookup"><span data-stu-id="423a6-132">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

 

 





