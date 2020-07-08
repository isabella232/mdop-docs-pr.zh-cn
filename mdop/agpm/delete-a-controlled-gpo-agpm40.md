---
title: 删除受控的 GPO
description: 删除受控的 GPO
author: dansimp
ms.assetid: 2a461018-aa0b-4ae3-b079-efc554ca4a3d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 103d2f7de9fa8055fdc57505e0e5ac4e0a50bbfa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802836"
---
# 删除受控的 GPO


审批者可以删除一个受控制的组策略对象（GPO），将其移动到回收站。

需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**删除受控 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  右键单击要删除的 GPO，然后单击 "**删除**"。

    -   若要从存档中删除 GPO，同时在生产环境中保持 GPO 的部署版本，请单击 "**仅从存档中删除 gpo**"。

    -   若要从域的存档和生产环境中删除 GPO，请单击 "**从存档和生产中删除 gpo**"。

4.  键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 GPO 将从 "**受控**" 选项卡中删除，并显示在 "**回收站**" 选项卡上，可在其中还原或销毁。 如果仅从存档中删除了该 GPO，它也会显示在 "不**受控制**" 选项卡上。

### 其他注意事项

-   默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并删除 GPO 的**gpo**权限。

-   若要从生产环境中删除不受管理的 GPO 而不先对其进行控制，请在**组策略管理控制台**中单击 "**林**"，单击 "**域**"，单击 " ** &lt; MyDomain &gt; **"，然后单击 "**组策略对象**"。 右键单击不受控制的 GPO，然后单击 "**删除**"。

### 其他参考资料

-   [删除、还原或销毁 GPO](deleting-restoring-or-destroying-a-gpo-agpm40.md)

 

 





