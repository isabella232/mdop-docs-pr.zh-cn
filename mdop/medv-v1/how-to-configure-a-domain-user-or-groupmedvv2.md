---
title: 如何配置域用户或组
description: 如何配置域用户或组
author: dansimp
ms.assetid: 055aba81-a9c9-4b98-969d-775e603becf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c51da13808df657c1341572767c24860d9d5e8b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804120"
---
# 如何配置域用户或组


部署设置使你能够控制哪些用户或组可以访问 MED-V 工作区，以及可以使用 MED-V 工作区的时间以及它是否可以脱机使用。 你还可以配置其他规则来控制 MED-V 工作区和主机之间的访问。

所有 MED-V 工作区权限都在 "**部署**" 选项卡上的 "**策略**" 模块中配置。

若要允许用户利用 MED-V 工作区，必须首先将域用户或组添加到 MED-V 工作区权限。 然后，你可以为每个用户或组设置权限。

## 如何添加域用户或组


**添加域用户或组**

1.  在 "**用户/组**" 窗口中，单击 "**添加"。**

2.  在 "**输入用户或组名称**" 对话框中，通过执行下列操作之一选择 "域用户" 或 "组"：

    -   在 "**输入用户或组名称**" 字段中，键入域中存在的用户或组，或者键入作为计算机上的本地用户或组的用户或组。 然后单击 "**检查姓名**" 以将其解析为完整的现有名称。

    -   单击 "**查找**" 以打开 "标准**选择用户或组**" 对话框。 然后选择 "域用户" 或 "组"。

3.  单击“确定”****。

    添加域用户或组。

    **注意**  
    应手动添加来自受信任域的用户。



~~~
**Warning**  
Do not run the management application from a computer that is part of a domain that is not trusted by the domain the server is installed on.
~~~



## 如何删除域用户或组


**删除域用户或组**

1.  在 "**用户/组**" 窗口中，选择一个用户或组。

2.  单击 "**删除**"。

    已删除用户或组。

## 如何为用户或组设置权限


**为用户或组设置权限**

1.  单击要为其设置权限的用户或组。

2.  按下表所述配置 MED-V 工作区属性。

3.  在 "**策略**" 菜单上，选择 "**提交**"。

**工作区部署属性**

属性说明*常规*

为 &lt; 用户或组启用工作区&gt;

选中此复选框以启用此用户或组的 MED-V 工作区。

工作区将在此日期到期

选中此复选框可为此用户或组分配权限集的到期日期。

选中后，将启用 "日期" 框。 设置日期和权限将在指定日期结束时过期。

脱机工作限制为

选中此复选框以分配必须为此用户或组刷新策略的时间段。 选中此选项时，将启用 "时间段" 框。 设置天数或小时数，在指定的时间段结束时，如果未刷新策略，用户或组将无法连接。

工作区删除选项

单击以设置 MED-V 工作区删除选项。 有关详细信息，请参阅[如何设置 Med-v 工作区删除选项](how-to-set-med-v-workspace-deletion-options.md)。

*数据传输*

在主机和工作区之间支持剪贴板

选中此复选框以启用主机和 MED-V 工作区之间的复制和粘贴。

在主机和工作区之间支持文件传输

选中此复选框以启用在主机和 MED-V 工作区之间传输文件。 从 "**文件传输**" 框中选择以下选项之一：

-   **Both**-启用在主机和 med-v 工作区之间传输文件。

-   **主机到工作区**-启用将文件从主机传输到 med-v 工作区。

-   **要承载的工作区**—支持将文件从 med-v 工作区传输到主机。

**注意**  
如果没有权限的用户尝试传输文件，则会显示一个窗口，提示他输入具有执行文件传输权限的用户的凭据。



**重要提示**  
若要支持 Windows XP SP3 中的文件传输，必须通过编辑注册表禁用脱机文件同步，如下所示：

`REG ADD HKLM\software\microsoft\windows\currentversion\netcache /V Enabled /T REG_DWORD /F /D 0`



高级

单击以设置高级文件传送选项。 有关详细信息，请参阅[如何设置高级文件传输选项](how-to-set-advanced-file-transfer-options.md)。

*设备控件*

允许打印到连接到主机的打印机

选中此复选框可允许用户使用主机打印机从 MED-V 工作区进行打印。

**注意**  
打印由主机上定义的打印机执行。



启用对 CD/DVD 的访问

选中此复选框可允许通过此 MED-V 工作区访问 CD 或 DVD 驱动器。



**多个成员身份**

1.  如果用户是组的一部分，并且权限应用于用户以及它们所属的组，则应用所有权限。

2.  如果用户是两个不同组的成员，则应用限制性最少的权限。

## 相关主题


[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)

[如何设置 MED-V 工作区删除选项](how-to-set-med-v-workspace-deletion-options.md)

[如何设置高级文件传输选项](how-to-set-advanced-file-transfer-options.md)









