---
title: 如何为 Windows XP 分配正确的凭据
description: 如何为 Windows XP 分配正确的凭据
author: dansimp
ms.assetid: cddbd556-d8f9-4981-a947-6e8e3f552b70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81581b75a9b7d5ce35e1c50fd01e0b7bbd3f7ef5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802171"
---
# 如何为 Windows XP 分配正确的凭据


使用以下过程为正确的 WindowsXP 凭据配置 App-v 桌面客户端。

**注意** 完成此过程后，非域加入的客户端可以在不加入域的情况下执行发布刷新。

 

**为运行 WindowsXP 的 App-v 客户端分配正确的凭据**

1.  在运行 WindowsXP 的 App-v 客户端上使用管理员权限，打开 "**用户帐户**" 控制面板（经典控制面板）。

2.  单击 "**高级" 选项卡**，然后选择 "**管理密码**"。

3.  在 "**存储的用户名和密码**" 屏幕上，单击 "**添加**"。

4.  在 "**登录信息属性**" 屏幕上，利用 app-v 基础结构中的信息填写以下字段：

    1.  **服务器：** 发布服务器外部名称的名称。

    2.  **用户名：** 表单 Domain\\username. 中外部用户的用户名

    3.  **密码：** 在 "**用户名**" 字段中输入的用户帐户的密码。

5.  单击“确定”****。 凭据将存储在客户端上。

## 相关主题


[加入域和未加入域的客户端](domain-joined-and-non-domain-joined-clients.md)

[如何为 Windows Vista 分配正确的凭据](how-to-assign--the-proper-credentials-for-windows-vista.md)

 

 





