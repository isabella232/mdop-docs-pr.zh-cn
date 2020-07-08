---
title: 修改 AGPM 服务帐户
description: 修改 AGPM 服务帐户
author: dansimp
ms.assetid: 0d8d8c7b-f299-4fee-8414-406492156942
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0672ceed2fba17060e17d2ffcfa264da458b9897
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802651"
---
# 修改 AGPM 服务帐户


AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对存档和生产环境中的组策略对象（Gpo）的访问。 如果此服务已停止或禁用，则 AGPM 客户端无法通过服务器执行操作。

存档路径和 AGPM 服务帐户是在安装 AGPM 服务器期间配置的，可在以后通过 AGPM 服务器上的 "**添加或删除程序**" 更改。

**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。 这样做可能会阻止 AGPM 服务启动。

 

一个用户帐户，该帐户是域管理员组的成员，并且有权访问 AGPM 服务器（安装了 Microsoft 高级组策略管理-服务器的计算机），需要完成此过程。

**重要提示** AGPM 服务帐户必须对它将管理的 Gpo 具有完全访问权限，并将其授予 **"以服务形式登录**" 权限。 如果你将在单个域上管理 Gpo，则可以将主域控制器的本地系统帐户设置为 AGPM 服务帐户。

如果你将在多个域上管理 Gpo，或者如果成员服务器是 AGPM 服务器，你应将其他帐户配置为 AGPM 服务帐户，因为一个域控制器的本地系统帐户无法访问其他域上的 Gpo。

 

**修改 AGPM 服务帐户**

1.  在安装了 Microsoft 高级组策略管理-服务器的计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**添加或删除程序**"。

2.  单击 " **Microsoft 高级组策略管理-服务器**"，然后单击 "**更改**"。

3.  单击 "**下一步**"，然后单击 "**修改**"。

4.  按照屏幕上的说明配置 AGPM 服务的设置：

    1.  对于存档路径，请确认或更改相对于 AGPM 服务器的存档位置。 存档路径可以指向 AGPM 服务器或其他位置上的文件夹，但位置应该有足够的空间来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。

    2.  为 AGPM 服务帐户输入新的凭据。

    3.  对于存档所有者，请输入 AGPM 管理员的凭据（"完全控制"）。

5.  单击 "**更改**"，完成安装后，单击 "**完成**"。

### 其他参考资料

-   [管理 AGPM 服务](managing-the-agpm-service.md)

 

 





