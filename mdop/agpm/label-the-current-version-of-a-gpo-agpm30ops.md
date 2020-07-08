---
title: 标记当前版本的 GPO
description: 标记当前版本的 GPO
author: dansimp
ms.assetid: 3845211a-0bc9-4875-9906-cb758c443825
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f9e656258591a56397c5a8053b2e98772f57949a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802708"
---
# 标记当前版本的 GPO


你可以标记组策略对象（GPO）的当前版本，以便在其历史记录中轻松识别。 你可以使用标签来标识在出现问题时可以回退的已知正常版本。 此外，在一次为多个具有相同标签的 Gpo 添加标识时，你可以将应回滚到同一点的相关 Gpo 标记为在稍后需要回滚。

需要具有编辑器、审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必需权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**在其历史记录中标记 Gpo 的当前版本**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  单击要为其标记当前版本的 GPO。 若要选择多个 Gpo，请按 SHIFT 并单击一组连续 Gpo 中的最后一个 GPO，或者按 CTRL 并单击各个 Gpo。 右键单击所选的 GPO，然后单击 "**标签**"。

4.  键入要在选定的每个 GPO 的历史记录中显示的标签和注释，然后单击 **"确定"**。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。

### 其他注意事项

-   默认情况下，你必须是编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有**列表内容**并**编辑设置**或为 gpo**部署 gpo**权限。

### 其他参考资料

-   [编辑 GPO](editing-a-gpo-agpm30ops.md)

 

 





