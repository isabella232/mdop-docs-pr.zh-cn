---
title: 通过使用 WMI 管理 MED-V 工作区设置
description: 通过使用 WMI 管理 MED-V 工作区设置
author: dansimp
ms.assetid: 05a665a3-2309-46c1-babb-a3e3bbb0b1f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e74e6fa4944ce0dacd5503baec73044b231abe83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803907"
---
# <span data-ttu-id="ecb07-103">通过使用 WMI 管理 MED-V 工作区设置</span><span class="sxs-lookup"><span data-stu-id="ecb07-103">Managing MED-V Workspace Settings by Using a WMI</span></span>


<span data-ttu-id="ecb07-104">你可以使用 Microsoft 企业桌面虚拟化（MED-V）2.0 中的 Windows Management Instrumentation （WMI）管理你的当前配置设置。</span><span class="sxs-lookup"><span data-stu-id="ecb07-104">You can use Windows Management Instrumentation (WMI) in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 to manage your current configuration settings.</span></span>

## <span data-ttu-id="ecb07-105">使用 WMI 管理 MED-V 工作区设置</span><span class="sxs-lookup"><span data-stu-id="ecb07-105">To manage MED-V workspace settings with a WMI</span></span>


<span data-ttu-id="ecb07-106">通过 WMI 浏览工具，你可以在 MED-V 工作区中查看和编辑设置。</span><span class="sxs-lookup"><span data-stu-id="ecb07-106">A WMI browsing tool lets you view and edit the settings in a MED-V workspace.</span></span> <span data-ttu-id="ecb07-107">WMI 提供程序是使用 Microsoft .Net Framework 3.5 中的 WMI 提供程序扩展框架实现的。</span><span class="sxs-lookup"><span data-stu-id="ecb07-107">The WMI provider is implemented by using the WMI Provider Extension framework from the Microsoft .Net Framework 3.5.</span></span>

<span data-ttu-id="ecb07-108">WMI 提供程序在**root\\microsoft\\medv**命名空间中实现并实现类**设置**。</span><span class="sxs-lookup"><span data-stu-id="ecb07-108">The WMI provider is implemented in the **root\\microsoft\\medv** namespace and implements the class **Setting**.</span></span> <span data-ttu-id="ecb07-109">Class**设置**包含的属性对应于 HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\medv 注册表项下的系统注册表中的设置。</span><span class="sxs-lookup"><span data-stu-id="ecb07-109">The class **Setting** contains properties that correspond to the settings in the system registry under the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv registry key.</span></span>

<span data-ttu-id="ecb07-110">**小心** WMI 浏览工具可用于删除或修改类和实例。</span><span class="sxs-lookup"><span data-stu-id="ecb07-110">**Caution** WMI browsing tools can be used to delete or modify classes and instances.</span></span> <span data-ttu-id="ecb07-111">删除或修改某些类和实例可能会导致重要数据丢失，并导致 MED-V 无法预料到正常工作。</span><span class="sxs-lookup"><span data-stu-id="ecb07-111">Deleting or modifying certain classes and instances can result in the loss of valuable data and cause MED-V to function unpredictably.</span></span>

 

<span data-ttu-id="ecb07-112">你可以使用你的首选 WMI 浏览工具，通过执行以下步骤来查看和编辑 MED-V 配置设置。</span><span class="sxs-lookup"><span data-stu-id="ecb07-112">You can use your preferred WMI browsing tool to view and edit MED-V configuration settings by following these steps.</span></span>

1.  <span data-ttu-id="ecb07-113">通过管理员权限打开你的首选 WMI 浏览工具。</span><span class="sxs-lookup"><span data-stu-id="ecb07-113">Open your preferred WMI browsing tool with administrator permissions.</span></span>

2.  <span data-ttu-id="ecb07-114">连接到命名空间**root\\microsoft\\medv**。</span><span class="sxs-lookup"><span data-stu-id="ecb07-114">Connect to the namespace **root\\microsoft\\medv**.</span></span>

3.  <span data-ttu-id="ecb07-115">枚举实例以连接到正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="ecb07-115">Enumerate the instances to connect to the running instance.</span></span> <span data-ttu-id="ecb07-116">您想要连接到类**设置**的实例。</span><span class="sxs-lookup"><span data-stu-id="ecb07-116">You want to connect to the instance of the class **Setting**.</span></span>

    <span data-ttu-id="ecb07-117">**对象编辑器**窗口随即打开。</span><span class="sxs-lookup"><span data-stu-id="ecb07-117">An **Object Editor** window opens.</span></span> <span data-ttu-id="ecb07-118">MED-V 配置设置列为 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="ecb07-118">The MED-V configuration settings are listed as **Properties**.</span></span>

<span data-ttu-id="ecb07-119">执行以下步骤以在 WMI 中编辑 MED-V 配置设置。</span><span class="sxs-lookup"><span data-stu-id="ecb07-119">Perform the following steps to edit a MED-V configuration setting in the WMI.</span></span>

1.  <span data-ttu-id="ecb07-120">在 "**对象编辑器**" 窗口的**属性**列表中，双击要编辑的配置设置的名称。</span><span class="sxs-lookup"><span data-stu-id="ecb07-120">In the list of **Properties** on the **Object Editor** window, double-click the name of the configuration setting you want to edit.</span></span> <span data-ttu-id="ecb07-121">例如，若要编辑 MED-V URL 重定向信息，请双击属性**UxRedirectUrls**。</span><span class="sxs-lookup"><span data-stu-id="ecb07-121">For example, to edit MED-V URL redirection information, double-click the property **UxRedirectUrls**.</span></span>

    <span data-ttu-id="ecb07-122">"**属性编辑器**" 窗口随即打开。</span><span class="sxs-lookup"><span data-stu-id="ecb07-122">A **Property Editor** window opens.</span></span>

2.  <span data-ttu-id="ecb07-123">编辑值以更新配置信息。</span><span class="sxs-lookup"><span data-stu-id="ecb07-123">Edit the value to update the configuration information.</span></span> <span data-ttu-id="ecb07-124">例如，若要编辑 MED-V URL 重定向信息，请在列表中添加或删除 web 地址。</span><span class="sxs-lookup"><span data-stu-id="ecb07-124">For example, to edit MED-V URL redirection information, add or remove a web address in the list.</span></span>

3.  <span data-ttu-id="ecb07-125">保存更新的属性设置。</span><span class="sxs-lookup"><span data-stu-id="ecb07-125">Save the updated property settings.</span></span>

<span data-ttu-id="ecb07-126">完成查看或编辑 MED-V 配置设置后，关闭 WMI 浏览工具。</span><span class="sxs-lookup"><span data-stu-id="ecb07-126">After you have finished viewing or editing MED-V configuration settings, close the WMI browsing tool.</span></span>

<span data-ttu-id="ecb07-127">**重要提示** 在某些情况下，必须重新启动 MED-V 工作区才能使 MED-V 配置设置更改生效。</span><span class="sxs-lookup"><span data-stu-id="ecb07-127">**Important** In some cases, a restart of the MED-V workspace is required for changes to MED-V configuration settings to take effect.</span></span>

 

<span data-ttu-id="ecb07-128">以下代码显示了用于定义**设置**类的托管对象格式（MOF）文件。</span><span class="sxs-lookup"><span data-stu-id="ecb07-128">The following code shows the Managed Object Format (MOF) file that defines the **Setting** class.</span></span>

``` syntax
[dynamic: ToInstance, provider("TroubleShooting, Version=2.0.392.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"), singleton: DisableOverride ToInstance ToSubClass]
class Setting : ConfigValueProvider
{
                boolean UxSmartCardLogonEnabled = TRUE;
                [read] string User;
                [implemented] void Clear([in] string propertyName);
};
```

<span data-ttu-id="ecb07-129">**设置**类继承自**ConfigValueProvider**类。</span><span class="sxs-lookup"><span data-stu-id="ecb07-129">The **Setting** class inherits from the **ConfigValueProvider** class.</span></span> <span data-ttu-id="ecb07-130">以下代码显示了定义**ConfigValueProvider**类的托管对象格式（MOF）文件。</span><span class="sxs-lookup"><span data-stu-id="ecb07-130">The following code shows the Managed Object Format (MOF) file that defines the **ConfigValueProvider** class.</span></span>

``` syntax
[abstract]
class ConfigValueProvider
{
                [write] string DiagEventLogLevel;
                [write] boolean FtsAddUserToAdminGroupEnabled;
                [write] string FtsComputerNameMask;
                [write] sint32 FtsDeleteVMStateTimeout;
                [write] sint32 FtsDetachVfdTimeout;
                [write] string FtsDialogUrl;
                [write] sint32 FtsExplorerTimeout;
                [write] string FtsFailureDialogMsg;
                [write] string FtsLogFilePaths[];
                [write] sint32 FtsMaxPostponeTime;
                [write] sint32 FtsMaxRetryCount;
                [write] string FtsMode;
                [write] sint32 FtsNonInteractiveRetryTimeoutInc;
                [write] sint32 FtsNonInteractiveTimeout;
                [write] string FtsPostponeUtcDateTimeLimit;
                [write] string FtsRetryDialogMsg;
                [write] boolean FtsSetComputerNameEnabled;
                [write] boolean FtsSetJoinDomainEnabled;
                [write] boolean FtsSetMachineObjectOUEnabled;
                [write] boolean FtsSetRegionalSettingsEnabled;
                [write] boolean FtsSetUserDataEnabled;
                [write] string FtsStartDialogMsg;
                [write] sint32 FtsTaskCancelTimeout;
                [write] sint32 FtsTaskVMTurnOffTimeout;
                [write] sint32 FtsUpgradeTimeout;
                [write] boolean UxAppPublishingEnabled;
                [write] boolean UxAudioSharingEnabled;
                [write] boolean UxClipboardSharingEnabled;
                [write] boolean UxCredentialCacheEnabled;
                [write] sint32 UxDialogTimeout;
                [write] sint32 UxHideVmTimeout;
                [write] boolean UxLogonStartEnabled;
                [write] boolean UxPrinterSharingEnabled;
                [write] sint32 UxRebootAbsoluteDelayTimeout;
                [write] string UxRedirectUrls[];
                [write] boolean UxShowExit;
                [write] boolean UxSmartCardLogonEnabled;
                [write] boolean UxSmartCardSharingEnabled;
                [write] boolean UxUSBDeviceSharingEnabled;
                [write] string VmCloseAction;
                [write] sint32 VmGuestMemFromHostMem[];
                [write] sint32 VmGuestUpdateDuration;
                [write] string VmGuestUpdateTime;
                [write] sint32 VmHostMemToGuestMem[];
                [write] boolean VmHostMemToGuestMemCalcEnabled;
                [write] sint32 VmMemory;
                [write] boolean VmMultiUserEnabled;
                [write] string VmNetworkingMode;
                [write] sint32 VmTaskTimeout;
};
```

## <span data-ttu-id="ecb07-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="ecb07-131">Related topics</span></span>


[<span data-ttu-id="ecb07-132">管理 MED-V 工作区配置设置</span><span class="sxs-lookup"><span data-stu-id="ecb07-132">Managing MED-V Workspace Configuration Settings</span></span>](managing-med-v-workspace-configuration-settings.md)

[<span data-ttu-id="ecb07-133">管理 MED-V 工作区设置</span><span class="sxs-lookup"><span data-stu-id="ecb07-133">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





