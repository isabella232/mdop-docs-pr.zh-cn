---
title: MED-V 1.0 SP1 升级清单
description: MED-V 1.0 SP1 升级清单
author: dansimp
ms.assetid: 1a462b37-8c7a-4826-9175-0b1b701d345b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9c418eff8dfb6146204d7d9212d42e49db000fb1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804134"
---
# MED-V 1.0 SP1 升级清单


若要将 Microsoft 企业版桌面虚拟化（MED-V）1.0 升级到 MED-V 1.0 服务 Pack1 （SP1），必须升级客户端。 服务器可以选择升级。

## 服务器升级


**将 MED-V 1.0 服务器升级到 MED-V 1.0 SP1**

1.  备份位于* &lt; InstallDir &gt; /Servers/ConfigurationServer*目录中的以下文件：

    -   OrganizationalPolicy.XML

    -   ClientPolicy.XML

    -   WorkspaceKeys.XML

2.  备份* &lt; InstallDir &gt; /服务器/ServerSettings.xml*文件。

3.  卸载 MED-V 1.0 服务器。

4.  安装 MED-V 1.0 SP1 服务器。

5.  将备份文件还原到相应的目录。

6.  重新启动 MED-V 服务器服务。

**注意** 如果服务器配置已更改为默认值，则文件可能存储在其他位置。

 

## 客户端升级


若要将 MED-V 1.0 客户端升级到 MED-V 1.0 SP1，请在 MED-V 1.0 客户端上安装 .msp 文件。 客户端和 MED-V 将自动升级。

 

 





