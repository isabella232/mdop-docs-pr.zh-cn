---
title: 如何在同一计算机上部署 App-V 4.6 和 App-V 5.0 客户端
description: 如何在同一计算机上部署 App-V 4.6 和 App-V 5.0 客户端
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.prod: w10
ms.openlocfilehash: f10f3d159c4724f3b486215b1169825bb029316d
ms.sourcegitcommit: 0132cd232b9c030820d95d91b71c4def0184400a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "11907225"
---
# <a name="how-to-deploy-the-app-v-46-and-the-app-v-50-client-on-the-same-computer"></a>如何在同一计算机上部署 App-V 4.6 和 App-V 5.0 客户端

**注意：** App-V 4.6 已退出主流支持。 以下假定已安装 App-V 4.6 SP3 客户端。

使用以下信息在同一计算机上安装 App-V 5.0 (最好使用最新的 Service Pack 和修补程序) 和 App-V 4.6 SP3 客户端。 有关支持的版本、要求和其他规划信息，请参阅 Planning [for Migrating from a Previous Version of App-V。](planning-for-migrating-from-a-previous-version-of-app-v.md)

**在同一计算机上部署 App-V 5.0 客户端和 App-V 4.6 客户端**

1.  在运行 App-V 4.6 版本的客户端计算机上安装 App-V 5.0 SP3 客户端。 为了获得最佳结果，我们建议您将所有可用更新安装到 App-V 5.0 SP3 客户端。

2.  逐步转换或重新排序程序包。

    -   若要转换包，请使用 App-V 5.0 包转换器，并将所需的包转换为 App-V 5.0 (**.appv**) 文件格式。

    -   若要对程序包重新排序，请考虑使用最新版本的 Sequencer，以获得最佳结果。

    有关发布程序包的信息，请参阅如何使用管理控制台 [发布程序包](how-to-publish-a-package-by-using-the-management-console-50.md)。

3.  将程序包部署到客户端计算机。

4.  根据需要转换扩展点。 有关详情，请参阅以下资源：

    -   [如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [如何转换在以前版本的 App-V 中创建的程序包](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  测试 App-V 5.0 程序包是否成功，然后删除 4.6 程序包。 若要检查客户端计算机的用户状态，建议使用用户体验虚拟化或其他用户环境管理工具。 [](https://technet.microsoft.com/library/dn458947.aspx)

    **收到 App-V 的建议**吗？ 在此处添加建议或对建议 [投票](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)。 **有 App-V 问题？** 使用 [App-V TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## <a name="related-topics"></a>相关主题


[计划从以前版本的 App-V 迁移](planning-for-migrating-from-a-previous-version-of-app-v.md)

[部署 App-V 5.0 Sequencer 和 Client](deploying-the-app-v-50-sequencer-and-client.md)

 

 





