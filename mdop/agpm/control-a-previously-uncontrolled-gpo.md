---
title: 控制以前不受控的 GPO
description: 控制以前不受控的 GPO
author: dansimp
ms.assetid: 452689a9-4e32-4e3b-8208-56353a82bf36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d7349b16b326a49b701efae5379c313bde0964f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801996"
---
# 控制以前不受控的 GPO


若要使用高级组策略管理（AGPM）为组策略对象（GPO）提供更改控制，必须首先使用 AGPM 控制 GPO。

需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**控制以前的不受控制的 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "未**控制**" 选项卡以显示非受控 gpo。

3.  右键单击要通过 AGPM 控制的 GPO，然后单击 "**控制**"。

4.  键入要在 GPO 的历史记录中显示的注释，然后单击 **"确定"**。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 GPO 将从 "不可**控制**" 选项卡上的列表中删除，并添加到 "**受控**" 选项卡。

### 其他注意事项

-   默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并为域**创建 GPO**权限。

### 其他参考资料

-   [创建、控制或导入 GPO](creating-controlling-or-importing-a-gpo-approver.md)

 

 





