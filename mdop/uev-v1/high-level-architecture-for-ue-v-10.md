---
title: UE-V 1.0 的高级别体系结构
description: UE-V 1.0 的高级别体系结构
author: dansimp
ms.assetid: d54f9f10-1a4d-4e56-802d-22d51646e1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 76703cf4c7297401e6516830bf194cef741d60ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804100"
---
# UE-V 1.0 的高级别体系结构


本主题介绍 Microsoft 用户体验虚拟化（UE-V）设置漫游解决方案的高级别体系结构元素。 以下元素是标准 UE-V 部署的一部分。

![ue-v agent 体系结构图](images/ue-vagentarchitecturaldiagram.gif)

UE-V Agent 将监视应用程序和操作系统进程，因为它们在 UE-V 设置位置模板中标识。 当应用程序或操作系统启动时，将从设置包中读取设置并将其应用于计算机。 当应用程序关闭或操作系统锁定或关闭时，设置将保存在设置存储位置的 UE-V settings 程序包中。

## 设置存储位置


设置存储位置是用户体验虚拟化代理访问的用于读取和写入设置的文件共享。 此位置可以是 Active Directory 主目录，也可以是在 UE-V 安装期间定义的。 你可以在安装 UE-V agent 的过程中设置位置，也可以稍后通过组策略、WMI 或 PowerShell 设置位置。 该位置可以是用户可以访问的任何通用文件共享。 如果在安装期间没有设置存储位置，则 UE-V 将使用 Active Directory 中的主目录。 UE-V agent 将验证位置并创建一个系统文件夹，该文件夹将被存储和访问用户设置的用户隐藏。 有关设置存储的详细信息，请参阅[为 Ue-v 准备环境](preparing-your-environment-for-ue-v.md)。

## UE-V Agent


UE-V agent 使用由用户体验虚拟化同步的设置在每台计算机上安装。 对于对设置所做的任何更改，代理将监视已注册的应用程序和操作系统，并在计算机之间同步这些设置。 应用程序启动时，设置将从设置存储位置应用到应用程序。 然后，在应用程序关闭时，这些设置将保存回设置存储位置。 当用户登录、计算机处于解锁状态或者当用户使用远程桌面协议（RDP）将远程连接到计算机时，将应用操作系统设置。 当用户注销、计算机被锁定或远程连接断开时，代理会保存设置。 有关 UE-V Agent 的详细信息，请参阅[为 Ue-v 准备环境](preparing-your-environment-for-ue-v.md)。

## <a href="" id="bkmk-settingslocationtemplate"></a>设置位置模板


设置位置模板是一个 XML 文件，用于定义要由用户体验虚拟化监视的设置位置。 在运行 UE-V Agent 的计算机上，仅捕获或应用在这些设置模板中定义的设置位置。 设置位置模板不包含设置值，仅包含值存储在计算机上的位置。

UE-V 包含一组设置位置模板，用于为某些 Microsoft 应用程序和 Windows 设置指定设置位置。 管理员可以使用 UE-V 生成器创建自定义设置位置模板。

[规划要使用 UE-V 1.0 同步的应用程序](planning-which-applications-to-synchronize-with-ue-v-10.md)

[规划 UE-V 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)

[使用自定义 UE-V 模板和 UE-V 生成器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## 设置程序包


应用程序设置和 Windows 设置存储在设置程序包中，由 UE-V Agent 创建。 设置包是在设置位置模板中表示的设置的集合。 这些设置程序包已生成，本地存储，然后复制到设置存储位置。 "上次写入 wins" 确定当单个用户将多台计算机同步到一个存储位置时，将保留哪些设置。 在一台计算机上运行的代理将读取和写入设置位置，与在其他计算机上运行的代理无关。 当下一个代理从设置存储位置读取时，将应用最近写入的设置和值。

![ue-v 发电机进程](images/ue-vgeneratorprocess.gif)

## 设置模板目录


设置模板目录是 UE-V 计算机上的文件夹路径或用于存储所有自定义设置位置模板的服务器消息块（SMB）网络共享。 UE-V agent 从该位置检索新的或更新的模板。 UE-V agent 每天检查此位置一次，它会根据此文件夹中的模板更新其同步行为。 自上次检查以来在此文件夹中添加或更新的模板由 UE-V agent 注册。 UE-V agent deregisters 从此文件夹中删除的模板。 任务计划程序每天注册和注销一次模板。 如果只使用 UE-V 附带的默认设置位置模板，则不需要设置模板目录。 有关设置部署目录的详细信息，请参阅[规划 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

## 用户体验虚拟化生成器


用户体验虚拟化生成器使你能够创建自定义设置位置模板，这些模板将存储在企业中使用的应用程序的设置位置以及你希望包括在漫游设置解决方案中的应用程序的设置位置。 UE-V 生成器将寻找发现应用程序的注册表值和设置文件的位置，然后将在设置位置模板 XML 文件中记录这些位置。 然后，你可以将这些设置位置模板分发给用户计算机。 UE-V 生成器还允许管理员编辑现有模板或验证使用其他 XML 编辑器创建的模板。

UE-V 生成器监视应用程序以发现和记录其设置的存储位置。 若要执行此操作，它会监视应用程序在 HKEY _CURRENT \ _USER 注册表中或在 "**用户**\\ [用户名 \] \ \ **AppData**  \\  **漫游** **AppData**" 下的文件文件夹中读取或写入的位置  \\  **Local**。

发现过程将排除登录用户无法写入值的注册表项和文件。 XML 文件中不包含任何内容。 该发现过程还会排除与 Windows 操作系统的核心功能相关联的注册表项和文件。

有关 UE-V 生成器的详细信息，请参阅[安装 Ue-v 生成器](installing-the-ue-v-generator.md)。

## 相关主题


[Microsoft 用户体验虚拟化 (UE-V) 1.0](index.md)

[用户体验虚拟化 1.0 入门](getting-started-with-user-experience-virtualization-10.md)

[关于用户体验虚拟化 1.0](about-user-experience-virtualization-10.md)

[使用自定义 UE-V 模板和 UE-V 生成器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





