---
title: 如何配置 Management Server 安装后的安全性
description: 如何配置 Management Server 安装后的安全性
author: dansimp
ms.assetid: 71979fa6-3d0b-4a8b-994e-cb728d013090
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 521e72ead78055a7d3261664ccb75d454c22e622
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801616"
---
# 如何配置 Management Server 安装后的安全性


使用 App-v 管理控制台添加证书并配置 app-v 管理服务器以增强安全性。 你可以使用以下过程配置安全性后的安装。

**配置管理服务器安全安装后**

1.  打开 app-v 管理控制台，并通过 App-v 管理员权限连接到**管理服务**。

2.  展开 "服务器"，展开 "**服务器组**"，然后选择注册管理服务器的相应服务器组。

3.  右键单击 "管理服务器" 对象，然后选择 "**属性**"。

4.  在 "**端口**" 选项卡上，单击 "**服务器证书**" 并完成向导，选择正确设置的证书。

    **注意** 如果向导中未显示任何证书，则证书尚未设置，或者证书确实满足 App-v 的要求。

     

5.  单击 "**下一步**" 继续**使用 "欢迎使用证书向导**" 页面。

6.  在 "**可用证书**" 屏幕中选择正确的证书。

7.  单击**完成**。

8.  完成向导后，清除**RTSP**作为可用的侦听端口。 这将阻止通过非安全通信通道进行连接。

9.  单击 "**应用**"，然后重新启动**Microsoft 虚拟应用程序服务器**服务。 使用服务的 MMC 管理单元完成此任务。

## 相关主题


[如何配置 Streaming Server 安装后的安全性](how-to-configure-streaming-server-security-post-installation.md)

[解决证书权限问题](troubleshooting-certificate-permission-issues.md)

 

 





