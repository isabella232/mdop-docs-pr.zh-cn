---
title: 为 MED-V 配置 Windows Virtual PC 映像
description: 为 MED-V 配置 Windows Virtual PC 映像
author: dansimp
ms.assetid: d87a0df8-9e08-4d1e-bfb0-9dc3cebf0d28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 340754b33576651c8ba89c85f369c48c0a0ab957
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804044"
---
# <span data-ttu-id="f40e1-103">为 MED-V 配置 Windows Virtual PC 映像</span><span class="sxs-lookup"><span data-stu-id="f40e1-103">Configuring a Windows Virtual PC Image for MED-V</span></span>


<span data-ttu-id="f40e1-104">在安装了要包括在 MED-V 图像中的所有内容后，可以将该映像配置为在 Microsoft 企业桌面虚拟化（MED-V）2.0 中使用。</span><span class="sxs-lookup"><span data-stu-id="f40e1-104">After you have installed everything that you want to include in your MED-V image, you can configure the image for use in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span> <span data-ttu-id="f40e1-105">本部分中的主题提供了配置 MED-V 图像的指南，以便在创建 MED-V 工作区程序包之前首先运行设置。</span><span class="sxs-lookup"><span data-stu-id="f40e1-105">The topics in this section provide guidance for configuring your MED-V image to run first time setup before you create your MED-V workspace package.</span></span>

<span data-ttu-id="f40e1-106">第一次设置为最终用户准备 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="f40e1-106">First time setup prepares the MED-V workspace for an end user.</span></span> <span data-ttu-id="f40e1-107">该过程从在 MED-V 工作区中打包的映像创建虚拟机，然后在虚拟机上运行 Windows 小型安装。</span><span class="sxs-lookup"><span data-stu-id="f40e1-107">The process creates a virtual machine from the image packaged in the MED-V workspace and then runs Windows Mini-Setup on the virtual machine.</span></span> <span data-ttu-id="f40e1-108">这包括运行自定义安装脚本和首次安装完成应用程序 FtsCompletion.exe。</span><span class="sxs-lookup"><span data-stu-id="f40e1-108">This includes the running of both custom setup scripts and the first time setup completion application, FtsCompletion.exe.</span></span>

<span data-ttu-id="f40e1-109">按照以下步骤配置你的 MED-V 映像，以便首次运行设置：</span><span class="sxs-lookup"><span data-stu-id="f40e1-109">Follow these steps to configure your MED-V image for running first time setup:</span></span>

1. <span data-ttu-id="f40e1-110">作为一个选项，你可以在继续配置 Windows 虚拟 PC 映像之前压缩虚拟硬盘（VHD）以回收空磁盘空间并减小 VHD 的大小。</span><span class="sxs-lookup"><span data-stu-id="f40e1-110">As an option, you can compact the virtual hard disk (VHD) to reclaim empty disk space and reduce the size of the VHD before you continue with configuring the Windows Virtual PC image.</span></span> <span data-ttu-id="f40e1-111">有关详细信息，请参阅[压缩 Med-v 虚拟硬盘](compacting-the-med-v-virtual-hard-disk.md)。</span><span class="sxs-lookup"><span data-stu-id="f40e1-111">For more information, see [Compacting the MED-V Virtual Hard Disk](compacting-the-med-v-virtual-hard-disk.md).</span></span>

2. <span data-ttu-id="f40e1-112">自定义虚拟机设置过程。</span><span class="sxs-lookup"><span data-stu-id="f40e1-112">Customize the virtual machine setup process.</span></span>

3. <span data-ttu-id="f40e1-113">使用 Sysprep 密封 MED-V 映像。</span><span class="sxs-lookup"><span data-stu-id="f40e1-113">Seal the MED-V image by using Sysprep.</span></span>

   **<span data-ttu-id="f40e1-114">自定义虚拟机设置过程</span><span class="sxs-lookup"><span data-stu-id="f40e1-114">Customizing the Virtual Machine Setup Process</span></span>**

4. <span data-ttu-id="f40e1-115">作为准备用于 MED-V 的映像的一部分，你可以配置虚拟机上的各种设置，例如指定运行 Windows 更新的设置。</span><span class="sxs-lookup"><span data-stu-id="f40e1-115">As part of preparing your image for use with MED-V, you can configure various settings on the virtual machine, such as specifying the settings for running Windows Update.</span></span> <span data-ttu-id="f40e1-116">先指定所有必需的虚拟机设置，然后再创建 MED-V 工作区程序包。</span><span class="sxs-lookup"><span data-stu-id="f40e1-116">Specify all the necessary virtual machine settings before you create the MED-V workspace package.</span></span>

5. <span data-ttu-id="f40e1-117">在创建 MED-V 工作区程序包之前，我们建议你在虚拟机上禁用还原点，以防止差异磁盘无限增长。</span><span class="sxs-lookup"><span data-stu-id="f40e1-117">Before you create the MED-V workspace package, we recommend that you disable restore points on the virtual machine to prevent the differencing disk from growing unbounded.</span></span> <span data-ttu-id="f40e1-118">有关详细信息，请参阅[如何在 WINDOWS XP 中关闭和打开系统还原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。</span><span class="sxs-lookup"><span data-stu-id="f40e1-118">For more information, see [How to turn off and turn on System Restore in Windows XP](https://go.microsoft.com/fwlink/?LinkId=195927) (https://go.microsoft.com/fwlink/?LinkId=195927).</span></span>

   **<span data-ttu-id="f40e1-119">注意</span><span class="sxs-lookup"><span data-stu-id="f40e1-119">Note</span></span>**  
   <span data-ttu-id="f40e1-120">你可以设置 Sysprep .inf 文件，以便在首次运行设置时禁用还原点。</span><span class="sxs-lookup"><span data-stu-id="f40e1-120">You can set up your Sysprep.inf file to disable restore points when first time setup is run.</span></span> <span data-ttu-id="f40e1-121">有关设置此 GuiRunOnce 密钥的示例，请参阅本部分后面的示例 Sysprep.inf 文件。</span><span class="sxs-lookup"><span data-stu-id="f40e1-121">For an example of setting this GuiRunOnce key, see the sample Sysprep.inf file later in this section.</span></span>



6. <span data-ttu-id="f40e1-122">将安装过程配置为运行 "最小化安装"，而不是默认的 "欢迎使用 Windows"。</span><span class="sxs-lookup"><span data-stu-id="f40e1-122">Configure the setup process to run Mini-Setup instead of the default Windows Welcome.</span></span> <span data-ttu-id="f40e1-123">必须使用 **-微型**开关运行 Sysprep 工具，或者在图形用户界面中选中 " **MiniSetup** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="f40e1-123">You must either run the Sysprep tool by using the **-mini** switch, or select the **MiniSetup** check box in the graphical user interface.</span></span> <span data-ttu-id="f40e1-124">有关详细信息，请参阅[如何用 Sysprep 密封图像](#bkmk-seal)。</span><span class="sxs-lookup"><span data-stu-id="f40e1-124">For more information, see [How to Seal the Image with Sysprep](#bkmk-seal).</span></span>

   **<span data-ttu-id="f40e1-125">第一次调用设置完成文件</span><span class="sxs-lookup"><span data-stu-id="f40e1-125">Calling the First time setup Completion File</span></span>**

   1.  <span data-ttu-id="f40e1-126">作为 MED-V 来宾代理安装的一部分，包括名为 FtsCompletion.exe 的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="f40e1-126">An executable called FtsCompletion.exe is included as part of the installation of the MED-V Guest Agent.</span></span> <span data-ttu-id="f40e1-127">默认情况下，它位于 "**程序文件-Microsoft 企业版虚拟化**" 下的 med-v 图像的系统驱动器中。</span><span class="sxs-lookup"><span data-stu-id="f40e1-127">By default, it is located in the system drive of your MED-V image under **Program Files – Microsoft Enterprise Desktop Virtualization**.</span></span>

       **<span data-ttu-id="f40e1-128">重要提示</span><span class="sxs-lookup"><span data-stu-id="f40e1-128">Important</span></span>**  
       <span data-ttu-id="f40e1-129">第一次设置过程中的最后一步，您必须运行此可执行程序。</span><span class="sxs-lookup"><span data-stu-id="f40e1-129">As the final step in the first time setup process, you must run this executable program.</span></span> <span data-ttu-id="f40e1-130">为其调用可执行程序的用户必须是来宾的本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="f40e1-130">The user for whom the executable program is being called must be a member of the guest’s local administrator group.</span></span>



   2.  <span data-ttu-id="f40e1-131">你可以决定希望如何调用此可执行程序，例如，通过使用 MED-V 工作区部署的脚本。</span><span class="sxs-lookup"><span data-stu-id="f40e1-131">You can decide how you want to call this executable program, for example, through a script that is deployed with the MED-V workspace.</span></span> <span data-ttu-id="f40e1-132">你可以将此可执行文件作为 Sysprep.inf 文件的最后一行进行调用。</span><span class="sxs-lookup"><span data-stu-id="f40e1-132">You can call this executable as the last line of your Sysprep.inf file.</span></span> <span data-ttu-id="f40e1-133">有关如何在 Sysprep.inf 文件中调用此可执行程序的示例，请参阅本部分后面的示例文件。</span><span class="sxs-lookup"><span data-stu-id="f40e1-133">For an example of how to call this executable program in your Sysprep.inf file, see the sample file later in this section.</span></span>

<span data-ttu-id="f40e1-134">完成对 MED-V 映像的自定义后，即可使用 Sysprep 对图像进行密封。</span><span class="sxs-lookup"><span data-stu-id="f40e1-134">After you have completed customization of your MED-V image, you are ready to seal the image by using Sysprep.</span></span>

<a href="" id="bkmk-seal"></a>**<span data-ttu-id="f40e1-135">使用 Sysprep 密封 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="f40e1-135">Sealing the MED-V Image by Using Sysprep</span></span>**

1.  <span data-ttu-id="f40e1-136">系统准备工具（Sysprep）是一种技术，可用于在整个网络中通过最少的管理员或 IT 人员干预执行基于映像的安装。</span><span class="sxs-lookup"><span data-stu-id="f40e1-136">The System Preparation tool (Sysprep) is a technology that you can use to perform image-based installations throughout the network with minimal intervention by an administrator or IT-Professional.</span></span>

2.  <span data-ttu-id="f40e1-137">在 MED-V 环境中，你可以使用 Sysprep 在首次启动每个 MED-V 工作区时为其分配唯一的安全 Id （SID）和其他设置。</span><span class="sxs-lookup"><span data-stu-id="f40e1-137">In a MED-V environment, you can use Sysprep to assign unique security IDs (SID) and other settings to each MED-V workspace the first time that they are started.</span></span>

    **<span data-ttu-id="f40e1-138">注意</span><span class="sxs-lookup"><span data-stu-id="f40e1-138">Note</span></span>**  
    <span data-ttu-id="f40e1-139">有关如何使用 Sysprep 的详细信息，请参阅[Sysprep 技术参考](https://go.microsoft.com/fwlink/?LinkId=195930)（ https://go.microsoft.com/fwlink/?LinkId=195930) 。</span><span class="sxs-lookup"><span data-stu-id="f40e1-139">For more information about how to use Sysprep, see [Sysprep Technical Reference](https://go.microsoft.com/fwlink/?LinkId=195930) (https://go.microsoft.com/fwlink/?LinkId=195930).</span></span>



~~~
**Caution**  
When you use non-ASCII characters in the Sysprep.inf file, you must save the file by using the encoding appropriate for the characters entered. Windows XP expects the Sysprep.inf file to be encoded by using the code page for the language that you are targeting.

You must also make sure that the System Locale of the computers to which the MED-V workspace is deployed is set to handle the language specific characters that might be present in the Sysprep.inf file. To change the settings for the System Locale, follow these steps:

1.  To open Region and Language, click **Start**, click **Control Panel**, and then click **Region and Language**.

2.  Click the **Administrative** tab, and then click **Change System Locale** under **Language for non-Unicode programs**.

    If you are prompted for an administrator password or confirmation, type the administrator password or provide confirmation.

3.  Select your preferred language and then click **OK**.



**To configure Sysprep on the MED-V Guest Computer**

1.  Create a folder named *Sysprep* in the root of the MED-V image system drive.

2.  Download the deploy.cab file. For more information, see [Windows XP Service Pack 3 Deployment Tools](https://go.microsoft.com/fwlink/?LinkId=195928) From the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195928).

3.  From the deploy.cab file, copy or extract the Setupmgr.exe, Sysprep.exe, and Setupcl.exe files to the Sysprep folder.

4.  In the Sysprep folder, run **Setup Manager** (Setupmgr.exe) to create a Sysprep.inf answer file.

    Or, you can create this file manually or use your company’s existing file. For more information, see [How to use the Sysprep tool to automate successful deployment of Windows XP](https://go.microsoft.com/fwlink/?LinkId=195929) (https://go.microsoft.com/fwlink/?LinkId=195929).

5.  Follow the **Setup Manager** wizard.

    **Important**  
    You must configure the MED-V guest to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.



    **Caution**  
    When you configure a proxy account for joining virtual machines to the domain, know that it is possible for an end user to obtain the proxy account credentials. Take all the necessary security precautions to minimize risk, such as limiting account user rights. For more information about security concerns when you configure a Windows Virtual PC image for MED-V, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).



    If end users must provide information during the first time setup process based on the parameters specified in the Sysprep.inf file, you must also specify that first time setup is run in **Attended** mode when you are creating your MED-V workspace package. If no information will be required from the end user, you can specify that first time setup is run in **Unattended** mode when you are creating your MED-V workspace package. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode. This requires that you provide all of the required settings information as you continue through the **Setup Manager** wizard.

    **Caution**  
    If you have set a local policy or registry entry to include a service level agreement (SLA) in your image (VHD), you must specify that first time setup is run in **Attended** mode or first time setup will fail. Or, a MED-V best practice is to enforce the SLA through Group Policy later so that the SLA is displayed to the end user after first time setup is finished.



    **Note**  
    You can configure the MED-V workspace to set certain Sysprep.inf settings based on the configuration of the host and the identity of the end user. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).



6.  Seal the MED-V image.

    **Important**  
    We recommend that you make a backup copy of the MED-V image before sealing it.



    After you have completed all the steps in the **Setup Manager** wizard, you are ready to run Sysprep to seal the MED-V image.

**To run Sysprep**

1.  Run the System Preparation Tool (Sysprep.exe) from the *Sysprep* folder that you created when you configured Sysprep in the MED-V virtual machine.

2.  In the warning message box that appears, click **OK**.

3.  In the **Options** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes. Also, make sure that the **Shutdown mode** box is set to **Shut down**.

4.  Click **Reseal**. This removes identity information and clears event logs to prepare for first time setup.

5.  If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and then change the selections.

6.  Click **OK** to complete the system preparation process.

After you have run Sysprep on your MED-V image, the virtual machine shuts down and is ready for use in creating a MED-V workspace.
~~~

## <span data-ttu-id="f40e1-140">示例</span><span class="sxs-lookup"><span data-stu-id="f40e1-140">Example</span></span>


<span data-ttu-id="f40e1-141">下面是一个 Sysprep.inf 文件的示例。</span><span class="sxs-lookup"><span data-stu-id="f40e1-141">Here is an example of a Sysprep.inf file.</span></span>

``` syntax
;SetupMgrTag
[GuiUnattended]
    EncryptedAdminPassword=NO
    TimeZone=10
    OEMDuplicatorstring="MED_V v2 Host"
    AdminPassword="administrator"
    AutoLogon=Yes
    AutoLogonCount=1
    OEMSkipRegional=1
    OemSkipWelcome=1

[UserData]
    ProductKey=
    FullName="MED-V User"
    OrgName="Contoso"
    ComputerName=*

[Identification]
    JoinDomain=domain.corp.contoso.com
    DomainAdmin=UserName
    DomainAdminPassword=Password

[Networking]
    InstallDefaultComponents=Yes

[Branding]
    BrandIEUsingUnattended=Yes

[Proxy]
    Proxy_Enable=0
    Use_Same_Proxy=0

[Unattended]
    InstallFilesPath=C:\sysprep\i386
    TargetPath=\WINDOWS
    UpdateServerProfileDirectory=1
    OemSkipEula=Yes

[RegionalSettings]
    LanguageGroup=1
    Language=00000409

[GuiRunOnce]
    Command0="wmic /namespace:\\root\default path SystemRestore call Disable %SystemDrive%\"
    Command1="c:\Program Files\Microsoft Enterprise Desktop Virtualization\FtsCompletion.exe"

[sysprepcleanup]
```

## <span data-ttu-id="f40e1-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="f40e1-142">Related topics</span></span>


[<span data-ttu-id="f40e1-143">创建 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="f40e1-143">Create a MED-V Workspace Package</span></span>](create-a-med-v-workspace-package.md)

[<span data-ttu-id="f40e1-144">准备 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="f40e1-144">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)









