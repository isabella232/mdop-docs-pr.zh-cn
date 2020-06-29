---
title: 如何更改服务器日志记录级别和数据库参数
description: 如何更改服务器日志记录级别和数据库参数
author: dansimp
ms.assetid: e3ebaee5-6c4c-4aa8-9766-c5aeb00f477a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bb35ac09c5e23f4847662171b68284f868e66dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801655"
---
# 如何更改服务器日志记录级别和数据库参数


你可以使用以下过程来更改应用程序虚拟化服务器管理控制台中的日志记录级别和数据库日志参数。

以下日志记录级别可用：

-   仅交易记录

-   致命错误

-   错误

-   警告/错误

-   信息/警告/错误

-   详细

**注意** 由于在使用**Verbose**模式时生成的日志文件的大小，因此建议你不要运行具有此日志记录集级别的生产服务器。

 

数据库日志记录参数确定了日志记录数据库的数据库驱动程序类型、访问凭据和位置。

**更改管理服务器的日志记录级别**

1.  单击 "**服务器组**" 节点以显示服务器组。

2.  右键单击服务器组，然后选择 "**属性**"。

3.  在 "**属性**" 对话框中，选择 "**日志记录**" 选项卡。

4.  在 "**服务器组属性**" 对话框中，选择服务器，然后单击 "**编辑**"。

5.  在 "**添加/编辑日志模块**" 对话框中，从 "**事件类型**" 下拉列表中选择日志记录级别。

6.  单击“确定”****。

7.  在 "**服务器组属性**" 对话框中，单击 **"确定" 或 "** **应用**"。

**更改流式服务器的日志记录级别**

1.  编辑以下注册表项值以更改日志记录级别：

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel

2.  选择以下值之一以设置日志记录级别。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">值</th>
    <th align="left">日志记录级别</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>0</p></td>
    <td align="left"><p>仅交易记录</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>raid-1</p></td>
    <td align="left"><p>致命错误</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>ppls-2</p></td>
    <td align="left"><p>错误</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>三维空间</p></td>
    <td align="left"><p>警告/错误</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>第</p></td>
    <td align="left"><p>信息/警告/错误</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>级</p></td>
    <td align="left"><p>详细</p></td>
    </tr>
    </tbody>
    </table>

     

**更改数据库日志参数**

1.  单击 "**服务器组**" 节点以显示服务器组。

2.  右键单击服务器组，然后选择 "**属性**"。

3.  在 "**属性**" 对话框中，选择 "**日志记录**" 选项卡。

4.  在 "**服务器组属性**" 对话框中，选择服务器，然后单击 "**编辑**"。

5.  在 "**添加/编辑日志模块**" 对话框中，从 "**数据库驱动程序**" 下拉列表中选择数据库驱动程序。

6.  输入**DNS 主机名**。

7.  单击 "**动态确定端口**" 复选框，或在 "**端口**" 字段中输入一个端口号。

8.  在对应字段中输入**服务名称**。

9.  单击“确定”****。

10. 在 "**服务器组属性**" 对话框中，单击 **"确定" 或 "** **应用**"。

## 相关主题


[如何在 Server Management Console 中自定义 Application Virtualization System](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

 

 





