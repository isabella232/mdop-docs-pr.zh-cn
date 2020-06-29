---
title: 仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
description: 仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
author: dansimp
ms.assetid: 74180d8d-7b0f-460f-b301-53595cde8381
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9b89e1a1383997d6ebc92f8e034fbf2945823f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798077"
---
# 仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件


如果你要使用 System Center Configuration Manager 集成功能安装 Microsoft BitLocker 管理和监视（MBAM）2.5，则必须完成本主题中所述的先决条件，以及[独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器必备条件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)中所述的先决条件。 你还必须创建或修改 Configuration Manager 集成拓扑所需的 mof 文件。

## Configuration Manager 集成功能的先决条件


如果你正在通过 System Center Configuration Manager 集成拓扑配置 MBAM，则必须完成 Configuration Manager 所需的其他先决条件。

[Configuration Manager 集成功能的先决条件](prerequisites-for-the-configuration-manager-integration-feature.md)

## 编辑配置 mof 文件


若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，您必须编辑 SystemCenter2012 ConfigurationManager 和 Microsoft System Center Configuration Manager 2007 的 Configuration mof 文件。

[编辑 Configuration.mof 文件](edit-the-configurationmof-file-mbam-25.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a>创建或编辑 Sms \ _def 的 mof 文件


若要使客户端计算机能够在 MBAM Configuration Manager 报表中报告 BitLocker 合规性详细信息，您必须创建或编辑 Sms \ _def 的 mof 文件。 如果您使用的是 SystemCenter2012 ConfigurationManager，则必须创建该文件。 在 Configuration Manager 2007 中，文件已存在，因此你需要编辑现有文件，但不能覆盖现有文件。

[创建或编辑 Sms \ _def 的 mof 文件](create-or-edit-the-sms-defmof-file-mbam-25.md)


## 相关主题


[为 MBAM 2.5 准备你的环境](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)

[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

 

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




