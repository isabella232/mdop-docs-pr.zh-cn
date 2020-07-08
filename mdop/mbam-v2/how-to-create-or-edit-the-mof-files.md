---
title: 如何创建或编辑 mof 文件
description: 如何创建或编辑 mof 文件
author: dansimp
ms.assetid: 4d19d707-b90f-4057-a6e9-e4221a607190
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5f59e9133dd25ecf45d16a5cb704d6ea00923d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803745"
---
# 如何创建或编辑 mof 文件


在通过配置管理器安装 Microsoft BitLocker 管理和监视（MBAM）之前，需要编辑配置 mof 文件。 你还需要根据你使用的 Configuration Manager 版本编辑或创建 Sms \ _def 的 mof 文件。

## 编辑 Configuration.mof 文件


若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，您必须编辑 Microsoft System Center Configuration Manager 2007 和 SystemCenter2012 ConfigurationManager 的 Configuration mof 文件。

[编辑 Configuration.mof 文件](edit-the-configurationmof-file.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a>创建或编辑 Sms \ _def 的 mof 文件


若要使客户端计算机能够在 MBAM Configuration Manager 报表中报告 BitLocker 合规性详细信息，您必须创建或编辑 Sms \ _def 的 mof 文件。 在 Configuration Manager 2007 中，文件已存在，因此你需要编辑现有文件，但不能覆盖现有文件。 如果您使用的是 SystemCenter2012 ConfigurationManager，则必须创建该文件。

[创建或编辑 Sms \ _def 的 mof 文件](create-or-edit-the-sms-defmof-file.md)

## 相关主题


[使用 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





