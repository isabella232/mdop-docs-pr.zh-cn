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
# 通过使用 WMI 管理 MED-V 工作区设置


你可以使用 Microsoft 企业桌面虚拟化（MED-V）2.0 中的 Windows Management Instrumentation （WMI）管理你的当前配置设置。

## 使用 WMI 管理 MED-V 工作区设置


通过 WMI 浏览工具，你可以在 MED-V 工作区中查看和编辑设置。 WMI 提供程序是使用 Microsoft .Net Framework 3.5 中的 WMI 提供程序扩展框架实现的。

WMI 提供程序在**root\\microsoft\\medv**命名空间中实现并实现类**设置**。 Class**设置**包含的属性对应于 HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\medv 注册表项下的系统注册表中的设置。

**小心** WMI 浏览工具可用于删除或修改类和实例。 删除或修改某些类和实例可能会导致重要数据丢失，并导致 MED-V 无法预料到正常工作。

 

你可以使用你的首选 WMI 浏览工具，通过执行以下步骤来查看和编辑 MED-V 配置设置。

1.  通过管理员权限打开你的首选 WMI 浏览工具。

2.  连接到命名空间**root\\microsoft\\medv**。

3.  枚举实例以连接到正在运行的实例。 您想要连接到类**设置**的实例。

    **对象编辑器**窗口随即打开。 MED-V 配置设置列为 "**属性**"。

执行以下步骤以在 WMI 中编辑 MED-V 配置设置。

1.  在 "**对象编辑器**" 窗口的**属性**列表中，双击要编辑的配置设置的名称。 例如，若要编辑 MED-V URL 重定向信息，请双击属性**UxRedirectUrls**。

    "**属性编辑器**" 窗口随即打开。

2.  编辑值以更新配置信息。 例如，若要编辑 MED-V URL 重定向信息，请在列表中添加或删除 web 地址。

3.  保存更新的属性设置。

完成查看或编辑 MED-V 配置设置后，关闭 WMI 浏览工具。

**重要提示** 在某些情况下，必须重新启动 MED-V 工作区才能使 MED-V 配置设置更改生效。

 

以下代码显示了用于定义**设置**类的托管对象格式（MOF）文件。

``` syntax
[dynamic: ToInstance, provider("TroubleShooting, Version=2.0.392.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"), singleton: DisableOverride ToInstance ToSubClass]
class Setting : ConfigValueProvider
{
                boolean UxSmartCardLogonEnabled = TRUE;
                [read] string User;
                [implemented] void Clear([in] string propertyName);
};
```

**设置**类继承自**ConfigValueProvider**类。 以下代码显示了定义**ConfigValueProvider**类的托管对象格式（MOF）文件。

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

## 相关主题


[管理 MED-V 工作区配置设置](managing-med-v-workspace-configuration-settings.md)

[管理 MED-V 工作区设置](manage-med-v-workspace-settings.md)

 

 





