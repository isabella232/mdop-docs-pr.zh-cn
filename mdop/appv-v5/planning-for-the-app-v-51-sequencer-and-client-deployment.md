---
title: 计划 App-V 5.1 Sequencer 和 Client 部署
description: 计划 App-V 5.1 Sequencer 和 Client 部署
author: dansimp
ms.assetid: d92f8773-fa7d-4926-978a-433978f91202
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 31a0296814b16ba1c776dca522423fc7b6b6ed96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798301"
---
# 计划 App-V 5.1 Sequencer 和 Client 部署


在开始使用 Microsoft Application Virtualization （App-v）5.1 之前，必须安装 app-v 5.1 sequencer、app-v 5.1 客户端以及可选的 App-v 5.1 共享内容存储。 以下各节将介绍这些安装的规划。

## 规划 app-v 5.1 sequencer 部署


App-v 5.1 使用名为 "先后顺序" 的进程创建虚拟化的应用程序和应用程序包。 排序需要使用运行 app-v 5.1 sequencer 的计算机。

**注意** 有关 app-v 5.1 sequencer 的新功能的信息，请参阅[关于 app-V 5.1](about-app-v-51.md)的**sequencer 改进**部分。

 

运行 app-v 5.1 sequencer 的计算机必须满足最低系统要求。 有关这些要求的列表，请参阅[App-V 5.1 支持的配置](app-v-51-supported-configurations.md)。

理想情况下，应在作为虚拟机运行的计算机上安装 sequencer。 这使你能够更轻松地将运行 sequencer 的计算机还原为 "干净" 状态，然后再对其他应用程序进行排序。 使用虚拟机安装 sequencer 时，应执行以下步骤：

1.  安装所有关联的 sequencer 先决条件。

2.  安装 sequencer。

3.  获取环境的 "快照"。

**重要提示** 您应让您的公司安全小组查看和批准排序过程计划。 出于安全考虑，应将 sequencer 操作保留在与生产环境分开的实验中。 根据您的业务要求，分色排列可以简单，也可以在必要时全面。 排序计算机必须能够连接到企业网络才能将完成的程序包复制到生产服务器。 但是，由于先后顺序计算机通常在没有防病毒保护的情况下运行，因此它们不能在未受保护的企业网络上。 例如，你可能能够在防火墙后或在隔离的网段上操作。 你还可以使用配置为共享隔离虚拟网络的虚拟机。 按照您的公司安全策略来安全地解决这些问题。

 

## 规划 app-v 5.1 客户端部署


若要在目标计算机上运行虚拟化程序包，必须在目标计算机上安装 app-v 5.1 客户端。 App-v 5.1 客户端是在目标计算机上运行虚拟化应用程序的组件。 客户端使用户能够与图标和特定文件类型交互，以启动虚拟化的应用程序。 客户端还有助于从管理服务器获取应用程序内容，并在客户端启动应用程序之前缓存内容。 有两种不同的客户端类型：远程桌面服务的客户端，用于远程桌面会话主机（RD 会话主机）服务器系统和 App-v 5.1 客户端，该客户端用于所有其他计算机。

App-v 5.1 客户端应使用安装程序命令行或在安装完成后使用 PowerShell 脚本进行配置。

必须仔细定义这些设置，以便加速 app-v 5.1 客户端软件的部署。 当您的计算机位于不同的办公室，并且客户端必须配置为使用不同的源位置时，这一点尤其重要。

您还必须确定部署客户端软件的方式。 虽然可以在每台计算机上手动部署客户端，但大多数组织希望通过自动化过程部署客户端。 较大的组织可能具有可操作的电子软件分发（ESD）系统，这是一个理想的客户端部署系统。 如果不存在 ESD 系统，则可以使用组织的标准安装软件的方法。 可能的方法包括组策略或各种脚本技术。 此部署过程可能很复杂，具体取决于客户端计算机的数量和不同位置。 你必须使用结构化方法来确保所有计算机都使用正确的配置来安装客户端。

有关客户端最低要求的列表，请参阅[App-V 5.1 先决条件](app-v-51-prerequisites.md)。

## <a href="" id="bkmk-client-coexist"></a>规划 app-v 客户端共存


你可以使用 app-v 4.6 客户端并排部署 app-v 5.1 客户端。 客户端共存要求你通过使用部署配置文件或用户配置文件来添加或发布虚拟化的应用程序，因为这些配置文件中的某些设置必须配置，才能使 app-v 5.1 与 App-v 4.6 客户端一起正常工作。 使用客户端或服务器升级程序包时，程序包必须重新提交配置文件。 对于具有相应配置文件的任何程序包，这是正确的，因此它不特定于客户端共存。 但是，如果在程序包升级期间未提交配置文件，则程序包状态在共存方案中将不会按预期运行。

App-v 5.1 动态配置文件为特定用户自定义程序包。 必须先创建动态用户配置（.xml）文件或动态部署配置文件，然后才能使用它们。 若要创建文件，它需要高级手动操作。

使用动态用户配置文件时，不会使用清单文件中的扩展的任何 App-v 5.1 信息。 这意味着，动态用户配置文件必须包含特定于清单文件中的 app-v 5.1 的扩展的所有内容，以及要进行的更改，例如删除和更新。 有关如何创建自定义配置文件的详细信息，请参阅[如何使用 app-v 5.1 管理控制台创建自定义配置文件](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)。

## <a href="" id="bkmk-plan-for-scs"></a>规划 app-v 5.1 共享内容存储（SCS）


App-v 5.1 共享的内容存储模式允许运行应用-V 5.1 客户端的计算机运行虚拟化的应用程序，并且不会在运行 App-v 5.1 客户端的计算机上保存任何程序包内容。 仅当客户端请求时，才会将虚拟应用程序流式传输到目标计算机。

下表显示了使用 app-v 5.1 共享内容存储的一些优点：

-   减少应用到应用和多用户应用程序冲突，因此降低了回归测试的需求

-   通过降低部署风险加快应用程序部署

-   简化的配置文件管理






## <a href="" id="other-resources-for-the-app-v-5-1-deployment-"></a>适用于 app-v 5.1 部署的其他资源


[计划部署 App-V](planning-to-deploy-app-v51.md)

## 相关主题


[如何安装 Sequencer](how-to-install-the-sequencer-51beta-gb18030.md)

[如何部署 App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)

[如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

[如何针对共享内容存储模式安装 App-V 5.1 Client](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

 

 





