---
title: 从文件导入 GPO
description: 从文件导入 GPO
author: dansimp
ms.assetid: 2cbcda72-4de3-47ad-aaf8-4fc7341d5a00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 04819dacac8df73f0a61cace0dab8b9fa79b7307
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802743"
---
# 从文件导入 GPO


在高级组策略管理（AGPM）中，如果你是 AGPM 管理员（完全控制），并且已将组策略对象（GPO）导出到 CAB 文件，则可以将该 GPO 中的策略设置导入新 GPO 或另一个林中的域中的现有 GPO。 有关将 GPO 设置导出到 CAB 文件的信息，请参阅[将 Gpo 导出到文件](export-a-gpo-to-a-file.md)。

需要使用 AGPM 管理员角色的用户帐户或 AGPM 中的必要权限才能将策略设置导入到新的受控 GPO 中。 需要具有编辑者或 AGPM 管理员角色的用户帐户或 AGPM 中的必需权限才能将策略设置导入到现有 GPO 中。 查看本主题中 "其他注意事项" 中的详细信息。

## 从文件导入策略设置


从文件导入策略设置时，可以将其导入到新的 GPO 或现有 GPO 中。 但是，如果将策略设置导入到现有 GPO 中，则会替换其中的所有策略设置。

-   [将策略设置导入到新的受控 GPO 中](#bkmk-new)

-   [将策略设置导入到现有 GPO 中](#bkmk-existing)

### <a href="" id="bkmk-new"></a>

**将策略设置导入新的受控 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要将策略设置导入到的域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  创建一个新的受控 GPO。 在 "**新建受控制的 GPO** " 对话框中，单击 "**导入**"，然后单击 "**启动向导**"。 有关如何创建 GPO 的详细信息，请参阅[创建新的受控 GPO](create-a-new-controlled-gpo-agpm40.md)。

4.  按照**导入设置向导**中的说明选择 GPO 备份，从其导入新 gpo 的策略设置，并为新 gpo 的审核跟踪输入注释。

### <a href="" id="bkmk-existing"></a>

**将策略设置导入到现有 GPO 中**

1.  在 "**组策略管理" 控制台**树中，单击要将策略设置导入到的域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  查看要将策略设置导入到的目标 GPO。

4.  右键单击目标 GPO，指向 "**导入**"，然后单击 "**文件**"。

5.  按照**导入设置向导**中的说明选择 GPO 备份，导入其策略设置以替换目标 gpo 中的这些设置，并输入目标 gpo 审核跟踪的注释。 默认情况下，向导完成时将签入目标 GPO。

### 其他注意事项

-   若要将策略设置导入到新的受控制的 GPO，必须具有**列表内容**、**导入 GPO**和为域**创建 gpo**权限。 默认情况下，您必须是 AGPM 管理员才能执行此过程。

-   若要将策略设置导入到现有 GPO，必须具有**列表内容**、**编辑设置**和为域**导入 gpo**权限，并且 GPO 必须由你签出。 默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。

### 其他参考资料

-   [管理存档](managing-the-archive-agpm40.md)

 

 





