---
title: 如何为 Windows Vista 分配正确的凭据
description: 如何为 Windows Vista 分配正确的凭据
author: dansimp
ms.assetid: cc11d2af-a350-4d16-ba7b-f9c1d89e14b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 111dafea505133f123cf8531a2891a452e725ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802954"
---
# 如何为 Windows Vista 分配正确的凭据


使用以下过程为正确的 WindowsVista 凭据配置 App-v 桌面客户端。

**注意** 必须在每个未加入域的计算机上完成此过程。 根据你的环境中未加入域的计算机的数量，这可能是一项单调乏味的操作。 你可以使用 "凭据管理器" 的脚本和命令行界面帮助管理员自动执行此过程。

 

**为运行 Windows Vista 的 App-v 客户端分配正确的凭据**

1.  在运行 Windows Vista 的 App-v 桌面客户端上使用管理员权限，打开 "**用户帐户**" 控制面板（"经典控制面板"）。

2.  从 "左侧任务" 窗格中的 "**用户帐户**" 中选择 "**管理您的网络密码**"。

3.  在 "存储的**用户名和密码**" 屏幕上选择 "**添加**"。

4.  在 "**存储的凭据属性**" 屏幕上，提供 app-v 基础结构的信息：

    1.  **登录到：** 发布服务器的外部名称。

    2.  **用户名：** 表单 Domain\\Username. 中外部用户的用户名

    3.  **密码：** 在 "**用户名**" 字段中输入的用户帐户的密码。

    4.  选中 "保留**凭据类型**"，然后单击 **"确定"**。

5.  单击**关闭**。 凭据存储在凭据存储中，以便对 app-v 基础结构进行正确身份验证。

## 相关主题


[加入域和未加入域的客户端](domain-joined-and-non-domain-joined-clients.md)

[如何为 Windows XP 分配正确的凭据](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





