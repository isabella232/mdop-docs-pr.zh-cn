---
title: App-V 5.1 安全注意事项
description: App-V 5.1 安全注意事项
author: dansimp
ms.assetid: 6bc6c1fc-f813-47d4-b763-06fd4faf6a72
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a5606b3e0ba5e6fb8c62f14e2ed8d93ea2cf134
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798627"
---
# App-V 5.1 安全注意事项


本主题包含有关 Microsoft Application Virtualization （App-v）5.1 的帐户和组、日志文件和其他安全相关注意事项的简要概述。

**重要提示**  
App-v 5.1 不是一种安全产品，并且不提供对安全环境的任何保证。



## PackageStoreAccessControl （PSAC）功能已弃用


从2014年6月起生效，在单用户和多用户环境中，在 Microsoft Application Virtualization （App-v） 5.0 Service Pack 2 （SP2）中引入的 PackageStoreAccessControl （PSAC）功能已被弃用。

## 常规安全注意事项


**了解安全风险。** App-v 5.1 的最严重的风险是它的功能可能会被未经授权的用户劫持，这样就可以在 app-v 5.1 客户端上重新配置密钥数据。 由于拒绝服务攻击，较短时间内的 app-v 5.1 功能丢失通常不会产生灾难性影响。

**确保计算机的物理安全**。 安全性不完整，没有物理安全。 对 app-v 5.1 服务器具有物理访问权限的任何人都可能会攻击整个客户端基。 任何潜在的物理攻击都必须被视为高风险并相应地缓解。 App-v 5.1 服务器应存储在具有可控访问权限的物理安全的服务器机房中。 通过让操作系统锁定计算机，或使用安全的屏幕保护程序，确保管理员不在物理上显示这些计算机。

**对所有计算机应用最新的安全更新**。 若要随时了解操作系统、Microsoft SQL Server 和 App-v 5.1 的最新更新，请订阅安全通知服务（ <https://go.microsoft.com/fwlink/p/?LinkId=28819> ）。

**使用强密码或密码短语**。 对于所有 App-v 5.1 和 App-v 5.1 管理员帐户，请始终使用具有15个或更多字符的强密码。 千万不要使用空白密码。 有关密码概念的详细信息，请参阅 TechNet 上的 "帐户密码和策略" 白皮书（ <https://go.microsoft.com/fwlink/p/?LinkId=30009> ）。

## App-v 5.1 中的帐户和组


用户帐户管理的最佳做法是创建域全局组并向其添加用户帐户。 然后，将域全局帐户添加到 App-v 5.1 服务器上必需的 App-v 5.1 本地组。

**注意**  
需要连接到发布服务器的 app-v 客户端计算机帐户必须是发布服务器**用户**本地组的一部分。 默认情况下，域中的所有计算机都是 "**授权用户**" 组的一部分，该用户组是 "**用户**本地组" 的一部分。



### <a href="" id="-------------app-v-5-1-server-security"></a> App-v 5.1 服务器安全

在 App-v 5.1 安装过程中不会自动创建任何组。 应创建以下 Active Directory 域服务全局组以管理 App-v 5.1 服务器操作。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组名称</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 管理管理员组</p></td>
<td align="left"><p>用于管理 app-v 5.1 管理服务器。 此组在 App-v 5.1 管理服务器安装期间创建。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>在完成安装后，没有使用管理控制台创建组的方法。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>管理服务帐户的数据库读/写</p></td>
<td align="left"><p>提供对管理数据库的读/写访问权限。 应在安装 app-v 5.1 管理数据库期间创建此帐户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 管理服务安装管理员帐户</p>
<div class="alert">
<strong>注意</strong><br/><p>仅当管理数据库与服务分开安装时，才需要执行此操作。</p>
</div>
<div>

</div></td>
<td align="left"><p>提供对管理数据库中的架构版本表的公共访问权限。 应在安装 app-v 5.1 管理数据库期间创建此帐户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v Reporting Service 安装管理员帐户</p>
<div class="alert">
<strong>注意</strong><br/><p>仅当报告数据库与服务分开安装时，才需要执行此操作。</p>
</div>
<div>

</div></td>
<td align="left"><p>对报告数据库中的架构版本表的公共访问。 此帐户应在 App-v 5.1 reporting 数据库安装期间创建。</p></td>
</tr>
</tbody>
</table>



请考虑以下其他信息：

-   访问软件包共享-如果与管理服务器位于同一台计算机上的共享位于同一台计算机上，则**网络**服务需要对该共享的读取访问权限。 此外，每个 App-v 客户端计算机必须具有程序包共享的读取访问权限。

    **注意**  
    在早期版本的 App-v 中，程序包共享称为内容共享。



-   向管理服务器注册发布服务器-发布服务器必须在管理服务器上注册。 例如，必须将其添加到数据库，以便发布服务器计算机帐户能够调用管理服务 API。

### <a href="" id="-------------app-v-5-1-package-security"></a> App-v 5.1 程序包安全性

以下将帮助你规划如何确保虚拟化程序包的安全。

-   如果应用程序安装程序将访问控制列表（ACL）应用到文件或目录，则该 ACL 不会保留在程序包中。 当部署程序包时，如果文件或目录由用户修改，它将在 **% userprofile%** 中继承 acl 或继承目标计算机目录的 acl。 如果文件或目录在虚拟文件系统位置中不存在，则会出现前一种情况;如果文件或目录存在于虚拟文件系统位置（例如 **% windir%**）中，则会出现后一种情况。

## <a href="" id="---------app-v-5-1-log-files"></a> App-v 5.1 日志文件


在 App-v 5.1 设置期间，安装日志文件在安装用户的 **% temp%** 文件夹中创建。






## 相关主题


[针对 App-V 5.1 准备环境](preparing-your-environment-for-app-v-51.md)









