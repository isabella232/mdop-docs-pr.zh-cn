---
title: 安装 MED-V 的先决条件
description: 安装 MED-V 的先决条件
author: dansimp
ms.assetid: cf3c0906-23eb-4c4a-8951-a65741720f95
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2b432b8c2b06e171eb339aab6c7b15efb20d5919
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803674"
---
# 安装 MED-V 的先决条件


以下是安装 MED-V 的先决条件：

[Active Directory 要求](#bkmk-activedirectoryrequirements)

[报表数据库](#bkmk-howtoinstallthereportdatabase)

[防病毒/备份软件配置](#bkmk-antivirusbackupsoftwareconfiguration)

[Microsoft Virtual PC 2007 SP1](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1)

## <a href="" id="bkmk-activedirectoryrequirements"></a>Active Directory 要求


配置 MED-V 服务器时，如果用户不属于服务器所属的同一域，则必须在域之间设置信任。

## <a href="" id="bkmk-howtoinstallthereportdatabase"></a>如何安装报表数据库


存储所有 MED-V 工作区日志需要报表数据库。 然后，日志数据库用于生成 MED-V 报告。 有关报表的信息，请参阅[Med-v 报告](med-v-reporting.md)。

SQL Server 可以安装在 MED-V 服务器所在的同一台服务器上，也可以安装在远程服务器上。 如果在远程服务器上安装，请参阅[在远程服务器上安装 SQL server](#bkmk-installingsqlserveronaremoteserver)。

### <a href="" id="bkmk-installingsqlserveronaremoteserver"></a>在远程服务器上安装 SQL Server

**在远程服务器上安装 SQL Server**

1.  在远程服务器上配置以下内容：

    -   实例名称-默认实例

    -   身份验证模式—混合模式

    -   用户-创建的默认用户是 "sa"

    -   密码-所需密码

    -   排序规则设置-默认

    -   使用情况报告设置中的错误-默认

2.  在 MED-V 服务器上安装以下文件：

    -   若要为 Microsoft SQL Server2008 安装管理包对象集合的先决条件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server2008 Native 客户端](https://go.microsoft.com/fwlink/?LinkId=164039)。

    -   若要为 Microsoft SQL Server2005 安装管理包对象集合的先决条件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server2005 Native 客户端](https://go.microsoft.com/fwlink/?LinkId=164038)。

    -   若要为 Microsoft SQL Server2008 安装所需的 dll 文件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server 2008 管理对象集合](https://go.microsoft.com/fwlink/?LinkId=164041)。

    -   若要为 Microsoft SQL Server2005 安装所需的 dll 文件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server2005 管理对象](https://go.microsoft.com/fwlink/?LinkId=164040)。

    -   若要安装为 SQL Server2008 提供其他值的独立安装程序包，请从 Microsoft 下载中心下载[MICROSOFT SQL Server2008 功能包](https://go.microsoft.com/fwlink/?LinkId=163960)。

    -   若要安装为 SQL Server2005 提供其他值的独立安装程序包，请从 Microsoft 下载中心下载[MICROSOFT SQL Server2005 的功能包]( https://go.microsoft.com/fwlink/?LinkId=163961)。

    有关这些文件的详细信息，请参阅 microsoft 下载中心的 microsoft [Sql Server2008 功能包](https://go.microsoft.com/fwlink/?LinkId=163960)（ https://go.microsoft.com/fwlink/?LinkId=163960) 或 microsoft [Sql Server2005 的功能包](https://go.microsoft.com/fwlink/?LinkId=163961)，请参阅 microsoft 下载中心（） https://go.microsoft.com/fwlink/?LinkId=163961) 。

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a>防病毒/备份软件配置


为了防止防病毒活动影响虚拟桌面的性能，建议在主机上运行的任何防病毒或备份处理中排除以下虚拟机文件类型：

-   \*.VMC

-   \*.VUD

-   \*.VSV

-   \*.CKM

-   \*.EVHD

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1"></a>如何安装和配置 Microsoft Virtual PC2007 SP1


**重要提示** 如果主计算机上存在虚拟 PC for Windows，请在安装 Virtual PC2007 SP1 之前将其卸载。

 

**安装 Microsoft Virtual PC2007 SP1**

1.  从 Microsoft 下载中心[虚拟 PC 2007 sp1](https://go.microsoft.com/fwlink/?LinkId=142994)下载虚拟 PC2007 SP1。

2.  在主机计算机上运行安装文件，然后按照向导操作。

3.  在提升模式下在主机计算机上安装 Virtual PC2007 SP1 更新。

    有关详细信息，请参阅[虚拟 PC 2007 SP1 的修补程序包说明](https://go.microsoft.com/fwlink/?LinkId=150575)。

    **注意** 运行 Virtual PC2007 SP1 需要虚拟 PC2007 SP1 更新。

     

## 相关主题


[支持的配置](supported-configurationsmedv-orientation.md)

 

 





