---
title: 为 UE-V 1.0 部署设置存储位置
description: 为 UE-V 1.0 部署设置存储位置
author: dansimp
ms.assetid: b187d44d-649b-487e-98d3-a61ee2be8c2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c179be0882bc6a0efc0f11f21fc231f03b63b0fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804008"
---
# 为 UE-V 1.0 部署设置存储位置


Microsoft 用户体验虚拟化（UE-V）部署需要设置存储位置，其中的用户设置存储在设置包文件中。 可通过以下两种方式之一配置设置存储位置：

-   **Active directory 主目录**-如果在 Active directory 中为用户定义了主目录，则 ue-v agent 将使用此位置存储设置位置程序包。 UE-V agent 会在主目录的根目录下动态创建特定于用户的存储文件夹。 如果未定义设置存储位置，则代理仅使用 Active Directory 的主目录。

-   **创建设置存储共享**-设置存储共享是可由 ue-v 用户访问的标准网络共享。

## 部署 UE-V 设置存储共享


创建设置存储共享时，应仅对需要访问权限的用户限制访问权限。 下表中显示了必要的权限。

**部署 UE-V 网络共享**

1.  为 UE-V 用户创建新的安全组。

2.  在集中放置的计算机上创建将存储 UE-V 设置程序包的新文件夹，然后向 UE-V 用户授予对该文件夹的组权限。 支持 UE-V 的管理员将需要此共享文件夹的权限。

3.  为设置存储位置文件夹设置以下共享级（SMB）权限：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>用户帐户</strong></th>
    <th align="left"><strong>推荐的权限</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>无权限</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 用户的安全组</p></td>
    <td align="left"><p>完全控制</p></td>
    </tr>
    </tbody>
    </table>

     

4.  为设置存储位置文件夹设置以下 NTFS 权限：

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>用户帐户</strong></th>
    <th align="left"><strong>推荐的权限</strong></th>
    <th align="left"><strong>文件夹</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>创建者/所有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>仅子文件夹和文件</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 用户的安全组</p></td>
    <td align="left"><p>列出文件夹/读取数据、创建文件夹/附加数据</p></td>
    <td align="left"><p>仅此文件夹</p></td>
    </tr>
    </tbody>
    </table>

     

5.  单击 **"确定"** 关闭对话框。

此权限配置允许用户为设置存储创建文件夹。 UE-V agent `settingspackage` 在用户的上下文中运行时创建并保护文件夹。 用户接收其文件夹的 "完全控制" `settingspackage` 。 其他用户不会继承对此文件夹的访问权限。 无需创建和保护单个用户目录，因为这将由在用户上下文中运行的代理自动完成。

**注意** 在为设置存储共享使用 Windows 服务器时，可以配置其他安全。 UE-V 可以配置为验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。 若要启用其他安全，请完成以下操作：

1.  将名为 "RepositoryOwnerCheckEnabled" 的**REG \ _DWORD**注册表项添加到**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration.**

2.  将注册表项值设置为1。

 

## 相关主题


[部署 UE-V 1.0](deploying-ue-v-10.md)

[UE-V 1.0 支持的配置](supported-configurations-for-ue-v-10.md)

部署用于用户体验虚拟化设置模板和设置程序包的中心存储[安装 Ue-v 生成器](installing-the-ue-v-generator.md)

[部署 UE-V 代理](deploying-the-ue-v-agent.md)

 

 





