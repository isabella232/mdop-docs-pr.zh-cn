---
title: 如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端
description: 如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.openlocfilehash: 38e77ce6ce6c0dba7c67f6c0dfa5c9e263e07e20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798481"
---
# 如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端

**注意：** App-v 4.6 已退出主流支持。 以下示例假设已安装了 App-v 4.6 SP3 客户端。

使用以下信息在同一台计算机上安装 app-v 5.0 客户端（最好是使用最新的服务包和修补程序）和 App-v 4.6 SP3 客户端。 有关受支持的版本、要求和其他计划信息，请参阅[规划从早期版本的 App-v 迁移](planning-for-migrating-from-a-previous-version-of-app-v.md)。

**在同一台计算机上部署 app-v 5.0 客户端和 App-v 4.6 客户端**

1.  在运行 app-v 4.6 版本的客户端的计算机上安装 app-v 5.0 SP3 客户端。 为获得最佳结果，建议你将所有可用更新安装到 app-v 5.0 SP3 客户端。

2.  逐步转换或重新序列化程序包。

    -   若要转换程序包，请使用 app-v 5.0 程序包转换器，并将所需的程序包转换为 App-v 5.0 （**appv**）文件格式。

    -   若要对程序包进行重新排序，请考虑使用最新版本的 Sequencer 来获得最佳结果。

    有关发布程序包的详细信息，请参阅[如何使用管理控制台发布程序包](how-to-publish-a-package-by-using-the-management-console-50.md)。

3.  将程序包部署到客户端计算机。

4.  根据需要转换扩展点。 有关详细信息，请参阅下列资源：

    -   [如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [如何转换在以前版本的 App-V 中创建的程序包](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  测试 app-v 5.0 程序包是否成功，然后删除4.6 程序包。 若要检查客户端计算机的用户状态，我们建议你使用[用户体验虚拟化](https://technet.microsoft.com/library/dn458947.aspx)或其他用户环境管理工具。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[计划从以前版本的 App-V 迁移](planning-for-migrating-from-a-previous-version-of-app-v.md)

[部署 App-V 5.0 Sequencer 和 Client](deploying-the-app-v-50-sequencer-and-client.md)

 

 





