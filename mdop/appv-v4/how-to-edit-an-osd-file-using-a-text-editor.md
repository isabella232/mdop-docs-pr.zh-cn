---
title: 如何使用文本编辑器编辑 OSD 文件
description: 如何使用文本编辑器编辑 OSD 文件
author: dansimp
ms.assetid: f4263a1b-824f-49b9-8060-b8229c9d9960
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c83547b38cee7e91e8348689583e0542a88dab83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801419"
---
# 如何使用文本编辑器编辑 OSD 文件


使用以下过程，使用文本编辑器编辑打开的软件描述符（OSD）文件。

**使用文本编辑器编辑 OSD 文件**

1.  使用任何 XML 或 ASCII 文本编辑器（如 Microsoft 记事本）打开 OSD 文件。

    **注意** 在修改 OSD 文件之前，请阅读安装目录中由 XSD 文件指定的架构。 无法关注此架构可能会引入错误，从而阻止序列化的应用程序成功启动。

     

2.  使用所选的 XML 或 ASCII 文本编辑器编辑 OSD 文件，遵循指定的架构和以下准则：

    1.  确保命名的元素嵌套在 &lt; SOFTPKG &gt; 根元素中。

    2.  确保元素名称全部为大写字母。

    3.  请注意，属性值区分大小写。

    4.  请仔细键入，并遵守 XML 规范。

## 相关主题


[关于“OSD”选项卡](about-the-osd-tab.md)

[如何编辑 OSD 文件](how-to-edit-an-osd-file.md)

[OSD 文件元素](osd-file-elements.md)

 

 





