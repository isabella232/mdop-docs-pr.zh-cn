---
title: 限制存储的 GPO 版本
description: 限制存储的 GPO 版本
author: dansimp
ms.assetid: da14edc5-0c36-4c54-b122-861c86b99eb1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20a3ae60cc330c27cbd19e943ba7f071d4ec60b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802691"
---
# 限制存储的 GPO 版本


默认情况下，每个受控制的组策略对象（GPO）的所有版本均保留在 AGPM 服务器上的存档中。 但是，你可以限制每个 GPO 的保留版本数，并在超过该限制时删除较早的版本。 删除 GPO 版本后，该版本的记录将保留在 GPO 的历史记录中，但 GPO 版本本身将从存档中删除。

需要具有 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必需权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**限制存储的 GPO 版本数**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中，单击 " **AGPM 服务器**" 选项卡。

3.  从 "存档" 复选框中选择 "**删除每个 gpo 的旧版本**" 复选框，然后键入要为每个 gpo 存储的最大 gpo 版本数，不包括当前版本。 若要仅保留当前版本，请输入0。 最大值不得大于999。

    **重要提示** 仅在 "**历史记录**" 窗口的 "**唯一版本**" 选项卡上显示的 GPO 版本将计为 "限制"。

     

4.  单击 "**应用**" 按钮。

### 其他注意事项

-   默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有域的 "**列表内容**" 和 "**修改选项**" 权限。

-   你可以通过将 GPO 版本标记在历史记录中，将其标记为不符合删除条件，从而阻止删除 GPO 版本。 若要执行此操作，请右键单击 GPO 历史记录中的版本，然后单击 "不**删除**"。

### 其他参考资料

-   [管理存档](managing-the-archive.md)

 

 





