---
title: 如何修改与现有 Windows Installer 文件关联的操作系统
description: 如何修改与现有 Windows Installer 文件关联的操作系统
author: dansimp
ms.assetid: 0633f7e2-aebf-4e00-be02-35bc59dec420
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63184852f996cbe09b476f456f7c2b509549f4fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801223"
---
# 如何修改与现有 Windows Installer 文件关联的操作系统


使用以下过程修改与使用 App-v 排序器创建的现有 Windows Installer （**MSI**）文件相关联的操作系统版本。

**修改现有 Windows Installer 文件的操作系统**

1.  在仅安装了操作系统的环境中的计算机上安装 app-v Sequencer。 或者，你可以在运行虚拟环境的计算机（例如 Microsoft 虚拟 PC）上安装 Sequencer。 此方法非常有用，因为它更易于维护可使用最少的额外配置的干净的顺序环境。 有关安装 app-v Sequencer 的详细信息，请参阅[如何安装 Sequencer](how-to-install-the-sequencer.md)。

2.  将包含要修改的 Windows Installer 文件的整个虚拟应用程序包复制到运行 Sequencer 的计算机。

3.  若要修改 Windows installer 文件，请打开 Sequencer 控制台，选择 "**程序包**  /  **打开**"，然后浏览到保存与 Windows Installer 文件关联的虚拟应用程序包的位置。

4.  若要添加或删除操作系统，请选择 Sequencer 控制台中的 "**部署**" 选项卡。 若要指定将与 Windows Installer 文件相关联的其他操作系统，请选择所需操作系统，然后单击指向**所选**操作系统列表控件的箭头。

    若要删除操作系统关联，请选择要删除的操作系统，然后单击指向**可用**操作系统列表控件的箭头。

5.  若要创建将与虚拟应用程序包关联的新 Windows 安装程序，请选择 "**生成 Microsoft Windows installer （MSI）程序包**"。 或者，你可以选择 "**工具**  /  **创建 MSI**"。

    **注意** 如果选择 "**工具** / **创建 MSI** " 以创建新的 Windows Installer 文件，则可以跳过此过程的**步骤 6** 。

     

6.  若要保存虚拟应用程序包，请选择 "**打包**  /  **保存**"。

## 相关主题


[Application Virtualization Sequencer 的任务](tasks-for-the-application-virtualization-sequencer.md)

 

 





