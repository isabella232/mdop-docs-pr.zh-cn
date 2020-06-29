---
title: 如何使用 Differential SFT 文件
description: 如何使用 Differential SFT 文件
author: dansimp
ms.assetid: 607e30fd-2f0e-4e2f-b669-0b3f010aebb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 85cc45f9665569d77fcf275db6dbc080eb919229
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798961"
---
# 如何使用 Differential SFT 文件


当对应用程序进行排序时，Microsoft Application Virtualization （App-v） Sequencer 将创建 SFT 文件（SFT）以存储虚拟应用程序的所有文件内容和配置信息。 在 App-v 的4.5 版本中，引入了差异 SFT （dsft）文件。 使用 Sequencer 创建现有程序包的升级后，你可以选择生成此文件，以便仅存储原始顺序应用程序包与新版本之间的差异。 因此，它比完整的 SFT 文件小得多，它将用于新版本的应用程序，并减少通过低带宽网络连接发送程序包更新的影响。 但是，仅在某些受限制的情况下才支持它的使用。 此功能旨在在你使用电子软件分发（ESD）系统的地方使用，以便通过低带宽连接管理具有本地文件服务器的一组用户，并且不使用 App-v 流式处理服务器。

如果使用配置 Manager2007 管理用户，则无需使用差异 SFT 文件，因为 Configuration Manager 支持已内置的低带宽部署。 如果你将应用程序虚拟化（App-v）管理或流服务器用于活动升级，也不是必需的，因为客户将仅检索旧版本和新程序包版本之间的差异。

以下过程介绍了如何使用 Sequencer 安装中包含的 mkdiffpkg.exe 来创建差异 SFT 文件，完成虚拟应用程序包升级后，并部署差异 SFT 文件。 完成此过程有助于确保从客户端计算机上卸载程序包的过程中，当用户下次尝试运行应用程序时，客户端将回退到替代 URL，该 URL 被设置为从本地文件共享中流出完整的程序包 V2。 这将在启动应用程序时避免任何用户出现故障。 如果整个客户端损坏或卸载，建议将 ESD 系统配置为将已升级程序包的完整版本（即 sft）部署到客户端。

有关升级程序包的详细信息，请参阅 App-v 4.5 操作指南中的 "如何升级现有虚拟应用程序" <https://go.microsoft.com/fwlink/?LinkId=133129>

**注意** 作为先决条件，由 ESD 定向的所有用户计算机必须将 V1 文件完全加载到其本地缓存中，并且必须在所有计算机上启用文件流。

 

**使用差异 SFT 文件**

1.  使用具有管理员权限的帐户登录到 Sequencer 计算机。 在 Sequencer 中打开原始程序包（V1）进行升级，然后将该程序包升级到新版本（V2），并将其另存为新的 V2. sft。

2.  在 App-v 4.5 Sequencer 安装文件夹中打开一个命令窗口，然后运行以下命令：

    `“mkdiffpkg.exe V2.sft V2.dsft”`

3.  使用 ESD 系统或其他文件复制过程，将完整的 V2 程序包内容文件 V2 复制到本地文件共享，用户计算机在连接良好的网络连接时可访问该文件。

4.  使用 ESD 系统，在每台用户计算机上放置差异 SFT 文件 dsft 的副本。

5.  若要导入 dsft 文件，请在每台用户计算机上运行以下 SFTMIME 命令：

    `“SFTMIME load package:<package name> /SFTPATH <path to V2.dsft>”`

6.  在每台用户计算机上运行以下 SFTMIME 命令，将替代 URL 设置为指向 V2 文件：

    `“SFTMIME configure package:<package name> /OverrideURL FILE://<network path to V2.sft>”`

**注意**  
-   差异 SFT 文件必须按正确的顺序应用到客户端。 例如，dsft 必须应用于 V1 应用程序，然后才能应用 V3 dsft。

-   Sequencer 中的 "**生成 Microsoft Windows Installer （MSI）" 程序包**功能不能与差异 SFT 文件配合使用。

 

## 相关主题


[如何使用 App-v Sequencer 创建或升级虚拟应用程序](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





