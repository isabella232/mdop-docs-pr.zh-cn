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
# 为 MED-V 配置 Windows Virtual PC 映像


在安装了要包括在 MED-V 图像中的所有内容后，可以将该映像配置为在 Microsoft 企业桌面虚拟化（MED-V）2.0 中使用。 本部分中的主题提供了配置 MED-V 图像的指南，以便在创建 MED-V 工作区程序包之前首先运行设置。

第一次设置为最终用户准备 MED-V 工作区。 该过程从在 MED-V 工作区中打包的映像创建虚拟机，然后在虚拟机上运行 Windows 小型安装。 这包括运行自定义安装脚本和首次安装完成应用程序 FtsCompletion.exe。

按照以下步骤配置你的 MED-V 映像，以便首次运行设置：

1. 作为一个选项，你可以在继续配置 Windows 虚拟 PC 映像之前压缩虚拟硬盘（VHD）以回收空磁盘空间并减小 VHD 的大小。 有关详细信息，请参阅[压缩 Med-v 虚拟硬盘](compacting-the-med-v-virtual-hard-disk.md)。

2. 自定义虚拟机设置过程。

3. 使用 Sysprep 密封 MED-V 映像。

   **自定义虚拟机设置过程**

4. 作为准备用于 MED-V 的映像的一部分，你可以配置虚拟机上的各种设置，例如指定运行 Windows 更新的设置。 先指定所有必需的虚拟机设置，然后再创建 MED-V 工作区程序包。

5. 在创建 MED-V 工作区程序包之前，我们建议你在虚拟机上禁用还原点，以防止差异磁盘无限增长。 有关详细信息，请参阅[如何在 WINDOWS XP 中关闭和打开系统还原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。

   **注意**  
   你可以设置 Sysprep .inf 文件，以便在首次运行设置时禁用还原点。 有关设置此 GuiRunOnce 密钥的示例，请参阅本部分后面的示例 Sysprep.inf 文件。



6. 将安装过程配置为运行 "最小化安装"，而不是默认的 "欢迎使用 Windows"。 必须使用 **-微型**开关运行 Sysprep 工具，或者在图形用户界面中选中 " **MiniSetup** " 复选框。 有关详细信息，请参阅[如何用 Sysprep 密封图像](#bkmk-seal)。

   **第一次调用设置完成文件**

   1.  作为 MED-V 来宾代理安装的一部分，包括名为 FtsCompletion.exe 的可执行文件。 默认情况下，它位于 "**程序文件-Microsoft 企业版虚拟化**" 下的 med-v 图像的系统驱动器中。

       **重要提示**  
       第一次设置过程中的最后一步，您必须运行此可执行程序。 为其调用可执行程序的用户必须是来宾的本地管理员组的成员。



   2.  你可以决定希望如何调用此可执行程序，例如，通过使用 MED-V 工作区部署的脚本。 你可以将此可执行文件作为 Sysprep.inf 文件的最后一行进行调用。 有关如何在 Sysprep.inf 文件中调用此可执行程序的示例，请参阅本部分后面的示例文件。

完成对 MED-V 映像的自定义后，即可使用 Sysprep 对图像进行密封。

<a href="" id="bkmk-seal"></a>**使用 Sysprep 密封 MED-V 映像**

1.  系统准备工具（Sysprep）是一种技术，可用于在整个网络中通过最少的管理员或 IT 人员干预执行基于映像的安装。

2.  在 MED-V 环境中，你可以使用 Sysprep 在首次启动每个 MED-V 工作区时为其分配唯一的安全 Id （SID）和其他设置。

    **注意**  
    有关如何使用 Sysprep 的详细信息，请参阅[Sysprep 技术参考](https://go.microsoft.com/fwlink/?LinkId=195930)（ https://go.microsoft.com/fwlink/?LinkId=195930) 。



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

## 示例


下面是一个 Sysprep.inf 文件的示例。

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

## 相关主题


[创建 MED-V 工作区程序包](create-a-med-v-workspace-package.md)

[准备 MED-V 映像](prepare-a-med-v-image.md)









