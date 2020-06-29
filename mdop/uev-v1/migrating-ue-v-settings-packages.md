---
title: 迁移 UE-V 设置包
description: 迁移 UE-V 设置包
author: dansimp
ms.assetid: 93d99254-3e17-4e96-92ad-87059d8554a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0087f334e916c06e7611d2671d0b50e7d1dd916
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803322"
---
# 迁移 UE-V 设置包


在 Microsoft 用户体验虚拟化（UE-V）部署的生命周期内，你可能需要在迁移到新服务器或备份时重新定位用户设置包。 在以下情况下可能需要迁移设置程序包：

-   将现有服务器硬件升级到新式服务器。

-   将设置存储位置的迁移从实验室共享到生产服务器。

只需复制文件和文件夹将不会保留安全设置和权限。 以下所述步骤将正确地将设置程序包文件复制到新共享的 NTFS 权限。

**如何在迁移到新服务器时保留 UE-V 设置程序包**

1.  在其他服务器上的新位置中，创建一个新文件夹;例如，MySettings。

2.  对旧服务器上的旧文件夹共享禁用共享。

3.  通过命令行将现有设置包从 Robocopy 移动到新服务器。 例如：

    ``` syntax
    c:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    **注意** 若要监视复制进度，请使用日志文件阅读器（如 Trace32）打开 MySettings.txt。

     

4.  向新共享授予共享级别的权限。 保留由 Robocopy 设置的 NTFS 权限。

    在运行 UE-V agent 的计算机上，将 SettingsStoragePath 配置设置更新为新共享的 UNC 路径。

## 相关主题


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 的操作](operations-for-ue-v-10.md)

 

 





