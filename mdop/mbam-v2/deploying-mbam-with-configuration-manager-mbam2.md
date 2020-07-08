---
title: 使用 Configuration Manager 部署 MBAM
description: 使用 Configuration Manager 部署 MBAM
author: dansimp
ms.assetid: 89d03e29-457a-471d-b893-e0b74a83ec50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c6cffc1cf51a26aeaa94fcb265199c19f0f34abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803371"
---
# 使用 Configuration Manager 部署 MBAM


以下过程介绍了如何使用 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 部署 Microsoft BitLocker 管理和监视（MBAM） usingthe 推荐的配置，这将在[配置管理器中使用 MBAM](getting-started---using-mbam-with-configuration-manager.md)中介绍。 建议的配置是在一个或多个 Microsoft BitLocker 管理和监视服务器上安装管理和监视功能，并在单独的服务器上安装 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager。

开始安装之前，请确保已满足系统必备和硬件和软件要求，以便通过使用[Configuration Manager 部署 MBAM 来](planning-to-deploy-mbam-with-configuration-manager-2.md)将 MBAM 与 configuration manager 一起安装。

如果你必须使用 Configuration Manager 拓扑重新安装 MBAM，你将需要首先删除某些 Configuration Manager 对象。 有关详细信息，请阅读[知识文库文章](https://go.microsoft.com/fwlink/?LinkId=286306)。

将 MBAM 与 Configuration Manager 一起安装的步骤分为以下类别。 完成每个类别的步骤以完成安装。

## 如何创建或编辑 mof 文件


若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，你必须编辑**配置 mof**文件，并根据你使用的 Configuration Manager 版本编辑或创建 Sms \ _def mof 文件。

[如何创建或编辑 mof 文件](how-to-create-or-edit-the-mof-files.md)

## 如何使用 Configuration Manager 安装 MBAM


本部分提供了有关如何在 Configuration Manager 服务器上安装以下内容的步骤： MBAM。数据库服务器上的恢复和审核数据库;以及管理和监视服务器上的管理和监视服务器功能。

[如何使用 Configuration Manager 安装 MBAM](how-to-install-mbam-with-configuration-manager.md)

## 如何验证 Configuration Manager 服务器上的 MBAM Server 功能安装


Microsoft BitLocker 管理和监视安装完成后，请验证安装是否已成功设置 Configuration Manager 服务器所需的所有必要 MBAM 功能。

[如何使用 Configuration Manager 验证 MBAM 安装](how-to-validate-the-mbam-installation-with-configuration-manager.md)

## 相关主题


[结合使用 MBAM 和 Configuration Manager](using-mbam-with-configuration-manager.md)

 

 





