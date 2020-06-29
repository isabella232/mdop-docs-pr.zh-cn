---
title: 如何为 App-V 配置 Windows Server 2008 防火墙
description: 如何为 App-V 配置 Windows Server 2008 防火墙
author: dansimp
ms.assetid: 57f4ed17-0651-4a3c-be1e-29d9520c6aeb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 19e4cda9ac3b908f68e4f69b9663033d8a21ae41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801528"
---
# 如何为 App-V 配置 Windows Server 2008 防火墙


随着 Windows Server2008 的推出，将防火墙和 IPsec 组件合并到一个服务中，并增强了此服务的功能。 新的防火墙服务支持传入和传出状态检查。 此外，你可以通过组策略配置特定防火墙规则和 IPsec 策略。 有关 Windows Server2008 中的 Windows 防火墙的其他信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151980> 。

以下过程不包括通过 SMB 或 HTTP/HTTPS 为 .ICO 和 OSD 发布添加例外。 这些例外会根据安装在 Windows Server 2008 防火墙上的网络配置文件和角色自动添加。

**注意** 如果管理服务器配置为使用 RTSP，请重复此过程以将程序添加 `sghwsvr.exe` 为例外。

对于 RTSPS 通信，app-v 流服务器需要程序异常 `sglwdsptr.exe` 。 使用 RTSP 进行通信的 app-v 流式处理服务器还需要程序例外 `sglwsvr.exe` 。

 

**为 App-v 配置 Windows Server2008 防火墙**

1.  通过 "控制面板" 或在 "运行" 行上键入 **，打开具有高级安全**管理控制台的 Windows 防火墙 `wf.msc` 。

2.  创建新的入站规则，然后选择 "**程序**"。

3.  选择程序路径并浏览到 `sghwdsptr.exe` ，默认情况下位于的位置 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。

4.  单击“下一步”****。

5.  在 "**操作**" 页面上，选择 "**允许连接**"，然后单击 "**下一步**"。

6.  选择相应的**配置文件**以应用于入站规则。

7.  提供规则的名称和说明，然后单击 "**完成**"。

## 相关主题


[如何为 App-V 配置 Windows Server 2003 防火墙](how-to-configure-windows-server-2003-firewall-for-app-v.md)

 

 





