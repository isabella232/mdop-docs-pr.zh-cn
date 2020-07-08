---
title: 如何为 App-V 配置 Windows Server 2003 防火墙
description: 如何为 App-V 配置 Windows Server 2003 防火墙
author: dansimp
ms.assetid: 2c0e80f8-41e9-4164-ac83-b23b132b489a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af75479504b454851ee2efc7ca2638d2daf45053
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801532"
---
# 如何为 App-V 配置 Windows Server 2003 防火墙


使用以下过程配置 app-v 的 WindowsServer 2003 防火墙。

**要为 App-v 配置 WindowsServer 2003 防火墙**

1.  在 "**控制面板**" 中，打开 " **Windows 防火墙**"。

    **注意** 如果在执行此步骤之前，服务器尚未配置为运行防火墙服务，系统将提示你启动防火墙服务。

     

2.  如果 .ICO 和 OSD 文件是通过 SMB 发布的，请确保已启用 "**例外**" 选项卡上的 "**文件和打印机共享**"。

    **注意** 如果通过管理服务器上的 HTTP/HTTPS 发布 .ICO 和 OSD 文件，可能需要为 HTTP 或 HTTPS 添加例外。 如果托管 .ICO 和 OSD 文件的 IIS 服务器托管在独立于管理服务器的计算机上，则需要将例外添加到该计算机。 为了最大程度地提高性能，建议你将 .ICO 和 OSD 文件托管在不同服务器上的管理服务器。

     

3.  为 `sghwdsptr.exe` 管理服务器服务可执行文件添加程序例外。 此可执行文件的默认路径为 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。

    **注意** 如果管理服务器使用 RTSP 进行通信，则你还必须添加的程序例外 `sghwsvr.exe` 。

    对于 RTSPS 通信，app-v 流服务器需要程序异常 `sglwdsptr.exe` 。 使用 RTSP 进行通信的 app-v 流式处理服务器还需要程序例外 `sglwsvr.exe` 。

     

4.  确保为每个异常配置正确的范围。 若要降低风险，请删除任何计算机，严格限制服务器将响应的 IP 地址。

## 相关主题


[如何为 App-V 配置 Windows Server 2008 防火墙](how-to-configure-windows-server-2008-firewall-for-app-v.md)

 

 





