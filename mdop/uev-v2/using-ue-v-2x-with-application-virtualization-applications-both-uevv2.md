---
title: 在应用程序虚拟化应用程序中使用 UE-V 2. x
description: 在应用程序虚拟化应用程序中使用 UE-V 2. x
author: dansimp
ms.assetid: 4644b810-fc48-4fd0-96e4-2fc6cd64d8ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221d21c5815b36b57a04a0299352e5fe64f657c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804135"
---
# 在应用程序虚拟化应用程序中使用 UE-V 2. x


Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 支持 Microsoft Application Virtualization （App-v）应用程序，而无需对 App-v 包或 UE-V 模板进行任何所需的修改。 但是，需要额外的步骤，因为不能直接在虚拟化 App-v 应用程序上运行 UE-V 生成器。 而必须在本地安装应用程序，生成模板，然后将该模板应用于虚拟化的应用程序。 UE-V 支持 app-v 4.5、App V 4.6 和 App-v 5.0 程序包。

## App-v 应用程序的 UE-V 设置同步


当应用程序按程序名称打开时，按文件版本号和产品版本号（可选）通过使用 App-v 安装应用程序时，UE-V 监视器。 当应用程序启动时，UE-V 会监视 app-v 进程，应用存储在用户的设置存储路径中的任何设置，然后使应用程序可以正常启动。 UE-V 监视 app-v 应用程序，并自动将相关文件和注册表路径转换为虚拟化位置，而不是应用 V 计算环境之外的物理位置。

 **实现虚拟化应用程序的设置同步**

1.  运行 UE-V 生成器以收集本地安装的应用程序的设置，该应用程序的设置要在计算机之间同步。 此过程将创建一个设置位置模板。 如果您使用的是内置模板（如 Microsoft Office 2010 模板），请跳过此步骤。 有关运行 UE-V 生成器的详细信息，请参阅[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates)

2.  安装 app-v 应用程序包（如果尚未执行此操作）。

3.  将模板发布到设置模板目录的位置，或使用 `Register-UEVTemplate` Windows PowerShell cmdlet 手动安装模板。

    **注意** 如果将新创建的模板发布到设置模板目录，则在同步提供程序更新设置之前，客户端不会收到模板。 若要手动启动此过程，请打开 "**任务计划程序**"，展开 "**任务计划程序库**"，展开 " **Microsoft**"，然后展开 " **ue-v**"。 在 "结果" 窗格中，右键单击 "**模板自动更新**"，然后单击 "**运行**"。

     

4.  启动 app-v 程序包。






## 相关主题


[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

 

 





