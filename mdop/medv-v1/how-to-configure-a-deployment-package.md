---
title: 如何配置部署包
description: 如何配置部署包
author: dansimp
ms.assetid: 748272a1-6af2-476e-a3f1-87435b8e94b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aba5e91a4da92f9e51a5ccc70502658ae724d76f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803870"
---
# <span data-ttu-id="d28f6-103">如何配置部署包</span><span class="sxs-lookup"><span data-stu-id="d28f6-103">How to Configure a Deployment Package</span></span>


<span data-ttu-id="d28f6-104">打包向导将引导你完成程序包创建，方法是在本地计算机上创建一个文件夹，并将所有所需的安装文件转移到单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="d28f6-104">The Packaging wizard walks you through the creation of a package by creating a folder on your local computer and transferring all the required installation files to the single folder.</span></span> <span data-ttu-id="d28f6-105">然后，可将该文件夹的内容移动到多个可移动媒体驱动器进行分发。</span><span class="sxs-lookup"><span data-stu-id="d28f6-105">The contents of the folder can then be moved to multiple removable media drives for distribution.</span></span>

**<span data-ttu-id="d28f6-106">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-106">Note</span></span>**  
<span data-ttu-id="d28f6-107">单个程序包不能包含 x86 和 x64 系统的安装文件。</span><span class="sxs-lookup"><span data-stu-id="d28f6-107">A single package cannot contain installation files for both x86 and x64 systems.</span></span>



## <span data-ttu-id="d28f6-108">如何创建部署包</span><span class="sxs-lookup"><span data-stu-id="d28f6-108">How to Create a Deployment Package</span></span>


**<span data-ttu-id="d28f6-109">创建部署包</span><span class="sxs-lookup"><span data-stu-id="d28f6-109">To create a deployment package</span></span>**

1. <span data-ttu-id="d28f6-110">在 "**映像**" 模块中验证你已创建了至少一个本地打包的映像。</span><span class="sxs-lookup"><span data-stu-id="d28f6-110">Verify in the **Images** module that you have created at least one local packed image.</span></span>

2. <span data-ttu-id="d28f6-111">在 "**工具**" 菜单上，选择 "**打包向导**"。</span><span class="sxs-lookup"><span data-stu-id="d28f6-111">On the **Tools** menu, select **Packaging wizard**.</span></span>

3. <span data-ttu-id="d28f6-112">在 "**打包向导**" 欢迎页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d28f6-112">On the **Packaging wizard** welcome page, click **Next**.</span></span>

4. <span data-ttu-id="d28f6-113">在 "**工作区图像**" 页面上，选中 "**在程序包中包含图像**" 复选框以在程序包中包含图像。</span><span class="sxs-lookup"><span data-stu-id="d28f6-113">On the **Workspace Image** page, select the **Include image in the package** check box to include an image in the package.</span></span>

   <span data-ttu-id="d28f6-114">"**图像**" 字段已启用。</span><span class="sxs-lookup"><span data-stu-id="d28f6-114">The **Image** field is enabled.</span></span>

   **<span data-ttu-id="d28f6-115">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-115">Note</span></span>**  
   <span data-ttu-id="d28f6-116">不需要在 MED-V 程序包中使用图像;可以创建不带映像的程序包。</span><span class="sxs-lookup"><span data-stu-id="d28f6-116">An image is not required in a MED-V package; the package can be created without an image.</span></span> <span data-ttu-id="d28f6-117">在这种情况下，应将图像上载到服务器，以便以后可以通过网络将其下载到客户端，或者将其推送到 "图像预暂存" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d28f6-117">In such a case, the image should be uploaded to the server so that it can later be downloaded over the network to the client, or pushed to an image pre-stage folder.</span></span>



5. <span data-ttu-id="d28f6-118">单击**图像**列表以查看所有可用图像。</span><span class="sxs-lookup"><span data-stu-id="d28f6-118">Click the **Image** list to view all available images.</span></span> <span data-ttu-id="d28f6-119">选择要复制到程序包的图像。</span><span class="sxs-lookup"><span data-stu-id="d28f6-119">Select the image to be copied to the package.</span></span> <span data-ttu-id="d28f6-120">单击 "**刷新**" 以刷新可用图像的列表。</span><span class="sxs-lookup"><span data-stu-id="d28f6-120">Click **Refresh** to refresh the list of available images.</span></span>

6. <span data-ttu-id="d28f6-121">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d28f6-121">Click **Next**.</span></span>

7. <span data-ttu-id="d28f6-122">在 " **Med-v 安装设置**" 页面上，通过执行下列操作之一选择 med-v 安装文件：</span><span class="sxs-lookup"><span data-stu-id="d28f6-122">On the **MED-V Installation Settings** page, select the MED-V installation file by doing one of the following:</span></span>

   -   <span data-ttu-id="d28f6-123">在 " **med-v 安装文件**" 字段中，键入安装文件所在目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="d28f6-123">In the **MED-V installation file** field, type the full path to the directory where the installation file is located.</span></span>

   -   <span data-ttu-id="d28f6-124">单击 " **...** " 浏览到安装文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="d28f6-124">Click **...** to browse to the directory where the installation file is located.</span></span>

   **<span data-ttu-id="d28f6-125">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-125">Note</span></span>**  
   <span data-ttu-id="d28f6-126">此字段是必需的，并且如果没有有效的文件名，向导将不会继续。</span><span class="sxs-lookup"><span data-stu-id="d28f6-126">This field is mandatory, and the wizard will not continue without a valid file name.</span></span>



8. <span data-ttu-id="d28f6-127">在 "**服务器地址**" 字段中，键入服务器名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d28f6-127">In the **Server address** field, type the server name or IP address.</span></span>

9. <span data-ttu-id="d28f6-128">在 "**服务器端口**" 字段中，键入服务器端口。</span><span class="sxs-lookup"><span data-stu-id="d28f6-128">In the **Server port** field, type the server port.</span></span>

10. <span data-ttu-id="d28f6-129">选中 "**使用 https 访问服务器**" 复选框，以要求 https 连接连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="d28f6-129">Select the **Server is accessed using https** check box to require an https connection to connect to the server.</span></span>

11. <span data-ttu-id="d28f6-130">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d28f6-130">Do one of the following:</span></span>

    -   <span data-ttu-id="d28f6-131">单击 "**默认安装设置**"，然后单击 "**下一步**" 继续并保留默认设置。</span><span class="sxs-lookup"><span data-stu-id="d28f6-131">Click **Default installation settings**, and then click **Next** to continue and leave the default settings.</span></span>

    -   <span data-ttu-id="d28f6-132">单击 "**自定义安装设置**"，然后单击 "**下一步**" 以自定义安装设置。</span><span class="sxs-lookup"><span data-stu-id="d28f6-132">Click **Custom installation settings**, and then click **Next** to customize the installation settings.</span></span>

        1.  <span data-ttu-id="d28f6-133">在 " **Med-v 安装" 自定义设置**页面上的 "**安装文件夹**" 字段中，键入将在主机计算机上安装 med-v 文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="d28f6-133">On the **MED-V Installation Custom Settings** page, in the **Installation folder** field, type the path of the folder where the MED-V files will be installed on the host computer.</span></span>

            **<span data-ttu-id="d28f6-134">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-134">Note</span></span>**  
            <span data-ttu-id="d28f6-135">建议在路径（而不是常量）中使用变量，这可能会因计算机而异。</span><span class="sxs-lookup"><span data-stu-id="d28f6-135">It is recommended to use variables in the path rather than constants, which might vary from computer to computer.</span></span>

            <span data-ttu-id="d28f6-136">例如，使用 *%ProgramFiles%\\MED-V*而不是*c:\\MED-V*。</span><span class="sxs-lookup"><span data-stu-id="d28f6-136">For example, use *%ProgramFiles%\\MED-V* instead of *c:\\MED-V*.</span></span>



    ~~~
    2.  In the **Virtual machines images folder** field, type the path of the folder where the virtual images files will be installed on the host computer.

        **Note**  
        If you are using image pre-staging, this is the image pre-stage folder where the image is located.



    3.  In the **Minimal required RAM** field, enter the RAM required to install a MED-V package. If the user installing the MED-V package does not have the minimal required RAM, the installation will fail.

    4.  Select the **Install the MED-V management application** check box to include the MED-V management console application in the installation.

    5.  Select the **Create a shortcut to MED-V on the desktop** check box to create a shortcut to MED-V on the host's desktop.

    6.  Select the **Start automatically on computer startup** check box to start MED-V automatically on startup.

    7.  Click **Next**.
    ~~~

12. <span data-ttu-id="d28f6-137">在 "**其他安装**" 页面上，选中 "**包括虚拟化软件的安装**" 复选框，以在程序包中包含虚拟 PC 安装。</span><span class="sxs-lookup"><span data-stu-id="d28f6-137">On the **Additional Installations** page, select the **Include installation of virtualization software** check box to include the Virtual PC installation in the package.</span></span>

    <span data-ttu-id="d28f6-138">"**安装文件**" 字段已启用。</span><span class="sxs-lookup"><span data-stu-id="d28f6-138">The **Installation file** field is enabled.</span></span> <span data-ttu-id="d28f6-139">键入虚拟化软件安装文件的完整路径，或单击 " **...** " 以浏览到该目录。</span><span class="sxs-lookup"><span data-stu-id="d28f6-139">Type the full path of the virtualization software installation file, or click **...** to browse to the directory.</span></span>

13. <span data-ttu-id="d28f6-140">选中 "**包括虚拟 PC QFE 的安装**" 复选框以在程序包中包含虚拟 pc 更新安装。</span><span class="sxs-lookup"><span data-stu-id="d28f6-140">Select the **Include installation of Virtual PC QFE** check box to include Virtual PC update installation in the package.</span></span>

    <span data-ttu-id="d28f6-141">"**安装文件**" 字段已启用。</span><span class="sxs-lookup"><span data-stu-id="d28f6-141">The **Installation file** field is enabled.</span></span> <span data-ttu-id="d28f6-142">键入虚拟 PC 更新安装文件的完整路径，或单击 " **...** " 以浏览到该目录。</span><span class="sxs-lookup"><span data-stu-id="d28f6-142">Type the full path of the Virtual PC update installation file, or click **...** to browse to the directory.</span></span>

14. <span data-ttu-id="d28f6-143">选中 "**包括 microsoft .Net framework 2.0 安装**" 复选框，以在程序包中包含 Microsoft .net framework 2.0 安装。</span><span class="sxs-lookup"><span data-stu-id="d28f6-143">Select the **Include installation of Microsoft .NET Framework 2.0** check box to include the Microsoft .NET Framework 2.0 installation in the package.</span></span>

    <span data-ttu-id="d28f6-144">"**安装文件**" 字段已启用。</span><span class="sxs-lookup"><span data-stu-id="d28f6-144">The **Installation file** field is enabled.</span></span> <span data-ttu-id="d28f6-145">键入 Microsoft .NET Framework 2.0 安装文件的完整路径，或单击 " **...** " 以浏览到该目录。</span><span class="sxs-lookup"><span data-stu-id="d28f6-145">Type the full path of the Microsoft .NET Framework 2.0 installation file, or click **...** to browse to the directory.</span></span>

15. <span data-ttu-id="d28f6-146">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d28f6-146">Click **Next**.</span></span>

16. <span data-ttu-id="d28f6-147">在 "**完成**" 页面上，通过执行下列操作之一选择要保存程序包的位置：</span><span class="sxs-lookup"><span data-stu-id="d28f6-147">On the **Finalize** page, select the location where the package should be saved by doing one of the following:</span></span>

    -   <span data-ttu-id="d28f6-148">在 "**程序包目标**" 字段中，键入应保存程序包的目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="d28f6-148">In the **Package destination** field, type the full path to the directory where the package should be saved.</span></span>

    -   <span data-ttu-id="d28f6-149">单击 " **...** " 浏览到应保存安装文件的目录。</span><span class="sxs-lookup"><span data-stu-id="d28f6-149">Click **...** to browse to the directory where the installation files should be saved.</span></span>

    **<span data-ttu-id="d28f6-150">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-150">Note</span></span>**  
    <span data-ttu-id="d28f6-151">构建程序包可能会占用比实际程序包大小更多的空间。</span><span class="sxs-lookup"><span data-stu-id="d28f6-151">Building the package might consume more space than the actual package size.</span></span> <span data-ttu-id="d28f6-152">因此，建议在硬盘上构建程序包。</span><span class="sxs-lookup"><span data-stu-id="d28f6-152">It is therefore recommended to build the package on the hard drive.</span></span> <span data-ttu-id="d28f6-153">创建程序包后，可以将其复制到 USB。</span><span class="sxs-lookup"><span data-stu-id="d28f6-153">After the package is created, it can then be copied to the USB.</span></span>



17. <span data-ttu-id="d28f6-154">在 "**程序包名称**" 字段中，输入程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="d28f6-154">In the **Package name** field, enter a name for the package.</span></span>

18. <span data-ttu-id="d28f6-155">单击 "**完成**" 以创建程序包。</span><span class="sxs-lookup"><span data-stu-id="d28f6-155">Click **Finish** to create the package.</span></span>

    <span data-ttu-id="d28f6-156">创建程序包。</span><span class="sxs-lookup"><span data-stu-id="d28f6-156">The package is created.</span></span> <span data-ttu-id="d28f6-157">这可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="d28f6-157">This might take several minutes.</span></span>

    <span data-ttu-id="d28f6-158">创建程序包后，将显示一条消息，通知您已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d28f6-158">After the package is created, a message appears notifying you that it has been completed successfully.</span></span>

**<span data-ttu-id="d28f6-159">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-159">Note</span></span>**  
<span data-ttu-id="d28f6-160">如果您在本地保存了所有文件，而不是直接在可移动媒体上保存，请确保只将文件夹的内容（而不是文件夹本身）复制到可移动媒体。</span><span class="sxs-lookup"><span data-stu-id="d28f6-160">If you saved all the files locally, and not directly on the removable media, ensure that you copy only the contents of the folder and not the folder itself to the removable media.</span></span>



**<span data-ttu-id="d28f6-161">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-161">Note</span></span>**  
<span data-ttu-id="d28f6-162">可移动媒体必须足够大，以便程序包内容最多只能使用可移动媒体内存的四分之三。</span><span class="sxs-lookup"><span data-stu-id="d28f6-162">The removable media must be large enough so that the package contents consume a maximum of only three-quarters of the removable media's memory.</span></span>



**<span data-ttu-id="d28f6-163">注意</span><span class="sxs-lookup"><span data-stu-id="d28f6-163">Note</span></span>**  
<span data-ttu-id="d28f6-164">创建程序包时，在生成完成时，可能需要最多两倍的实际包大小。</span><span class="sxs-lookup"><span data-stu-id="d28f6-164">When creating the package, up to double the size of the actual package size might be required when the build is complete.</span></span>



## <span data-ttu-id="d28f6-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="d28f6-165">Related topics</span></span>


[<span data-ttu-id="d28f6-166">创建 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="d28f6-166">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)









