---
title: 计划 Application Virtualization Sequencer 实现
description: 计划 Application Virtualization Sequencer 实现
author: dansimp
ms.assetid: 052f32fe-ad13-4921-a8ce-4a657eb2b2bf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac62991e290dcd2da1c42f025a19365bda239fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798862"
---
# 计划 Application Virtualization Sequencer 实现


排序（应用程序虚拟化用于创建虚拟应用程序和应用程序包的过程）需要使用安装了 Application Virtualization Sequencer 软件的计算机。

在排序过程中，排序器将置于监视器模式，并且要排序的应用程序安装在排序计算机上。 接下来，将启动序列化的应用程序，并执行最重要且最常用的函数，以便监视进程可以配置主要功能块，它包含应用程序包中的最小内容，该应用程序包是应用程序运行所必需的。 完成这些步骤后，将停止监视模式，并保存和测试序列化的应用程序以验证操作是否正确。

确定要选择用于排序的应用程序时，请记住无法对某些应用程序进行排序。 其中包括 Windows 操作系统的某些部分，如 Internet Explorer、设备驱动程序和启动时启动服务的应用程序。

有关安装 Sequencer 的分步信息，请参阅[如何安装 Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)。

**重要提示** 整个排序过程计划应由您的公司安全团队审核和批准。 Sequencer 操作通常与实验室中的生产环境保持独立。 根据您的业务要求，此操作可以很简单，也可以在必要时全面。 排序计算机需要连接到企业网络才能将完成的程序包复制到生产服务器。 但是，由于它们通常在没有防病毒保护的情况下运行，因此它们不能在未受保护的企业网络上使用-例如，您可能能够在防火墙后面或在隔离的网段上操作。 使用配置为共享隔离虚拟网络的虚拟机也可能是可接受的方法。 按照您的公司安全策略来安全地解决这种情况。

 

规划排序过程的关键步骤包括以下几个步骤：

-   考虑你希望每月处理的应用数、这些应用程序的大小，并添加一个用于序列化未来更新的余量。 软件包最大可达 4 GB，压缩或解压缩。

-   在对每个应用程序进行排序时，为你的组织准备和记录一个可重复的、可重复的过程。 这应包括对每个运行的清单以及版本控制过程的使用。 在调查程序包可能的技术问题时，对每个顺序应用程序使用跟踪日志也非常有用。

-   对于排序应用程序，请使用针对处理吞吐量优化的高性能计算机，其中至少有 4 GB RAM 和快速 CPU （3 GHz 或更快）。 快速硬盘和使用单独的磁盘卷也可以提高性能。 虚拟机非常适合用于序列化，因为它们很容易被重置，或者你可以在本地分区上使用具有干净映像的物理计算机，以便在每个程序包排序操作完成后能够快速重新映像。

    **重要提示** 在安全模式下运行 app-v sequencer 不受支持。

     

-   验证你是否了解序列化应用程序的操作环境（包括 Microsoft Office 或 Java 运行时环境等集成元素），因为这通常会确定是否必须在序列化计算机上安装应用程序之前的任何内容。

-   确保每个新的顺序操作始终从干净的基本映像开始。 通过将已保存的映像还原到物理计算机或在放弃所有更改后重新启动虚拟机，确保先后顺序计算机已重置。 在保存之前，基本图像应具有从 Windows 更新应用的最新更新。

-   在顺序计算机上关闭可能干扰安装监视过程（如防病毒扫描程序和 Windows 更新）的任何内容，因为在排序过程中拥有稳定的平台非常重要。 由于此步骤会产生重大的安全风险，因此请确保采取正确的预防措施来保护计算机和网络以及序列化的应用程序包。 我们建议你在对应用程序包进行排序之前对其进行防病毒扫描。

-   在序列化后包含测试每个应用程序的详细流程。 测试序列化的应用程序将确定该应用程序是否正常运行，并在将虚拟化应用程序部署到最终用户之前是该过程的重要部分。 作为在大规模部署到最终用户之前测试的最后一步，你还应该规划测试组的试点部署。

-   测试顺序应用程序时，请选择相同类型的计算机设备，并运行公司生产环境中使用的相同操作系统。 只要正确配置，就可以使用虚拟机或物理计算机。

## 相关主题


[Application Virtualization Sequencer 硬件和软件要求](application-virtualization-sequencer-hardware-and-software-requirements.md)

[如何安装 Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)

[如何升级 Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)

[安全和保护概述](security-and-protection-overview.md)

 

 





