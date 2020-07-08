---
title: 使用 DaRT 7.0 恢复计算机
description: 使用 DaRT 7.0 恢复计算机
author: dansimp
ms.assetid: bcded7ca-237b-4971-ac34-4394b05cbc50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 44dd48146155294bd8013b4b5a9bf23ffb3e8316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803234"
---
# 使用 DaRT 7.0 恢复计算机


有两种方法可用于使用 Microsoft 诊断和恢复工具集（DaRT）7恢复计算机。 你可以在本地运行 DaRT7 恢复映像，也可以使用 DaRT7 中提供的远程连接功能来恢复远程计算机。 本节将更详细地介绍这两种方法。

## 使用 DaRT 恢复映像恢复本地计算机


若要使用 DaRT7 恢复本地计算机，您必须在遇到需要 DaRT 的问题的最终用户计算机上进行物理演示。

你可以选择多种不同的方法来启动到 DaRT，具体取决于你部署 DaRT 恢复映像的方式。

-   将 DaRT 恢复映像 CD、DVD 或 USB 闪存驱动器插入到有问题的计算机中，然后使用它启动到计算机。

-   从有问题的计算机上的恢复分区启动到 DaRT。

-   从网络上的远程分区启动到 DaRT。

有关每种方法的优点和缺点的信息，请参阅[规划如何保存和部署 DaRT 7.0 恢复映像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)。

无论使用哪种方法启动到 DaRT，您都必须在 BIOS 中为启动选项启用启动设备，或者您希望向最终用户提供的选项。

**注意** 配置 BIOS 是唯一的，具体取决于您的组织中使用的硬盘驱动器、网络适配器和其他硬件的类型。

 

[如何使用 DaRT 恢复映像恢复本地计算机](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)

## 使用 DaRT 恢复映像恢复远程计算机


DaRT 中的远程连接功能允许 IT 管理员在最终用户计算机上远程运行 DaRT 工具。 当最终用户（或由支持最终用户计算机的技术支持人员）提供某些信息后，IT 管理员或支持人员可以控制最终用户的计算机并远程运行必要的 DaRT 工具。

**重要提示** 建立远程连接的两台计算机必须是同一网络的一部分。

 

"**诊断和恢复工具集**" 窗口包括从管理员计算机远程运行最终用户计算机上的 DaRT 的选项。 最终用户在问题计算机上打开 DaRT 工具，然后通过单击 "**远程连接**" 启动远程会话。

最终用户计算机上的 "远程连接" 功能创建以下连接信息：票证编号、端口和所有可用 IP 地址的列表。 票据号码和端口是随机生成的。

IT 管理员或支持人员代理将此信息输入到**DaRT 远程连接查看器**中，以便与最终用户计算机建立终端服务连接。 已建立的终端服务连接允许 IT 管理员与最终用户计算机上的 DaRT 工具远程交互。 最终用户计算机将处理连接信息、共享其屏幕，并响应来自 IT 管理员计算机的说明。

[如何使用 DaRT 恢复映像恢复远程计算机](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)

## 使用 DaRT7 恢复计算机的其他资源


[DaRT 7.0 的操作](operations-for-dart-70-new-ia.md)

 

 





