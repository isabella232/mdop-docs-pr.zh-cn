---
title: 虚拟应用程序包附加组件
description: 虚拟应用程序包附加组件
author: dansimp
ms.assetid: 476b0f40-ebd6-4296-92fa-61fa9495c03c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d30c2c6561b0d2c08fd75e0c977bf4590d7e6688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798699"
---
# 虚拟应用程序包附加组件


App-v Sequencer 检测到一个目录，其中包含依赖于相同并行程序集的64位和32位可执行文件和/或动态链接库（.dll）文件。 通常，排序器为程序包使用的所有公共程序集创建专用的并行程序集;但是，不能在同一目录中创建私有程序集的32位和64位版本。

如果 Sequencer 检测到单个冲突，则它将执行以下操作：

-   删除整个程序包中的所有现有64位专用程序集，无论该目录是否有冲突。

-   仅创建32位版本的私有并行程序集。

你应该在运行 Sequencer 的计算机上和所有 App-v 客户端计算机上本机安装所有必需的64位程序集的公共版本。

若要查找所需的现有公共程序集，请打开保存程序包的目录，然后查看**VFS**文件夹。 例如，如果程序包根为**Q:\\MyApp**，则当你对应用程序进行排序时，请在**Q:\\MyApp\\VFS\\CSIDL\ _Windows \\winsxs\\manifests**中查找所有现有公共程序集。 这些文件的64位版本将始终以以下文本开头，清单名称的开头： **amd64 ...**。 可以在关联的清单文件中找到该程序集的确切名称和版本。

使用以下任一链接下载并安装所需先决条件的正确版本：

-   [Microsoft Visual c + + 2005 可再发行程序包（x64）](https://go.microsoft.com/fwlink/?LinkId=152697)

-   [Microsoft Visual c + + 2005 SP1 可再发行程序包（x64）](https://go.microsoft.com/fwlink/?LinkId=152698)

-   [Microsoft Visual c + + 2008 可再发行程序包（x64）](https://go.microsoft.com/fwlink/?LinkId=152699)

-   [Microsoft Visual c + + 2008 SP1 可再发行程序包（x64）](https://go.microsoft.com/fwlink/?LinkId=152700)

 

 





