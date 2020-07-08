---
title: 从备份还原存档
description: 从备份还原存档
author: dansimp
ms.assetid: b83f6173-a236-4da2-b16e-8df20920d4cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a1b7039ad587cf9c8d7f914fe3b963e12ba8949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801800"
---
# 从备份还原存档


如果发生灾难且高级组策略管理（AGPM）的存档已损坏或被破坏，则 AGPM 管理员（完全控制）可以先预准备好的备份副本还原存档，然后从域的生产环境中导入不在存档中的任何组策略对象（Gpo），或者生产中版本的版本比存档中的版本更新。 有关如何将档案备份还原到其他服务器的信息，请参阅[移动 AGPM 服务器和存档](move-the-agpm-server-and-the-archive-agpm40.md)。

完成此过程需要访问 AGPM 服务器（安装了 AGPM 服务的计算机）和包含该存档的文件夹的用户帐户。

**从备份还原存档**

1.  停止 AGPM 服务。 有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。

2.  删除现有存档。 默认情况下，"存档" 文件夹是%ProgramData%\\Microsoft\\AGPM，但安装了 Microsoft 高级组策略管理-服务器的 AGPM 管理员可能在安装过程中输入了不同的位置。

3.  通过配置存档路径、AGPM 服务帐户、存档所有者和侦听端口来重新创建存档文件夹。 使用在原始安装期间使用的相同值不是必需的。 有关详细信息，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm40.md)。

4.  将档案备份的内容复制到 "存档" 文件夹，复制子文件夹和文件，以确保每个子文件夹和文件继承 "存档" 文件夹的权限。 注意不要覆盖 "存档" 文件夹。

5.  如果不确定存档备份中的 GPO 是否比生产中该 GPO 的副本更新，请生成差异报告并比较其设置。 有关详细信息，请参阅[标识 gpo、Gpo 版本或模板之间的差异](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md)。

6.  重新启动 AGPM 服务。 有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。

### 其他参考资料

-   [备份存档](back-up-the-archive-agpm40.md)

-   [移动 AGPM 服务器和存档](move-the-agpm-server-and-the-archive-agpm40.md)

-   [管理存档](managing-the-archive-agpm40.md)

 

 





