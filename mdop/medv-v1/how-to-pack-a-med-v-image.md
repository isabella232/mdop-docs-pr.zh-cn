---
title: 如何打包 MED-V 映像
description: 如何打包 MED-V 映像
author: dansimp
ms.assetid: e1ce2307-0f1b-4bf8-b146-e4012dc138d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a330b8feca922239691bed083767c3acc57105d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803616"
---
# <span data-ttu-id="7dd80-103">如何打包 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="7dd80-103">How to Pack a MED-V Image</span></span>


<span data-ttu-id="7dd80-104">必须先压缩 MED-V 映像，然后才能将其添加到部署包或上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="7dd80-104">A MED-V image must be packed before it can be added to a deployment package or uploaded to the server.</span></span>

**<span data-ttu-id="7dd80-105">创建打包的 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="7dd80-105">To create a packed MED-V image</span></span>**

1.  <span data-ttu-id="7dd80-106">单击 "**图像**管理" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7dd80-106">Click the **Images** management button.</span></span>

2.  <span data-ttu-id="7dd80-107">在 "**图像**" 模块的 "**本地打包的图像**" 窗格中，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="7dd80-107">In the **Images** module, in the **Local Packed Images** pane, click **New**.</span></span>

3.  <span data-ttu-id="7dd80-108">在 "**打包图像创建**" 对话框中，通过执行下列操作之一选择虚拟机映像：</span><span class="sxs-lookup"><span data-stu-id="7dd80-108">In the **Packed Image Creation** dialog box, select the virtual machine image by doing one of the following:</span></span>

    -   <span data-ttu-id="7dd80-109">在 "**基本图像文件**" 字段中，键入为 med-v 准备的 MICROSOFT 虚拟 PC 映像所在目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="7dd80-109">In the **Base image file** field, type the full path to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

    -   <span data-ttu-id="7dd80-110">单击 "**浏览**" 浏览到准备用于 Med-v 的 MICROSOFT 虚拟 PC 映像所在的目录。</span><span class="sxs-lookup"><span data-stu-id="7dd80-110">Click **Browse** to browse to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

4.  <span data-ttu-id="7dd80-111">通过执行下列操作之一指定新图像的名称：</span><span class="sxs-lookup"><span data-stu-id="7dd80-111">Specify the name of the new image by doing one of the following:</span></span>

    -   <span data-ttu-id="7dd80-112">在 "**图像名称**" 字段中，键入所需的名称。</span><span class="sxs-lookup"><span data-stu-id="7dd80-112">In the **Image name** field, type the desired name.</span></span>

        **<span data-ttu-id="7dd80-113">注意</span><span class="sxs-lookup"><span data-stu-id="7dd80-113">Note</span></span>**  
        <span data-ttu-id="7dd80-114">以下字符不能包含在 "图像名称：空间" &lt; &gt; |\\ / : \* ?</span><span class="sxs-lookup"><span data-stu-id="7dd80-114">The following characters cannot be included in the image name: space " &lt; &gt; | \\ / : \* ?</span></span>



~~~
    A new packed image will be created.

-   From the drop-down list, select an existing name.

    A new version of the existing image will be created.
~~~

5. <span data-ttu-id="7dd80-115">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dd80-115">Click **OK**.</span></span>

   <span data-ttu-id="7dd80-116">将在你的主机上使用下表中定义的属性创建新的 MED-V 包装图像。</span><span class="sxs-lookup"><span data-stu-id="7dd80-116">A new MED-V packed image is created on your host computer with the properties defined in the following table.</span></span>

**<span data-ttu-id="7dd80-117">注意</span><span class="sxs-lookup"><span data-stu-id="7dd80-117">Note</span></span>**  
<span data-ttu-id="7dd80-118">在 "**本地打包的图像**" 和 **"服务器" 窗格上的打包图像**中，每个图像的最新版本将显示为父节点。</span><span class="sxs-lookup"><span data-stu-id="7dd80-118">In the **Local Packed Images** and **Packed Images on Server** panes, the most recent version of each image is displayed as the parent node.</span></span> <span data-ttu-id="7dd80-119">单击父节点以查看该映像的所有其他现有版本。</span><span class="sxs-lookup"><span data-stu-id="7dd80-119">Click the parent node to view all other existing versions of the image.</span></span>



**<span data-ttu-id="7dd80-120">本地打包的图像属性</span><span class="sxs-lookup"><span data-stu-id="7dd80-120">Local Packed Images Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7dd80-121">属性</span><span class="sxs-lookup"><span data-stu-id="7dd80-121">Property</span></span></th>
<th align="left"><span data-ttu-id="7dd80-122">描述</span><span class="sxs-lookup"><span data-stu-id="7dd80-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd80-123">图像名称</span><span class="sxs-lookup"><span data-stu-id="7dd80-123">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd80-124">在管理员创建图像时定义的压缩图像的名称。</span><span class="sxs-lookup"><span data-stu-id="7dd80-124">The name of the packed image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7dd80-125">版本</span><span class="sxs-lookup"><span data-stu-id="7dd80-125">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd80-126">所显示的图像的版本。</span><span class="sxs-lookup"><span data-stu-id="7dd80-126">The version of the displayed image.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="7dd80-127">注意</span><span class="sxs-lookup"><span data-stu-id="7dd80-127">Note</span></span></strong><br/><p><span data-ttu-id="7dd80-128">所有以前的版本都将保留，除非已删除。</span><span class="sxs-lookup"><span data-stu-id="7dd80-128">All previous versions are kept unless deleted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd80-129">文件大小（已压缩）</span><span class="sxs-lookup"><span data-stu-id="7dd80-129">File Size (compressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd80-130">图像的物理压缩大小。</span><span class="sxs-lookup"><span data-stu-id="7dd80-130">The physical compressed size of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7dd80-131">图像大小（未压缩）</span><span class="sxs-lookup"><span data-stu-id="7dd80-131">Image Size (uncompressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd80-132">图像的物理未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="7dd80-132">The physical uncompressed size of the image.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="7dd80-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="7dd80-133">Related topics</span></span>


[<span data-ttu-id="7dd80-134">如何安装 MED-V 客户端和 MED-V 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7dd80-134">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="7dd80-135">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="7dd80-135">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="7dd80-136">为 MED-V 创建虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="7dd80-136">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)









