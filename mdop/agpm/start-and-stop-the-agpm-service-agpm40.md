---
title: 启动和停止 AGPM 服务
description: 启动和停止 AGPM 服务
author: dansimp
ms.assetid: dcc9566c-c515-4fbe-b7f5-8ac030141307
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c254cc122c43262ff5ec4cb0bf5a5ab2c77fac3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802524"
---
# 启动和停止 AGPM 服务


AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对存档和生产环境中的组策略对象（Gpo）的访问。

**重要提示** 停止或禁用 AGPM 服务将阻止 AGPM 客户端通过服务器执行任何操作（如列出或编辑 Gpo）。

 

需要访问 AGPM 服务器（安装了 AGPM 服务的计算机）的用户帐户才能完成此过程。

**启动或停止 AGPM 服务**

1.  在安装了 Microsoft 高级组策略管理-服务器（以及 AGPM 服务）的计算机上，单击 "**开始**"，单击 "**控制面板**"，单击 "**管理工具**"，然后单击 "**服务**"。

2.  在服务列表中，右键单击 " **AGPM 服务**"，然后选择 "**开始**"、"**重新启动**" 或 "**停止**"。

    **小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。 这样做可能会阻止 AGPM 服务启动。

     

### 其他参考资料

-   [管理 AGPM 服务](managing-the-agpm-service-agpm40.md)

 

 





