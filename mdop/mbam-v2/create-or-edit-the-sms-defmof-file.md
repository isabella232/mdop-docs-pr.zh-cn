---
title: 创建或编辑 Sms \ _def 的 mof 文件
description: 创建或编辑 Sms \ _def 的 mof 文件
author: dansimp
ms.assetid: d1747e43-484e-4031-a63b-6342fe588aa2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/04/2017
ms.openlocfilehash: 15f1d1a1c19cb9b19b7d83534e035d5410720ce9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803383"
---
# <span data-ttu-id="96d5c-103">创建或编辑 Sms \ _def 的 mof 文件</span><span class="sxs-lookup"><span data-stu-id="96d5c-103">Create or Edit the Sms\_def.mof File</span></span>


<span data-ttu-id="96d5c-104">若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，您必须创建或编辑 Sms \ _def 的 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="96d5c-104">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to create or edit the Sms\_def.mof file.</span></span>

<span data-ttu-id="96d5c-105">如果您使用的是 SystemCenter2012 ConfigurationManager，则必须创建该文件。</span><span class="sxs-lookup"><span data-stu-id="96d5c-105">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span>

<span data-ttu-id="96d5c-106">在 Configuration Manager 2007 中，文件已存在，因此只需对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="96d5c-106">In Configuration Manager 2007, the file already exists, so you only have to edit it.</span></span> <span data-ttu-id="96d5c-107">**不要覆盖现有文件**。</span><span class="sxs-lookup"><span data-stu-id="96d5c-107">**Do not overwrite the existing file**.</span></span>

<span data-ttu-id="96d5c-108">在以下部分中，完成与你正在使用的 Configuration Manager 版本对应的说明。</span><span class="sxs-lookup"><span data-stu-id="96d5c-108">In the following sections, complete the instructions that correspond to the version of Configuration Manager that you are using.</span></span>

**<span data-ttu-id="96d5c-109">创建 SystemCenter2012 ConfigurationManager 的 Sms \ _def mof 文件</span><span class="sxs-lookup"><span data-stu-id="96d5c-109">To create the Sms\_def.mof file for SystemCenter2012 ConfigurationManager</span></span>**

1.  <span data-ttu-id="96d5c-110">在 Configuration Manager 服务器上，浏览到要在其中创建 Sms \ _def mof 文件（例如桌面）的位置。</span><span class="sxs-lookup"><span data-stu-id="96d5c-110">On the Configuration Manager Server, browse to the location where you have to create the Sms\_def.mof file, for example, the Desktop.</span></span>

2.  <span data-ttu-id="96d5c-111">创建一个名为**Sms \ _def 的**文本文件，然后复制以下代码以使用下列 Sms \ _def 将文件填充到该文件。 MBAM 类：</span><span class="sxs-lookup"><span data-stu-id="96d5c-111">Create a text file called **Sms\_def.mof** and copy the following code to populate the file with the following Sms\_def.mof MBAM classes:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL)
    [ SMS_Report (TRUE),
      SMS_Group_Name ("BitLocker Encryption Details"),
      SMS_Class_ID ("MICROSOFT|BITLOCKER_DETAILS|1.0")]
    class Win32_BitLockerEncryptionDetails : SMS_Class_Template
    {
        [ SMS_Report (TRUE), key ]
        String     DeviceId;
        [ SMS_Report (TRUE) ]
        String     BitlockerPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        String     MbamPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        SInt32     MbamVolumeType;
        [ SMS_Report (TRUE) ]
        String     DriveLetter;
        [ SMS_Report (TRUE) ]
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        SInt32     Compliant;
        [ SMS_Report (TRUE) ]
        SInt32     ReasonsForNonCompliance[];
        [ SMS_Report (TRUE) ]
        SInt32     KeyProtectorTypes[];
        [ SMS_Report (TRUE) ]
        SInt32     EncryptionMethod;
        [ SMS_Report (TRUE) ]
        SInt32     ConversionStatus;
        [ SMS_Report (TRUE) ]
        SInt32     ProtectionStatus;
        [ SMS_Report (TRUE) ]
        Boolean     IsAutoUnlockEnabled;
    };
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")

    #pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0")]

    Class Win32Reg_MBAMPolicy: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;

        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser;
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    //Read Win32_OperatingSystem.SKU WMI property in a new class - because SKU is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Operating System Ex"),
      SMS_Class_ID   ("MICROSOFT|OPERATING_SYSTEM_EXT|1.0") ]
    class CCM_OperatingSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
            string     Name;
        [SMS_Report (TRUE) ]
            uint32     SKU;
    };

    //Read Win32_ComputerSystem.PCSystemType WMI property in a new class - because PCSystemType is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Computer System Ex"),
      SMS_Class_ID   ("MICROSOFT|COMPUTER_SYSTEM_EXT|1.0") ]
    class CCM_ComputerSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
        string     Name;
        [SMS_Report (TRUE) ]
        uint16     PCSystemType;
    };
    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================
    ```

3.  <span data-ttu-id="96d5c-112">通过执行下列操作导入**Sms \ _def 的 mof**文件：</span><span class="sxs-lookup"><span data-stu-id="96d5c-112">Import the **Sms\_def.mof** file by doing the following:</span></span>

    1.  <span data-ttu-id="96d5c-113">打开**SystemCenter2012 ConfigurationManager 控制台**，然后选择 "**管理**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="96d5c-113">Open the **SystemCenter2012 ConfigurationManager console** and select the **Administration** tab.</span></span>

    2.  <span data-ttu-id="96d5c-114">在 "**管理**" 选项卡上，选择 "**客户端设置**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-114">On the **Administration** tab, select **Client Settings**.</span></span>

    3.  <span data-ttu-id="96d5c-115">右键单击 "**默认客户端设置**"，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-115">Right-click **Default Client Settings**, and then select **Properties**.</span></span>

    4.  <span data-ttu-id="96d5c-116">在 "**默认设置**" 窗口中，选择 "**硬件清单**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-116">In the **Default Settings** window, select **Hardware Inventory**.</span></span>

    5.  <span data-ttu-id="96d5c-117">单击 "**设置类**"，然后单击 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-117">Click **Set Classes**, and then click **Import**.</span></span>

    6.  <span data-ttu-id="96d5c-118">在打开的浏览器中，选择您**的 mof**文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-118">In the browser that opens, select your **.mof** file, and then click **Open**.</span></span> <span data-ttu-id="96d5c-119">将打开 "**导入摘要**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="96d5c-119">The **Import Summary** window opens.</span></span>

    7.  <span data-ttu-id="96d5c-120">在 "**导入摘要**" 窗口中，确保选中用于导入硬件清单类和类设置的选项，然后单击 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-120">In the **Import Summary** window, ensure that the option to import both hardware inventory classes and class settings is selected, and then click **Import**.</span></span>

    8.  <span data-ttu-id="96d5c-121">在 "**硬件清单类**" 窗口和 "**默认设置**" 窗口中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="96d5c-121">In both the **Hardware Inventory Classes** window and the **Default Settings** window, click **OK**.</span></span>

4.  <span data-ttu-id="96d5c-122">启用**Win32 \ _Tpm**类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="96d5c-122">Enable the **Win32\_Tpm** class as follows:</span></span>

    1.  <span data-ttu-id="96d5c-123">打开**SystemCenter2012 ConfigurationManager 控制台**，然后选择 "**管理**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="96d5c-123">Open the **SystemCenter2012 ConfigurationManager console** and select the **Administration** tab.</span></span>

    2.  <span data-ttu-id="96d5c-124">在 "**管理**" 选项卡上，选择 "**客户端设置**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-124">On the **Administration** tab, select **Client Settings**.</span></span>

    3.  <span data-ttu-id="96d5c-125">右键单击 "**默认客户端设置**"，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-125">Right-click **Default Client Settings**, and then select **Properties**.</span></span>

    4.  <span data-ttu-id="96d5c-126">在 "**默认设置**" 窗口中，选择 "**硬件清单**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-126">In the **Default Settings** window, select **Hardware Inventory**.</span></span>

    5.  <span data-ttu-id="96d5c-127">单击 "**设置类**"。</span><span class="sxs-lookup"><span data-stu-id="96d5c-127">Click **Set Classes**.</span></span>

    6.  <span data-ttu-id="96d5c-128">在主窗口中，向下滚动，然后选择**TPM （Win32 \ _Tpm）** 类。</span><span class="sxs-lookup"><span data-stu-id="96d5c-128">In the main window, scroll down, and then select the **TPM (Win32\_Tpm)** class.</span></span>

    7.  <span data-ttu-id="96d5c-129">在 " **TPM**" 下，确保已选中 " **SpecVersion** " 属性。</span><span class="sxs-lookup"><span data-stu-id="96d5c-129">Under **TPM**, ensure that the **SpecVersion** property is selected.</span></span>

    8.  <span data-ttu-id="96d5c-130">在 "**硬件清单类**" 窗口和 "**默认设置**" 窗口中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="96d5c-130">In both the **Hardware Inventory Classes** window and the **Default Settings** window, click **OK**.</span></span>

**<span data-ttu-id="96d5c-131">编辑 Configuration Manager 2007 的 sms \ _def mof 文件</span><span class="sxs-lookup"><span data-stu-id="96d5c-131">To edit the sms\_def.mof file for Configuration Manager 2007</span></span>**

1.  <span data-ttu-id="96d5c-132">在 Configuration Manager 服务器上，浏览到**sms \ _def 的 mof**文件的位置：</span><span class="sxs-lookup"><span data-stu-id="96d5c-132">On the Configuration Manager Server, browse to the location of the **sms\_def.mof** file:</span></span>

    <span data-ttu-id="96d5c-133">&lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv</span><span class="sxs-lookup"><span data-stu-id="96d5c-133">&lt;CMInstallLocation&gt;\\Inboxes\\clifiles.src\\hinv</span></span>\\

    <span data-ttu-id="96d5c-134">在默认安装中，安装位置是% systemdrive% \\Program Files （x86） \\Microsoft Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="96d5c-134">On a default installation, the installation location is %systemdrive% \\Program Files (x86)\\Microsoft Configuration Manager.</span></span>

2.  <span data-ttu-id="96d5c-135">复制以下代码，然后将其追加到**Sms \ _def 的 mof**文件中，将以下必需的 MBAM 类添加到该文件：</span><span class="sxs-lookup"><span data-stu-id="96d5c-135">Copy the following code, and then append it to **Sms\_def.mof** file to add the following required MBAM classes to the file:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL)
    [ SMS_Report (TRUE),
      SMS_Group_Name ("BitLocker Encryption Details"),
      SMS_Class_ID ("MICROSOFT|BITLOCKER_DETAILS|1.0")]
    class Win32_BitLockerEncryptionDetails : SMS_Class_Template
    {
        [ SMS_Report (TRUE), key ]
        String     DeviceId;
        [ SMS_Report (TRUE) ]
        String     BitlockerPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        String     MbamPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        SInt32     MbamVolumeType;
        [ SMS_Report (TRUE) ]
        String     DriveLetter;
        [ SMS_Report (TRUE) ]
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        SInt32     Compliant;
        [ SMS_Report (TRUE) ]
        SInt32     ReasonsForNonCompliance[];
        [ SMS_Report (TRUE) ]
        SInt32     KeyProtectorTypes[];
        [ SMS_Report (TRUE) ]
        SInt32     EncryptionMethod;
        [ SMS_Report (TRUE) ]
        SInt32     ConversionStatus;
        [ SMS_Report (TRUE) ]
        SInt32     ProtectionStatus;
        [ SMS_Report (TRUE) ]
        Boolean     IsAutoUnlockEnabled;
    };

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0"),
      SMS_Context_1("__ProviderArchitecture=32|uint32"),
      SMS_Context_2("__RequiredArchitecture=true|boolean")]
    Class Win32Reg_MBAMPolicy: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;

        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;

        //MBAM Agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser;
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        // Encoded Computer Name
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0"),
      SMS_Context_1("__ProviderArchitecture=64|uint32"),
      SMS_Context_2("__RequiredArchitecture=true|boolean")]
    Class Win32Reg_MBAMPolicy_64: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;

        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;

        //MBAM Agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser;
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        // Encoded Computer Name
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    //Read Win32_OperatingSystem.SKU WMI property in a new class - because SKU is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Operating System Ex"),
      SMS_Class_ID   ("MICROSOFT|OPERATING_SYSTEM_EXT|1.0") ]
    class CCM_OperatingSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
            string     Name;
        [SMS_Report (TRUE) ]
            uint32     SKU;
    };

    //Read Win32_ComputerSystem.PCSystemType WMI property in a new class - because PCSystemType is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Computer System Ex"),
      SMS_Class_ID   ("MICROSOFT|COMPUTER_SYSTEM_EXT|1.0") ]
    class CCM_ComputerSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
        string     Name;
        [SMS_Report (TRUE) ]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================
    ```

3.  <span data-ttu-id="96d5c-136">修改**Win32 \ _Tpm**类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="96d5c-136">Modify the **Win32\_Tpm** class as follows:</span></span>

    -   <span data-ttu-id="96d5c-137">在课堂属性中将**SMS \ _REPORT**设置为**TRUE** 。</span><span class="sxs-lookup"><span data-stu-id="96d5c-137">Set **SMS\_REPORT** to **TRUE** in the class attributes.</span></span>

    -   <span data-ttu-id="96d5c-138">在**SpecVersion**属性属性中将**SMS \ _REPORT**设置为**TRUE** 。</span><span class="sxs-lookup"><span data-stu-id="96d5c-138">Set **SMS\_REPORT** to **TRUE** in the **SpecVersion** property attribute.</span></span>

## <span data-ttu-id="96d5c-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="96d5c-139">Related topics</span></span>


[<span data-ttu-id="96d5c-140">如何创建或编辑 mof 文件</span><span class="sxs-lookup"><span data-stu-id="96d5c-140">How to Create or Edit the mof Files</span></span>](how-to-create-or-edit-the-mof-files.md)

[<span data-ttu-id="96d5c-141">使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="96d5c-141">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





