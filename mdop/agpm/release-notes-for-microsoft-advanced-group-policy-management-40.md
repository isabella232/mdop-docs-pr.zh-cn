---
title: Microsoft 高级组策略管理 4.0 发行说明
description: Microsoft 高级组策略管理 4.0 发行说明
author: dansimp
ms.assetid: 44c19e61-c8e8-48aa-a2c2-20396d14d5bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c4a279893d4da4121e422af99e7c1708a0126b4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802599"
---
# Microsoft 高级组策略管理 4.0 发行说明


2009 年 10 月

## 关于 Microsoft 高级组策略管理4。0


Microsoft 高级组策略管理（AGPM）4.0 扩展了组策略管理控制台（GPMC）的功能。 AGPM 提供全面的更改控制和改进的组策略对象（Gpo）管理。

以下文档可帮助你开始使用 AGPM 4.0。

-   有关 AGPM 功能的概述，请参阅[Microsoft 高级组策略管理](https://go.microsoft.com/fwlink/?LinkID=162671)（）概述 https://go.microsoft.com/fwlink/?LinkID=162671) 。

-   有关 AGPM 4.0 与 AGPM 3.0 有何不同的信息，请参阅 AGPM 4.0 （.）[中的新增功能](https://go.microsoft.com/fwlink/?LinkId=160058) https://go.microsoft.com/fwlink/?LinkId=160058) 。

-   有关如何确定 AGPM 4.0、AGPM 3.0 或 AGPM 2.5 是否适合你的环境的指导，请参阅[选择要安装的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=145981)（ https://go.microsoft.com/fwlink/?LinkId=145981) 。

-   有关如何安装 AGPM 和使用 AGPM 的示例方案的基本指导，请参阅[Microsoft 高级组策略管理4.0 （.）的分步指南](https://go.microsoft.com/fwlink/?LinkID=153505) https://go.microsoft.com/fwlink/?LinkID=153505) 。 本指南主要用于帮助评估用户和首次用户。

-   有关如何从早期版本的 AGPM 中升级的信息或有关如何在组织中规划 AGPM 部署的详细指南，请参阅[Microsoft 高级组策略管理 4.0](https://go.microsoft.com/fwlink/?LinkID=156883) （.）的规划指南 https://go.microsoft.com/fwlink/?LinkID=156883) 。

-   有关如何使用 AGPM 执行特定任务的信息，请参阅高级组策略管理4.0 帮助，它也可在 TechNet 上作为[AGPM 4.0 的操作指南](https://go.microsoft.com/fwlink/?LinkId=159872)（ https://go.microsoft.com/fwlink/?LinkId=159872) 。

## 详细信息


有关 AGPM 的详细信息，请参阅以下内容：

-   [高级组策略管理 TechNet 库](https://go.microsoft.com/fwlink/?LinkID=146846)（https://go.microsoft.com/fwlink/?LinkID=146846)

-   [Microsoft 桌面优化包技术中心](https://go.microsoft.com/fwlink/?LinkId=159870)（https://www.microsoft.com/technet/mdop)

-   [组策略技术中心](https://go.microsoft.com/fwlink/?LinkId=145531)（https://www.microsoft.com/gp)

## 提供反馈


您可以将有关 AGPM 的反馈或问题发布到[组策略论坛](https://go.microsoft.com/fwlink/?LinkId=145532)（ https://go.microsoft.com/fwlink/?LinkId=145532) 。

## 有关 AGPM 4.0 的已知问题


### "从生产中导入" 命令不会将设置导入已签出的 GPO 中

如果在生产环境中编辑 GPO，则必须从生产导入 GPO 以更新脱机存档中的 GPO。 "**从生产中导入**" 命令旨在让你在完成编辑之前执行最终生产备份，以便你可以在需要时回滚到生产备份。

如果在运行 "**从生产中导入**" 命令时已签出 gpo，则不会将生产更改合并到 GPO 的已签出版本中。 但是，即使该版本不可编辑，也会将该 GPO 的导入版本添加到 GPO 的历史记录中。 GPO 签入后，该版本将取代存档中的导入版本，但这两个版本都在 GPO 的历史记录中可用。

**解决方法：** 在从生产中导入之前，请确保已签入该 GPO。 如果在导入该 GPO 之前未签入该 GPO，则可以使用 "**撤消签出**" 命令放弃所做的更改，然后回退到从生产导入的 gpo 版本。

### 在使用多站点 Active Directory 拓扑的环境中，已签出的 Gpo 无法编辑几分钟

AGPM 使用客户端/服务器模型。 AGPM 服务器和 AGPM 客户端分别为组策略操作确定其自己最近的域控制器。 使用 AGPM 客户端签出 GPO 时，它实际上是一个 AGPM 服务器，它将 GPO 从脱机存档检查到 SYSVOL 文件夹中的临时文件夹。

如果 AGPM 服务器和 AGPM 客户端位于不同的站点，则临时签出的 GPO 可能不会在本地站点的域控制器上出现几分钟或最多30分钟，因为 SYSVOL 复制延迟。 在这种情况下，你无法在 AGPM 客户端上使用 GPMC 编辑已签出的 GPO，直到已签出 GPO 的 SYSVOL 复制发生。

**解决方法：** 最佳做法是，你应将 AGPM 客户端放置在与它们连接的 AGPM 服务器相同的站点中，以便你无需等待 SYSVOL 复制发生，然后才能编辑已签出的 GPO。

### 如果你的帐户没有存档的权限，则 AGPM 无法读取备份限制

在 AGPM 客户端上，如果使用尚未委派给 AGPM 存档权限的帐户登录，请启动组策略管理控制台（GPMC），然后单击 "**更改控制**"，收到以下错误。

``` syntax
Failed to read backup purge limit for this domain. 

The following error occurred: 
You do not have sufficient permissions to perform this operation. 
Microsoft.Agpm.AccessDeniedException (80070005)
```

**解决方法：** 与 AGPM 管理员（完全控制）联系，请求他们为您的帐户委派对 AGPM 的访问权限。 如果你是 AGPM 管理员，请使用分配了 AGPM 管理员角色的帐户登录，以便你可以为其他帐户委派访问权限。 有关详细信息，请参阅 AGPM 帮助中的 "委派域级别对存档的访问权限"。

## 发行说明版权信息


本文档中的信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知，仅供参考。 本文档使用或结果的全部风险由用户承担，Microsoft Corporation 不作任何明示或暗示的保证。 此处所述的示例公司、组织、产品、人员和事件纯属虚构。 无意与任何真实公司、组织、产品、人员或事件关联，也不应进行任何推测。 用户有责任遵守所有适用的版权法。 在不限制版权法规定的权利的情况下，未经 Microsoft Corporation 明确书面允许，不得出于任何目的，以任何形式或通过任何方式（电子、机械、影印、录制或其他方式）对本文档中的任何内容进行复制、传输或者将其存储到或引入到检索系统。

Microsoft 可能拥有涉及本文档中的主题的专利、专利申请、商标、版权和其他知识产权。 除非得到 Microsoft 的明确书面许可，否则本文档不授予用户任何使用这些专利、商标、版权或其他知识产权的许可。



Microsoft、MS-DOS、Windows、WindowsServer 和 Windows Vista 是 U.S.A. 和/或其他国家/地区的 MicrosoftCorporation 注册商标或商标。

此处提及的真实公司和产品的名称可能是其各自所有者的商标。

 

 





