---
title: 如何使用 SQL 脚本部署 App-V 数据库
description: 如何使用 SQL 脚本部署 App-V 数据库
author: dansimp
ms.assetid: 23637936-475f-4ca5-adde-76bb27d2372b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 511d1020571eead25af9e9591fe1834a9f97f068
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798464"
---
# 如何使用 SQL 脚本部署 App-V 数据库


按照以下说明使用 SQL 脚本（而不是 Windows 安装程序）执行以下操作：

-   安装 app-v 5.0 数据库

-   将5.0 数据库升级到更高版本

**如何使用 SQL 脚本安装 app-v 数据库**

1. 在安装数据库脚本之前，请检查并保留 App-v 许可证条款的副本。 运行数据库脚本即已同意许可条款。 如果您不接受这些功能，则不应使用本软件。

2. 将**appv\_server\_setup.exe**从 app-v 版本媒体复制到临时位置。

3. 在命令提示符处，运行**appv\_server\_setup.exe**并指定用于提取数据库脚本的临时位置。

   示例： appv\_server\_setup.exe/layout c:\\ &lt; 临时位置路径&gt;

4. 通过浏览找到您创建的临时位置，打开解压缩的**DatabaseScripts**文件夹，然后查看相应的 Readme.txt 文件，了解有关说明：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">数据库</th>
   <th align="left">要使用 Readme.txt 文件的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>管理数据库</p></td>
   <td align="left"><p>ManagementDatabase 子文件夹</p>
   <div class="alert">
   <strong>重要提示</strong><br/><p>如果要升级到或安装 app-v 5.0 SP3 管理数据库，请参阅 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安装或升级 app-v 5.0 Sp3 管理服务器数据库失败的 SQL 脚本 </a> 。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p>报告数据库</p></td>
   <td align="left"><p>ReportingDatabase 子文件夹</p></td>
   </tr>
   </tbody>
   </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相关主题


[部署 App-V 5.0 Server](deploying-the-app-v-50-server.md)

[如何部署 App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)









