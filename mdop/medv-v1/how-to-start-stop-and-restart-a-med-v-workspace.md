---
title: 如何启动、停止和重启 MED-V 工作区
description: 如何启动、停止和重启 MED-V 工作区
author: dansimp
ms.assetid: 54ce139c-8f32-499e-944b-72f123ebfd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2739ace085a4d57d333daf7872e01a7712a7fbd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803825"
---
# 如何启动、停止和重启 MED-V 工作区


**启动 MED-V 工作区**

1.  在通知区域中，右键单击 MED-V 图标。

2.  在子菜单上，单击 "**启动工作区**"。

    -   如果计算机上运行有多个 MED-V 工作区，则会显示 "**工作区选择**" 窗口。

        1.  选择 MED-V 工作区。

        2.  选中 "**启动所选工作区而不询问我**" 复选框，以在下次启动客户端时跳过此窗口，并自动打开所选的 med-v 工作区。

        3.  单击“确定”****。

    将显示 "**启动工作区身份验证**" 窗口。

    -   如果计算机上有多个 MED-V 工作区，并且您选择使用指定的 MED-V 工作区，则会出现下图所示的窗口。

        ![](images/medv-logon.gif)

    -   如果计算机上只有一个 MED-V 工作区，则 "启动上次使用的工作区" 选项不可用。

3.  键入您的域用户凭据。

    **注意** 第一次启动 med-v 工作区时，用户名应采用以下格式： &lt; 域名 &gt; \\ &lt; 用户名 &gt; 。

     

4.  选择 **"保存我的密码"** 以在会话之间保存密码。

    **注意** 若要启用 "保存密码" 功能，必须在 ClientSettings.xml 文件中将 EnableSavePassword 属性设置为 True。 可在*Servers\\Configuration Server\\*文件夹中找到该文件。

     

5.  清除 "**启动上次使用的工作区**" 复选框以选择其他 med-v 工作区。

6.  单击“确定”****。

    将显示多个状态屏幕，具体取决于 MED-V 工作区配置。

    将显示 "**启动工作区**" 屏幕。

**重新启动 MED-V 工作区**

1.  当客户端运行时，在通知区域中，右键单击 MED-V 图标。

2.  在子菜单上，单击 "**重新启动工作区**"。

    将重新启动 MED-V 工作区。

    -   在永久性的 MED-V 工作区中，虚拟机将关闭，然后重新启动。

    -   在 revertible MED-V 工作区中，虚拟机实际上不会关闭;而是返回到其原始状态。

**停止 MED-V 工作区**

1.  在通知区域中，右键单击 MED-V 图标。

2.  在子菜单上，单击 "**停止工作区**"。

    MED-V 工作区已停止。

## 相关主题


[如何启动和退出 MED-V 客户端](how-to-start-and-exit-the-med-v-client.md)

 

 





