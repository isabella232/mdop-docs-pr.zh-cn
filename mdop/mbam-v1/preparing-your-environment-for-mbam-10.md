---
title: 针对 MBAM 1.0 准备环境
description: 针对 MBAM 1.0 准备环境
author: dansimp
ms.assetid: 915f7c3c-70ad-4a90-a434-73e7fba97ecb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a2de4e825d5c89aeabcf57d78dc856bacb03e11
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803319"
---
# 针对 MBAM 1.0 准备环境


在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，请确保满足安装该产品所必需的先决条件。 如果事先知道先决条件，则可以有效地部署产品并启用其功能，以便更有效地支持组织的业务目标。

## 查看 MBAM 1.0 部署先决条件


MBAM 客户端和每个 MBAM 服务器功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装它们。

为了确保 MBAM 客户端和 MBAM 服务器功能的安装成功，你应该计划确保为 MBAM 客户端或 MBAM Server 功能安装指定的计算机正确做好 MBAM 设置的准备。

**注意** MBAM 安装程序将在安装开始之前验证是否满足所有先决条件。 如果不满足这些要求，安装程序将失败。

 

[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)

## 规划 MBAM 1.0 组策略要求


在 MBAM 可以管理企业中的客户端之前，必须为环境的加密要求定义组策略。

**重要提示** MBAM 将不会与独立的 BitLocker 驱动器加密的策略配合使用。 必须为 MBAM 定义组策略;否则，BitLocker 加密和强制将失败。

 

[计划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)

## 规划 MBAM 1.0 管理员角色


MBAM 管理员角色由在安装以下各项时由 MBAM 安装程序创建的本地组管理： BitLocker 管理和监视服务器、合规性和审核报告功能以及合规性和审核状态数据库。

如果在 ActiveDirectoryDomainServices 中创建安全组，则可以更有效地管理 MBAM 角色的成员身份，将相应的管理员帐户添加到这些组，然后将这些安全组添加到 MBAM 本地组。 有关详细信息，请参阅[如何管理 MBAM 管理员角色](how-to-manage-mbam-administrator-roles-mbam-1.md)。

[计划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)

## MBAM 规划的其他资源


[计划 MBAM 1.0](planning-for-mbam-10.md)

 

 





