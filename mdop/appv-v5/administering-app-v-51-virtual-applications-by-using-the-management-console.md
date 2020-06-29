---
title: 使用 Management Console 管理 App-V 5.1 虚拟应用程序
description: 使用 Management Console 管理 App-V 5.1 虚拟应用程序
author: dansimp
ms.assetid: a4d078aa-ec54-4fa4-9463-bfb3b971d724
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63ec965519bedef08b09c961dc5d1c90e1d8d694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798652"
---
# 使用 Management Console 管理 App-V 5.1 虚拟应用程序


使用 Microsoft Application Virtualization （App-v）5.1 管理服务器管理你的环境中的程序包、连接组和程序包访问。 服务器将应用程序图标、快捷方式和文件类型关联发布到运行 app-v 5.1 客户端的已授权计算机。 一个或多个管理服务器通常共享一个用于配置和程序包信息的通用数据存储。

管理服务器使用 Active Directory 域服务（AD DS）组管理用户身份验证，并安装 SQL Server 以管理数据库和数据存储。

由于管理服务器将应用程序流式处理应用程序，因此，这些服务器非常适合具有可靠、高带宽 Lan 的系统配置。 管理服务器包含以下组件：

-   管理服务器-使用管理服务器管理程序包和连接组。

-   发布服务器-使用发布服务器将程序包部署到运行 app-v 5.1 客户端的计算机。

-   管理数据库-使用管理数据库管理程序包访问和发布服务器与管理服务器的同步。

## 管理控制台任务


可通过 app-v 5.1 管理控制台执行的最常见任务有：

-   [如何连接到 Management Console](how-to-connect-to-the-management-console-51.md)

-   [如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)

-   [如何使用管理控制台配置对程序包的访问权限](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

-   [如何使用管理控制台发布程序包](how-to-publish-a-package-by-using-the-management-console-51.md)

-   [如何使用管理控制台删除程序包](how-to-delete-a-package-in-the-management-console-51.md)

-   [如何使用管理控制台添加或删除管理员](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)

-   [如何使用管理控制台注册和注销发布服务器](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console51.md)

-   [如何使用 App-V 5.1 Management Console 创建自定义配置文件](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)

-   [如何使用 Management Console 将访问权限和配置转移到其他版本的程序包](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console51.md)

-   [如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console51.md)

-   [如何使用管理控制台查看和配置应用程序和默认虚拟应用程序扩展](how-to-view-and-configure-applications-and-default-virtual-application-extensions-by-using-the-management-console-beta.md)

App-v 5.1 管理控制台的主要元素包括：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">管理控制台选项卡</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>"程序包" 选项卡</p></td>
<td align="left"><p>使用 " <strong> 程序包 </strong> " 选项卡添加或升级程序包。</p></td>
</tr>
<tr class="even">
<td align="left"><p>"连接组" 选项卡</p></td>
<td align="left"><p>使用 " <strong> 连接组" </strong> 选项卡管理连接组。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>服务器选项卡</p></td>
<td align="left"><p>使用 " <strong> 服务器" </strong> 选项卡注册新服务器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>"管理员" 选项卡</p></td>
<td align="left"><p>使用 " <strong> 管理员 </strong> " 选项卡注册、添加或删除 app-v 5.1 环境中的管理员。</p></td>
</tr>
</tbody>
</table>

 

**重要提示** 必须在打开 Web 管理控制台的浏览器上启用 JavaScript。

 






## <a href="" id="other-resources-for-this-app-v-5-1-deployment-"></a>此 App-v 5.1 部署的其他资源


-   [Microsoft Application Virtualization 5.1 管理员指南](microsoft-application-virtualization-51-administrators-guide.md)

-   [App-V 5.1 的操作](operations-for-app-v-51.md)

 

 





