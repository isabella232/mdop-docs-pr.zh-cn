---
title: 如何配置客户端日志文件
description: 如何配置客户端日志文件
author: dansimp
ms.assetid: dd79f8ce-61e2-4dc8-af03-2a353554a1b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 729089d683c5d102eb7eb45314583023d3362639
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801560"
---
# 如何配置客户端日志文件


你可以使用以下过程配置应用程序虚拟化（app-v）客户端日志文件。

**更改日志文件位置**

-   编辑以下注册表项值以指定日志文件的新路径。 更改此值后，必须重新启动**sftlist**服务。 此位置也可以在安装后以交互方式进行更改。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName

**更改日志报告级别**

-   默认情况下，写入日志的消息类型包括严重级别4（信息）或更高版本的所有事件。 严重级别存储在以下键值中。 将此项值设置为5以启用详细日志记录。 在故障排除期间使用详细日志记录，因为它将生成大量的消息，并导致日志快速填充。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMinSeverity

**更改日志大小**

-   在应用程序虚拟化（App-v）4.5 中，日志大小由以下注册表项值控制。 此值默认为256MB，定义在重置之前日志可以增长到的最大大小（以 MB 为单位）。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMaxSize

    **小心** 此注册表项值必须设置为大于零的值，以确保日志文件恢复正常。

     

**更改备份副本的数量**

-   当日志文件达到最大大小时，将在下次写入日志时发生强制重置。 重置导致创建新的日志文件，并且旧文件被重命名为备份。 以下注册表设置控制重置文件时保留的日志文件备份副本数。 默认值为4。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount

    备份日志文件的格式如下所示： **sftlog\_YYYYMMDD\_hhmmss-uuu.txt**和基于重置时间（采用协调世界时（UTC）。 下表列出了用于创建文件名及其说明的符号。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">符号</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>YYYY</p></td>
    <td align="left"><p>4位数年份</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>分钟</p></td>
    <td align="left"><p>2位数的月份（01–12）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>DD</p></td>
    <td align="left"><p>2位月的第几天（01–31）</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>h</p></td>
    <td align="left"><p>小时（00–23）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>分钟</p></td>
    <td align="left"><p>分钟（00–59）</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>ss</p></td>
    <td align="left"><p>秒（00–59）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>uuu</p></td>
    <td align="left"><p>毫秒（000–999）</p></td>
    </tr>
    </tbody>
    </table>

     

## 相关主题


[如何使用命令行配置 App-V Client 注册表设置](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





