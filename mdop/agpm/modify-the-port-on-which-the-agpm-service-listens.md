---
title: 修改 AGPM 服务侦听的端口
description: 修改 AGPM 服务侦听的端口
author: dansimp
ms.assetid: a82c6873-e916-4a04-b263-aa612cd6956b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2af79ecb9bd05acbc55083163903ae14ab44d06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802636"
---
# 修改 AGPM 服务侦听的端口


AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对存档和生产环境中的组策略对象（Gpo）的访问。 默认情况下，AGPM 服务在端口4600上侦听。 你可以通过修改每个存档的高级组策略管理（AGPM）存档索引文件来更改此端口。

**注意** 在修改 AGPM 服务侦听的端口之前，建议备份 AGPM 存档索引文件（gpostate.xml）。 在安装高级组策略管理-服务器期间，此文件位于输入为存档路径的文件夹中。 默认情况下，此文件的此位置为 AGPM 服务器上% CommonAppData% \\Microsoft\\AGPM\\gpostate.xml%。 如果不知道哪些计算机托管存档，则可以按照修改存档路径的过程显示当前的存档路径。 有关详细信息，请参阅[修改存档路径](modify-the-archive-path.md)。

 

有权访问 AGPM 服务器（安装了 AGPM 服务的计算机）的用户帐户，需要存档索引文件才能完成此过程。

**修改 AGPM 服务侦听的端口**

1.  在托管存档的计算机上，在文本编辑器中打开存档索引文件（gpostate.xml）。

2.  在文件中，搜索 " **agpm： port =" 4600 "**。

3.  将**4600**替换为应侦听的 AGPM 服务的端口;然后，保存并关闭该文件。

4.  在 AGPM 服务器上，重新启动 AGPM 服务。 （有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service.md)。）

5.  在 AGPM 服务器连接中修改每个组策略管理员的端口。 （有关详细信息，请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。）

6.  对每个存档和 AGPM 服务器重复上述操作。

### 其他参考资料

-   [管理 AGPM 服务](managing-the-agpm-service.md)

 

 





