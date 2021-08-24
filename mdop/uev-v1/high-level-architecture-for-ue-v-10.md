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
ms.openlocfilehash: b54a9a207f9b74ad3d028cf4ab1f9842d59b0b3a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910447"
---
# <a name="high-level-architecture-for-ue-v-10"></a>UE-V 1.0 的高级别体系结构


本主题介绍应用程序设置漫游解决方案Microsoft 用户体验虚拟化 (UE-V) 体系结构元素。 以下元素是标准部署UE-V一部分。

![ue-v 代理体系结构图。](images/ue-vagentarchitecturaldiagram.gif)

当UE-V设置位置模板中标识应用程序和操作系统进程时，UE-V代理。 当应用程序或操作系统启动时，会从设置包中读取设置，并应用于计算机。 当应用程序关闭或操作系统锁定或关闭时，设置将保存在设置UE-V设置包中。

## <a name="settings-storage-location"></a>设置存储位置


设置存储位置是用户体验虚拟化代理访问以读取和写入设置的文件共享。 此位置是 Active Directory 主目录，或在安装过程中UE-V定义。 您可以在安装 UE-V 代理期间设置位置，或者稍后可以使用组策略、WMI 或 PowerShell 设置位置。 该位置可以位于用户可以访问的任何公用文件共享上。 如果在安装过程中未设置任何设置存储位置，UE-V将使用 Active Directory 中的主目录。 该UE-V代理验证位置，并创建一个系统文件夹，该文件夹对要存储和访问用户设置的用户隐藏。 有关设置存储详细信息，请参阅[准备环境以UE-V。](preparing-your-environment-for-ue-v.md)

## <a name="ue-v-agent"></a>UE-V代理


该UE-V代理安装在每台计算机上，其设置由用户体验虚拟化进行同步。 代理监视注册的应用程序和操作系统，以对设置进行的任何更改，并且它会在计算机之间同步这些设置。 设置在应用程序启动时，从设置存储位置应用到应用程序。 然后，当应用程序关闭时，这些设置将保存回设置存储位置。 当用户登录、解锁计算机时，或者当用户使用远程桌面协议或 RDP) 远程连接到计算机时，将应用操作系统 (设置。 当用户注销、计算机锁定或远程连接断开时，代理将保存设置。 有关安全代理UE-V，请参阅[准备环境UE-V。](preparing-your-environment-for-ue-v.md)

## <a name="settings-location-templates"></a><a href="" id="bkmk-settingslocationtemplate"></a>设置位置模板


设置位置模板是一个 XML 文件，它定义用户体验虚拟化要监视的设置位置。 只有这些设置模板中定义的设置位置会捕获或应用到运行 UE-V 代理的计算机上。 设置位置模板不包含设置值，仅包含值存储在计算机上的位置。

UE-V一组设置位置模板，用于指定某些 Microsoft 应用程序的设置位置和Windows位置。 管理员可以使用生成器创建自定义设置位置UE-V模板。

[规划要使用 UE-V 1.0 同步的应用程序](planning-which-applications-to-synchronize-with-ue-v-10.md)

[规划 UE-V 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)

[使用自定义 UE-V 模板和 UE-V 生成器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## <a name="settings-packages"></a>设置包


应用程序设置Windows设置存储在设置包中，设置包由 UE-V 代理创建。 设置包是在设置位置模板中表示的设置的集合。 这些设置包在本地存储，然后复制到设置存储位置。 "最后写入优先"确定当单个用户将多台计算机同步到存储位置时保留哪些设置。 在一台计算机上运行的代理独立于在其他计算机上运行的代理读取和写入设置位置。 当下一个代理从设置存储位置读取时，将应用最近写入的设置和值。

![ue-v 生成器进程。](images/ue-vgeneratorprocess.gif)

## <a name="settings-template-catalog"></a>设置模板目录


设置模板目录是 SMB UE-V上的文件夹路径或 SMB (SMB) 存储所有自定义设置位置模板的服务器消息块。 该UE-V代理从此位置检索新的或更新的模板。 代理UE-V检查此位置一次，并基于此文件夹中的模板更新其同步行为。 自上次检查以来在此文件夹中添加或更新的模板由UE-V注册。 该UE-V代理将取消注册从此文件夹中删除的模板。 模板由任务计划程序每天注册和注销一次。 如果您将仅使用自定义模板中包含的默认设置位置UE-V，则不需要设置模板目录。 有关设置部署目录详细信息，请参阅 Planning [for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md)。

## <a name="user-experience-virtualization-generator"></a>用户体验虚拟化生成器


用户体验虚拟化生成器使你能够创建自定义设置位置模板，这些模板将存储企业中使用的应用程序以及你想要包括在漫游设置解决方案中的应用程序的设置位置。 the UE-V Generator will seek to discover the location of registry values and the settings files for applications and then it will record those locations in a settings location template XML file. 然后，可以将这些设置位置模板分发给用户计算机。 此外UE-V生成器还允许管理员编辑现有模板或验证使用另一个 XML 编辑器创建的模板。

该UE-V生成器监视应用程序以发现并记录其设置存储位置。 为此，它监视应用程序在 HKEY\_CURRENT\_USER 注册表中或 Users **\\** \[User name\] \\ **AppData**  \\  **Roaming and Users** \\ \[User name\] \\ **AppData**  \\  **Local**下的文件文件夹中读取或写入的位置。

发现过程将排除登录用户无法写入值的注册表项和文件。 XML 文件中不会包含所有这些内容。 发现过程还会排除与操作系统的核心功能关联的注册表项Windows文件。

有关生成器UE-V，请参阅[安装UE-V生成器。](installing-the-ue-v-generator.md)

## <a name="related-topics"></a>相关主题


[Microsoft 用户体验虚拟化 (UE-V) 1.0](index.md)

[用户体验虚拟化 1.0 入门](getting-started-with-user-experience-virtualization-10.md)

[关于用户体验虚拟化 1.0](about-user-experience-virtualization-10.md)

[使用自定义 UE-V 模板和 UE-V 生成器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





