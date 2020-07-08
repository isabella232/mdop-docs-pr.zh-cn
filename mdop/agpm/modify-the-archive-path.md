---
title: 修改存档路径
description: 修改存档路径
author: dansimp
ms.assetid: 6d90daf9-58db-4166-b5b3-e84bb261164a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1fc6ba2bf415d3d1bc67144d0dec1030c6173026
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802639"
---
# 修改存档路径


存档路径是存档相对于 AGPM 服务器的位置。 存档路径可以指向 AGPM 服务器上的文件夹，也可以指向同一林中的另一台服务器上的文件夹。

存档路径和 AGPM 服务帐户是在安装 AGPM 服务器期间配置的，可在以后通过 AGPM 服务器上的 "**添加或删除程序**" 更改。

一个用户帐户，该帐户是域管理员组的成员，并且有权访问 AGPM 服务器（安装了 Microsoft 高级组策略管理-服务器的计算机），需要完成此过程。

**修改存档路径**

1.  在安装了 Microsoft 高级组策略管理-服务器的计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**添加或删除程序**"。

2.  单击 " **Microsoft 高级组策略管理-服务器**"，然后单击 "**更改**"。

3.  单击 "**下一步**"，然后单击 "**修改**"。

4.  按照屏幕上的说明配置 AGPM 服务的设置：

    1.  对于存档路径，输入与 AGPM 服务器相关的存档的新位置。 存档路径可以指向 AGPM 服务器或其他位置上的文件夹，但位置应该有足够的空间来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。

    2.  输入 AGPM 服务帐户的凭据。

        **重要提示** 修改安装会清除 AGPM 服务帐户的凭据。 您必须重新输入凭据，但它们不需要与原始安装期间使用的凭据相匹配。

        AGPM 服务帐户必须对它将管理的 Gpo 具有完全访问权限。 如果你将在单个域上管理 Gpo，则可以将主域控制器的本地系统帐户设置为 AGPM 服务帐户。

        如果你将在多个域上管理 Gpo，或者如果成员服务器是 AGPM 服务器，你应将其他帐户配置为 AGPM 服务帐户，因为一个域控制器的本地系统帐户无法访问其他域上的 Gpo。

         

    3.  对于存档所有者，请输入 AGPM 管理员的凭据（"完全控制"）。

5.  单击 "**更改**"，完成安装后，单击 "**完成**"。

### 其他参考资料

-   [管理 AGPM 服务](managing-the-agpm-service.md)

 

 





