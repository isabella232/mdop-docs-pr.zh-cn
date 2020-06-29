---
title: 关于 App-V 包加速器 (App-V 4.6 SP1)
description: 关于 App-V 包加速器 (App-V 4.6 SP1)
author: manikadhiman
ms.assetid: fc2d2375-8f17-4a6d-b374-771cb947cb8c
ms.reviewer: ''
manager: dansimp
ms.author: v-madhi
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cb7b8e6fa9482838283257843caf4b291c03bf2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802479"
---
# 关于 App-V 包加速器 (App-V 4.6 SP1)


你可以使用 App-v 程序包加速器自动序列大型、复杂的应用程序。 此外，当你应用 app-v 包加速器时，并非始终需要手动安装应用程序来创建虚拟应用程序包。

**注意** 在某些情况下，系统会提示你在运行 App-v Sequencer 的计算机本地安装应用程序，然后才能使用程序包加速器。 如果必须安装应用程序，则必须将应用程序安装到应用程序的默认位置。 App-v Sequencer 不监视此安装。 创建 app-v 包加速器时，程序包加速器的作者确定是否需要在本地安装应用程序。

 

App-v Sequencer 从 App-v 程序包加速器提取所需的文件，并从关联的安装媒体中提取所需的文件，以创建虚拟程序包，而无需监视应用程序的安装。

**重要提示** 免责声明： Microsoft Application Virtualization Sequencer 不向你提供用于创建程序包加速器的软件应用程序的许可证权利。 您必须遵守此类应用程序的所有最终用户许可条款。 您有责任确保软件应用程序的许可条款允许您使用 Application Virtualization Sequencer 创建软件包加速器。

 

App-v 程序包加速器和项目模板彼此不同。 程序包加速器特定于应用程序。 项目模板使用户能够保存特定于某个组织的常用设置，并将其应用到多个应用程序。 你还可以在命令提示符处创建项目模板，而相反，你必须使用 App-v Sequencer 控制台创建程序包加速器。 此外，不支持通过使用包加速器创建程序包和应用项目模板。

## 共享 app-v 包加速器


本部分提供有关如何共享程序包加速器的最佳做法信息。 如果你计划共享程序包加速器，则程序包加速器中可能包含计算机名称、用户帐户信息以及有关关联的应用程序的信息。以下列表介绍了创建包加速器时应考虑的方法：

-   **用户名**。 当你登录到运行 App-v Sequencer 的计算机时，你应该使用通用用户帐户，例如用于管理计算机/域的内置**管理员**帐户。 不应使用基于现有用户名的帐户。

-   **计算机名**。 为运行 Sequencer 的计算机指定一般的、非标识的名称。

-   **服务器 URL**。 在 Sequencer 控制台中，在 "**部署**" 选项卡上，使用服务器 URL 配置信息的默认设置。

-   **应用程序**。 如果你不想共享在创建程序包加速器时运行 Sequencer 的计算机上安装的应用程序的列表，则必须删除**appv\_manifest.xml**文件。 此文件位于虚拟应用程序包的程序包根目录中。

你还应查看与虚拟应用程序包关联的任何设置或配置文件，以确保应用不包含任何个人信息。

## 保护 app-v 程序包加速器


始终将 App-v 程序包加速器和任何关联的安装媒体保存在网络上的安全位置，以保护 app-v 程序包加速器以及安装文件不会被篡改或损坏。 由于程序包加速器还可以包含密码和特定于用户的信息，因此必须在安全位置保存 App-v 程序包加速器，并且在创建程序包加速器后必须对其进行数字签名，以便可以在应用程序包加速器时验证发布者。 有关数字签名的详细信息，请参阅[适用于通用条件安全性的数字签名做法的应用程序指南](https://go.microsoft.com/fwlink/?LinkId=204705)（ https://go.microsoft.com/fwlink/?LinkId=204705) 。

## 相关主题


[如何创建 App-V 包加速器 (App-V 4.6 SP1)](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)

[如何应用程序包加速器以创建虚拟应用程序包（App-v 4.6 SP1）](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)

 

 





