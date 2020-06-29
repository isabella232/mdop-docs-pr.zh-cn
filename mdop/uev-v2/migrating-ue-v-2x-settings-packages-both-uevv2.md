---
title: 迁移 UE-V 2 x-blade 设置程序包
description: 迁移 UE-V 2 x-blade 设置程序包
author: dansimp
ms.assetid: f79381f4-e142-405c-b728-5c048502aa70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0aa1f1c36594d69de40306dfa70a4a0cf5c86dbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803784"
---
# 迁移 UE-V 2 x-blade 设置程序包


在 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 部署的生命周期中，你可能需要在迁移到新服务器或执行备份时重新定位用户设置包。 在以下情况下，可能需要迁移设置程序包：

-   将现有服务器硬件升级到新式服务器。

-   将设置存储位置从测试服务器迁移到生产服务器。

只需复制文件和文件夹，就不会保留安全设置和权限。 以下步骤介绍了如何将设置包及其 NTFS 文件系统权限正确复制到新共享。

**在迁移到新服务器时保留 UE-V 2 设置程序包**

1.  在其他服务器上的新位置中，创建一个新文件夹，例如 MySettings。

2.  对旧服务器上的旧文件夹共享禁用共享。

3.  通过 Robocopy 将现有设置包复制到新服务器

    ``` syntax
    C:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    **注意** 若要监视复制进度，请使用日志查看器（如 Trace32）打开 MySettings.txt。

     

4.  向新共享授予共享级别的权限。 保留由 Robocopy 设置的 NTFS 文件系统权限。

    在运行 UE-V Agent 的计算机上，将**SettingsStoragePath**配置设置更新为新共享的通用命名约定（UNC）路径。

    已**获得有关 ue-v 的建议**？ 在[此处](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)添加或投票建议。 是否**遇到了 ue-v 问题**？ 使用[Ue-v TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## 相关主题


[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

 

 





