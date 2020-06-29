---
title: 关于“共享包加速器”页
description: 关于“共享包加速器”页
author: dansimp
ms.assetid: 9630cde0-e2c3-476f-8fa1-58b3c9f7d3f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 34fe55d910a7532f011b239ff5b8162aa9240f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802439"
---
# 关于“共享包加速器”页


以下信息提供了有关如何共享程序包加速器的最佳做法信息。 如果你计划共享程序包加速器文件，则程序包加速器文件中可能包含计算机名、用户帐户信息以及有关转换中包含的应用程序的信息。 你应该检查与虚拟应用程序包关联的任何设置或配置文件，以确保应用不包含任何个人信息。此页面包含以下元素。

-   **用户名**。 当您登录到运行 Microsoft App-v 排序器的计算机时，应使用通用用户帐户，例如内置**管理员**帐户。 不应使用基于现有用户名的帐户。

-   **计算机名**。 指定运行 Sequencer 的计算机的常规、非标识名称。

-   **服务器 URL**。 在 App-v Sequencer 控制台中的 "**部署**" 选项卡上，使用服务器 URL 配置信息的默认设置。

-   **应用程序**。 如果你不想共享在创建程序包加速器时运行 Sequencer 的计算机上安装的应用程序的列表，则必须删除**appv\_manifest.xml**文件。 此文件位于虚拟应用程序包的程序包根目录中。

## 相关主题


[“创建包加速器”向导 (AppV 4.6 SP1)](create-package-accelerator-wizard--appv-46-sp1-.md)

[关于 App-V 包加速器 (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)

 

 





