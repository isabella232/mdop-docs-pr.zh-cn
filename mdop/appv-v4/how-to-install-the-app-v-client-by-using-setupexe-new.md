---
title: 如何使用 Setup.exe 安装 App-V Client
description: 如何使用 Setup.exe 安装 App-V Client
author: dansimp
ms.assetid: 106a5d97-b5f6-4a16-bf52-a84f4d558c74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60f79a2d2f74848ab121ba13cdf8c215088d54db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801376"
---
# 如何使用 Setup.exe 安装 App-V Client


本主题介绍了如何使用 setup.exe 程序安装 App-v 客户端。 使用 setup.exe 程序安装 App-v 客户端时，安装程序确定需要哪些必备软件，并在安装客户端之前自动安装该软件。

**使用 Setup.exe 安装应用程序虚拟化客户端**

1.  请确保使用具有计算机管理员权限的帐户登录。

2.  打开命令提示符窗口，然后将目录更改为包含安装程序文件的文件夹。 在安装版本4.6 或更高版本的 App-v 客户端时，必须使用适用于计算机操作系统、32位或64位的正确安装程序。 如果你使用了错误的安装程序，安装将失败，并且将显示一条错误消息。

3.  在命令提示符处输入安装命令字符串。 或者，你可以创建一个命令文件并从命令提示符处运行它。 你还可以使用脚本语言（如 VBScript 或 Windows PowerShell）运行命令。

4.  下面的命令行示例演示如何将 setup.exe 用于许多可选参数。 有关这些参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。

    **"setup.exe"/s/v "/qn SWICACHESIZE = \ \" SWIPUBSVRDISPLAY = \ "=" SWIPUBSVRTYPE = \ "HTTP/secure\\" SWIPUBSVRHOST = \ "PRODSYS\\" SWIPUBSVRPORT = \ \ "" SWIPUBSVRPATH = \\ "/AppVirt/appsntype.xml \" SWIPUBSVRREFRESH = \ \ "on\\" SWIGLOBALDATA = \ \ "D:\\AppVirt\\Global\\" SWIUSERDATA = \ "^% LOCALAPPDATA ^%\\Windows\\Application 虚拟化 Client\\" SWIFSDRIVE = \ \ "Q\\" "**

    **重要提示**  
    -   "**/V**" 部分中显示的引号必须被视为特殊字符，并使用前面的 " **\\** " 输入。 只有当值包含空格时，才需要使用引号。但是，为了保持一致性，上述示例中的所有实例都显示为带有引号。

    -   " **%** **% HomeDrive%**" 中的 "" 字符必须前面有 " **^** " 转义字符。 否则，Windows 命令外壳程序会将值设置为执行安装的用户的值。

    -   需要使用**InstallShield**开关 **/s**和 **/qn**将其设置为静默安装。 **/Qn**开关必须跟在 **/v**开关之后，由不带空格的引号字符分隔。

    -   在**SWIGLOBALDATA**值中指定的文件夹必须已存在。

     

5.  安装完成后，我们建议你运行 Microsoft 更新扫描以确保安装最新的更新。

## 相关主题


[如何使用命令行安装客户端](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





