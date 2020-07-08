---
title: 委派针对生产环境的访问权限
description: 委派针对生产环境的访问权限
author: dansimp
ms.assetid: 4c670581-8c47-41ea-80eb-02846ff1ec1f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a3920a8ba5835cbbcb8a74f0af4e3ca1e1c5f43f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801932"
---
# 委派针对生产环境的访问权限


在高级组策略管理（AGPM）中，你可以更改对域生产环境中的组策略对象（Gpo）的访问权限，从而替换这些 Gpo 上的任何现有权限。 你可以在域级别配置权限，以允许或阻止用户在未使用组策略管理控制台（GPMC）中的 "**更改控制**" 文件夹时编辑、删除或修改生产环境中的 gpo 的安全。

**注意**  
-   更改对生产环境的访问权限的委派不会影响用户链接 Gpo 的能力。

-   当 Gpo 受控制或部署时，将删除除具有 "**读取**" 和 "**应用**" 权限的帐户之外的任何其他帐户的访问权限。

 

具有 AGPM 管理员（完全控制）角色的用户帐户，或者需要高级组策略管理（AGPM）中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**更改对域生产环境中的 Gpo 的访问权限**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  单击 "**生产委派**" 选项卡。

3.  若要为无权访问生产环境的用户或组添加权限，或者替换具有访问权限的用户或组的权限，请执行以下操作：

    1.  单击 "**添加**"，选择用户或组，然后单击 **"确定"**。

    2.  为生产环境选择要委派给该用户或组的权限，然后单击 **"确定"**。

4.  若要删除用户或组对生产环境的所有权限，请选择该用户或组，单击 "**删除**"，然后单击 **"确定"**。

### 其他注意事项

-   默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。 具体说来，您必须具有域的 "**修改安全**权限"。

-   无法在 "**生产委派**" 选项卡上更改 AGPM 服务帐户的权限。

-   默认情况下，以下帐户具有生产环境中的 Gpo 的权限：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">帐户</th>
    <th align="left">Gpo 的默认权限</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>&lt;AGPM 服务帐户&gt;</p></td>
    <td align="left"><p>编辑设置、删除、修改安全性</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>经过身份验证的用户</p></td>
    <td align="left"><p>阅读、应用</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>域管理员</p></td>
    <td align="left"><p>编辑设置、删除、修改安全性</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>企业管理员</p></td>
    <td align="left"><p>编辑设置、删除、修改安全性</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>企业域控制器</p></td>
    <td align="left"><p>已阅读</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>系统</p></td>
    <td align="left"><p>编辑设置、删除、修改安全性</p></td>
    </tr>
    </tbody>
    </table>

     

-   组策略创建者所有者组的成员身份应受到限制，soit 不会用于绕过对 Gpo 的访问的 AGPM 管理。 （在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）

### 其他参考资料

-   [配置高级组策略管理](configuring-advanced-group-policy-management-agpm40.md)

 

 





