---
title: 如何为 App-V Management Server 配置 Windows Server 2008
description: 如何为 App-V Management Server 配置 Windows Server 2008
author: dansimp
ms.assetid: 38b4016f-de82-4209-9159-387d20ddee25
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d1cd7e84ffc0036c98e70a9a0ee1fd3a4ade790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801531"
---
# 如何为 App-V Management Server 配置 Windows Server 2008


在其上安装 Microsoft Application Virtualization （App-v）管理 Web 服务的 Windows Server 2008 服务器上需要将 Internet Information Services （IIS）作为角色安装在服务器上。 使用以下过程配置 Windows Server 2008 以支持应用 Vserver 安装。

**在 Windows Server2008 计算机上安装 IIS**

1.  在 Windows Server2008 计算机上，单击 "**开始**"，单击 "**所有程序**"，单击 "**管理工具**"，然后单击 "**服务器管理器**" 以启动服务器管理器。 在服务器管理器中，右键单击 "**角色**" 节点，然后单击 "**添加角色**" 以启动 "**添加角色向导**"。

2.  在 "**添加角色" 向导**的 "**选择服务器角色**" 页面上，选择 " **Web 服务器（IIS）**"。 出现提示时，单击 "**添加所需功能**" 以添加相关功能。

3.  在 "**选择服务器角色**" 页面上，单击 "**下一步**"，然后再次单击 "**下一步**"。

4.  在 "**添加角色" 向导**的 "**选择角色服务**" 页面上：

    1.  在 "**应用程序开发**" 下，选择 " **ASP.NET** "，然后在出现提示时单击 "**添加所需的角色服务**" 以添加从属角色服务和功能。

    2.  在 "**安全**" 下，选择 " **Windows 身份验证**"。

    3.  在 "**管理工具**" 节点中，选择 " **IIS 管理脚本和工具**"。 在 " **IIS6 管理兼容性**" 下，确保已选中**IIS6 配置数据库兼容性**和**IIS6 WMI 兼容性**，然后单击 "**下一步**"。

5.  在 "**确认安装选择**" 页面上，单击 "**安装**"，然后完成向导的其余部分。

6.  单击 "**关闭**" 以退出 "**添加角色向导**"，然后关闭 "服务器管理器"。

## 相关主题


[Application Virtualization 部署要求](application-virtualization-deployment-requirements.md)

[Application Virtualization 部署和升级清单](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





