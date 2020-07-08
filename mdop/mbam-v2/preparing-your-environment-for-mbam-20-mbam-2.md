---
title: 针对 MBAM 2.0 准备环境
description: 针对 MBAM 2.0 准备环境
author: dansimp
ms.assetid: 5fb01da9-620e-4992-9e54-2ed3fb69e6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1be989112d456064db302952d50159d00b5597a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803802"
---
# 针对 MBAM 2.0 准备环境


在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，应确保已满足安装产品的先决条件。 当您知道先决条件提前的时候，您可以高效地部署产品并启用其功能，以便最有效地支持组织的业务目标。

如果你要部署 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 的 Microsoft BitLocker 管理和监视，请参阅[计划通过 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。

## 查看 MBAM 2.0 部署先决条件


MBAM 客户端和每个 MBAM 服务器功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装它们。

若要确保 MBAM 客户端和 MBAM 服务器功能的安装成功，请确保为 MBAM 客户端或 MBAM Server 功能安装指定的计算机正确做好 MBAM 设置的准备。

**注意** MBAM 安装程序将检查在安装开始之前是否满足所有先决条件。 如果不满足所有先决条件，安装程序将失败。

 

[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)

## 规划 MBAM 2.0 组策略要求


在 MBAM 可以管理企业中的客户端之前，必须为环境的加密要求定义组策略。

**重要提示** MBAM 将不会与独立的 BitLocker 驱动器加密的策略配合使用。 必须为 MBAM 定义组策略设置，否则 BitLocker 加密和强制将失败。

 

[计划 MBAM 2.0 组策略要求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)

## 规划 MBAM 2.0 管理员角色


MBAM 管理员角色由在安装 BitLocker 管理和监视服务器、合规性和审核报告功能以及合规性和审核状态数据库时由 MBAM 安装程序创建的本地组管理。

通过在 ActiveDirectoryDomainServices 中创建安全组，将相应的管理员帐户添加到这些组，然后将这些安全组添加到 BitLocker 管理和监视本地组，可以更好地管理 Microsoft BitLocker 管理和监视角色的成员身份。 有关详细信息，请参阅[如何管理 MBAM 管理员角色](how-to-manage-mbam-administrator-roles-mbam-2.md)。

## MBAM 规划的其他资源


[计划 MBAM 2.0](planning-for-mbam-20-mbam-2.md)

[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)

 

 





