---
title: 如何在单个服务器上安装 MBAM 语言更新
description: 如何在单个服务器上安装 MBAM 语言更新
author: dansimp
ms.assetid: e6fe59a3-a3e1-455c-a059-1f23ee083cf6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94814158335430aba433c180cdba83d0cf15b760
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803631"
---
# 如何在单个服务器上安装 MBAM 语言更新


Microsoft BitLocker 管理和监视（MBAM）包括可在一台或多台计算机上运行的四个服务器角色。 但是，只有两个 MBAM 服务器功能才需要更新以支持安装 MBAM 1.0 语言版本和 MBAM 策略模板。 若要更新一台计算机上安装的全部三个 MBAM 功能，请执行本主题中所述的步骤。

**在单个服务器上安装 MBAM 语言更新**

1.  打开 "Internet 信息服务（IIS）管理" 控制台，转到 "**网站**"，然后关闭 Microsoft BitLocker 管理和监视网站。

2.  编辑 MBAM 网站的绑定，然后暂时修改该网站的绑定。 例如，将端口从443更改为9443。

3.  找到并运行 MBAM 安装向导（MBAMsetup.exe），然后选择以下三个功能：

    1.  合规性和审核报告

    2.  管理和监视服务器

    3.  组策略模板

    **重要提示** 必须按以下顺序更新 MBAM 服务器功能：合规性和审核报告，然后是 "管理和监视服务器"。 组策略模板可以随时更新，而无需考虑顺序。

     

4.  升级服务器数据库后，打开 IIS 管理控制台并查看 Microsoft BitLocker 管理和监视网站的绑定。

5.  删除其中一个绑定，并确保剩余的绑定具有正确的 MBAM 企业配置的主机名、证书和端口号。

6.  重新启动 MBAM 网站。

7.  测试 MBAM 网站功能：

    -   打开 MBAM web 界面，确保你可以获取客户端的恢复密钥。

    -   强制加密新的或手动解密的客户端计算机。

        **注意** 仅当 MBAM 客户端可以与恢复和硬件数据库通信时，才会打开它。

         

## 相关主题


[部署 MBAM 1.0 语言版本更新](deploying-the-mbam-10-language-release-update.md)

 

 





