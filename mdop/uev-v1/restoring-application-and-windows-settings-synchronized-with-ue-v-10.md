---
title: 还原与 UE-V 1.0 同步的应用程序和 Windows 设置
description: 还原与 UE-V 1.0 同步的应用程序和 Windows 设置
author: dansimp
ms.assetid: 254a16b1-f186-44a4-8e22-49a4ee87c734
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ae83e0a44f98b66a9930f8c5db2231992a4700
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798030"
---
# <span data-ttu-id="39b51-103">还原与 UE-V 1.0 同步的应用程序和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="39b51-103">Restoring Application and Windows Settings Synchronized with UE-V 1.0</span></span>


<span data-ttu-id="39b51-104">Microsoft 用户体验虚拟化（UE-V）的 WMI 和 PowerShell 功能提供了还原设置程序包的功能。</span><span class="sxs-lookup"><span data-stu-id="39b51-104">WMI and PowerShell features of Microsoft User Experience Virtualization (UE-V) provide the ability to restore settings packages.</span></span> <span data-ttu-id="39b51-105">WMI 和 PowerShell 命令允许你在安装 UE-V Agent 后首次启动应用程序时，将应用程序和 Windows 设置还原到计算机上的设置值。</span><span class="sxs-lookup"><span data-stu-id="39b51-105">WMI and PowerShell commands allow you to restore application and Windows settings to the settings values that were on the computer the first time the application launched after the UE-V Agent was installed.</span></span> <span data-ttu-id="39b51-106">将在每个应用程序或 Windows 设置基础上执行此还原操作。</span><span class="sxs-lookup"><span data-stu-id="39b51-106">This restoring action is performed on a per-application or Windows settings basis.</span></span> <span data-ttu-id="39b51-107">下次运行应用程序时或当用户登录到操作系统时，将还原这些设置。</span><span class="sxs-lookup"><span data-stu-id="39b51-107">The settings are restored the next time that the application is run or when the user logs on to the operating system.</span></span>

**<span data-ttu-id="39b51-108">通过 PowerShell 还原应用程序设置和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="39b51-108">To restore application settings and Windows settings with PowerShell</span></span>**

1.  <span data-ttu-id="39b51-109">打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="39b51-109">Open the Windows PowerShell window.</span></span> <span data-ttu-id="39b51-110">若要导入 Microsoft UE-V PowerShell 模块，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="39b51-110">To import the Microsoft UE-V PowerShell module, enter the following command:</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="39b51-111">输入以下 PowerShell cmdlet 以还原应用程序设置和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="39b51-111">Enter the following PowerShell cmdlet to restore the application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="39b51-112">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="39b51-112">PowerShell cmdlet</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="39b51-113">描述</span><span class="sxs-lookup"><span data-stu-id="39b51-113">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="39b51-114">Restore-UevUserSetting</span><span class="sxs-lookup"><span data-stu-id="39b51-114">Restore-UevUserSetting</span></span></p></td>
    <td align="left"><p><span data-ttu-id="39b51-115">还原应用程序的用户设置或还原一组 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="39b51-115">Restores the user settings for an application or restores a group of Windows settings</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="39b51-116">通过 WMI 还原应用程序设置和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="39b51-116">To restore application settings and Windows settings with WMI</span></span>**

1.  <span data-ttu-id="39b51-117">打开一个 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="39b51-117">Open a PowerShell window.</span></span>

2.  <span data-ttu-id="39b51-118">输入以下 WMI 命令以还原应用程序设置和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="39b51-118">Enter the following WMI command to restore application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="39b51-119">WMI 命令</span><span class="sxs-lookup"><span data-stu-id="39b51-119">WMI command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="39b51-120">描述</span><span class="sxs-lookup"><span data-stu-id="39b51-120">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="39b51-121">WmiMethod-命名空间 root\Microsoft\UEV 类 UserSettings-Name RestoreByTemplateId-ArgumentList &lt; template_ID&gt;</span><span class="sxs-lookup"><span data-stu-id="39b51-121">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="39b51-122">还原应用程序的用户设置或还原一组 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="39b51-122">Restores the user settings for an application or restores a group of Windows settings</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="39b51-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="39b51-123">Related topics</span></span>


[<span data-ttu-id="39b51-124">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="39b51-124">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="39b51-125">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="39b51-125">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





