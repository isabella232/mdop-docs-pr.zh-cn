---
title: 如何在客户端上发布虚拟应用程序
description: 如何在客户端上发布虚拟应用程序
author: dansimp
ms.assetid: 90af843e-b5b3-4a71-a3a1-fa5f4c087f28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5585f82150db69929ccedbee3aecab969c5e7dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801191"
---
# 如何在客户端上发布虚拟应用程序


使用电子软件分发系统部署应用程序虚拟化时，可以使用以下过程之一将应用程序包发布给用户。

**使用独立的 Windows Installer 文件发布程序包**

1.  应安装客户端，将*REQUIREAUTHORIZATIONIFCACHED*参数设置为0（零）。 有关设置此参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)

2.  将 Windows Installer 文件和 SFT 文件复制到目标计算机上的同一文件夹中。

3.  在计算机上运行以下命令：

    `Msiexec.exe /I "packagename.msi" /q`

**使用 Windows Installer 和程序包清单发布程序包**

1.  将 Windows Installer 文件复制到目标计算机，然后将 SFT 文件复制到流服务器上的内容共享。

2.  在每个用户的计算机上运行以下命令：

    `Msiexec.exe /I "\\pathtomsi\packagename.msi" MODE=STREAMING  OVERRIDEURL="\\\\server\\share\\package.sft" LOAD=TRUE /q`

    **重要提示** 对于 OVERRIDEURL，所有反斜杠字符必须使用前面的反斜杠进行转义，否则将不会正确分析 OVERRIDEURL 路径。 此外，必须以大写形式输入属性和值，除非值是文件的路径。

     

**使用 SFTMIME 发布程序包**

-   有关如何为计算机上的所有用户发布应用程序的示例，请在用户的计算机上运行以下命令：

    `SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

    有关这些和其他 SFTMIME 命令的其他详细信息，请参阅[SFTMIME 命令参考](sftmime--command-reference.md)。

## 相关主题


[确定发布方法](determine-your-publishing-method.md)

[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)

[SFTMIME 命令引用](sftmime--command-reference.md)

[适用于 Application Virtualization Client 的独立传递方案](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





