---
title: 脱机编辑 GPO
description: 脱机编辑 GPO
author: dansimp
ms.assetid: 51677d8a-6209-41b5-82ed-4f3be817abc0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74b6ae9fdf11456a9a45cb5504ed97a9bc6aecb4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801891"
---
# 脱机编辑 GPO


若要对受控制的组策略对象（GPO）进行更改，必须首先从存档中签出 GPO 的副本。 任何其他人都将无法修改 GPO，直到再次签入该 GPO，以防多个组策略管理员的冲突更改被引入。 修改完 GPO 后，将其签入存档，以便可以对其进行检查并将其部署到生产环境。

具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理（AGPM）中具有必要权限的用户帐户才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

## 脱机编辑 GPO


若要编辑 GPO，请从存档中签出 GPO，脱机编辑 GPO，然后将 GPO 检查到存档中，以便可以查看和部署该 GPO （或由其他编辑器修改）。

-   [从存档中签出 GPO 进行编辑](#bkmk-checkout)

-   [脱机编辑 GPO](#bkmk-edit)

-   [将 GPO 签入存档](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**从存档中签出 GPO 以进行编辑**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  右键单击要编辑的 GPO，然后单击 "**签出**"。

4.  键入要在已签出的 GPO 的历史记录中显示的注释，然后单击 **"确定"**。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 在 "**受控**" 选项卡上，GPO 的状态现在标识为 "**已签出**"。

### <a href="" id="bkmk-edit"></a>

**脱机编辑 GPO**

1.  在 "**受控**" 选项卡上，右键单击要编辑的 GPO，然后单击 "**编辑**"。

2.  在 "**组策略管理编辑器**" 窗口中，对 GPO 的脱机副本进行更改。

    **注意** 若要禁用所有计算机配置设置或所有用户配置设置，请在 "**组策略管理编辑器**" 窗口中右键单击该 GPO，然后单击 "**属性**"。 根据需要，选择 "**禁用计算机配置设置**" 或 "**禁用用户配置设置**"。

     

3.  完成对 GPO 的修改后，请关闭 "**组策略管理编辑器**" 窗口。

### <a href="" id="bkmk-checkin"></a>

**将 GPO 签入存档**

1.  在 "**受控**" 选项卡上：

    -   如果你未对 GPO 进行任何更改，请右键单击该 GPO，然后单击 "**撤消签出**"，然后单击 **"是"** 进行确认。

    -   如果你已对 GPO 进行了更改，请右键单击该 GPO，然后单击 "**签入**"。

2.  键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。

3.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 在 "**受控**" 选项卡上，将 GPO 的状态标识为 **"已签入**"。

### 其他注意事项

-   若要签出和编辑 GPO，默认情况下，你必须是创建或控制 GPO、编辑器或 AGPM 管理员（完全控制）的审批者。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。 此外，若要编辑 GPO，您必须是已签出 GPO 的个人。

-   若要签入 GPO，默认情况下，您必须是编辑者、审批者或 AGPM 管理员（"完全控制"）。 具体而言，您必须具有**列表内容**并**编辑设置**或为 gpo**部署 gpo**权限。 如果您不是审批者或 AGPM 管理员（或具有 "**部署 GPO**权限" 的其他组策略管理员），则您必须是已签出 GPO 的编辑器。

-   编辑 GPO 时，其他 GPO 中的程序包的任何组策略软件安装升级都应引用部署的 GPO，而不是已签出的副本。

### 其他参考资料

-   [编辑 GPO](editing-a-gpo-agpm30ops.md)

-   查看 GPO

    -   [查看 GPO 设置](review-gpo-settings-agpm30ops.md)

    -   [查看 GPO 链接](review-gpo-links-agpm30ops.md)

    -   [识别各 GPO、GPO 版本或模板之间的差异](identify-differences-between-gpos-gpo-versions-or-templates-agpm30ops.md)

-   部署 GPO

    -   [请求部署 GPO](request-deployment-of-a-gpo-agpm30ops.md)

    -   [部署 GPO](deploy-a-gpo-agpm30ops.md)

 

 





