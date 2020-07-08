---
title: DaRT 7.0 的安全注意事项
description: DaRT 7.0 的安全注意事项
author: dansimp
ms.assetid: 52ad7e6c-c169-4ba4-aa76-56335a585eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739c0319195aeb26e38d55ffe01d14b623de7f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803227"
---
# DaRT 7.0 的安全注意事项


Microsoft 诊断和恢复工具集（DaRT）7包含允许管理员远程运行 DaRT 工具以解决最终用户计算机上的问题的功能。 在早期版本的 DaRT 中，技术支持技术人员或管理员必须使用包含 DaRT 恢复映像的 CD 或 DVD，才能在最终用户计算机上启动到 DaRT。 现在，技术支持技术人员或管理员可以远程执行相同的过程。

此外，在 DaRT7 中，除了刻录 CD 或 DVD，你现在可以将国际标准化组织（ISO）映像保存到 USB 闪存驱动器。 你还可以将 ISO 映像放在网络上，或将其内容包含在计算机硬盘上的恢复分区。

DaRT7 中的**远程连接**功能允许最终用户使用这些新部署方法之一访问 DaRT。 因此，他们可以更轻松地启动 DaRT 和访问 DaRT 工具。

DaRT7 中的新功能在您的企业中使用 DaRT 的方式提供了更大的灵活性。 但是，他们还会创建自己的一组必须解决的安全问题。 我们建议你在配置 DaRT 时考虑以下安全提示。

## 创建 DaRT 恢复映像时帮助保持安全


创建 DaRT 恢复映像时，可以选择要包含的工具。 出于安全原因，你可能希望限制最终用户对更强大的 DaRT 工具（如磁盘擦除和 Locksmith）的访问。 在 DaRT7 中，你可以在配置期间禁用某些工具，并且当最终用户启动远程连接功能时仍将它们提供给帮助台代理。

您甚至可以配置 DaRT 映像，以便用于启动远程连接会话的选项是最终用户可用的唯一工具。

**重要提示** 建立远程连接后，你包含在恢复映像中的所有工具（包括最终用户不可用的工具）将对在最终用户计算机上工作的帮助台工程师可用。

 

有关在 DaRT 恢复映像中包括工具在内的详细信息，请参阅[如何使用 Dart 恢复映像向导创建恢复映像](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)。

## 通过加密 DaRT 恢复映像来帮助维护安全性


如果你使用 DaRT7 中新增的一个部署选项（例如，保存到 USB 闪存驱动器或创建远程分区或恢复分区），则可以在 ISO 上包括公司的首选驱动器加密方法。 这将帮助确保最终用户不能使用 DaRT 的功能来获得恢复映像的访问权限。 此外，它还将确保未经授权的用户无法在属于其他人的计算机上启动到 DaRT。

应在所有计算机中部署和启用加密方法。

**注意** DaRT7 支持 BitLocker 本身。

 

## 在远程连接期间帮助保持两台计算机的安全


默认情况下，已建立**远程连接**会话的两台计算机之间的通信可能不会加密。 因此，为了帮助维护两台计算机之间的安全，我们建议两台计算机都是同一网络的一部分。

## 相关主题


[DaRT 7.0 的操作](operations-for-dart-70-new-ia.md)

 

 





