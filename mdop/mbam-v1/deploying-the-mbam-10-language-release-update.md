---
title: 部署 MBAM 1.0 语言版本更新
description: 部署 MBAM 1.0 语言版本更新
author: dansimp
ms.assetid: 9dbd85c3-e470-4752-a90f-25754dd46dab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a819be81594efd9349e3f6c0f6559c2b810bdc9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798142"
---
# 部署 MBAM 1.0 语言版本更新


Microsoft BitLocker 管理和监视（MBAM）1.0 语言版本是对 MBAM 的更新，其中包括新语言的支持。 新语言为：

-   英语（en-us）

-   法语（fr）

-   意大利语（it）

-   德语（de）

-   西班牙语（es）

-   朝鲜语（ko）

-   日语（ja）

-   巴西葡萄牙语（pt-br）

-   俄语（ru）

-   繁体中文（zh-cn&platform）

-   简体中文（zh-cn&platform-cn）

MBAM 1.0 语言更新将版本号从 MBAM 1.0.1237.1 更改为 MBAM 1.0.2001。

无需重新安装所有 MBAM 功能即可添加这些其他语言。 本主题定义添加新支持的语言所需的步骤。

## 将 MBAM 国际版部署到 MBAM 服务器功能


若要开始，必须更新以下 MBAM 服务器功能：

-   合规性和审核报告

-   管理和监视服务器

-   策略模板

然后，您必须运行**MbamSetup.exe**以升级在同一台服务器上运行的 MBAM 功能。

[如何在单个服务器上安装 MBAM 语言更新](how-to-install-the-mbam-language-update-on-a-single-server-mbam-1.md)

[如何在分布式服务器上安装 MBAM 语言更新](how-to-install-the-mbam-language-update-on-distributed-servers-mbam-1.md)

## 为组策略安装 MBAM 语言更新


可以在每个管理工作站上安装 MBAM 组策略模板，也可以将其复制到组策略中央存储，以便所有组策略管理员均可使用这些模板。 策略模板不能直接安装在域控制器上。 如果不使用组策略中央存储，则必须手动将策略复制到管理 MBAM 组策略的每个域控制器。

若要添加 MBAM 语言策略模板，请将组策略语言文件从安装了 "策略模板" 角色的计算机上的%SystemRoot%\\PolicyDefinitions 复制到工作站计算机上的同一位置。 下面是组策略文件的一些示例：

-   BitLockerManagement

-   BitLockerUserManagement

-   en-us\\BitLockerManagement.adml

-   en-us\\BitLockerUserManagement.adml

-   fr-fr\\ BitLockerManagement adml

-   fr-fr\\ BitLockerUserManagement adml

-   （同样适用于每种支持的语言）

## MBAM 国际发行版中的已知问题


本主题包含 Microsoft BitLocker 管理和监控国际发布版的已知问题。

[MBAM 国际版本中的已知问题](known-issues-in-the-mbam-international-release-mbam-1.md)

## 用于部署 MBAM 1.0 语言更新的其他资源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





