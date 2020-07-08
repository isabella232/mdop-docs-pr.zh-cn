---
title: 如何使用 Configuration Manager 验证 MBAM 安装
description: 如何使用 Configuration Manager 验证 MBAM 安装
author: dansimp
ms.assetid: 8e268539-91c3-4e8a-baae-faf3605da818
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 500c6f6ee5138b5677bf1fa20e2627a56981df1f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803208"
---
# 如何使用 Configuration Manager 验证 MBAM 安装


使用配置管理器安装 Microsoft BitLocker 管理和监视（MBAM）后，通过完成以下步骤验证安装是否已成功设置 MBAM 的所有必要功能。

**通过 Configuration Manager 验证 MBAM Server 功能安装**

1.  在部署 System Center Configuration Manager 的服务器上，打开 **"控制面板"**。 选择用于卸载或更改程序的程序。 验证 " **Microsoft BitLocker 管理和监视**" 是否显示在 "程序和功能" 列表中。

    **注意** 若要验证安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。

     

2.  使用 Configuration Manager 控制台确认显示名为 "MBAM 支持的计算机" 的新集合。

    若要查看 Configuration Manager 2007 的集合，请执行以下操作：单击 "**网站数据库**" （ &lt; **SiteCode** &gt;  -  &lt; **服务器名** &gt; 、 &lt; **SiteName** &gt; ）、"**计算机管理**"。

    要查看具有 SystemCenter2012 ConfigurationManager 的集合，请执行以下操作：单击 "**资源和合规性**" 工作区，**设备集合**。

3.  使用 Configuration Manager 控制台验证 " **MBAM** " 文件夹中是否列出以下报表：

    -   BitLocker 计算机合规性

    -   BitLocker 企业合规性仪表板

    -   BitLocker 企业合规性详细信息

    -   BitLocker 企业合规性摘要

    若要查看 Configuration Manager 2007 的报表，请单击 "**报告**"、"**报告服务**"、"\\ &lt; **服务器名** &gt; "、"**报告文件夹**"

    查看带有 SystemCenter2012 ConfigurationManager 的报表：单击 "**监视**" 工作区、"**报告**" 和 "**报告**"。

4.  使用 Configuration Manager 控制台确认已列出配置基线 "BitLocker 保护"。

    若要查看配置管理器的配置基线2007：单击 "**所需配置管理**"、"**配置基线**"。

    通过 SystemCenter2012 ConfigurationManager 查看配置基线：单击 "**资源和合规性**" 工作区、"**合规性设置**"、"**配置基线**"。

5.  使用 Configuration Manager 控制台确认显示以下新配置项目：

    -   BitLocker 固定数据驱动器保护

    -   BitLocker 操作系统驱动器保护

    若要查看 Configuration Manager 2007 的配置项目，请单击 "**所需的配置管理**"、"**配置项目**"。

    若要查看 SystemCenter2012 ConfigurationManager 的配置项目，请执行以下操作：单击 "**资源和合规性**" 工作区、**合规性设置**、**配置项目**。

## 相关主题


[使用 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





