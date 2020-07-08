---
title: 计划 MBAM 2.0 管理员角色
description: 计划 MBAM 2.0 管理员角色
author: dansimp
ms.assetid: 6f813297-6479-42d3-a21b-896d54466b5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a89a04c0ef074407dc3cd081d351d44023e65e70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803659"
---
# 计划 MBAM 2.0 管理员角色


本主题列出并介绍 Microsoft BitLocker 管理和监视（MBAM）中可用的可用管理员角色以及创建本地组的服务器位置。

## MBAM 管理员角色


<a href="" id="---------------mbam-system-administrators"></a> **MBAM 系统管理员**  
此角色中的管理员有权访问所有 Microsoft BitLocker 管理和监视功能。 此角色的本地组安装在管理和监视服务器上。

<a href="" id="---------------mbam-helpdesk-users"></a> **MBAM 帮助台用户**  
此角色中的管理员可以访问 MBAM 中的技术支持功能。 此角色的本地组安装在管理和监视服务器上。

<a href="" id="---------------mbam-report-users"></a> **MBAM 报表用户**  
此角色中的管理员可以访问 MBAM 中的合规性和审核报告。 此角色的本地组安装在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的服务器上。

<a href="" id="---------------mbam-advanced-helpdesk-users"></a> **MBAM 高级帮助台用户**  
此角色中的管理员已增加了对 MBAM 中技术支持功能的访问权限。 此角色的本地组安装在管理和监视服务器上。 如果用户是 MBAM 帮助台用户和 MBAM 高级帮助台用户的成员，则 MBAM 高级帮助台用户权限将替代 MBAM 帮助台用户权限。

**重要提示** 若要查看报表，管理用户必须是管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告功能的服务器上的**MBAM Report Users**安全组的成员。 最佳做法是在 Active Directory 域服务中使用本地**MBAM 报表**上的权限在管理和监视服务器以及托管合规性和审核报表的服务器上创建安全组。

 

## 相关主题


[针对 MBAM 2.0 准备环境](preparing-your-environment-for-mbam-20-mbam-2.md)

 

 





