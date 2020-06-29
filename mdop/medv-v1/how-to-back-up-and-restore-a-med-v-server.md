---
title: 如何备份和还原 MED-V 服务器
description: 如何备份和还原 MED-V 服务器
author: dansimp
ms.assetid: 8d05e3a4-279b-4ce6-a319-8a09e7a30c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51cfe3727896ed68a1fd67441174a294a1073cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803298"
---
# 如何备份和还原 MED-V 服务器


可以备份服务器上的 XML 文件，然后在服务器上的数据丢失的情况下还原。

**备份 MED-V 服务器**

-   备份位于* &lt; InstallDir &gt; \\Servers\\ConfigurationServer*中的以下文件：

    **注意** 如果配置已更改为默认值，则文件可能存储在其他位置。

     

    -   ClientPolicy.xml

    -   ClientSettings.xml

    -   ConfigurationFiles.xml

    -   OrganizationPolicy.xml

    -   WorkspaceKeys.xml

    **注意** ServerSettings.xml 文件也可以备份。 但是，如果特定配置已更改（例如，在原始服务器上，则 MED-V VM 目录位于 "*C:\\Vms*" 中，在新服务器上不存在此类目录），可能会导致错误。

     

**还原 MED-V 服务器**

1.  安装新的 MED-V 服务器。

2.  将备份文件复制到以下目录：

    *&lt;InstallDir &gt; \\Servers\\ConfigurationServer*

3.  重新启动 MED-V 服务。

 

 





