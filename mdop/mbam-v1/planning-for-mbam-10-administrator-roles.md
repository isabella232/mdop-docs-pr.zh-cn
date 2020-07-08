---
title: 计划 MBAM 1.0 管理员角色
description: 计划 MBAM 1.0 管理员角色
author: dansimp
ms.assetid: 95be0eb4-25e9-43ca-a8e7-27373d35544d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 104d650824330ea990881c520a7811511f496dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803858"
---
# 计划 MBAM 1.0 管理员角色


本主题包括和介绍 Microsoft BitLocker 管理和监视（MBAM）中提供的管理员角色，以及创建本地组的服务器位置。

## MBAM 管理员角色


<a href="" id="---------------mbam-system-administrators"></a> **MBAM 系统管理员**  
此角色中的管理员有权访问所有 MBAM 功能。 此角色的本地组安装在管理和监视服务器上。

<a href="" id="---------------mbam-hardware-users"></a> **MBAM 硬件用户**  
此角色中的管理员可以访问 MBAM 中的硬件功能功能。 此角色的本地组安装在管理和监视服务器上。

<a href="" id="---------------mbam-helpdesk-users"></a> **MBAM 帮助台用户**  
此角色中的管理员可以访问 MBAM 中的帮助台功能。 此角色的本地组安装在管理和监视服务器上。

<a href="" id="---------------mbam--report-users"></a> **MBAM 报表用户**  
此角色中的管理员可以访问 MBAM 中的合规性和审核报告功能。 此角色的本地组安装在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的服务器上。

<a href="" id="---------------mbam--advanced-helpdesk-users"></a> **MBAM 高级帮助台用户**  
此角色的管理员已增加了对 MBAM 中的帮助台功能的访问权限。 此角色的本地组安装在管理和监视服务器上。 如果用户是 MBAM 帮助台用户和 MBAM 高级帮助台用户的成员，则 MBAM 高级帮助台用户权限将覆盖 MBAM 帮助台用户权限。

**重要提示** 若要查看报表，管理用户必须是管理和监视服务器、合规性和审核数据库以及托管合规性和报告功能的服务器上的**MBAM Report Users**安全组的成员。 最佳做法是在 Active Directory 中创建一个安全组，其中包含管理和监视服务器以及托管合规性和报告的服务器上的本地**MBAM 报表用户**安全组的权限。

 

## 相关主题


[针对 MBAM 1.0 准备环境](preparing-your-environment-for-mbam-10.md)

 

 





