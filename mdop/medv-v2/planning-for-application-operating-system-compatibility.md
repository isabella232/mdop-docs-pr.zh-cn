---
title: 规划应用程序操作系统兼容性
description: 规划应用程序操作系统兼容性
author: dansimp
ms.assetid: cdb0a7f0-9da4-4562-8277-12972eb0fea8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b10da2c870e5ddc32098136225515cdd0523809
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803774"
---
# 规划应用程序操作系统兼容性


本主题帮助确定如何解决应用程序操作系统兼容性问题，并讨论 Microsoft 企业版桌面虚拟化（MED-V）2.0 作为你的组织的解决方案的工作方式。

本主题讨论 MED-V 的业务要求，并将 MED-V 与 Windows XP 模式和 Microsoft Application Virtualization （App-v）进行比较：

-   [MED-V 的业务要求](#bkmk-whenmedv)

-   [MED-V 与 Windows XP 模式的优点](#bkmk-medvvsxp)

-   [MED-V 与 App-v 的好处](#bkmk-medvvsappv)

## <a href="" id="bkmk-whenmedv"></a>MED-V 的业务要求


当贵公司的 IT 部门确定是否升级到 Windows 7 时，必须注意它的业务线应用程序和基于 web 的业务线应用程序，以确保它们可以在新操作系统上运行。 通常，创建这些应用程序和 Url 以使用较早版本的 Windows 或 Internet Explorer 进行工作，并且在新操作系统中尝试使用它们时可能会出现问题。 Microsoft 提供了多种不同的方法来处理升级时可能出现的各种兼容性问题，例如应用程序兼容性工具包（ACT）和 Windows 7 程序兼容性助手。 即使在所有应用程序都已确定兼容性和修复已确定的情况下，某些应用程序在 Windows 7 上仍无法正常工作，或者太昂贵，无法解决。

通过使用 MED-V，你可以通过运行 Windows XP 的 Windows 虚拟 PC 环境运行这些旧版应用程序。 由于您不再需要在升级之前在新操作系统上测试和验证这些问题应用程序，因此你的迁移到 Windows 7 的速度将会更快、更快。

### 使用 MED-V 清单

如果以下任何情况适用于你，请考虑 MED-V：

-   您是大型组织（例如，500用户和更多），拥有与 Microsoft 的企业协议，并计划升级到 Windows 7。

-   你已测试你的业务线应用程序并发现与 Windows 7 不兼容的应用程序。

-   你已通过升级应用程序或使用 Microsoft 提供的填充（如应用程序兼容性工具包（ACT））解决了其中某些问题应用程序的兼容性问题，但某些应用程序的兼容性问题仍然存在。

-   你已将 app-v 视为用于传递不兼容的应用程序的选项，并在完成后（即使在实现 App-v 后），你仍然具有必须解决的应用程序操作系统兼容性问题。

-   你已将 Windows XP 模式视为解决方案，并已确定它不是有效的选项，因为：

    -   你希望能够同时将包含问题应用程序的虚拟映像部署到所有最终用户，而不是单独部署，并让虚拟图像自动加入到域。

    -   你已决定管理这些旧式应用程序（实际上是在虚拟上提供），并从一个集中位置（而不是每个最终用户的桌面上）控制 Windows 虚拟 PC 设置。

    -   你希望能够按比例（而不是按桌面）更新和支持虚拟机。

    -   你希望能够将更早版本的 Internet Explorer 中更好地运行的 Url 重定向到虚拟机，并在稍后轻松管理 URL 重定向。

-   你已确定它将更加经济高效，并且有助于尽快升级到 Windows 7，并决定推迟解决剩余的应用程序兼容性问题，直到你在 MED-V 中提供了解决方案。

## <a href="" id="bkmk-medvvsxp"></a> MED-V 与 Windows XP 模式的优点


Windows 虚拟电脑 for Windows 7 允许你在单个设备上同时运行不同版本的操作系统，并且包含在 Windows 7 专业版和更高版本中。

通过提供预配置的 Windows XP 映像（可让你创建虚拟 Windows XP 环境），windows XP 模式功能利用 Windows 虚拟 PC。 在此虚拟环境中，你可以手动安装与 Windows 7 不兼容的应用程序，并通过 Windows 虚拟 PC 从桌面无缝运行。

**通过使用 Windows XP 模式，你可以执行以下操作：**

-   在 Windows 虚拟 PC 中运行的虚拟机内运行与 Windows XP 兼容的应用程序。

-   将这些应用程序发布到主机的桌面或程序菜单。

如果你希望将这些虚拟机作为企业迁移到 Windows 7 的一部分提供，则必须能够快速部署虚拟机、预配和自定义它们，并可轻松地控制其设置和支持这些虚拟机。

基于 Windows XP 模式构建的 MED-V 提供企业范围的应用程序兼容性。 虽然 Windows XP 模式仅限于向个人和小型企业提供虚拟应用程序功能，但 MED-V 允许在整个公司网络中大规模部署预配置的 Windows XP 映像。 它为这些虚拟 MED-V 工作区的配置、部署和维护提供了一个企业就绪的管理解决方案。 MED-V 还为 enterpriseadministrators 提供了一组用于控制图像使用的策略。 这包括哪些用户将有权访问这些映像中的哪些特定应用程序。

**通过使用 MED-V，您可以执行以下操作：**

-   升级到新操作系统，无需测试和解决每个不兼容的应用程序和 URL。

-   部署按用户自动加入域和自定义的虚拟 Windows XP 映像。

-   为用户预配应用程序和 URL 重定向信息。

-   控制 Windows 虚拟电脑设置。

-   通过监视和疑难解答来维护和支持终结点。

-   确保已修补来宾计算机，即使处于暂停状态也是如此。

-   自动化每用户虚拟机创建和 sysprep 初始化。

-   轻松诊断主机和来宾计算机上的问题。

-   通过 Windows 虚拟 PC NAT 模式无缝管理连接的来宾计算机。

## <a href="" id="bkmk-medvvsappv"></a>MED-V 与 App-v 的好处


MED-V 和 App-v 是两种截然不同的技术，可轻松协同工作以解决你的应用程序操作系统兼容性问题。 通过使用 App-v，你可以为每个应用程序创建一个个性化的程序包，其中每个应用程序都与其他应用程序单独保存。 然后，可以将每个虚拟应用程序立即发送到最终用户，这对于 Windows 7 部署策略非常有用。

MED-V 不单独处理应用程序。 而是在运行 Windows 7 的同一桌面上创建 Windows XP 的其他实例。 你可以根据需要在此虚拟图像中安装任意数量的应用程序，并像管理组织中的任何其他桌面一样管理图像。

此外，你可以将 MED-V 与 App-v 结合使用，以便通过使用 MED-V 安装、发布和管理由 App-v 排序的虚拟应用程序。

## 相关主题


[定义和规划 MED-V 部署](define-and-plan-your-med-v-deployment.md)

 

 





