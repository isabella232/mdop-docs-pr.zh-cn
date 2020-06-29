---
title: 关于 MBAM 2.0 SP1
description: 关于 MBAM 2.0 SP1
author: dansimp
ms.assetid: 5ba89ed8-bb6e-407b-82c2-e2e36dd1078e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 73b92cd852d4f75f63f3dcba9f18167012b61401
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803391"
---
# 关于 MBAM 2.0 SP1

本主题介绍 Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）中的更改。 有关 MBAM 的一般说明，请参阅[MBAM 2.0 入门](getting-started-with-mbam-20-mbam-2.md)。

## <a href="" id="what-s-new-in-mbam-2-0-sp1"></a>MBAM 2.0 SP1 中的新增功能

此版本的 MBAM 提供以下新特性和功能。

### Windows 8.1、Windows Server 2012 R2 和 System Center 的支持 2012 R2 配置管理器

Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）添加了对 Windows 8.1、Windows Server 2012 R2 和 System Center 2012 R2 配置管理器的支持。

### Microsoft SQL Server 2008 R2 SP2 的支持

Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）添加对 Microsoft SQL Server 2008 R2 SP2 的支持。 如果你运行的是 Microsoft System Center Configuration Manager 2007 R2，则必须使用 Microsoft SQL Server 2008 R2 或更高版本。

### 客户反馈汇总

MBAM 2.0 SP1 包括一个修补程序，用于解决自 Microsoft BitLocker 管理和监视（MBAM）2.0 版本以来发现的问题。 作为这些更改的一部分，在运行 MBAM 与 Microsoft System Center Configuration Manager 2007 时，计算机名称字段现在将显示在 BitLocker 计算机合规性和 BitLocker 企业合规性详细信息报告中。

### 必须在自助服务门户和管理和监视网站的端口上设置防火墙例外

配置自助服务门户和管理和监视网站时，必须设置防火墙例外以通过指定的端口启用通信。 以前，MBAM 服务器安装会在 Windows 防火墙中自动打开端口。

### 配置管理器中 MBAM 报表的位置已更改

Configuration Manager 集成拓扑的 MBAM 报表现在位于 MBAM 节点内的子文件夹下。 子文件夹名称表示子文件夹中报表的语言。

### 使用 Configuration Manager 安装 MBAM 时，在主站点服务器上安装 MBAM 的功能

在使用 Configuration Manager 集成拓扑安装 MBAM 时，可以在主站点服务器或管理中心网站服务器上安装 MBAM。 以前，您需要在管理中心网站服务器上安装 MBAM。

**重要提示**  
在其上安装 MBAM 的服务器必须是你的层次结构中的顶层服务器。



对于 Microsoft System Center Configuration Manager 2007 和 Microsoft System Center 2012 配置管理器，MBAM 安装的运行方式如下所示：

-   **配置管理器 2007** ：如果在属于较大配置管理器层次结构的主站点服务器上安装 MBAM，并且具有中心网站父服务器，则 MBAM 将解析中心网站父服务器，并在该父服务器上执行所有安装操作。 安装操作包括检查先决条件以及安装 Configuration Manager 对象和报告。 例如，如果在作为中心站点父服务器的子站点的主站点服务器上安装 MBAM，则 MBAM 将在父服务器上安装所有 Configuration Manager 对象和报告。 如果在父服务器上安装 MBAM，MBAM 将在该父服务器上执行所有安装操作。

-   **System Center 2012 配置管理器**：如果在主站点服务器或中央管理服务器上安装 MBAM，MBAM 将在该网站服务器上执行所有安装操作。

### <a href="" id="-------------configuration-manager-console-must-be-installed-on-the--computer-on-which-you-install-the-mbam-server"></a> Configuration Manager 控制台必须安装在安装了 MBAM Server 的计算机上

当你通过 Configuration Manager 集成拓扑安装 MBAM 时，你必须在将安装 MBAM 的同一台计算机上安装 Configuration Manager 控制台。 如果你使用建议的体系结构（将在[入门中使用 MBAM 和配置管理器](getting-started---using-mbam-with-configuration-manager.md)中所述），请在 Configuration Manager 主站点服务器上安装 MBAM。

### Configuration Manager 集成拓扑的新设置命令行参数

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令行参数</th>
<th align="left">说明</th>
<th align="left">示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CM_SSRS_REMOTE_SERVER_NAME</p></td>
<td align="left"><p>使你能够在远程 SQL Server Reporting Services （SSRS）服务器上安装 Configuration Manager 报告，该服务器属于安装了 MBAM 的同一 Configuration Manager 站点。 你可以将值设置为远程 SSRS 点角色服务器的完全限定的域名。</p></td>
<td align="left"><p>MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME = ssrsServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>CM_REPORTS_ONLY</p></td>
<td align="left"><p>使你可以仅安装配置管理器报表，而无需其他 Configuration Manager 对象，如基线、集合和配置项目。</p>
<div class="alert">
<strong>注意</strong><br/><p>必须将此参数与 CM_REPORTS_COLLECTION_ID 参数结合。</p>
</div>
<div>

</div>
<p>有效参数值：</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul>
<p>如果要将报表仅安装到远程 SSRS 点角色服务器，则可以将此参数与 CM_SSRS_REMOTE_SERVER_NAME 参数结合使用。</p>
<p>如果不设置该参数或将其设置为 False，MBAM 安装程序将安装所有配置管理器对象，包括报告。</p></td>
<td align="left"><p>MbamSetup.exe CM_REPORTS_ONLY = True</p>
<p>CM_REPORTS_COLLECTION_ID = SMS00001</p></td>
</tr>
<tr class="odd">
<td align="left"><p>CM_REPORTS_COLLECTION_ID</p></td>
<td align="left"><p>一个现有的集合 ID，用于标识报告合规性数据将显示的集合。 你可以指定任何集合 ID。 您无需使用 "MBAM 支持的计算机" 集合 ID。</p></td>
<td align="left"><p>MbamSetup.exe CM_REPORTS_ONLY = True</p>
<p>CM_REPORTS_COLLECTION_ID = SMS00001</p></td>
</tr>
</tbody>
</table>



### 打开或关闭自助门户通知文本的功能

MBAM 2.0 SP1 使你能够在自助服务门户上关闭声明文本。 以前，默认情况下显示通知文本，您无法将其关闭。

**关闭声明文本**

1.  在安装了自助服务门户的服务器上，打开 "Internet 信息服务（IIS）"，然后浏览到 " ** &gt; Microsoft BitLocker 管理和监视网站" &gt; SelfService &gt; 应用程序设置**。

2.  在 "**名称**" 列中，选择 " **DisplayNotice**"，然后将值设置为**false**。

### 能够本地化将用户指向更多自助服务门户信息的 HelpdeskText 语句

你可以配置自助服务门户 "HelpdeskText" 语句的本地化版本，这将告知最终用户使用自助服务门户时如何获取其他帮助。 如果为语句配置本地化的文本，如以下说明中所述，MBAM 将显示本地化版本。 如果 MBAM 未找到本地化版本，它将显示**HelpdeskText**参数中的值。

**显示 HelpdeskText 语句的本地化版本**

1.  在安装了自助服务门户的服务器上，打开 IIS 并浏览到 " ** &gt; Microsoft BitLocker 管理和监视网站" &gt; SelfService &gt; 应用程序设置**。

2.  在 "**操作**" 窗格中，单击 "**添加**" 以打开 "**添加应用程序设置**" 对话框。

3.  在 "**名称**" 字段中，键入**HelpdeskText**\ _ &lt; *语言* &gt; ，其中 &lt; *语言* &gt; 是文本的相应语言代码。 例如，若要使用西班牙语创建本地化的 HelpdeskText 语句，请将参数命名为 HelpdeskText \ _es。 有关可使用的有效语言代码的列表，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)。

4.  在 "**值**" 字段中，键入要向最终用户显示的本地化文本。

### 能够本地化自助服务门户 HelpdeskURL

你可以配置自服务门户 HelpdeskURL 的本地化版本，以便默认显示给最终用户。 如果创建本地化版本（如以下说明所述），MBAM 将查找并显示本地化版本。 如果 MBAM 未找到本地化版本，它将显示为 HelpDeskURL 参数配置的 URL。

**显示本地化的 HelpdeskURL**

1.  在安装了自助服务门户的服务器上，打开 IIS 并浏览到 " ** &gt; Microsoft BitLocker 管理和监视网站" &gt; SelfService &gt; 应用程序设置**。

2.  在 "**操作**" 窗格中，单击 "**添加**" 以打开 "**添加应用程序设置**" 对话框。

3.  在 "**名称**" 字段中，键入**HelpdeskURL**\ _ &lt; *语言* &gt; ，其中 &lt; *language* &gt; "语言" 是 URL 的相应语言代码。 例如，若要在西班牙语中创建本地化的 HelpdeskURL，请将参数命名为 HelpdeskURL \ _es。 有关可使用的有效语言代码的列表，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)。

4.  在 "**值**" 字段中，键入要向最终用户显示的本地化 HelpdeskURL。

### 能够本地化自助服务门户通知文本

你可以将本地化声明文本配置为在自助服务门户中默认显示给最终用户。 显示声明文本的 notice.txt 文件位于以下根目录中：

&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\

若要显示本地化声明文本，请创建一个已本地化的 notice.txt 文件，并将其保存在以下目录中的特定语言文件夹下：

&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\

MBAM 根据以下规则显示声明文本：

-   如果在相应的语言文件夹中创建已本地化的 notice.txt 文件，MBAM 将显示本地化声明文本。

-   如果 MBAM 没有找到 notice.txt 文件的本地化版本，它将在默认 notice.txt 文件中显示文本。

-   如果 MBAM 没有找到默认的 notice.txt 文件，它将在自助服务门户中显示默认文本。

**注意**  
如果最终用户的浏览器设置为不具有相应语言子文件夹或 notice.txt 的语言，则显示以下根目录中 notice.txt 文件中的文本：

&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\



**创建本地化的 notice.txt 文件**

1.  在安装了自助服务门户的服务器上，在 &lt; *language* &gt; 以下目录中创建一个语言文件夹，其中的 &lt; *语言* &gt; 表示本地化语言的名称：

    &lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\

    **注意**  
    某些语言文件夹已存在，因此你可能不需要创建一个。 如果确实需要创建语言文件夹，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)，了解可用于 &lt; *语言*文件夹的有效名称的列表 &gt; 。



2.  创建一个包含本地化声明文本的 notice.txt 文件。

3.  将 notice.txt 文件保存在 " &lt; *语言*" &gt; 文件夹中。 例如，若要使用西班牙语创建本地化的 notice.txt 文件，请将本地化的 notice.txt 文件保存在以下文件夹中：

    &lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\es-es

## 升级到 MBAM 2.0 SP1


你可以从 MBAM 的任何早期版本升级到 MBAM 2.0 SP1。

### 升级 MBAM 基础结构

你可以将 MBAM Server 基础结构升级到 MBAM 2.0 SP1，如下所示：

**手动就地服务器更换**：必须手动卸载现有的 MBAM 服务器基础结构，然后安装 MBAM 2.0 SP1 服务器基础结构。 不必删除数据库即可进行升级。 而是选择已创建 MBAM 早期版本的现有数据库。 MBAM 2.0 SP1 升级安装然后将现有数据库迁移到 MBAM 2.0 SP1。

**分布式客户端升级**：如果你使用的是独立的 MBAM 拓扑，则可以在安装 MBAM 2.0 SP1 服务器基础结构后逐步升级 MBAM 客户端。

升级 MBAM 服务器基础结构后，MBAM 1.0 或2.0 客户端将成功向 MBAM 2.0 SP1 服务器报告，并将存储恢复数据，但合规性将基于当前已安装的 MBAM 客户端版本的可用策略。 若要针对 MBAM 2.0 SP1 策略启用报告，必须将客户端计算机升级到 MBAM 2.0 SP1。 你可以将客户端计算机升级到 MBAM 2.0 SP1 客户端，而不卸载以前的客户端，并且客户端将基于 MBAM 2.0 SP1 策略开始应用和报告。

有关升级 MBAM 服务器的详细信息，请参阅[从早期版本的 MBAM 升级](upgrading-from-previous-versions-of-mbam.md)。

### 将 MBAM 客户端升级到 MBAM 2.0 SP1

若要将最终用户计算机升级到 MBAM 2.0 SP1 客户端，请在每台客户端计算机上运行**MbamClientSetup.exe** 。 安装程序会自动将客户端更新到 MBAM 2.0 SP1 客户端。 安装完成后，客户端计算机无需重新启动，MBAM 2.0 SP1 客户端将开始应用并报告 MBAM 2.0 SP1 策略。

如果你将 MBAM 与 Configuration Manager 配合使用，则必须将 MBAM 客户端计算机升级到 MBAM 2.0 SP1。

有关升级 MBAM 客户端计算机的详细信息，请参阅[从早期版本的 MBAM 升级](upgrading-from-previous-versions-of-mbam.md)。

## 通过 Configuration Manager 安装或升级到 MBAM 2.0 SP1


本部分介绍将 MBAM 2.0 SP1 安装为新安装或升级到以前的 MBAM 2.0 SP1 安装时的要求。

### 如果你将 MBAM 与 Configuration Manager 配合使用，则安装 MBAM 2.0 SP1 所需的文件

如果你是第一次安装 MBAM，而你将 MBAM 2.0 SP1 与 System Center Configuration Manager 配合使用，则必须创建或编辑 mof 文件，以使 MBAM 能够使用 Configuration Manager 正常工作。

-   **配置 mof 文件**

    -   如果你使用的是 Configuration Manager 2007，则必须编辑配置 mof 文件，方法是从项目中完成步骤 3**更新配置 mof 文件（如果升级到 MBAM 2.0 SP1，并将 MBAM 与 Configuration Manager 2007 一起使用**，这将在此项之后使用）。

    -   如果您使用的是 System Center 2012 配置管理器，请按照[编辑配置 Mof 文件](edit-the-configurationmof-file.md)中的说明编辑配置 mof 文件。

-   **sms \ _def mof 文件**-按照[创建或编辑 sms \ _def mof 文件](create-or-edit-the-sms-defmof-file.md)中的说明进行操作。

### 如果升级到 MBAM 2.0 SP1 并将 MBAM 与 Configuration Manager 2007 结合使用，请更新配置 mof 文件

如果你要升级到 MBAM 2.0 SP1，而你将 MBAM 与 Configuration Manager 2007 结合使用，则必须更新配置 mof 文件，以确保 MBAM 2.0 SP1 正常工作。

**若要更新 configuration mof 文件，请执行以下操作：**

1.  在 Configuration Manager 服务器上，浏览到配置 mof 文件的位置：

    &lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv\\

    在默认安装中，安装位置是%systemdrive%\\Program Files （x86） \\Microsoft Configuration Manager。

2.  查看追加到配置 mof 文件中的代码块，然后将其删除。 代码块将与以下步骤中所示类似。

3.  复制以下代码块，然后将其追加到配置 mof 文件，将以下必需的 MBAM 类添加到该文件：

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL) 

    [Union, ViewSources{"select DeviceId, BitlockerPersistentVolumeId, BitLockerManagementPersistentVolumeId, BitLockerManagementVolumeType, DriveLetter, Compliant, ReasonsForNonCompliance, KeyProtectorTypes, EncryptionMethod, ConversionStatus, ProtectionStatus, IsAutoUnlockEnabled from Mbam_Volume"}, ViewSpaces{"\\\\.\\root\\microsoft\\mbam"}, dynamic, Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class Win32_BitLockerEncryptionDetails
    {
        [PropertySources{"DeviceId"},key]
        String     DeviceId;
        [PropertySources{"BitlockerPersistentVolumeId"}]
        String     BitlockerPersistentVolumeId;
        [PropertySources{"BitLockerManagementPersistentVolumeId"}]
        String     MbamPersistentVolumeId;
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        [PropertySources{"BitLockerManagementVolumeType"}]
        SInt32     MbamVolumeType;
        [PropertySources{"DriveLetter"}]
        String     DriveLetter;
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        [PropertySources{"Compliant"}]
        SInt32     Compliant;
        [PropertySources{"ReasonsForNonCompliance"}]
        SInt32     ReasonsForNonCompliance[];
        [PropertySources{"KeyProtectorTypes"}]
        SInt32     KeyProtectorTypes[];
        [PropertySources{"EncryptionMethod"}]
        SInt32     EncryptionMethod;
        [PropertySources{"ConversionStatus"}]
        SInt32     ConversionStatus;
        [PropertySources{"ProtectionStatus"}]
        SInt32     ProtectionStatus;
        [PropertySources{"IsAutoUnlockEnabled"}]
        Boolean     IsAutoUnlockEnabled;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
     [DYNPROPS]
    Class Win32Reg_MBAMPolicy
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate;
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

     [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy
    {
        KeyName="BitLocker policy";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [DYNPROPS]
    Class Win32Reg_MBAMPolicy_64
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

    [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy_64
    {
        KeyName="BitLocker policy 64";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
         [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,OperatingSystemSKU from Win32_OperatingSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_OperatingSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"OperatingSystemSKU"}]
        uint32     SKU;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,PCSystemType from Win32_ComputerSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_ComputerSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"PCSystemType"}]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================

    ```

### MBAM 2.0 SP1 的翻译

MBAM 2.0 SP1 现已提供以下语言版本：

-   英语（美国） en-us
-   法语（法国） fr-fr
-   意大利语（意大利） it
-   德语（德国） de
-   西班牙语、国际排序（西班牙） es
-   朝鲜语（韩国） ko-KR
-   日语（日本） ja-jp
-   葡萄牙语（巴西） pt-BR
-   俄语（俄罗斯） ru-RU
-   繁体中文 zh-cn&platform-幼圆
-   中文简体 zh-cn&platform-CN

## 如何获取 MDOP 技术

MBAM 2.0 SP1 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相关主题

[MBAM 2.0 SP1 发行说明](release-notes-for-mbam-20-sp1.md)









