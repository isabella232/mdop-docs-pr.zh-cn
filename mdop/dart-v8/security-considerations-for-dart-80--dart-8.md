---
title: DaRT 8.0 的安全注意事项
description: DaRT 8.0 的安全注意事项
author: dansimp
ms.assetid: 45ef8164-fee7-41a1-9a36-de4e3264e7a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02d32d926c0def7d33bebd399cd380eed4e8385e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798110"
---
# DaRT 8.0 的安全注意事项


本主题包含有关客户和组、日志文件以及有关 Microsoft 诊断和恢复工具集（DaRT）8.0 的其他安全相关注意事项的简要概述。 有关详细信息，请访问本文中的链接。

## 常规安全注意事项


**了解安全风险**。 DaRT 8.0 包括允许管理员或技术支持人员远程运行 DaRT 工具以解决最终用户计算机上的问题的功能。 此外，你可以将国际标准化组织（ISO）映像保存到 USB 闪存驱动器，或将 ISO 映像放在网络上以将其内容包含在计算机硬盘上的恢复分区中。 这些功能提供了灵活性，但还带来了在配置 DaRT 时应考虑的潜在安全风险。

**确保计算机的物理安全**。 当管理员和技术支持工作者不是在其计算机上实际使用时，他们应该锁定其计算机并使用安全的屏幕保护程序。

**对所有计算机应用最新的安全更新**。 通过订阅安全通知服务（），随时了解操作系统的新更新 <https://go.microsoft.com/fwlink/?LinkId=28819> 。

## 限制最终用户访问 DaRT 工具


创建 DaRT 恢复映像时，可以选择要包含的工具。 出于安全原因，你可能希望限制最终用户对更强大的 DaRT 工具（如磁盘擦除和 Locksmith）的访问。 在 DaRT 8.0 中，你可以在配置期间禁用某些工具，并且当最终用户启动远程连接功能时仍将其提供给技术支持人员。

您甚至可以配置 DaRT 映像，以便用于启动远程连接会话的选项是最终用户可用的唯一工具。

**重要提示** 建立远程连接后，在恢复映像中包括的所有工具（包括最终用户不可用的工具）将提供给任何正在使用最终用户计算机的技术支持人员使用。

 

有关在 DaRT 恢复映像中包括工具在内的详细信息，请参阅[dart 8.0 中的工具概述](overview-of-the-tools-in-dart-80-dart-8.md)。

## 保护 DaRT 恢复映像


如果你通过将 DaRT 恢复映像保存到 USB 闪存驱动器或创建远程分区或恢复分区来部署它，你可能希望在 ISO 上包含公司的首选驱动器加密方法。 加密 ISO 有助于确保最终用户无法使用 DaRT 功能（如果他们获取恢复映像的访问权限），并确保未经授权的用户无法在属于其他人的计算机上启动 DaRT。 如果使用加密方法，请确保在所有计算机中部署并启用它。

**注意** DaRT 8.0 本身支持 BitLocker。

 

若要包括驱动器加密，请在创建恢复映像时添加加密解决方案文件。 您的加密解决方案必须能够在 WinPE 上运行。 然后，从 ISO 启动的最终用户可以访问该加密解决方案并取消阻止驱动器。

## 使用远程连接时维护两台计算机之间的安全性


默认情况下，已建立**远程连接**会话的两台计算机之间的通信可能不会加密。 因此，为了帮助维护两台计算机之间的安全，我们建议两台计算机都是同一网络的一部分。

## 相关主题


[DaRT 8.0 的安全和隐私](security-and-privacy-for-dart-80-dart-8.md)

 

 





