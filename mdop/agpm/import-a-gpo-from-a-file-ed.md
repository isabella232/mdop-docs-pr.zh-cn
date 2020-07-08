---
title: 从文件导入 GPO
description: 从文件导入 GPO
author: dansimp
ms.assetid: 6e901a52-1101-4fed-9f90-3819b573b378
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15704806f089bb0d8530cd84df64b0889413426
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802731"
---
# 从文件导入 GPO


在高级组策略管理（AGPM）中，如果已将组策略对象（GPO）导出到 CAB 文件，则可以将该 GPO 中的策略设置导入另一个林中的域中的现有 GPO。 将策略设置导入现有 GPO 将替换该 GPO 中的所有策略设置。 有关将 GPO 设置导出到 CAB 文件的信息，请参阅[将 Gpo 导出到文件](export-a-gpo-to-a-file.md)。

需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。查看本主题中 "其他注意事项" 中的详细信息。

## <a href="" id="bkmk-existing"></a>


**将策略设置导入到现有 GPO 中**

1.  在 "**组策略管理" 控制台**树中，单击要将策略设置导入到的域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  查看要将策略设置导入到的目标 GPO。

4.  右键单击目标 GPO，指向 "**导入**"，然后单击 "**文件**"。

5.  按照**导入设置向导**中的说明选择 GPO 备份，导入其策略设置以替换目标 gpo 中的这些设置，并输入目标 gpo 审核跟踪的注释。 默认情况下，向导完成时将签入目标 GPO。

### 其他注意事项

-   默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有 "**列表内容**"、"**编辑设置**" 和 "**导入**域的 gpo" 权限，并且 GPO 必须由您签出。

-   尽管编辑器在创建新 GPO 期间无法将策略设置导入到新 GPO 中，但编辑器可请求创建新 GPO，然后在创建新 GPO 后将策略设置导入该 GPO。

### 其他参考资料

-   [使用测试环境](using-a-test-environment.md)

 

 





