---
title: 创建新的受控 GPO
description: 创建新的受控 GPO
author: dansimp
ms.assetid: 5ce760f6-9f05-42b4-b787-7835ab8e324e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67c6af686b9ba7254cdaf93bd2d294b2d5bbb681
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802880"
---
# 创建新的受控 GPO


通过 "**更改控制**" 文件夹创建的新组策略对象（gpo）将自动受控制，从而使你能够管理它们。

需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**使用通过 AGPM 管理的更改控制创建新 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  右键单击 "**更改控件**"，然后单击 "**新建受控制的 GPO**"。

3.  在 "**新建受控 GPO** " 对话框中：

    1.  键入新 GPO 的名称。

    2.  可选：键入要在 GPO 的**历史记录**中显示的新 GPO 的注释。

    3.  要立即将新的 GPO 部署到域的生产环境中，请单击 "**创建实时**"。 若要在不立即部署的情况下创建新的 GPO，请单击 "**脱机创建**"。

    4.  选择要用作新 GPO 的起始点的 GPO 模板，然后单击 **"确定"**。

4.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 新的 GPO 将显示在 "**受控**" 选项卡上的 gpo 列表中。

### 其他注意事项

-   默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并为域**创建 GPO**权限。

### 其他参考资料

-   [创建或控制 GPO](creating-or-controlling-a-gpo-agpm40-app.md)

 

 





