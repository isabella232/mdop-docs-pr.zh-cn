---
title: 创建 MED-V 工作区程序包
description: 创建 MED-V 工作区程序包
author: dansimp
ms.assetid: 3f75fe73-41ac-4389-ae21-5efb2d437f4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e20cf4cc9394c4a5e90178fff4fc36ed83c12d60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803333"
---
# <span data-ttu-id="f30cd-103">创建 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="f30cd-103">Create a MED-V Workspace Package</span></span>


<span data-ttu-id="f30cd-104">MED-V 工作区是 Windows XP 桌面环境，最终用户与 MED-V 提供的虚拟机交互。</span><span class="sxs-lookup"><span data-stu-id="f30cd-104">A MED-V workspace is the Windows XP desktop environment where end users interact with the virtual machine provided by MED-V.</span></span> <span data-ttu-id="f30cd-105">管理员创建和自定义 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="f30cd-105">The administrator creates and customizes the MED-V workspace.</span></span> <span data-ttu-id="f30cd-106">工作区包含一个图像和组策略，用于定义 MED-V 工作区的规则和功能。</span><span class="sxs-lookup"><span data-stu-id="f30cd-106">The workspace consists of an image and the Group Policy that defines the rules and functionality of the MED-V workspace.</span></span>

<span data-ttu-id="f30cd-107">你可以创建多个 MED-V 工作区，每个都具有其自己的配置、设置和规则进行自定义。</span><span class="sxs-lookup"><span data-stu-id="f30cd-107">You can create multiple MED-V workspaces, each customized with its own configuration, settings, and rules.</span></span> <span data-ttu-id="f30cd-108">用户、组或多个用户或组可以与每个 MED-V 工作区相关联。</span><span class="sxs-lookup"><span data-stu-id="f30cd-108">A user, group, or multiple users or groups can be associated with each MED-V workspace.</span></span> <span data-ttu-id="f30cd-109">自定义使该 MED-V 工作区仅适用于该用户或组。</span><span class="sxs-lookup"><span data-stu-id="f30cd-109">The customization makes that MED-V workspace available only for that user or group.</span></span>

<span data-ttu-id="f30cd-110">使用**Med-v 工作区包装**程序创建 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="f30cd-110">Use the **MED-V Workspace Packager** to create MED-V workspaces.</span></span> <span data-ttu-id="f30cd-111">**Med-v 工作区包装**程序分为两个主要部分：</span><span class="sxs-lookup"><span data-stu-id="f30cd-111">The **MED-V Workspace Packager** is divided into two main sections:</span></span>

-   <span data-ttu-id="f30cd-112">主面板，其中包含用于创建和管理 MED-V 工作区的三个按钮。</span><span class="sxs-lookup"><span data-stu-id="f30cd-112">A main panel that includes three buttons that you use to create and manage MED-V workspaces.</span></span> <span data-ttu-id="f30cd-113">"**创建 Med-v 工作区程序包**" 按钮可打开用于创建 med-v 工作区的 "**创建 Med-v 工作区程序包" 向导**。</span><span class="sxs-lookup"><span data-stu-id="f30cd-113">The **Create a MED-V Workspace Package** button opens the **Create MED-V Workspace Package Wizard** that you use to create your MED-V workspaces.</span></span>

-   <span data-ttu-id="f30cd-114">窗口右侧的**帮助中心**，提供帮助你创建、测试和管理 med-v 工作区的信息和指南。</span><span class="sxs-lookup"><span data-stu-id="f30cd-114">A **Help Center** on the right-hand side of the window that provides information and guidance to help you create, test, and manage your MED-V workspaces.</span></span>

**<span data-ttu-id="f30cd-115">重要提示</span><span class="sxs-lookup"><span data-stu-id="f30cd-115">Important</span></span>**  
<span data-ttu-id="f30cd-116">在可以使用**Med-v 工作区包装程序**之前，必须首先确保 Windows PowerShell 执行策略设置为 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-116">Before you can use the **MED-V Workspace Packager**, you must first make sure that the Windows PowerShell execution policy is set to Unrestricted.</span></span>

`Set-ExecutionPolicy Unrestricted`

<span data-ttu-id="f30cd-117">此外，运行**Med-v 工作区包装**程序的计算机的 SAN 策略必须设置为 "全部联机"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-117">In addition, the SAN policy for the computer on which the **MED-V Workspace Packager** is run must be set to “Online All”.</span></span> <span data-ttu-id="f30cd-118">若要检查 SAN 策略的设置，请使用管理凭据在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f30cd-118">To check the setting of the SAN policy, run the following commands at a command prompt with administrative credentials:</span></span>

`diskpart.exe`

`DISKPART> san`

`DISKPART> exit`

<span data-ttu-id="f30cd-119">如有必要，请在命令提示符下通过使用管理凭据键入以下命令，将 SAN 策略更改为 "联机"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-119">If it is necessary, change the SAN policy to "Online All" by typing the following commands at the command prompt with administrative credentials:</span></span>

`diskpart.exe`

`DISKPART> san policy=onlineall`

`DISKPART> exit`



**<span data-ttu-id="f30cd-120">重要提示</span><span class="sxs-lookup"><span data-stu-id="f30cd-120">Important</span></span>**  
<span data-ttu-id="f30cd-121">如果在用于装载虚拟硬盘和构建 MED-V 工作区程序包的计算机上安装了自动磁盘加密软件，则必须在开始之前禁用该软件。</span><span class="sxs-lookup"><span data-stu-id="f30cd-121">If automatic disk encryption software is installed on the computer that you use to mount the virtual hard disk and build the MED-V workspace package, you must disable the software before you start.</span></span> <span data-ttu-id="f30cd-122">否则，不能在任何其他计算机上使用 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="f30cd-122">Otherwise, you cannot use the MED-V workspace on any other computer.</span></span>



<span data-ttu-id="f30cd-123">我们在此处提供的信息可帮助你创建 MED-V 工作区部署包。</span><span class="sxs-lookup"><span data-stu-id="f30cd-123">The information we provide here can help you create your MED-V workspace deployment package.</span></span>

## <a href="" id="bkmk-prereq"></a><span data-ttu-id="f30cd-124">必备条件</span><span class="sxs-lookup"><span data-stu-id="f30cd-124">Prerequisites</span></span>


<span data-ttu-id="f30cd-125">开始构建 MED-V 工作区部署程序包之前，请验证你是否具有以下项目的访问权限：</span><span class="sxs-lookup"><span data-stu-id="f30cd-125">Before you start to build your MED-V workspace deployment package, verify that you have access to the following items:</span></span>

-   **<span data-ttu-id="f30cd-126">已准备好的 Windows XP 映像</span><span class="sxs-lookup"><span data-stu-id="f30cd-126">A prepared Windows XP image</span></span>**

    <span data-ttu-id="f30cd-127">有关如何创建与 MED-V 配合使用的 Windows XP 映像的详细信息，请参阅[准备 Med-v 映像](prepare-a-med-v-image.md)。</span><span class="sxs-lookup"><span data-stu-id="f30cd-127">For more information about how to create a Windows XP image for use with MED-V, see [Prepare a MED-V Image](prepare-a-med-v-image.md).</span></span>

-   **<span data-ttu-id="f30cd-128">包含 URL 重定向信息的文本文件或列表</span><span class="sxs-lookup"><span data-stu-id="f30cd-128">A text file or list that contains URL redirection information</span></span>**

    <span data-ttu-id="f30cd-129">你的 URL 重定向文本文件或列表包含你希望从主机计算机重定向到 MED-V 工作区中的 Internet Explorer 的 Url。</span><span class="sxs-lookup"><span data-stu-id="f30cd-129">Your URL redirection text file or list contains those URLs that you want redirected from the host computer to Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="f30cd-130">使用打包向导创建 MED-V 工作区时，可导入、键入或复制并粘贴该重定向信息作为程序包创建过程中的步骤之一。</span><span class="sxs-lookup"><span data-stu-id="f30cd-130">When you are using the packaging wizard to create your MED-V workspace, you import, type, or copy and paste this redirection information as one of the steps in the package creation process.</span></span>

    **<span data-ttu-id="f30cd-131">注意</span><span class="sxs-lookup"><span data-stu-id="f30cd-131">Note</span></span>**  
    <span data-ttu-id="f30cd-132">MED-V 中的 URL 重定向仅支持 HTTP 和 HTTPS 协议。</span><span class="sxs-lookup"><span data-stu-id="f30cd-132">URL redirection in MED-V only supports the protocols HTTP and HTTPS.</span></span> <span data-ttu-id="f30cd-133">MED-V 不提供对 FTP 或任何其他协议的支持。</span><span class="sxs-lookup"><span data-stu-id="f30cd-133">MED-V does not provide support for FTP or any other protocols.</span></span>



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



## <span data-ttu-id="f30cd-134">将 MED-V 工作区与 MED-V 工作区包装计算机的语言之外的其他语言打包</span><span class="sxs-lookup"><span data-stu-id="f30cd-134">Packaging a MED-V Workspace for a Language Other than the Language of the MED-V Workspace Packager Computer</span></span>


<span data-ttu-id="f30cd-135">默认情况下，MED-V 工作区支持计算机语言和英语中的字符。</span><span class="sxs-lookup"><span data-stu-id="f30cd-135">By default, the MED-V workspace supports characters in both the language of the computer and in English.</span></span> <span data-ttu-id="f30cd-136">若要为计算机上安装的另一种语言创建 MED-V 工作区，请在位于 MED-V 工作区名称后的 PowerShell 脚本（ps1）中指定**loc \ [locale \]** 。</span><span class="sxs-lookup"><span data-stu-id="f30cd-136">To create a MED-V workspace for a language other than the one installed on the computer, specify **-loc \[locale\]** in the PowerShell script (.ps1) after the MED-V workspace name.</span></span>

<span data-ttu-id="f30cd-137">若要使用除 MED-V 工作区包装计算机的默认语言之外的其他语言创建 MED-V 工作区程序包，请运行 MED-V 工作区包装器，然后根据你的区域设置所需修改输出脚本，以默认语言生成脚本。</span><span class="sxs-lookup"><span data-stu-id="f30cd-137">To create a MED-V workspace package in a language other than the default language of the MED-V Workspace Packager computer, generate a script in the default language by running the MED-V Workspace Packager and then modifying the output script as required for your locale.</span></span> <span data-ttu-id="f30cd-138">该脚本位于打包期间指定的 MED-V 工作区输出目录中。</span><span class="sxs-lookup"><span data-stu-id="f30cd-138">The script is located in the MED-V workspace output directory that was specified during packaging.</span></span> <span data-ttu-id="f30cd-139">区域设置的名称位于 ""。以下目录中的 WXL 文件：</span><span class="sxs-lookup"><span data-stu-id="f30cd-139">The names of the locale settings are on the .WXL files in the following directory:</span></span>

<span data-ttu-id="f30cd-140">C:\\program files Files\\Microsoft 企业版桌面 Virtualization\\WindowsPowerShell\\Modules\\Microsoft.Medv.Administration.Commands.WorkspacePackager\\locale</span><span class="sxs-lookup"><span data-stu-id="f30cd-140">C:\\Program Files\\Microsoft Enterprise Desktop Virtualization\\WindowsPowerShell\\Modules\\Microsoft.Medv.Administration.Commands.WorkspacePackager\\locale</span></span>

## <span data-ttu-id="f30cd-141">创建 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="f30cd-141">Creating a MED-V Workspace Package</span></span>


<span data-ttu-id="f30cd-142">若要创建 MED-V 工作区程序包，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f30cd-142">To create a MED-V workspace package, follow these steps:</span></span>

****

1.  <span data-ttu-id="f30cd-143">若要打开**Med-v 工作区包装程序**，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 工作区包装程序**"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-143">To open the **MED-V Workspace Packager**, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager**.</span></span>

2.  <span data-ttu-id="f30cd-144">在**Med-v 工作区包装**程序主面板上，单击 "**创建 Med-v 工作区程序包**"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-144">On the **MED-V Workspace Packager** main panel, click **Create a MED-V Workspace Package**.</span></span>

    <span data-ttu-id="f30cd-145">将显示 "MED-V**创建 Med-v 工作区程序包" 向导**。</span><span class="sxs-lookup"><span data-stu-id="f30cd-145">The MED-V **Create MED-V Workspace Package Wizard** appears.</span></span> <span data-ttu-id="f30cd-146">向导包含以下页面：</span><span class="sxs-lookup"><span data-stu-id="f30cd-146">The wizard consists of the following pages:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="f30cd-147">程序包信息</span><span class="sxs-lookup"><span data-stu-id="f30cd-147">Package Information</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-148">为 MED-V 工作区指定一个名称，并选择保存 MED-V 工作区包文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f30cd-148">Specify a name for the MED-V workspace and select a folder where the MED-V workspace package files are saved.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="f30cd-149">选择 Windows XP 映像</span><span class="sxs-lookup"><span data-stu-id="f30cd-149">Select Windows XP Image</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-150">指定准备好的 Windows XP 虚拟 PC 映像。</span><span class="sxs-lookup"><span data-stu-id="f30cd-150">Specify your prepared Windows XP Virtual PC image.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="f30cd-151">首次设置</span><span class="sxs-lookup"><span data-stu-id="f30cd-151">First Time Setup</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-152">指定首次设置时的 MED-V 所遵循的设置过程。</span><span class="sxs-lookup"><span data-stu-id="f30cd-152">Specify the setup process that MED-V follows during first time setup.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="f30cd-153">MED-V 消息</span><span class="sxs-lookup"><span data-stu-id="f30cd-153">MED-V Messages</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-154">为最终用户首次设置时看到的帮助信息指定消息和可选 URL。</span><span class="sxs-lookup"><span data-stu-id="f30cd-154">Specify the messages and optional URL for Help information that the end user sees during first time setup.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="f30cd-155">命名计算机</span><span class="sxs-lookup"><span data-stu-id="f30cd-155">Naming Computers</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-156">指定如何命名 MED-V 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="f30cd-156">Specify how the MED-V virtual machine is named.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="f30cd-157">从主机复制设置</span><span class="sxs-lookup"><span data-stu-id="f30cd-157">Copy Settings from Host</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-158">指定如何定义 MED-V 工作区的设置。</span><span class="sxs-lookup"><span data-stu-id="f30cd-158">Specify how the settings for the MED-V workspace are defined.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="f30cd-159">启动和网络</span><span class="sxs-lookup"><span data-stu-id="f30cd-159">Startup and Networking</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-160">指定启动 MED-V 工作区、网络和用户凭据的设置。</span><span class="sxs-lookup"><span data-stu-id="f30cd-160">Specify the settings for starting the MED-V workspace, networking, and user credentials.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="f30cd-161">Web 重定向</span><span class="sxs-lookup"><span data-stu-id="f30cd-161">Web Redirection</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-162">指定要在 MED-V 工作区中重定向到 Internet Explorer 的 Url 的文本文件或 Url 列表。</span><span class="sxs-lookup"><span data-stu-id="f30cd-162">Specify a text file or a list of the URLs you want redirected to Internet Explorer in the MED-V workspace.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="f30cd-163">摘要</span><span class="sxs-lookup"><span data-stu-id="f30cd-163">Summary</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="f30cd-164">验证你的 MED-V 工作区设置，并开始构建你的 MED-V 工作区部署包。</span><span class="sxs-lookup"><span data-stu-id="f30cd-164">Verify your MED-V workspace settings and start to build your MED-V workspace deployment package.</span></span></p></td>
    </tr>
    </tbody>
    </table>



3.  <span data-ttu-id="f30cd-165">在 "**程序包信息**" 页面上，输入 med-v 工作区的名称，并选择保存 med-v 工作区包文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f30cd-165">On the **Package Information** page, enter a name for the MED-V workspace and select a folder where the MED-V workspace package files are saved.</span></span>

    **<span data-ttu-id="f30cd-166">警告</span><span class="sxs-lookup"><span data-stu-id="f30cd-166">Warning</span></span>**  
    <span data-ttu-id="f30cd-167">你必须命名 MED-V 工作区并指定一个文件夹以继续。</span><span class="sxs-lookup"><span data-stu-id="f30cd-167">You must name the MED-V workspace and specify a folder to continue.</span></span>



~~~
After you have finished, click **Next**.
~~~

4. <span data-ttu-id="f30cd-168">在 "**选择 WINDOWS XP 映像**" 页面上，指定准备好的 MED-V Windows XP 虚拟 PC 映像（.vhd 文件）的位置。</span><span class="sxs-lookup"><span data-stu-id="f30cd-168">On the **Select Windows XP Image** page, specify the location of your prepared MED-V Windows XP Virtual PC image (.vhd file).</span></span>

   **<span data-ttu-id="f30cd-169">警告</span><span class="sxs-lookup"><span data-stu-id="f30cd-169">Warning</span></span>**  
   <span data-ttu-id="f30cd-170">必须指定 Windows XP VHD 映像才能继续。</span><span class="sxs-lookup"><span data-stu-id="f30cd-170">You must specify a Windows XP VHD image to continue.</span></span>



~~~
After you have finished, click **Next**.
~~~

5. <span data-ttu-id="f30cd-171">在 "**首次设置**" 页面上，选择是希望首次设置在参与还是无人参与时运行，以及是希望在共享计算机上的所有最终用户分别使用还是使用 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="f30cd-171">On the **First Time Setup** page, select whether you want first time setup to run while attended or unattended and whether you want the MED-V workspace used separately or used by all end users on a shared computer.</span></span>

   <span data-ttu-id="f30cd-172">如果你选择**无人参与安装，而不发送任何通知**，则在首次运行设置之前不会通知最终用户，并且首次设置期间，虚拟机不会显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="f30cd-172">If you select **Unattended setup, without any notification**, the end user is not informed before first time setup is run and the virtual machine is not shown to the end user during first time setup.</span></span> <span data-ttu-id="f30cd-173">此外，向导的 " **Med-v 消息**" 页面是隐藏的，因为首次设置在完全无人参与的模式下运行时不需要任何消息。</span><span class="sxs-lookup"><span data-stu-id="f30cd-173">In addition, the **MED-V Messages** page of the wizard is hidden because no messages are required if first time setup runs in a completely unattended mode.</span></span>

   <span data-ttu-id="f30cd-174">如果选择了 **"无人参与安装"，但在首次设置开始之前通知最终用户**，则会在首次运行设置之前通知最终用户。</span><span class="sxs-lookup"><span data-stu-id="f30cd-174">If you select **Unattended setup, but notify end users before first time setup begins**, the end user is informed before first time setup is run.</span></span> <span data-ttu-id="f30cd-175">但是，首次设置时，虚拟机不会显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="f30cd-175">However, the virtual machine is not shown to the end user during first time setup.</span></span>

   <span data-ttu-id="f30cd-176">如果最终用户在首次设置时必须输入信息，请选择 "**有人参与的设置**"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-176">Select **Attended setup** if the end user must enter information during first time setup.</span></span>

   <span data-ttu-id="f30cd-177">默认行为是**无人参与安装，但在首次开始设置之前通知最终用户**。</span><span class="sxs-lookup"><span data-stu-id="f30cd-177">The default behavior is **Unattended setup, but notify end users before first time setup begins**.</span></span>

   **<span data-ttu-id="f30cd-178">注意</span><span class="sxs-lookup"><span data-stu-id="f30cd-178">Caution</span></span>**  
   <span data-ttu-id="f30cd-179">如果你创建了 Sysprep.inf 文件，以便最小化安装需要用户输入才能完成，则必须选择 "**有人参与设置**" 或 "首次设置时可能出现问题"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-179">If you created the Sysprep.inf file so that Mini-Setup requires user input to complete, you must select **Attended setup** or problems might occur during first time setup.</span></span>



~~~
You can also specify how a MED-V workspace is used on computers that are shared by multiple end users. You can decide that you want to create a unique MED-V workspace for each end user or that you want the MED-V workspace made available to all end users who share the computer. The default is that the MED-V workspace is unique for each end user.

**Important**  
We recommend that you disable the fast user switching feature in Windows if you configure the MED-V workspace to be accessed by all users on a shared computer. Problems can occur if an end user logs on by using the fast user switching feature in Windows when another user is still logged on.



**Tip**  
When you create a name mask for the MED-V workspace on the **Naming Computers** page, make sure that each virtual machine on a shared computer has a unique computer name.



You can also specify whether the MED-V workspace is added to the Administrators group or administrator credentials are managed outside MED-V. By default, the MED-V workspace is not automatically added to the Administrators group.

After you have finished, click **Next**.
~~~

6. <span data-ttu-id="f30cd-180">在 " **Med-v 消息**" 页面上，指定首次设置时最终用户看到的以下消息：</span><span class="sxs-lookup"><span data-stu-id="f30cd-180">On the **MED-V Messages** page, specify the following messages that the end user sees during first time setup:</span></span>

   -   <span data-ttu-id="f30cd-181">第一次启动时，最终用户看到的消息。</span><span class="sxs-lookup"><span data-stu-id="f30cd-181">The message that the end user sees when first time setup starts.</span></span>

   -   <span data-ttu-id="f30cd-182">最终用户第一次设置失败或出现错误时所看到的消息。</span><span class="sxs-lookup"><span data-stu-id="f30cd-182">The message that the end user sees if first time setup fails or an error occurs.</span></span>

   **<span data-ttu-id="f30cd-183">注意</span><span class="sxs-lookup"><span data-stu-id="f30cd-183">Note</span></span>**  
   <span data-ttu-id="f30cd-184">如果您选择了 **"无人参与安装"，并且**在**首次设置**页面上没有任何通知，向导的 " **med-v 消息**" 页面将被隐藏。</span><span class="sxs-lookup"><span data-stu-id="f30cd-184">The **MED-V Messages** page of the wizard is hidden if you selected **Unattended setup, without any notification** on the **First Time Setup** page.</span></span>



~~~
You can also specify an optional URL location for help information that is provided to the end user when first time setup is running.

For example, the URL can point to an internal IT webpage with answers to questions such as "How long will this take and how will I know when it has completed?" or "What do you do if you get an error message?"

**Note**  
If you specify a URL, a link is shown during first time setup that points the end user to this help information. If you do not specify a URL, no link is provided.



After you have finished, click **Next**.
~~~

7. <span data-ttu-id="f30cd-185">在 "**命名计算机**" 页面上，可以指定由 med-v 或系统管理工具（如 Sysprep）管理计算机命名。</span><span class="sxs-lookup"><span data-stu-id="f30cd-185">On the **Naming Computers** page, you can specify whether computer naming is managed by MED-V or by a system management tool, such as Sysprep.</span></span> <span data-ttu-id="f30cd-186">默认情况下，计算机命名由系统管理工具管理。</span><span class="sxs-lookup"><span data-stu-id="f30cd-186">The default is that computer naming is managed by a system management tool.</span></span>

   <span data-ttu-id="f30cd-187">如果你指定由 MED-V 管理计算机命名，请从下拉列表中选择预定义的计算机命名约定（掩码）。</span><span class="sxs-lookup"><span data-stu-id="f30cd-187">If you specify that computer naming is managed by MED-V, select a predefined computer naming convention (mask) from the drop-down list.</span></span> <span data-ttu-id="f30cd-188">将显示一个示例计算机名的预览，它基于你用于构建 MED-V 工作区程序包的计算机。</span><span class="sxs-lookup"><span data-stu-id="f30cd-188">A preview of a sample computer name appears that is based on the computer that you are using to build the MED-V workspace package.</span></span>

   <span data-ttu-id="f30cd-189">如果选择其中一个自定义命名约定，则可以指定的字段限制为以下字符：</span><span class="sxs-lookup"><span data-stu-id="f30cd-189">If you select one of the custom naming conventions, the fields you can specify are limited to the following characters:</span></span>

   -   <span data-ttu-id="f30cd-190">前缀和后缀字段限制为字符 A-z、A-z、0-9 和特殊字符！</span><span class="sxs-lookup"><span data-stu-id="f30cd-190">The prefix and suffix fields are limited to the characters A-Z, a-z, 0-9, and the special characters !</span></span> <span data-ttu-id="f30cd-191">@ \ # $% ^ & （）-\ _ "{}。</span><span class="sxs-lookup"><span data-stu-id="f30cd-191">@ \# $ % ^ & ( ) - \_ ' { } .</span></span> <span data-ttu-id="f30cd-192">和 ~。</span><span class="sxs-lookup"><span data-stu-id="f30cd-192">and ~.</span></span>

   -   <span data-ttu-id="f30cd-193">"主机名" 和 "用户名" 字段限制为0到9的数字。</span><span class="sxs-lookup"><span data-stu-id="f30cd-193">The hostname and username fields are limited to the digits 0 through 9.</span></span>

   **<span data-ttu-id="f30cd-194">重要提示</span><span class="sxs-lookup"><span data-stu-id="f30cd-194">Important</span></span>**  
   <span data-ttu-id="f30cd-195">计算机名必须是唯一的，并且最多只能有15个字符。</span><span class="sxs-lookup"><span data-stu-id="f30cd-195">Computer names must be unique and are limited to a maximum of 15 characters.</span></span> <span data-ttu-id="f30cd-196">确定计算机命名方法时，请考虑拥有多台计算机或共享计算机的最终用户，避免使用可能导致网络冲突的计算机名称掩码。</span><span class="sxs-lookup"><span data-stu-id="f30cd-196">When you decide on your computer naming method, consider end users who have multiple computers or that share a computer, and avoid using computer name masks that could cause a collision on the network.</span></span>



~~~
**Caution**  
The computer name settings that you specify on this page override those specified in the Sysprep.inf answer file.



After you have finished, click **Next**.
~~~

8. <span data-ttu-id="f30cd-197">在 "**从主机复制设置**" 页面上，你可以选择以下设置来指定 med-v 工作区的配置方式：</span><span class="sxs-lookup"><span data-stu-id="f30cd-197">On the **Copy Settings from Host** page, you can select the following settings to specify how the MED-V workspace is configured:</span></span>

   **<span data-ttu-id="f30cd-198">注意</span><span class="sxs-lookup"><span data-stu-id="f30cd-198">Caution</span></span>**  
   <span data-ttu-id="f30cd-199">在此页面上指定的、从主机复制到 MED-V 工作区的设置将替代在 Sysprep.inf 应答文件中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="f30cd-199">The settings that you specify on this page that are copied from the host computer to the MED-V workspace override those specified in the Sysprep.inf answer file.</span></span>



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Copy regional settings</strong></p></td>
<td align="left"><p>Select this check box to copy the regional settings from the host computer to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[RegionalSettings]
Language
SystemLocale
UserLocale
UserLocale_DefaultUser
InputLocale
InputLocale_DefaultUser
</code></pre></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy user settings</strong></p></td>
<td align="left"><p>Select this check box to copy certain user settings, such as user name and company name, from the host to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[UserData]
OrgName
FullName</code></pre>
<div class="alert">
<strong>Note</strong>  
<p>Personal settings, such as Internet browsing history, are not copied over to the MED-V workspace.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain name</strong></p></td>
<td align="left"><p>Select this check box to let the guest join the same domain as the host.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><div class="alert">
<strong>Important</strong>  
<p>The MED-V guest must be configured to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain organizational unit</strong></p></td>
<td align="left"><p>Select this check box to copy the domain organizational unit from the host computer to the MED-V workspace. This check box is only enabled if you select to copy the domain name from the host computer.</p></td>
</tr>
</tbody>
</table>



After you have finished, click **Next**.
~~~

9. <span data-ttu-id="f30cd-200">在 "**启动和网络**" 页面上，可以更改以下设置的默认行为：</span><span class="sxs-lookup"><span data-stu-id="f30cd-200">On the **Startup and Networking** page, you can change the default behavior for the following settings:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="f30cd-201">启动 MED-V-V 工作区</span><span class="sxs-lookup"><span data-stu-id="f30cd-201">Start MED-V workspace</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="f30cd-202">选择是在用户登录时启动 MED-V 工作区还是首次使用，或者让最终用户决定 MED-V 工作区何时启动。</span><span class="sxs-lookup"><span data-stu-id="f30cd-202">Choose whether to start the MED-V workspace at user logon, at first use, or to let the end user decide when the MED-V workspace starts.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><span data-ttu-id="f30cd-203">MED-V 工作区通过以下两种方式之一启动：最终用户登录时或首次启动需要 MED-V 的操作时，例如打开已发布的应用程序或输入需要重定向的 URL。</span><span class="sxs-lookup"><span data-stu-id="f30cd-203">The MED-V workspace starts in one of two ways: either when the end user logs on or when they first start an action that requires MED-V, such as opening a published application or entering a URL that requires redirection.</span></span></p>
   <p><span data-ttu-id="f30cd-204">你可以为最终用户定义此设置，也可以让最终用户控制 MED-V 的启动方式。</span><span class="sxs-lookup"><span data-stu-id="f30cd-204">You can either define this setting for the end user or let the end user control how MED-V starts.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="f30cd-205">注意</span><span class="sxs-lookup"><span data-stu-id="f30cd-205">Note</span></span></strong><br/><p><span data-ttu-id="f30cd-206">如果你指定最终用户决定，其体验的默认行为是 MED-V 工作区在登录时启动。</span><span class="sxs-lookup"><span data-stu-id="f30cd-206">If you specify that the end user decides, the default behavior they experience is that the MED-V workspace starts when they log on.</span></span> <span data-ttu-id="f30cd-207">用户可以通过右键单击通知区域中的 MED-V 图标并选择 "Med-v 用户设置" 来更改默认值 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f30cd-207">They can change the default by right-clicking the MED-V icon in the notification area and selecting <strong>MED-V User Settings</strong>.</span></span> <span data-ttu-id="f30cd-208">如果为最终用户定义此设置，则无法更改 MED-V 的启动方式。</span><span class="sxs-lookup"><span data-stu-id="f30cd-208">If you define this setting for the end user, they cannot change how MED-V starts.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="f30cd-209">网络</span><span class="sxs-lookup"><span data-stu-id="f30cd-209">Networking</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="f30cd-210"><strong> </strong> <strong> </strong> 为您的网络设置选择 "共享" 或 "桥接"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-210">Select <strong>Shared</strong> or <strong>Bridged</strong> for your networking setting.</span></span> <span data-ttu-id="f30cd-211">默认值为 " <strong> 共享" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f30cd-211">The default is <strong>Shared</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong><span data-ttu-id="f30cd-212">共享 </strong> - 的 med-v 工作区使用网络地址转换（NAT）将主机&#39;s IP 用于传出通信。</span><span class="sxs-lookup"><span data-stu-id="f30cd-212">Shared</strong> - The MED-V workspace uses Network Address Translation (NAT) to share the host&#39;s IP for outgoing traffic.</span></span></p>
   <p><strong><span data-ttu-id="f30cd-213">已桥接 </strong> - med-v 工作区有自己的网络地址，通常通过 DHCP 获得。</span><span class="sxs-lookup"><span data-stu-id="f30cd-213">Bridged</strong> - The MED-V workspace has its own network address, typically obtained through DHCP.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="f30cd-214">存储凭据</span><span class="sxs-lookup"><span data-stu-id="f30cd-214">Store credentials</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="f30cd-215">选择是否要存储最终用户凭据。</span><span class="sxs-lookup"><span data-stu-id="f30cd-215">Choose whether you want to store the end user credentials.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><span data-ttu-id="f30cd-216">默认行为是禁用凭据存储，以便最终用户必须在每次登录时进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f30cd-216">The default behavior is that credential storing is disabled so that the end user must be authenticated every time that they log on.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="f30cd-217">重要提示</span><span class="sxs-lookup"><span data-stu-id="f30cd-217">Important</span></span></strong><br/><p><span data-ttu-id="f30cd-218">即使缓存最终用户的凭据可提供最佳用户体验，你也应该知道所涉及的风险。</span><span class="sxs-lookup"><span data-stu-id="f30cd-218">Even though caching the end user’s credentials provides the best user experience, you should be aware of the risks involved.</span></span></p>
   <p><span data-ttu-id="f30cd-219">最终用户的域凭据以一种可还原的格式存储在 Windows 凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="f30cd-219">The end user’s domain credential is stored in a reversible format in the Windows Credential Manager.</span></span> <span data-ttu-id="f30cd-220">因此，攻击者可以编写一个用于检索密码的程序，并可以获取用户凭据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f30cd-220">As a result, an attacker could write a program that retrieves the password and could gain access to the user’s credentials.</span></span> <span data-ttu-id="f30cd-221">您只能通过禁用终端用户凭据的存储来减少这种风险。</span><span class="sxs-lookup"><span data-stu-id="f30cd-221">You can only lessen this risk by disabling the storing of end-user credentials.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



~~~
After you have finished, click **Next**.
~~~

10. <span data-ttu-id="f30cd-222">在**Web 重定向**页面上，你可以在 med-v 工作区中输入、粘贴或导入已重定向到 Internet Explorer 的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="f30cd-222">On the **Web Redirection** page, you can enter, paste, or import a list of the URLs that are redirected to Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="f30cd-223">有关如何配置 URL 重定向信息的详细信息，请参阅[先决条件](#bkmk-prereq)。</span><span class="sxs-lookup"><span data-stu-id="f30cd-223">For more information about how to configure your URL redirection information, see [Prerequisites](#bkmk-prereq).</span></span>

   <span data-ttu-id="f30cd-224">你还可以指定如何为最终用户配置 MED-V 工作区中的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="f30cd-224">You can also specify how Internet Explorer in the MED-V workspace is configured for end users.</span></span> <span data-ttu-id="f30cd-225">默认情况下，Internet 区域安全级别设置为 "高"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-225">By default, the Internet zone security level is set to High.</span></span> <span data-ttu-id="f30cd-226">此外，还会删除某些默认浏览功能，例如地址栏。</span><span class="sxs-lookup"><span data-stu-id="f30cd-226">Also, certain default browsing capabilities, such as the address bar, are removed.</span></span> <span data-ttu-id="f30cd-227">在 MED-V 工作区中，此 Internet Explorer 默认配置为最终用户提供更安全的浏览环境。</span><span class="sxs-lookup"><span data-stu-id="f30cd-227">This default configuration of Internet Explorer in the MED-V workspace provides a more secure browsing environment for end users.</span></span>

   **<span data-ttu-id="f30cd-228">注意</span><span class="sxs-lookup"><span data-stu-id="f30cd-228">Caution</span></span>**  
   <span data-ttu-id="f30cd-229">通过更改默认设置，你可以在 MED-V 工作区中自定义 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="f30cd-229">By changing the default settings, you can customize Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="f30cd-230">但是，请注意，如果你更改默认设置以降低安全性，你可以将组织暴露给较早版本的 Internet Explorer 中提供的安全风险。</span><span class="sxs-lookup"><span data-stu-id="f30cd-230">However, realize that if you change the default settings so as to make them less secure, you can expose your organization to those security risks that are present in older versions of Internet Explorer.</span></span> <span data-ttu-id="f30cd-231">有关详细信息，请参阅[Med-v 操作的安全最佳做法](security-best-practices-for-med-v-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="f30cd-231">For more information, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).</span></span>



~~~
After you have finished, click **Next**.
~~~

11. <span data-ttu-id="f30cd-232">在 "**摘要**" 页面上，您可以查看此 med-v 工作区的包装设置。</span><span class="sxs-lookup"><span data-stu-id="f30cd-232">On the **Summary** page, you can review the packaging settings for this MED-V workspace.</span></span> <span data-ttu-id="f30cd-233">如果要更改任何设置，请单击 "**上一步**" 按钮以返回到相关页面。</span><span class="sxs-lookup"><span data-stu-id="f30cd-233">If you want to change any settings, click the **Previous** button to return to the relevant page.</span></span> <span data-ttu-id="f30cd-234">查看完设置后，单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="f30cd-234">After you have finished reviewing the settings, click **Create**.</span></span>

   <span data-ttu-id="f30cd-235">将打开 "**创建 Med-v 工作区程序包" 向导**的 "**完成**" 页面，显示程序包创建的进度。</span><span class="sxs-lookup"><span data-stu-id="f30cd-235">The **Completion** page of the **Create MED-V Workspace Package Wizard** opens to show the progress of the package creation.</span></span>

   **<span data-ttu-id="f30cd-236">注意</span><span class="sxs-lookup"><span data-stu-id="f30cd-236">Note</span></span>**  
   <span data-ttu-id="f30cd-237">MED-V 工作区程序包的创建过程可能需要几分钟才能完成，具体取决于指定 VHD 的大小。</span><span class="sxs-lookup"><span data-stu-id="f30cd-237">The MED-V workspace package creation process might take several minutes to complete, depending on the size of the VHD specified.</span></span>



~~~
If the MED-V workspace package is created successfully, the **Completion** page displays a list of the files that you created and their respective locations. The following is a list of the files that are created and their descriptions:

-   **setup.exe**—an installation program that you deploy and run on end-user computers to install the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.msi**—an installer file that you deploy to the end-user computers. The setup.exe file will run this file to install the MED-V workspaces.

-   **&lt;*vhd\_name*&gt;.medv**—a compressed VHD file that you deploy to the end-user computers. The setup.exe file uses it when it installs the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.reg**—the configuration settings that are installed when the setup.exe, &lt;*workspace\_name*&gt;.msi, and &lt;*vhd\_name*&gt;.medv files are deployed and setup.exe is run.

-   **&lt;*workspace\_name*&gt;.ps1**—a Windows PowerShell script that you can use to rebuild the registry file and re-build the MED-V workspace package.

    **Important**  
    Before deployment, you can edit configuration settings by updating the .ps1 file that has your preferred method of script editing, such as Windows PowerShell. After you change the .ps1 file, use that file to rebuild the MED-V workspace package that you deploy to your enterprise. For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).

    However, after the MED-V workspace is deployed, you must edit configuration settings through the registry. For a list and description of the configuration settings, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).
~~~



12. <span data-ttu-id="f30cd-238">单击 "**关闭**" 关闭打包向导并返回到**Med-v 工作区包装程序**。</span><span class="sxs-lookup"><span data-stu-id="f30cd-238">Click **Close** to close the packaging wizard and return to the **MED-V Workspace Packager**.</span></span>

<span data-ttu-id="f30cd-239">现在，你的 MED-V 工作区程序包已准备好在部署之前进行测试。</span><span class="sxs-lookup"><span data-stu-id="f30cd-239">Your MED-V workspace package is now ready for testing before deployment.</span></span>

## <span data-ttu-id="f30cd-240">相关主题</span><span class="sxs-lookup"><span data-stu-id="f30cd-240">Related topics</span></span>


[<span data-ttu-id="f30cd-241">使用 Windows PowerShell 配置高级设置</span><span class="sxs-lookup"><span data-stu-id="f30cd-241">Configuring Advanced Settings by Using Windows PowerShell</span></span>](configuring-advanced-settings-by-using-windows-powershell.md)

[<span data-ttu-id="f30cd-242">测试 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="f30cd-242">Testing the MED-V Workspace Package</span></span>](testing-the-med-v-workspace-package.md)

[<span data-ttu-id="f30cd-243">准备 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="f30cd-243">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)









