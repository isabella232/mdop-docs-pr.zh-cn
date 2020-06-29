---
title: 如何创建和使用项目模板
description: 如何创建和使用项目模板
author: dansimp
ms.assetid: e5ac1dc8-a88f-4b16-8e3c-df07ef5e4c3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de3471eca39d3804e8c5f070c5ec37560fae5dc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798498"
---
# 如何创建和使用项目模板


你可以使用 app-v 5.1 项目模板来保存与现有虚拟应用程序包关联的常用设置。 然后，在你的环境中创建新的虚拟应用程序包时，可以应用这些设置。 使用项目模板可以简化创建虚拟应用程序包的过程。

**注意**  
你可以和经常在程序包升级期间应用 app-v 5.1 项目模板。 例如，如果使用自定义排除列表对应用程序进行了序列化，建议在升级序列化应用程序时创建和保存关联模板以供将来使用。



App-v 5.1 项目模板与 App-v 5.1 应用程序加速器不同，因为 App-v 5.1 应用程序加速器是特定于应用程序的，而 app-v 5.1 项目模板可应用于多个应用程序。

使用以下过程创建和应用新模板。

**创建项目模板**

1.  若要启动 app-v 5.1 排序器，请在运行 sequencer 的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**"。

2.  **注意**  
    如果虚拟应用程序包当前已在 app-v 5.1 Sequencer 控制台中打开，请跳到此过程的步骤3。



~~~
To open the existing virtual application package that contains the settings you want to save with the App-V 5.1 project template, click **File** / **Open**, and then click **Edit Package**. On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open. Click **Edit**.
~~~

3. 在 app-v 5.1 Sequencer 控制台中，若要保存模板文件，请单击 "**文件**  /  **另存为模板**"。 查看将与新模板一起保存的设置后，单击 **"确定"**。 指定将与新的 App-v 5.1 项目模板关联的名称。 单击“保存”。

   新的 App-v 5.1 项目模板保存在此过程的步骤3中指定的目录中。

**应用项目模板**

1.  **重要提示**  
    不支持与程序包加速器一起使用项目模板创建虚拟应用程序包。



~~~
To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. 若要使用 app-v 5.1 项目模板创建或升级新的虚拟应用程序包，请单击 " **File**  /  **从模板新建**文件"。

3. 若要选择要使用的项目模板，请浏览到保存项目模板的目录，选择项目模板，然后单击 "**打开**"。

   创建新的虚拟应用程序包。 与指定模板一起保存的设置将应用于您创建的新虚拟应用程序包。

   已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)









