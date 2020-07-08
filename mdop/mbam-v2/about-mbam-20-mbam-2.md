---
title: 关于 MBAM 2.0
description: 关于 MBAM 2.0
author: dansimp
ms.assetid: b43a0ba9-1c83-4854-a2c5-14eea0070e36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7bdf24d1f375dd1fa8b18ac90c2fc49d2887c6c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803544"
---
# 关于 MBAM 2.0


Microsoft BitLockerAdministration 和监视（MBAM）2.0 为 BitLocker 驱动器加密提供了简化的管理接口。 对于丢失或被盗的计算机，BitLocker 提供增强的防护功能，防止数据失窃或数据暴露。 BitLocker 将加密存储在 Windows 操作系统卷和已配置数据卷上的所有数据。

## 关于 MBAM 2。0


BitLockerAdministration 和 Monitoring 2.0 强制执行你为你的企业设置的 BitLocker 加密策略选项，监视客户端计算机与这些策略的合规性，并报告企业和个人计算机的加密状态。 此外，MBAM 允许你在用户忘记其 PIN 或密码时，或者在其 BIOS 或启动记录发生更改时访问恢复密钥信息。

**注意** 本指南中未详细介绍 BitLocker。 有关 BitLocker 的概述，请参阅[Bitlocker 驱动器加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。

 

以下组可能对使用 MBAM 管理 BitLocker 感兴趣：

-   管理员、IT 安全专家和合规性监察官负责确保机密数据在未经授权的情况下不公开

-   负责远程或分支办公室中的计算机安全的管理员

-   负责运行 Windows 的客户端计算机的管理员

## <a href="" id="what-s-new-in-mbam-2-0"></a>MBAM 2.0 中的新增功能


MBAM 2.0 提供以下新增功能和功能。

### 将 System Center Configuration Manager 与 MBAM 集成

MBAM 现支持与 System Center Configuration Manager 集成。 此集成将 MBAM 合规基础结构移动到 Configuration Manager 的本机环境中。 在企业中使用 Configuration Manager 的 IT 管理员现在可以在 Microsoft 管理控制台中查看其企业的合规性状态，并深入查看报表以查看个别计算机。

### 硬件兼容性仅在 Configuration Manager 集成拓扑中可用

将配置管理器与 MBAM 集成支持允许或禁止对某些硬件类型使用 MBAM 的配置管理器功能，并提供比 MBAM 1.0 中提供的硬件兼容性更大的灵活性。 IT 管理员可以创建自己的集合来限制硬件，并且可以将 MBAM 配置基线部署到这些集合。 1.0 中显示的 MBAM 硬件兼容性现在仅在 MBAM Configuration Manager 拓扑中可用，并且从 Configuration Manager 管理。

### 保护灵活的策略

已使用保护器加密的计算机（例如，TPM + PIN 或自动解锁和密码），并且接收需要该加密的子集的 MBAM 策略（例如，TPM 或自动解锁）被视为合规性。 在上述示例中，不会自动删除 PIN 和密码，除非 IT 管理员专门定义不再允许的这些功能。

未加密且收到 MBAM 策略（例如，TPM 或自动解锁）的计算机会相应地加密。 允许本地管理员的用户使用 BitLocker 工具（控制面板项 BitLocker 驱动器加密或 manage-bde）添加或修改现有保护器（例如，TPM + PIN 或自动解锁和密码）。 除非 MBAM 策略明确定义，否则它们保持合规。

### 升级 MBAM 客户端的能力

MBAM 2.0 客户端 Windows 安装程序检测现有客户端的版本，并执行所需步骤以升级到以前版本的 MBAM 2.0 客户端。

### 从早期版本升级 MBAM 服务器的功能

你可以从早期版本的 MBAM 升级 MBAM 2.0 服务器基础结构，如下所示：

**手动就地服务器更换**-必须手动卸载现有的 MBAM 服务器基础结构，然后安装 MBAM 2.0 服务器基础结构。 不必删除数据库即可进行升级。 而是选择 MBAM 客户端的早期版本创建的现有数据库。 然后，MBAM 2.0 升级安装将现有数据库迁移到 MBAM 2.0。

**分布式客户端升级**-如果你使用的是独立的 MBAM 拓扑，则可以在安装 MBAM 2.0 服务器基础结构后逐步升级 MBAM 客户端。 MBAM 2.0 服务器检测现有客户端的版本并执行升级到2.0 客户端所需的步骤。

升级 MBAM 2.0 服务器基础结构后，MBAM 1.0 客户端会继续向 MBAM 2.0 服务器报告 escrowing 恢复数据，但合规性将基于 MBAM 1.0 中的策略。 必须将客户端升级到 MBAM 2.0 以使客户端计算机能够根据 MBAM 2.0 策略准确地报告合规性。 你可以将客户端升级到 MBAM 2.0 客户端，而不卸载以前的客户端，并且客户端将开始应用和报告 MBAM 2.0 策略。

如果你将 MBAM 与 Configuration Manager 配合使用，则必须将 MBAM 1.0 客户端升级到 MBAM 2.0。

### <a href="" id="mbam-support-for-bitlocker-s-enterprise-scenarios-on-the-windows-8-platform"></a>适用于 Windows 8 平台上的 BitLocker 企业方案的 MBAM 支持

MBAM 支持 Windows 8 操作系统作为 MBAM 客户端安装的目标平台。 此支持使 IT 管理员能够安装 MBAM 代理、加密 Windows 8 操作系统驱动器以及报告计算机合规性。 MBAM 利用 TPM 和 TPM + PIN 保护器管理 Windows 8 操作系统，就像处理 Windows 7 操作系统一样。 MBAM 2.0 还添加了对加密 Windows To Go 客户端的支持。

### 自助服务门户的添加

最终用户现在可以使用自助服务门户来恢复其恢复密钥。 自助服务门户可以在具有其他 MBAM 功能的单个服务器上部署，或者在单独的服务器上，让 IT 管理员能够灵活地根据需要向用户公开自助服务器门户。 在自助服务门户对用户进行身份验证后，用户只需输入恢复密钥 ID 的前八位数字即可接收其恢复密钥。

MBAM 还通过允许用户仅恢复他们为其用户的计算机来恢复密钥，从而降低其他用户获得未经授权访问权限的风险。

### 从暂停状态自动恢复 BitLocker 保护的功能

MBAM 不再允许 IT 管理员在长时间内暂停和不保护 BitLocker。 如果 IT 管理员暂停 BitLocker，MBAM 会在重新启动计算机时自动重新启用它，从而降低计算机受攻击的风险。

### 固定数据驱动器可以配置为在没有密码的情况下自动解锁

现可将固定数据驱动器（FDD）策略配置为允许不使用密码自动解锁驱动器。 在加密 FDD 之前，系统不会提示用户输入密码，并且 FDD 将受到保护，并使用操作系统驱动器自动解锁。

## <a href="" id="---------mbam-2-0-release-notes"></a> MBAM 2.0 发行说明


有关详细信息以及文档中未包含的最新新闻，请参阅[MBAM 2.0 的发行说明](release-notes-for-mbam-20-mbam-2.md)。

## 如何获取 MBAM 2。0


此技术是 Microsoft 桌面优化包（MDOP）的一部分。 企业客户可以通过 Microsoft 软件保障获得 MDOP。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop？](https://go.microsoft.com/fwlink/p/?LinkId=322049)

## 相关主题


[MBAM 2.0 入门](getting-started-with-mbam-20-mbam-2.md)

 

 





