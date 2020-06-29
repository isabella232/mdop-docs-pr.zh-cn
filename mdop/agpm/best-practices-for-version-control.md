---
title: 版本控制最佳做法
description: 版本控制最佳做法
author: dansimp
ms.assetid: 89067f6a-f7ea-4dad-999d-118284cf6c5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ed91408faeb8968175976382f9dd97d45becddb5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802123"
---
# 版本控制最佳做法


Microsoft 高级组策略管理（AGPM）为组策略对象（Gpo）提供版本控制，与 Microsoft Visual SourceSafe®提供源代码的版本控制。 开发人员可以使用 Visual SourceSafe 管理每个源文件的多个版本。 组策略管理员可以使用 AGPM 对 Gpo 执行相同操作。 使用 AGPM 时，组策略管理员应注意适用于任何版本控制系统的最佳做法：

-   **日期和时间：** AGPM 使用日期和时间标记 GPO 的每个版本。 为确保历史记录准确，尤其是在多台计算机上编辑 Gpo 时，请确保每台计算机都将其时钟与一个权威性的时间源同步。

-   **完成编辑 gpo 时，请签入这些 gpo：** 通常，编辑器签出 Gpo 并忘记将其签回存档中。 但是，这可能会阻止其他组策略管理员更改 GPO。 完成编辑后，始终将 Gpo 立即重新签入到 AGPM。

-   **经常保存更改：** 编辑 GPO 时，请经常保存所做的更改。 大多数编辑器签出 GPO，进行许多更改，然后将 GPO 签入存档。 而是定期将 GPO 检查到存档中，然后再次将其签出。 在您更改每个设置（不推荐）或在您进行相关更改组之后检查 GPO 时，详细信息可以较小。 结果为每个 GPO 提供了一个更好记录的历史记录，可帮助解决问题。

-   **经常部署 gpo：** 不要让尚未部署的新和编辑的 Gpo 累积在存档中的大量数字中。 而是尽快部署新的和编辑的 Gpo，以便它们对生产环境具有最小的影响。 一次部署许多新的和已编辑的 Gpo 可能会危害生产环境。

-   在**签入 gpo 时记录更改的用途：** 任何审阅者都可以比较 GPO 的版本以查看二者之间的特定更改。 记录这些特定的更改不会增加任何价值。 而是通过查看差异报告来记录更改的意图和用途，而不是记录审阅者可以查看哪些内容。 版本注释应该为比较报告增加价值，并帮助审阅者了解编辑器更改 GPO 的原因。

-   在**部署之前在实验室中测试 gpo：** 将 Gpo 部署到生产环境而无需先测试它们才有风险。 而是在实验室环境中测试 Gpo，方法是将 Gpo 链接到包含测试计算机和用户的组织单元，然后验证它们是否正常工作。 验证实验室中的每个 GPO 后，将 GPO 部署到生产环境。

### 其他参考资料

-   [Microsoft 高级组策略管理 3.0 操作指南](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





