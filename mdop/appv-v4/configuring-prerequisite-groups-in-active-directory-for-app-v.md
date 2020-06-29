---
title: 在 Active Directory 中为 App-V 配置必备组
description: 在 Active Directory 中为 App-V 配置必备组
author: dansimp
ms.assetid: 0010d534-46c0-44a3-b5c1-621b4d5e2c31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa1ab6393dee20203b715311d4e1dfdc4c22c679
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803053"
---
# 在 Active Directory 中为 App-V 配置必备组


在安装 Microsoft Application Virtualization （App-v）管理服务器之前，必须在 Active Directory 中创建以下对象。 App-v 使用 Active Directory 组控制对应用程序和管理功能的访问。 在服务器安装过程中以及发布应用程序时，您将使用这些组。

## 在 Active Directory 中为应用程序虚拟化配置必备项组


下表列出了安装 app-v 所需的 Active Directory 组。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">对象</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>组织单位（OU）</p></td>
<td align="left"><p>在 Active Directory 中为 App-v 所需的特定组创建一个 OU。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 管理组</p></td>
<td align="left"><p>在安装 app-v 管理服务器的过程中，必须选择一个 Active Directory 组以用作 App-v 管理员组，以便控制对管理控制台的管理访问。 为 App-v 管理员创建安全组，并将需要使用管理控制台的每位用户添加到该组。 您不能直接从 App-v 管理服务器安装程序创建此组。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Users 组</p></td>
<td align="left"><p>App-v 要求访问 App-v 函数的每个用户帐户都是与单个组相关联的提供程序策略的成员，用于通用平台访问。 使用现有组;例如，如果所有用户都具有对 App-v 的访问权限，或者创建新组，则为域用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>应用程序组</p></td>
<td align="left"><p>App-v 将使用单个应用程序与 Active Directory 组相关联的权限。 为每个应用程序创建一个 Active Directory 组，并根据需要向这些组分配用户，以控制用户对应用程序的访问权限。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[Application Virtualization 部署要求](application-virtualization-deployment-requirements.md)

[如何为 App-V Management Server 配置 Windows Server 2008](how-to-configure-windows-server-2008-for-app-v-management-servers.md)

 

 





