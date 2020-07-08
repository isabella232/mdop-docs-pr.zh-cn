---
title: 适用于 Application Virtualization Sequencer 的最佳做法
description: 适用于 Application Virtualization Sequencer 的最佳做法
author: dansimp
ms.assetid: 95e5e216-864f-41a1-90d4-b8d7e1eb42a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859514fb34185a339c7f2c2734f331e5a99d050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803080"
---
# 适用于 Application Virtualization Sequencer 的最佳做法


本主题提供运行 Microsoft Application Virtualization （app-v） Sequencer 的最佳做法。 在你的环境中规划和使用 Sequencer 时，请查看并考虑以下建议。

## 计算机配置最佳做法排序


配置运行 App-v Sequencer 的计算机时，应考虑以下最佳做法：

-   **在具有类似配置且运行的操作系统比目标计算机较早版本的计算机上的顺序。**

    确保运行 Sequencer 的计算机运行的是早期版本的操作系统，而不是目标计算机。 这包括服务包和更新版本。 例如，如果目标计算机运行的是 WindowsVista 和 WindowsXP，则应在运行 WindowsXP 的计算机上序列化应用程序。 在一个操作系统上进行排序并不保证在不同操作系统上运行虚拟化应用程序的功能，具体取决于特定应用程序和操作系统。 如果遇到问题，可能会要求你在与应用 V 客户端运行的操作系统环境相同的操作系统环境上进行序列化。

-   **配置运行具有多个分区的 Sequencer 的计算机。**

    应将运行 Sequencer 的计算机配置为至少两个主分区。 第一个分区（**C：**）应包含操作系统，并且应使用 NTFS 文件系统设置其格式。 第二个分区（**Q：**）用作虚拟应用程序安装的目标路径，还应使用 NTFS 文件系统进行格式设置。

-   **配置具有足够的可用磁盘空间的 temp 目录。**

    排序器使用 **% TMP%** 或 **% TEMP%** 目录和**暂存**目录在排序期间存储临时文件。 你应该在运行 Sequencer 的计算机上配置这些目录，其可用磁盘空间相当于估计的应用程序安装要求。 你可以通过打开 Sequencer 控制台并选择 "**工具**"、"**选项**"，然后选择 "**路径**" 选项卡来验证**暂存**目录的位置。在排序期间，配置临时目录和**暂存**目录在不同的硬驱分区上可以提高性能。

-   **使用 Microsoft VirtualPC 序列应用程序。**

    你将多个应用程序序列数超过一次。 为了帮助实现此操作，你应该考虑在虚拟环境中运行的计算机上的排序。 这将允许你在运行 Sequencer 的计算机上对应用程序进行排序，并使用最少的重新配置还原到干净状态。

    如果你在你的环境中运行 Microsoft Hyper-v，则运行它的 Hyper-v 虚拟计算机将运行 app-v 排序器：

    -   暂停和恢复。

    -   已保存和还原其状态。

    -   另存为快照并被还原。

    -   作为实时迁移的一部分迁移到其他硬件。

-   **在对新应用程序进行排序之前，请关闭其他正在运行的程序。**

    通常在顺序计算机上运行的进程和计划任务可能会减慢排序过程，并导致在排序期间收集不相关的数据。 开始先后顺序之前，应关闭所有不需要的应用程序和程序。

-   **在运行终端服务的计算机上的顺序**

    在安装 sequencer 之前，不应在运行终端服务的计算机上配置安装模式。

## 排序最佳做法


在对新应用程序进行排序时，应考虑以下最佳做法：

-   

    **注意** 如果您运行的是 app-v 4.6 SP1，则无需按8.3 命名约定的目录进行排序。

     

-   **序列到遵循8.3 命名约定的唯一目录。**

    应将所有应用程序序列化到遵守8.3 命名约定的目录中。 指定的目录名不能超过八个字符，后跟三个字符的文件名扩展名，例如**Q:\\MYAPP。ABC**。

-   **序列到驱动器根目录的目标文件夹，而不是子目录。**

    如果应用程序套件有多个部分，请将每个应用程序安装到主目录的子目录中。 例如，如果程序包中包含一个应用程序和一个客户端，请将**Q:\\AppSuite**用作主目录并将主应用程序序列化到**Q:\\AppSuite\\Main**，并将客户端序列化到**Q:\\AppSuite\\Client**。

-   **在安装阶段配置和测试应用程序。**

    完成应用程序的安装通常需要执行不属于应用程序安装过程的多个手动步骤。 这些步骤可能涉及配置到数据库的连接或复制更新的文件。 应在安装阶段执行这些配置，然后运行该应用程序以确保其正常工作。

-   **如果需要，请多次运行该应用程序，直至程序稳定。**

    在安装期间，你应该多次运行该应用程序，以确保所有关联的注册和对话框配置均已完成。 在安装期间多次打开应用程序将确保仅将相关的应用程序功能加载到**主功能块**中。

-   **禁用与应用程序相关联的所有自动更新功能。**

    某些应用程序能够在安装期间自动检查最新的更新。 若要协助虚拟应用程序包的版本控制，应在排序期间禁用此功能。 如果存在必需的更新，则应该对安装了相关更新的新虚拟应用程序包进行排序。

## 相关主题


[规划 Application Virtualization System 部署](planning-for-application-virtualization-system-deployment.md)

 

 





