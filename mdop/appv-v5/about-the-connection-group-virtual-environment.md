---
title: 关于连接组虚拟环境
description: 关于连接组虚拟环境
author: dansimp
ms.assetid: 535fa640-cbd9-425e-8437-94650a70c264
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bd93c9e7acbf7bbf3f9da506d5d95b8df09e1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798663"
---
# 关于连接组虚拟环境


**本主题内容：**

-   [如何确定程序包优先级](#bkmk-pkg-priority-deter)

-   [将相同的包路径合并到连接组中的一个虚拟目录中](#bkmk-merged-root-ve-exp)

## <a href="" id="bkmk-pkg-priority-deter"></a>如何确定程序包优先级


虚拟环境及其当前状态与连接组关联，而不是与单个程序包关联。 如果从连接组中删除了 App-v 包，则作为连接组的一部分存在的状态将不会与程序包一起迁移。

如果同一程序包是两个不同连接组的一部分，则必须指明应使用的连接组 App-v。 例如，你可能在连接组中有两个程序包，每个程序包都定义相同的注册表 DWORD 值。

所使用的连接组基于**AppConnectionGroup** XML 文档中程序包出现的顺序：

-   第一个程序包具有最高优先级。

-   第二个程序包具有最高优先级。

请考虑以下示例部分：

```xml
<appv:Packages><appv:PackagePackageId="A8731008-4523-4713-83A4-CD1363907160"VersionId="E889951B-7F30-418B-A69C-B37283BC0DB9"/><appv:PackagePackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"VersionId="01F1943B-C778-40AD-BFAD-AC34A695DF3C"/><appv:PackagePackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"/></appv:Packages>
```

假设在第一个和第三个程序包中定义了相同的 DWORD 值 ABC （HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region），例如：

-   程序包1（A8731008-4523-4713-83A4-CD1363907160）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5

-   程序包3（04220DCA-EE77-42BE-A9F5-96FD8E8593F2）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 10

由于程序包1首先出现，AppConnectionGroup 的虚拟环境将具有单个 DWORD 值5（HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5）。 这意味着在查询 HKEY \ _LOCAL \ _MACHINE 时，程序包1、程序包2和程序包3中的虚拟应用程序都将看到值 5 \ \\software\\contoso\\finapp\\region。

其他虚拟环境资源的解析方式类似，但通常情况下，注册表中发生冲突。

## <a href="" id="bkmk-merged-root-ve-exp"></a>将相同的包路径合并到连接组中的一个虚拟目录中


如果连接组中的两个或多个程序包包含相同的目录路径，则路径将合并到连接组虚拟环境内的单个虚拟目录中。 这种路径合并允许一个程序包中的应用程序访问不同程序包中的文件。

从连接组中删除程序包时，删除的程序包中的应用程序将无法再访问连接组中其余程序包中的文件。

App-v 在 "连接" 组中查找文件名称的顺序由在连接组清单文件中列出 App-v 包的顺序指定。

以下示例显示了**程序包 a**和**程序包 B**的连接组中的文件名查找的顺序和关系。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">程序包 A</th>
<th align="left">程序包 B</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>C：\Windows\System32</p></td>
<td align="left"><p>C：\Windows\System32</p></td>
</tr>
<tr class="even">
<td align="left"><p>C:\AppTest</p></td>
<td align="left"><p>C:\AppTest</p></td>
</tr>
</tbody>
</table>

 

在上面的示例中，当虚拟化应用程序尝试查找特定文件时，将首先搜索程序包 A，查找匹配的文件路径。 如果找不到匹配路径，将使用以下映射规则搜索 Package B：

-   如果在两个应用程序包的同一虚拟文件夹层次结构中存在名为**test.txt**的文件，则使用第一个匹配的文件。

-   如果一个名为**bar.txt**的文件存在于一个应用程序包的虚拟文件夹层次结构中，但不在另一个应用程序包中，则使用第一个匹配的文件。






## 相关主题


[管理连接组](managing-connection-groups.md)

 

 





