---
title: 如何配置映像预暂存
description: 如何配置映像预暂存
author: dansimp
ms.assetid: 92781b5a-208f-45a4-a078-ee90cf9efd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38ddb7a69845aa4dbcb9cbd16b84dedc04438732
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803962"
---
# <span data-ttu-id="ce071-103">如何配置映像预暂存</span><span class="sxs-lookup"><span data-stu-id="ce071-103">How to Configure Image Pre-staging</span></span>


<span data-ttu-id="ce071-104">**注意** 映像预转储仅适用于初始图像下载。</span><span class="sxs-lookup"><span data-stu-id="ce071-104">**Note** Image pre-staging is useful only for the initial image download.</span></span> <span data-ttu-id="ce071-105">不支持图像更新。</span><span class="sxs-lookup"><span data-stu-id="ce071-105">It is not supported for image update.</span></span>

 

## <span data-ttu-id="ce071-106">如何配置映像预暂存</span><span class="sxs-lookup"><span data-stu-id="ce071-106">How to Configure Image Pre-staging</span></span>


**<span data-ttu-id="ce071-107">配置映像预暂存</span><span class="sxs-lookup"><span data-stu-id="ce071-107">To configure image pre-staging</span></span>**

1.  <span data-ttu-id="ce071-108">在客户端计算机上的 "映像存储目录" 下，为预暂存的映像创建一个文件夹，并将其命名为 " *Med-v 图像*"。</span><span class="sxs-lookup"><span data-stu-id="ce071-108">On the client computer, under the image store directory, create a folder for the pre-staging image, and name it *MED-V Images*.</span></span>

    <span data-ttu-id="ce071-109">**注意** 此文件夹必须称为 " *med-v" 图像*。</span><span class="sxs-lookup"><span data-stu-id="ce071-109">**Note** This folder must be called *MED-V Images*.</span></span>

     

2.  <span data-ttu-id="ce071-110">在 "MED-V 图像" 文件夹中，创建一个子文件夹并将其命名为 " *PrestagedImages*"。</span><span class="sxs-lookup"><span data-stu-id="ce071-110">Inside the MED-V Images folder, create a subfolder and name it *PrestagedImages*.</span></span>

    <span data-ttu-id="ce071-111">**注意** 此文件夹必须名为*PrestagedImages*。</span><span class="sxs-lookup"><span data-stu-id="ce071-111">**Note** This folder must be called *PrestagedImages*.</span></span>

     

3.  <span data-ttu-id="ce071-112">若要将访问控制列表（ACL）安全性应用到*Med-v 图像*文件夹，请设置以下 ACL：</span><span class="sxs-lookup"><span data-stu-id="ce071-112">To apply Access Control Lists (ACL) security to the *MED-V Images* folder, set the following ACL:</span></span>

    **<span data-ttu-id="ce071-113">NT AUTHORITY\\Authenticated 用户：（OI）（CI）（特殊访问权限：）</span><span class="sxs-lookup"><span data-stu-id="ce071-113">NT AUTHORITY\\Authenticated Users:(OI)(CI)(special access:)</span></span>**

                                             **READ\_CONTROL**

                                    **SYNCHRONIZE**

                                    **FILE\_GENERIC\_READ**

                                    **FILE\_READ\_DATA**

    **                                 <span data-ttu-id="ce071-114">文件 \ _APPEND \ _DATA</span><span class="sxs-lookup"><span data-stu-id="ce071-114">FILE\_APPEND\_DATA</span></span>**

                                    **FILE\_READ\_EA**

                                    **FILE\_READ\_ATTRIBUTES**

    **<span data-ttu-id="ce071-115">NT AUTHORITY\\SYSTEM：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="ce071-115">NT AUTHORITY\\SYSTEM:(OI)(CI)F</span></span>**

    **<span data-ttu-id="ce071-116">BUILTIN\\Administrators：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="ce071-116">BUILTIN\\Administrators:(OI)(CI)F</span></span>**

    <span data-ttu-id="ce071-117">**注意** 建议将 ACL 安全性应用到 " *Med-v 图像*" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce071-117">**Note** It is recommended to apply ACL security to the *MED-V Images* folder.</span></span>

     

4.  <span data-ttu-id="ce071-118">若要将 ACL 安全性应用于*PrestagedImages*文件夹，请设置以下 ACL：</span><span class="sxs-lookup"><span data-stu-id="ce071-118">To apply ACL security to the *PrestagedImages* folder, set the following ACL:</span></span>

    **<span data-ttu-id="ce071-119">NT AUTHORITY\\Authenticated 用户：（OI）（CI）（特殊访问权限：）</span><span class="sxs-lookup"><span data-stu-id="ce071-119">NT AUTHORITY\\Authenticated Users:(OI)(CI)(special access:)</span></span>**

    **<span data-ttu-id="ce071-120">READ \ _CONTROL</span><span class="sxs-lookup"><span data-stu-id="ce071-120">READ\_CONTROL</span></span>**

    **<span data-ttu-id="ce071-121">同步</span><span class="sxs-lookup"><span data-stu-id="ce071-121">SYNCHRONIZE</span></span>**

    **<span data-ttu-id="ce071-122">文件 \ _GENERIC \ _READ</span><span class="sxs-lookup"><span data-stu-id="ce071-122">FILE\_GENERIC\_READ</span></span>**

    **<span data-ttu-id="ce071-123">文件 \ _READ \ _DATA</span><span class="sxs-lookup"><span data-stu-id="ce071-123">FILE\_READ\_DATA</span></span>**

    **<span data-ttu-id="ce071-124">文件 \ _READ \ _EA</span><span class="sxs-lookup"><span data-stu-id="ce071-124">FILE\_READ\_EA</span></span>**

    **<span data-ttu-id="ce071-125">文件 \ _READ \ _ATTRIBUTES</span><span class="sxs-lookup"><span data-stu-id="ce071-125">FILE\_READ\_ATTRIBUTES</span></span>**

    **<span data-ttu-id="ce071-126">NT AUTHORITY\\SYSTEM：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="ce071-126">NT AUTHORITY\\SYSTEM:(OI)(CI)F</span></span>**

    **<span data-ttu-id="ce071-127">BUILTIN\\Administrators：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="ce071-127">BUILTIN\\Administrators:(OI)(CI)F</span></span>**

    <span data-ttu-id="ce071-128">**注意** 建议将 ACL 安全性应用到*PrestagedImages*文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce071-128">**Note** It is recommended to apply ACL security to the *PrestagedImages* folder.</span></span>

     

5.  <span data-ttu-id="ce071-129">将图像文件（CKM 和索引文件）推送到*PrestagedImages*文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce071-129">Push the image files (CKM and INDEX files) to the *PrestagedImages* folder.</span></span>

    <span data-ttu-id="ce071-130">**注意** 将图像文件推送到 "预调试" 文件夹后，建议运行数据完整性检查并将文件标记为只读。</span><span class="sxs-lookup"><span data-stu-id="ce071-130">**Note** After the image files have been pushed to the pre-stage folder, it is recommended to run a data integrity check and to mark the files as read-only.</span></span>

     

6.  <span data-ttu-id="ce071-131">在 MED-V 客户端安装中包括以下参数： *Client.MSI VMSFOLDER = "C:\\MED-V Images"*。</span><span class="sxs-lookup"><span data-stu-id="ce071-131">Include the following parameter in the MED-V client installation: *Client.MSI VMSFOLDER=”C:\\MED-V Images”*.</span></span>

## <span data-ttu-id="ce071-132">如何更新前阶段位置</span><span class="sxs-lookup"><span data-stu-id="ce071-132">How to Update the Pre-stage Location</span></span>


**<span data-ttu-id="ce071-133">更新前阶段位置</span><span class="sxs-lookup"><span data-stu-id="ce071-133">To update the pre-stage location</span></span>**

1.  <span data-ttu-id="ce071-134">注册表项*PrestagedImagesPath*指向默认图像位置。</span><span class="sxs-lookup"><span data-stu-id="ce071-134">The registry key, *PrestagedImagesPath*, points to the default image location.</span></span> <span data-ttu-id="ce071-135">它位于以下目录中：</span><span class="sxs-lookup"><span data-stu-id="ce071-135">It is located in the following directory:</span></span>

    -   <span data-ttu-id="ce071-136">在 x86-</span><span class="sxs-lookup"><span data-stu-id="ce071-136">On an x86 -</span></span> `KEY_LOCAL_MACHINE\SOFTWARE\Kidaro`

    -   <span data-ttu-id="ce071-137">在 x64</span><span class="sxs-lookup"><span data-stu-id="ce071-137">On an x64 -</span></span> `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432node`

2.  <span data-ttu-id="ce071-138">如果图像位于其他位置，请更改路径。</span><span class="sxs-lookup"><span data-stu-id="ce071-138">If the image is in a different location, change the path.</span></span>

 

 





