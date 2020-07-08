---
title: 配置 UE-V 2. x 的公司设置中心
description: 配置 UE-V 2. x 的公司设置中心
author: dansimp
ms.assetid: 48fadb0a-c0dc-4287-9474-f94ce1417003
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0226b3c156a6d6ca39b0214de8acf0c5990db349
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803339"
---
# 配置 UE-V 2. x 的公司设置中心


Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 包括新应用程序（公司设置中心），该应用程序可帮助用户管理要同步的设置。 公司设置中心通过使用 UE-V Agent 进行安装。 用户在 "控制面板" 的 "**开始**" 菜单或 "**开始**" 屏幕上，以及通过 ue-v 通知区域图标访问公司设置中心。 公司设置中心显示已同步的设置，并帮助用户查看 UE-V 的同步状态。 用户可以使用公司设置中心来选择哪些应用程序或 Windows 功能在计算机之间同步其设置。 他们还可以单击 "**立即同步**" 按钮，立即同步所有设置。 管理员还可以在 "公司设置中心" 中包含支持链接。

## 关于公司设置中心


公司设置中心桌面应用程序向用户提供有关 UE-V 设置同步的信息。 公司设置中心可通过多种不同的方式进行访问：

-   通知区域图标-启用**任务栏图标**组策略设置或 Windows PowerShell 配置后，将在通知区域中显示 ue-v 图标。 单击 "UE-V" 图标以打开 "公司设置中心"。

    **注意** 可通过使用以下设置禁用通知区域图标：

    -   组策略设置： `Policy Tray Icon`

    -   Windows PowerShell cmdlet： `TrayIconEnabled`

    -   SystemCenter2012 ConfigurationManager 的 UE-V 配置包中的配置项目： `Tray icon enabled`

     

-   控制面板应用程序-在 "控制面板" 中，通过浏览找到 "**外观和个性化**"，然后单击 "**公司设置中心**"。

-   第一次使用通知-除非 "已禁用"，UE-V Agent 将提醒用户在计算机上首次运行 UE-V 代理时，设置现在已同步。 单击 "通知" 对话框以打开 "公司设置中心"。

-   "**开始**" 屏幕或 "**开始**" 菜单包含指向公司设置中心的链接。 "搜索公司设置中心" 将查找应用程序。

## 在公司设置中心配置支持链接


公司设置中心可以包括超链接，用户可单击该超链接以获取 UE-V 设置同步问题的支持。 此链接可以打开任何有效的 URL 协议，例如用于网页的 http://或电子邮件的 mailto://。 支持链接可以使用组策略、Windows PowerShell 或 System Center 2012 Configuration Manager UE-V 配置包进行配置。

**如何配置公司设置中心支持链接**

1.  打开你的首选管理工具：

    -   **组策略**-如果尚未执行此操作，请从[MDOP 管理模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)中下载 ue-v 2 的 ADMX 模板。

    -   **Windows powershell** -在安装了 ue-v Agent 的计算机上，打开**Windows PowerShell**。 有关使用 Windows PowerShell 管理 UE-V 的详细信息，请参阅[使用 Windows powershell 和 WMI 管理 ue-v 2。](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

    -   **适用于 Microsoft 用户体验虚拟化（ue-v）的 System Center 2012 配置包**-导入 Ue-v 配置包，然后按照配置包文档创建配置项。 有关 UE-V 配置包的详细信息，请参阅[通过 System Center Configuration Manager 2012 配置 ue-v 2。](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

2.  编辑以下策略的设置：

    -   **联系 It 链接文本**-此设置在 "公司设置中心" 中指定 "联系 IT URL" 超链接的文本。 如果启用此设置，公司设置中心将在指向联系人 IT URL 的链接中显示指定文本。

        -   组策略设置： `Contact IT Link Text`

        -   Windows PowerShell cmdlet： `ContactITDescription`

        -   配置包配置项目： `IT contact descriptive text`

    -   **联系 IT URL** -此设置使用有效的 URL 协议（例如网页的 http://或电子邮件 mailto://）指定 "联系人 IT" 链接在 "公司设置中心" 中的 URL。

        -   组策略设置： `Contact IT URL`

        -   Windows PowerShell cmdlet： `ContactITUrl`

        -   配置包配置项目： `IT contact URL`

3.  使用管理工具将设置部署到用户计算机。






 

 





