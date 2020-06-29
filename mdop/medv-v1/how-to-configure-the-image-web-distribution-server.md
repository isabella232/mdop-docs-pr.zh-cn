---
title: 如何配置映像 Web 分发服务器
description: 如何配置映像 Web 分发服务器
author: dansimp
ms.assetid: 2d32ae79-dff5-4c05-a412-dd15452b6007
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a21b14fbaca6bbc09d4c35b4d8fb86365c42e3b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803712"
---
# <span data-ttu-id="21104-103">如何配置映像 Web 分发服务器</span><span class="sxs-lookup"><span data-stu-id="21104-103">How to Configure the Image Web Distribution Server</span></span>


<span data-ttu-id="21104-104">图像存储库是用于映像分发的可选服务器（在此情况下，管理员上载新图像和客户端计算机每15分钟检查一次服务器，并在有新的映像时更新其映像）。</span><span class="sxs-lookup"><span data-stu-id="21104-104">An image repository is an optional server that is used for image distribution (where administrators upload new images and client computers check the server every 15 minutes and update their image if a new one is available).</span></span>

## <a href="" id="bkmk-configuringanimagereporitoryusingiis"></a>


<span data-ttu-id="21104-105">映像分发服务器需要以下内容：</span><span class="sxs-lookup"><span data-stu-id="21104-105">An image distribution server requires the following:</span></span>

-   <span data-ttu-id="21104-106">Internet information Services （IIS）-有关信息，请参阅[Internet 信息服务](https://go.microsoft.com/fwlink/?LinkId=142995)。</span><span class="sxs-lookup"><span data-stu-id="21104-106">Internet Information Services (IIS)—For information, see [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=142995).</span></span>

    <span data-ttu-id="21104-107">在 IIS 安装期间，在添加角色服务时，请选择以下受支持的身份验证方法：</span><span class="sxs-lookup"><span data-stu-id="21104-107">During the IIS installation, when adding role services, select the following supported authentication methods:</span></span>

    -   **<span data-ttu-id="21104-108">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="21104-108">Basic Authentication</span></span>**

    -   **<span data-ttu-id="21104-109">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="21104-109">Windows Authentication</span></span>**

    -   **<span data-ttu-id="21104-110">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="21104-110">Client Certificate Mapping Authentication</span></span>**

    <span data-ttu-id="21104-111">配置 IIS 时，请包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="21104-111">When configuring IIS, include the following:</span></span>

    -   <span data-ttu-id="21104-112">使用名为**MEDVImages**的别名添加虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="21104-112">Add a virtual directory, with the alias named **MEDVImages**.</span></span> <span data-ttu-id="21104-113">物理路径应指向图像的位置。</span><span class="sxs-lookup"><span data-stu-id="21104-113">The physical path should point to the location of the images.</span></span>

    -   <span data-ttu-id="21104-114">启用 BITS。</span><span class="sxs-lookup"><span data-stu-id="21104-114">Enable BITS.</span></span>

    -   <span data-ttu-id="21104-115">添加以下 MIME 类型：</span><span class="sxs-lookup"><span data-stu-id="21104-115">Add the following MIME types:</span></span>

        -   **<span data-ttu-id="21104-116">。 ckm （应用程序/八进制流）</span><span class="sxs-lookup"><span data-stu-id="21104-116">.ckm (application/octet-stream)</span></span>**

        -   <span data-ttu-id="21104-117">**。索引（应用程序/八进制流**）</span><span class="sxs-lookup"><span data-stu-id="21104-117">**.index (application/octet-stream**)</span></span>

    -   <span data-ttu-id="21104-118">在 MED-V 网站上，向**所有人**添加 "读取" 权限。</span><span class="sxs-lookup"><span data-stu-id="21104-118">On the MED-V site, add read permissions to **Everyone**.</span></span>

    -   <span data-ttu-id="21104-119">重新启动 IIS。</span><span class="sxs-lookup"><span data-stu-id="21104-119">Restart IIS.</span></span>

-   <span data-ttu-id="21104-120">适用于 IIS 的 BITS 服务器扩展-有关信息，请参阅[安装 BITS 服务器扩展](https://go.microsoft.com/fwlink/?LinkId=142996)。</span><span class="sxs-lookup"><span data-stu-id="21104-120">BITS Server Extensions for IIS—For information, see [Install BITS Server Extensions](https://go.microsoft.com/fwlink/?LinkId=142996).</span></span>

## <span data-ttu-id="21104-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="21104-121">Related topics</span></span>


[<span data-ttu-id="21104-122">支持的配置</span><span class="sxs-lookup"><span data-stu-id="21104-122">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="21104-123">设计 MED-V 映像存储库</span><span class="sxs-lookup"><span data-stu-id="21104-123">Design the MED-V Image Repositories</span></span>](design-the-med-v-image-repositories.md)

 

 





