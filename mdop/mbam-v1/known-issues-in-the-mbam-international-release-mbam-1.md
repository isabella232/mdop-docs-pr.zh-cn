---
title: MBAM 国际版本中的已知问题
description: MBAM 国际版本中的已知问题
author: dansimp
ms.assetid: bbf888dc-93c1-4323-b43c-0ded098e9b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af32551135ff297d25930f94b40bf04c0fcaaafe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803838"
---
# MBAM 国际版本中的已知问题

本部分包含 Microsoft BitLocker 管理和监视（MBAM）国际版的已知问题。

## MBAM 国际版本中的已知问题

### 安装过程未指定更新

更新 Microsoft BitLocker 管理和监视服务器或服务器时，安装程序不会声明正在安装更新。

**解决方法**：无。

### 用于管理和监视服务器角色的证书

如果在 MBAM 服务器之间使用证书进行身份验证，则在更新 MBAM 管理和监视服务器之后，必须确保该证书有效且未被吊销或已过期。

**解决方法**：无。

### MBAM Svclog 文件填充磁盘空间

如果你已关注[知识库文章 2668170](https://go.microsoft.com/fwlink/?LinkID=247277)，则可能需要在安装此更新后重复 KB 步骤。

**解决方法**：无。

## 相关主题

[部署 MBAM 1.0 语言版本更新](deploying-the-mbam-10-language-release-update.md)

 

 





