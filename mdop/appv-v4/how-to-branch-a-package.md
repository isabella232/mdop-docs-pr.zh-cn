---
title: 如果对程序包进行分支
description: 如果对程序包进行分支
author: dansimp
ms.assetid: bfe46a8a-f0ee-4a71-9e9c-64ac08aac9c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2de36fae1a09aeae4d1b7b21ebe00f683e3b3693
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801692"
---
# 如果对程序包进行分支


使用此过程修改现有的顺序应用程序包，以便可以与原始顺序的应用程序包并行运行。 此过程称为分支。 当你对虚拟应用程序包进行分支时，你可以运行两个版本的同一程序包。 例如，你可以将 service pack 应用于现有程序包，并与原始已排序虚拟应用程序包并行运行。

使用以下过程对已排序的虚拟应用程序包进行分支。

**对已排序的虚拟应用程序包进行分支**

1.  打开 Microsoft Application Virtualization （App-v） Sequencer。 若要指定包含要分支的程序包（sprj）的目标目录，请选择 "**文件**"，然后单击 "**打开**"。

2.  导航到包含计划要分支的序列化应用程序的目录，然后单击 "**打开**"。

3.  若要保存程序包的副本，请在 app-v 排序器中选择 "**文件**"，然后选择 "**另存为**"。 指定新的唯一名称，并为程序包副本指定新的唯一程序包根目录。 单击 **“保存”**。

    **重要提示**  
    必须指定新的程序包名称，否则将覆盖程序包的现有版本。



~~~
The sequencer will automatically generate new GUID files for the new package. The version number associated with the package will also be automatically appended to the OSD file name.
~~~

4. 保存新版本后，你可以应用所需的配置更改，并将关联的 .ICO、OSD、SFT 和 SPRJ 文件保存到应用程序虚拟化（app-v）服务器上的正确位置。

## 相关主题


[Application Virtualization Sequencer 的任务](tasks-for-the-application-virtualization-sequencer.md)









