---
title: 如何配置 Streaming Server 安装后的安全性
description: 如何配置 Streaming Server 安装后的安全性
author: dansimp
ms.assetid: 9bde3677-d1aa-4dcc-904e-bb49a268d748
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1945b38da5dd50c0bd2fb0c741bd92012e78586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801603"
---
# 如何配置 Streaming Server 安装后的安全性


通过注册表配置 app-v 流式处理服务器以增强安全性。 与 App-v 管理服务器一样，在完成以下安装后过程之前，必须使用正确的 "服务器身份验证" EKU 标识符正确设置证书。

**配置流式服务器安全安装后的安全**

1.  创建 MMC，添加 "**证书**" 管理单元，然后选择 "**本地计算机证书存储**"。

2.  打开计算机的**个人**证书，然后打开为 app-v 预配的证书。

3.  在 "**详细信息**" 选项卡上，向下滚动到指纹，然后在 "详细信息" 窗格中复制哈希。

4.  打开注册表编辑器，然后导航到 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server` 。

5.  编辑 `X509CertHash` 值，在 "值" 字段中粘贴指纹哈希，然后删除所有空格。 单击 **"确定"** 接受编辑。

6.  在注册表编辑器中，导航到 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts` 。

7.  创建一个名为 "322" 的新**DWORD**值，然后输入十进制值作为322或十六进制值作为142。

8.  重新启动流服务。

## 相关主题


[如何配置 Management Server 安装后的安全性](how-to-configure-management-server-security-post-installation.md)

[解决证书权限问题](troubleshooting-certificate-permission-issues.md)

 

 





