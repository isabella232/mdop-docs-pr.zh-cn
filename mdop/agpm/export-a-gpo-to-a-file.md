---
title: 将 GPO 导出到文件
description: 将 GPO 导出到文件
author: dansimp
ms.assetid: 0d01b1f7-a6a4-4d0d-9aa7-2d6f1ae93d9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4622930cb0e5b439649cc0445ae2b3d02d7d3224
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802783"
---
# 将 GPO 导出到文件


你可以将受控制的组策略对象（GPO）导出到 CAB 文件，以便你可以将其复制到另一个林中的域，并将 GPO 导入到该域中的高级组策略管理（AGPM）中。 有关如何将 GPO 设置导入新的或现有 GPO 的信息，请参阅[从文件导入 gpo](import-a-gpo-from-a-file-ed.md)。

需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。查看本主题中 "其他注意事项" 中的详细信息。

**将 GPO 导出到文件**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  右键单击该 GPO，然后单击 "**导出到**"。

4.  输入要将 GPO 导出到的文件的文件名，然后单击 "**导出**"。 如果文件不存在，则会创建该文件。 如果已存在，将替换它。

### 其他注意事项

-   默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有**列表内容**、**阅读设置**和 gpo 的**导出 gpo**权限。

### 其他参考资料

-   [使用测试环境](using-a-test-environment.md)

 

 





