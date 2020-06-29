---
title: 如何创建和测试 MED-V 映像
description: 如何创建和测试 MED-V 映像
author: dansimp
ms.assetid: 40e4aba6-12cb-4794-967d-2c09dc20d808
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f7989871a695b09c987124ab02c0143082148f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804089"
---
# <span data-ttu-id="b709f-103">如何创建和测试 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="b709f-103">How to Create and Test a MED-V Image</span></span>


<span data-ttu-id="b709f-104">MED-V 管理员创建了一个 MED-V 映像，以便它可以上载，与 MED-V 工作区相关联，然后通过 Web 分发给客户端，添加到 MED-V 程序包，或使用第三方系统下载到客户端。</span><span class="sxs-lookup"><span data-stu-id="b709f-104">The MED-V administrator creates a MED-V image so that it can be uploaded, associated with a MED-V workspace, and then distributed to the client over the Web, added to a MED-V package, or downloaded to the client by using a third-party system.</span></span> <span data-ttu-id="b709f-105">建议在部署之前先创建一个测试图像并在 MED-V 客户端上对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="b709f-105">It is recommended to first create a test image and test it on MED-V client before deploying it.</span></span>

<span data-ttu-id="b709f-106">创建 MED-V 图像时，它将经历以下阶段：</span><span class="sxs-lookup"><span data-stu-id="b709f-106">When creating a MED-V image, it goes through the following stages:</span></span>

1.  <span data-ttu-id="b709f-107">**本地测试图像**-可在本地测试的基本图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-107">**Local test image**—A basic image that can be tested locally.</span></span>

2.  <span data-ttu-id="b709f-108">**本地打包的映像**-测试图像后，图像将打包为测试前的存在。</span><span class="sxs-lookup"><span data-stu-id="b709f-108">**Local packed image**—After the image is tested, the image is packed as it existed prior to testing.</span></span> <span data-ttu-id="b709f-109">打包的映像中不包含测试期间所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b709f-109">No changes made during testing are included in the packed image.</span></span>

3.  <span data-ttu-id="b709f-110">**在服务器上打包的图像**-将打包的图像上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="b709f-110">**Packed image on server**—The packed image is uploaded to the server.</span></span>

## <span data-ttu-id="b709f-111">如何创建 MED-V 测试图像</span><span class="sxs-lookup"><span data-stu-id="b709f-111">How to Create a MED-V Test Image</span></span>


**<span data-ttu-id="b709f-112">创建新的 MED-V 测试图像</span><span class="sxs-lookup"><span data-stu-id="b709f-112">To create a new MED-V test image</span></span>**

1.  <span data-ttu-id="b709f-113">单击 "**图像**管理" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b709f-113">Click the **Images** management button.</span></span>

    <span data-ttu-id="b709f-114">将显示 "**图像**" 模块。</span><span class="sxs-lookup"><span data-stu-id="b709f-114">The **Images** module appears.</span></span>

    -   <span data-ttu-id="b709f-115">"**图像**" 模块包含以下窗格：</span><span class="sxs-lookup"><span data-stu-id="b709f-115">The **Images** module consists of the following panes:</span></span>

        -   <span data-ttu-id="b709f-116">**本地测试图像**-本地解包的图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-116">**Local Test Images**—Local unpacked images.</span></span>

        -   <span data-ttu-id="b709f-117">**本地打包的图像**-本地计算机上的所有打包图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-117">**Local Packed Images**—All packed images on the local computer.</span></span>

        -   <span data-ttu-id="b709f-118">**服务器上的压缩图像**-已打包并上载到服务器的所有图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-118">**Packed Images on Server**—All images that have been packed and uploaded to the server.</span></span>

    -   <span data-ttu-id="b709f-119">在 "**本地打包的图像**" 和 **"服务器" 窗格上的打包图像**中，每个图像的最新版本将显示为父节点。</span><span class="sxs-lookup"><span data-stu-id="b709f-119">In the **Local Packed Images** and **Packed Images on Server** panes, the most recent version of each image is displayed as the parent node.</span></span> <span data-ttu-id="b709f-120">单击父节点以查看该映像的所有其他现有版本。</span><span class="sxs-lookup"><span data-stu-id="b709f-120">Click the parent node to view all other existing versions of the image.</span></span>

2.  <span data-ttu-id="b709f-121">在 "**本地测试图像**" 窗格中，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="b709f-121">In the **Local Test Images** pane, click **New**.</span></span>

3.  <span data-ttu-id="b709f-122">在 "**测试映像创建**" 对话框中，通过执行下列操作之一，选择要配置为 med-v 测试映像的虚拟机映像：</span><span class="sxs-lookup"><span data-stu-id="b709f-122">On the **Test Image Creation** dialog box, select the virtual machine image that you want to configure as a MED-V test image by doing one of the following:</span></span>

    -   <span data-ttu-id="b709f-123">在 "**基本图像**文件" 字段中，键入为 med-v 准备的 MICROSOFT 虚拟 PC 映像所在目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b709f-123">In the **Base image** file field, type the full path to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

    -   <span data-ttu-id="b709f-124">单击 "**浏览**" 浏览到准备用于 Med-v 的 MICROSOFT 虚拟 PC 映像所在的目录。</span><span class="sxs-lookup"><span data-stu-id="b709f-124">Click **Browse** to browse to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

4.  <span data-ttu-id="b709f-125">在 "**图像名称**" 字段中，键入或选择所需的名称。</span><span class="sxs-lookup"><span data-stu-id="b709f-125">In the **Image name** field, type or select the desired name.</span></span>

    <span data-ttu-id="b709f-126">**注意** 以下字符不能包含在 "图像名称：空间" &lt; &gt; |\\ / : \* ?</span><span class="sxs-lookup"><span data-stu-id="b709f-126">**Note** The following characters cannot be included in the image name: space " &lt; &gt; | \\ / : \* ?</span></span>

     

5.  <span data-ttu-id="b709f-127">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b709f-127">Click **OK**.</span></span>

    <span data-ttu-id="b709f-128">将在你的主机上使用下表中定义的属性创建新的 MED-V 测试图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-128">A new MED-V test image is created on your host computer with the properties defined in the following table.</span></span>

    <span data-ttu-id="b709f-129">有关配置 MED-V 工作区映像的详细信息，请参阅[配置 Med-v 工作区策略](configuring-med-v-workspace-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b709f-129">For more information about configuring the MED-V workspace image, refer to [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

**<span data-ttu-id="b709f-130">本地测试图像属性</span><span class="sxs-lookup"><span data-stu-id="b709f-130">Local Test Images Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b709f-131">属性</span><span class="sxs-lookup"><span data-stu-id="b709f-131">Property</span></span></th>
<th align="left"><span data-ttu-id="b709f-132">描述</span><span class="sxs-lookup"><span data-stu-id="b709f-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b709f-133">图像名称</span><span class="sxs-lookup"><span data-stu-id="b709f-133">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b709f-134">在管理员创建图像时定义的测试映像的名称。</span><span class="sxs-lookup"><span data-stu-id="b709f-134">The name of the test image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b709f-135">图像路径</span><span class="sxs-lookup"><span data-stu-id="b709f-135">Image Path</span></span></p></td>
<td align="left"><p><span data-ttu-id="b709f-136">测试图像的本地路径。</span><span class="sxs-lookup"><span data-stu-id="b709f-136">The local path of the test image.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b709f-137">已创建</span><span class="sxs-lookup"><span data-stu-id="b709f-137">Created</span></span></p></td>
<td align="left"><p><span data-ttu-id="b709f-138">测试映像的创建日期。</span><span class="sxs-lookup"><span data-stu-id="b709f-138">The date the test image was created.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b709f-139">如何从 MED-V 客户端测试 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="b709f-139">How to Test a MED-V Image from the MED-V Client</span></span>


<span data-ttu-id="b709f-140">创建 MED-V 测试图像后，请使用以下过程在本地测试图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-140">After a MED-V test image is created, use the following procedure to test the image locally.</span></span>

**<span data-ttu-id="b709f-141">测试 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="b709f-141">To test a MED-V image</span></span>**

1.  <span data-ttu-id="b709f-142">单击 "**策略**管理" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b709f-142">Click the **Policy** management button.</span></span>

2.  <span data-ttu-id="b709f-143">在**策略**模块中，通过执行下列操作将 med-v 测试映像分配给 med-v 工作区：</span><span class="sxs-lookup"><span data-stu-id="b709f-143">In the **Policy** module, assign the MED-V test image to a MED-V workspace by doing the following:</span></span>

    1.  <span data-ttu-id="b709f-144">单击 "**虚拟机**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b709f-144">Click the **Virtual Machine** tab.</span></span>

    2.  <span data-ttu-id="b709f-145">在 "**分配的图像**" 字段中，选择您创建的 med-v 测试图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-145">In the **Assigned Image** field, select the MED-V test image you created.</span></span> <span data-ttu-id="b709f-146">如果你的测试图像不在列表中，请单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="b709f-146">If your test image is not in the list, click **Refresh**.</span></span>

    3.  <span data-ttu-id="b709f-147">在工具栏上，单击 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="b709f-147">On the toolbar, click **Save changes**.</span></span>

3.  <span data-ttu-id="b709f-148">配置要测试的任何其他 MED-V 工作区设置。</span><span class="sxs-lookup"><span data-stu-id="b709f-148">Configure any other MED-V workspace settings to be tested.</span></span> <span data-ttu-id="b709f-149">有关详细信息，请参阅[配置 Med-v 工作区策略](configuring-med-v-workspace-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b709f-149">For more information, see [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

4.  <span data-ttu-id="b709f-150">启动 MED-V-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="b709f-150">Start MED-V client.</span></span>

5.  <span data-ttu-id="b709f-151">在 "**确认正在运行的测试**确认" 框中，单击 "**使用测试图像**"。</span><span class="sxs-lookup"><span data-stu-id="b709f-151">In the **Confirm Running Test** confirmation box, click **Use Test Image**.</span></span>

6.  <span data-ttu-id="b709f-152">测试 MED-V 工作区测试图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-152">Test the MED-V workspace test image.</span></span>

    <span data-ttu-id="b709f-153">有关启动和运行 MED-V 客户端的信息，请参阅[Med-v 客户端操作](med-v-client-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="b709f-153">For information about starting and running MED-V client, see [MED-V Client Operations](med-v-client-operations.md).</span></span>

<span data-ttu-id="b709f-154">**注意** 测试图像时，请勿打开 VPC 并对图像进行更改。</span><span class="sxs-lookup"><span data-stu-id="b709f-154">**Note** While testing an image, do not open VPC and make changes to the image.</span></span>

 

<span data-ttu-id="b709f-155">**注意** 测试图像时，不会在会话之间保存任何更改;而是保存在单独的临时文件中。</span><span class="sxs-lookup"><span data-stu-id="b709f-155">**Note** When testing an image, no changes are saved to the image between sessions; instead, they are saved in a separate, temporary file.</span></span> <span data-ttu-id="b709f-156">这是为了确保在生产环境中打包和运行图像时，它是原始的干净图像。</span><span class="sxs-lookup"><span data-stu-id="b709f-156">This is to ensure that when the image is packed and run on the production environment, it is the original, clean image.</span></span>

 

## <span data-ttu-id="b709f-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="b709f-157">Related topics</span></span>


[<span data-ttu-id="b709f-158">为 MED-V 创建虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="b709f-158">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="b709f-159">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="b709f-159">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="b709f-160">配置 MED-V 工作区策略</span><span class="sxs-lookup"><span data-stu-id="b709f-160">Configuring MED-V Workspace Policies</span></span>](configuring-med-v-workspace-policies.md)

[<span data-ttu-id="b709f-161">MED-V 客户端操作</span><span class="sxs-lookup"><span data-stu-id="b709f-161">MED-V Client Operations</span></span>](med-v-client-operations.md)

 

 





