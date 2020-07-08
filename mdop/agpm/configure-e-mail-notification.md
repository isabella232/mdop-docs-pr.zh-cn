---
title: 配置电子邮件通知
description: 配置电子邮件通知
author: dansimp
ms.assetid: 6e152de0-4376-4963-8d1a-3e7f5866d30f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 46e8d00c2446a0185de30bbd1f39a7e3eaf90080
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802032"
---
# 配置电子邮件通知


当编辑者或审阅者尝试创建、部署或删除组策略对象（GPO）时，将向指定的电子邮件地址或地址发送对此操作的请求，以便审批者可以评估请求并实现或拒绝它。 您确定要向其发送通知的电子邮件地址或地址，以及发送通知的别名。

要完成此过程，需要具有 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限。 查看本主题中 "其他注意事项" 中的详细信息。

**配置 AGPM 的电子邮件通知**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中，单击 "**域委派**" 选项卡。

3.  在 "**发件**时间" 字段中，键入要从中发送通知的 AGPM 的电子邮件别名。

4.  在 "**收件人**" 字段中，键入应接收审批请求的审批者的电子邮件地址的逗号分隔列表。

5.  在 " **SMTP 服务器**" 字段中，键入有效的 SMTP 邮件服务器。

6.  在 "**用户名**" 和 "**密码**" 字段中，键入有权访问 SMTP 服务的用户的凭据。

7.  单击**应用**。

### 其他注意事项

-   默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有域的 "**列表内容**" 和 "**修改选项**" 权限。

-   AGPM 的电子邮件通知是域级设置。 可以在每个域的 "**域委派**" 选项卡上提供不同的审批者电子邮件地址或 AGPM 电子邮件别名，或在整个环境中使用相同的电子邮件地址。

### 其他参考资料

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks.md)

 

 





