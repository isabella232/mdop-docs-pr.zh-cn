---
title: 备份存档
description: 备份存档
author: dansimp
ms.assetid: 400176da-3518-4475-ad19-c96cda6ca7ba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a75099e7a6624850ee0511cf65feddf63909a0c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802124"
---
# 备份存档


若要帮助恢复高级组策略管理（AGPM）的存档（如果存在灾难），AGPM 管理员（完全控制）应经常备份存档。 默认情况下，将在%ProgramData%\\Microsoft\\AGPM. 中创建存档。 但是，你可以在 Microsoft 高级组策略管理-服务器的安装期间指定另一个路径。

对 AGPM 服务器具有访问权限的用户帐户（安装了 AGPM 服务的计算机）和包含存档的文件夹需要完成此过程。

**备份存档**

1.  停止 AGPM 服务。 有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm30ops.md)。

2.  使用 Windows 资源管理器、Xcopy、Windows Server®备份或其他备份工具备份存档文件夹。 请确保备份隐藏、系统和只读文件。

3.  将档案备份存储在安全位置。

4.  重新启动 AGPM 服务。 有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm30ops.md)。

**注意** 如果 AGPM 管理员很少备份存档，则档案备份中的组策略对象（Gpo）将不会是最新的。 为了更好地确保存档备份是最新的，请将存档备份为组织的每日备份策略的一部分。

 

### 其他参考资料

-   [从备份还原存档](restore-the-archive-from-a-backup.md)

-   [移动 AGPM 服务器和存档](move-the-agpm-server-and-the-archive.md)

-   [管理存档](managing-the-archive.md)

 

 





