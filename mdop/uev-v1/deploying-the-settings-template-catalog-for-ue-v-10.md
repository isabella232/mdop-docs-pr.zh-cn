---
title: 为 UE-V 1.0 部署设置模板目录
description: 为 UE-V 1.0 部署设置模板目录
author: dansimp
ms.assetid: 0e6ab5ef-8eeb-40b4-be7b-a841bd83be96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f342daa958607a077fa5eb2a27ec705c8d99e67f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804007"
---
# 为 UE-V 1.0 部署设置模板目录


自定义设置位置模板可以存储在 Microsoft 用户体验虚拟化（UE-V）计算机或服务器消息块（SMB）网络共享上的文件夹路径中。 计算机上的计划任务从该位置检查新的或更新的模板。 该任务每天检查此位置一次，并根据此文件夹中的模板更新其同步行为。 自上次检查以来在此文件夹中添加或更新的模板由 UE-V agent 注册。 从该文件夹中删除的 UE-V agent deregisters 模板。 计划任务作为系统运行。 至少，网络共享必须为 "域计算机" 组授予权限。 此外，将网络共享文件夹的访问权限授予将管理存储的模板的管理员。 有关自定义设置位置模板的详细信息，请参阅[规划 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

**配置 UE-V 的设置模板目录**

1.  在将存储 UE-V 设置模板目录的计算机上创建一个新文件夹。

2.  为设置模板目录文件夹设置以下共享级别（SMB）权限。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>用户帐户</strong></th>
    <th align="left"><strong>推荐权限</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>无权限</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>域计算机</p></td>
    <td align="left"><p>读取权限级别</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>管理员</p></td>
    <td align="left"><p>读/写权限级别</p></td>
    </tr>
    </tbody>
    </table>

     

3.  为设置模板目录文件夹设置以下 NTFS 权限。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">用户帐户</th>
    <th align="left">推荐的权限</th>
    <th align="left">应用于</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>创建者/所有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>此文件夹、子文件夹和文件</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>域计算机</p></td>
    <td align="left"><p>列出文件夹内容和阅读</p></td>
    <td align="left"><p>此文件夹、子文件夹和文件</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>无权限</p></td>
    <td align="left"><p>无权限</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>管理员</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>此文件夹、子文件夹和文件</p></td>
    </tr>
    </tbody>
    </table>

     

4.  单击 **"确定"** 关闭对话框。

## 相关主题


[部署 UE-V 1.0](deploying-ue-v-10.md)

[规划 UE-V 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)

 

 





