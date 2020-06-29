---
title: 使用 Management Console 管理 App-V 5.0 虚拟应用程序
description: 使用 Management Console 管理 App-V 5.0 虚拟应用程序
author: dansimp
ms.assetid: e9280dbd-782b-493a-b495-daab25247795
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2016
ms.openlocfilehash: 7a71f7c0fd82f8ef9d1efd5b978591b6838a648a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798653"
---
# 使用 Management Console 管理 App-V 5.0 虚拟应用程序


使用 Microsoft Application Virtualization （App-v）5.0 管理服务器管理你的环境中的程序包、连接组和程序包访问。 服务器将应用程序图标、快捷方式和文件类型关联发布到运行 app-v 5.0 客户端的已授权计算机。 一个或多个管理服务器通常共享一个用于配置和程序包信息的通用数据存储。

管理服务器使用 Active Directory 域服务（AD DS）组管理用户身份验证，并安装 SQL Server 以管理数据库和数据存储。

由于管理服务器将应用程序流式处理应用程序，因此，这些服务器非常适合具有可靠、高带宽 Lan 的系统配置。 管理服务器包含以下组件：

-   管理服务器-使用管理服务器管理程序包和连接组。

-   发布服务器-使用发布服务器将程序包部署到运行 app-v 5.0 客户端的计算机。

-   管理数据库-使用管理数据库管理程序包访问和发布服务器与管理服务器的同步。

## 管理控制台任务


可通过 app-v 5.0 管理控制台执行的最常见任务有：

-   [如何连接到 Management Console](how-to-connect-to-the-management-console-beta.md)

-   [如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)

-   [如何使用管理控制台配置对程序包的访问权限](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

-   [如何使用管理控制台发布程序包](how-to-publish-a-package-by-using-the-management-console-50.md)

-   [如何使用管理控制台删除程序包](how-to-delete-a-package-in-the-management-console-beta.md)

-   [如何使用管理控制台添加或删除管理员](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)

-   [如何使用管理控制台注册和注销发布服务器](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console.md)

-   [如何使用 App-V 5.0 Management Console 创建自定义配置文件](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)

-   [如何使用 Management Console 将访问权限和配置转移到其他版本的程序包](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console.md)

-   [如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console.md)

-   [在管理控制台中配置应用程序和默认虚拟应用程序扩展](configure-applications-and-default-virtual-application-extensions-in-management-console.md)

App-v 5.0 管理控制台的主要元素包括：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">管理控制台选项卡</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>概述</p></td>
<td align="left"><p></p>
<ul>
<li><p><strong>App-v Sequencer </strong> - 若要查看有关使用 app-v 5.0 Sequencer 的常规信息，请选择此选项。</p></li>
<li><p><strong>应用程序包库 </strong> –选择此选项可打开 <strong> 管理控制台的 "程序包" </strong> 页面。 使用此页面查看已添加到服务器的程序包。 您还可以管理连接组以及添加或升级程序包。</p></li>
<li><p><strong>服务器 </strong> -选择此选项可打开 <strong> 管理控制台的 "服务器" </strong> 页面。 使用此页面查看已向 app-v 5.0 基础结构注册的服务器的列表。</p></li>
<li><p><strong>客户端 </strong> -选择此选项可查看有关 app-v 5.0 客户端的常规信息。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>"程序包" 选项卡</p></td>
<td align="left"><p>使用 " <strong> 程序包 </strong> " 选项卡添加或升级程序包。 您也可以通过单击 "连接组" 来管理连接组 <strong> </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>服务器选项卡</p></td>
<td align="left"><p>使用 " <strong> 服务器" </strong> 选项卡注册新服务器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>"管理员" 选项卡</p></td>
<td align="left"><p>使用 " <strong> 管理员 </strong> " 选项卡注册、添加或删除 app-v 5.0 环境中的管理员。</p></td>
</tr>
</tbody>
</table>

 






## <a href="" id="other-resources-for-this-app-v-5-0-deployment-"></a>此 App-v 5.0 部署的其他资源


-   [Microsoft Application Virtualization 5.0 管理员指南](microsoft-application-virtualization-50-administrators-guide.md)

-   [App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





