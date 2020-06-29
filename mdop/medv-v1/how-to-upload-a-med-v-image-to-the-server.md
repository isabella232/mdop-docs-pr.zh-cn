---
title: 如何将 MED-V 映像上传到服务器
description: 如何将 MED-V 映像上传到服务器
author: dansimp
ms.assetid: 0e70dfdf-3e3a-4860-970c-535806caa907
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6703eb24bc3542c280af41988a257a2f14643645
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803821"
---
# <span data-ttu-id="887b4-103">如何将 MED-V 映像上传到服务器</span><span class="sxs-lookup"><span data-stu-id="887b4-103">How to Upload a MED-V Image to the Server</span></span>


<span data-ttu-id="887b4-104">测试了 MED-V 图像后，可以将其打包，然后上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="887b4-104">After a MED-V image has been tested, it can be packed and then uploaded to the server.</span></span> <span data-ttu-id="887b4-105">有关配置图像 Web 分发服务器的信息，请参阅[如何配置图像 Web 分发服务器](how-to-configure-the-image-web-distribution-server.md)。</span><span class="sxs-lookup"><span data-stu-id="887b4-105">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span>

<span data-ttu-id="887b4-106">将 MED-V 映像打包并上传到服务器后，可以使用企业软件分发中心将其分发给用户，也可以使用部署包由用户下载。</span><span class="sxs-lookup"><span data-stu-id="887b4-106">Once a MED-V image is packed and uploaded to the server, it can be distributed to users by using an enterprise software distribution center, or it can be downloaded by users using a deployment package.</span></span> <span data-ttu-id="887b4-107">有关使用企业软件分发中心进行部署的信息，请参阅[使用企业软件分发系统部署 Med-v 工作区](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)。</span><span class="sxs-lookup"><span data-stu-id="887b4-107">For information on deployment using an enterprise software distribution center, see [Deploying a MED-V Workspace Using an Enterprise Software Distribution System](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md).</span></span> <span data-ttu-id="887b4-108">有关使用程序包进行部署的信息，请参阅[使用部署包部署 Med-v 工作区](deploying-a-med-v-workspace-using-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="887b4-108">For information on deployment using a package, see [Deploying a MED-V Workspace Using a Deployment Package](deploying-a-med-v-workspace-using-a-deployment-package.md).</span></span>

**<span data-ttu-id="887b4-109">注意</span><span class="sxs-lookup"><span data-stu-id="887b4-109">Note</span></span>**  
<span data-ttu-id="887b4-110">在上载图像之前，验证未在浏览器设置中定义 Web 代理，并且 Windows 更新当前未运行。</span><span class="sxs-lookup"><span data-stu-id="887b4-110">Before uploading an image, verify that a Web proxy is not defined in your browser settings and that Windows Update is not currently running.</span></span>



**<span data-ttu-id="887b4-111">将 MED-V 图像上载到服务器</span><span class="sxs-lookup"><span data-stu-id="887b4-111">To upload a MED-V image to the server</span></span>**

1.  <span data-ttu-id="887b4-112">在 "**本地打包的图像**" 窗格中，选择您创建的图像。</span><span class="sxs-lookup"><span data-stu-id="887b4-112">In the **Local Packed Images** pane, select the image you created.</span></span>

2.  <span data-ttu-id="887b4-113">单击 "**上载**"。</span><span class="sxs-lookup"><span data-stu-id="887b4-113">Click **Upload**.</span></span>

    <span data-ttu-id="887b4-114">将图像上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="887b4-114">The image is uploaded to the server.</span></span> <span data-ttu-id="887b4-115">这可能需要花费大量时间。</span><span class="sxs-lookup"><span data-stu-id="887b4-115">This might take a considerable amount of time.</span></span>

    <span data-ttu-id="887b4-116">服务器上的图像是用下表中列出的属性定义的。</span><span class="sxs-lookup"><span data-stu-id="887b4-116">Images on the server are defined with the properties listed in the following table.</span></span>

**<span data-ttu-id="887b4-117">服务器属性上的压缩图像</span><span class="sxs-lookup"><span data-stu-id="887b4-117">Packed Images on Server Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="887b4-118">属性</span><span class="sxs-lookup"><span data-stu-id="887b4-118">Property</span></span></th>
<th align="left"><span data-ttu-id="887b4-119">描述</span><span class="sxs-lookup"><span data-stu-id="887b4-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="887b4-120">图像名称</span><span class="sxs-lookup"><span data-stu-id="887b4-120">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="887b4-121">在管理员创建图像时定义的压缩图像的名称。</span><span class="sxs-lookup"><span data-stu-id="887b4-121">The name of the packed image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="887b4-122">版本</span><span class="sxs-lookup"><span data-stu-id="887b4-122">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="887b4-123">所显示的图像的版本。</span><span class="sxs-lookup"><span data-stu-id="887b4-123">The version of the displayed image.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="887b4-124">注意</span><span class="sxs-lookup"><span data-stu-id="887b4-124">Note</span></span></strong><br/><p><span data-ttu-id="887b4-125">所有以前的版本都将保留，除非已删除。</span><span class="sxs-lookup"><span data-stu-id="887b4-125">All previous versions are kept unless deleted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="887b4-126">文件大小（已压缩）</span><span class="sxs-lookup"><span data-stu-id="887b4-126">File Size (compressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="887b4-127">图像的物理压缩大小。</span><span class="sxs-lookup"><span data-stu-id="887b4-127">The physical compressed size of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="887b4-128">图像大小（未压缩）</span><span class="sxs-lookup"><span data-stu-id="887b4-128">Image Size (uncompressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="887b4-129">图像的物理未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="887b4-129">The physical uncompressed size of the image.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="887b4-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="887b4-130">Related topics</span></span>


[<span data-ttu-id="887b4-131">如何安装 MED-V 客户端和 MED-V 管理控制台</span><span class="sxs-lookup"><span data-stu-id="887b4-131">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="887b4-132">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="887b4-132">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="887b4-133">为 MED-V 创建虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="887b4-133">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="887b4-134">如何打包 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="887b4-134">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)









