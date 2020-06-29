---
title: 如何部署 App-V 5.1 Server
description: 如何部署 App-V 5.1 Server
author: dansimp
ms.assetid: 4729beda-b98f-481b-ae74-ad71c59b1d69
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4a367be7db4cea1835124657dbdfa3375474228e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798469"
---
# 如何部署 App-V 5.1 Server


使用以下过程安装 Microsoft Application Virtualization （App-v）5.1 服务器。 有关部署 app-v 5.1 服务器的信息，请参阅[关于 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)。

**开始之前：**

-   确保安装了必备软件。 请参阅[App-V 5.1 先决条件](app-v-51-prerequisites.md)。

-   查看[app-v 5.1 安全注意事项](app-v-51-security-considerations.md)的 "服务器" 部分。

-   指定将托管每个组件的端口。

-   添加防火墙规则以允许传入请求访问指定的端口。

-   如果使用 SQL 脚本（而不是 Windows 安装程序）设置管理数据库或报告数据库，则必须先运行 SQL 脚本，然后再安装管理服务器或报告服务器。 请参阅[如何使用 SQL 脚本部署 App-v 数据库](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md)。

**安装 app-v 5.1 服务器**

1. 将 app-v 5.1 服务器安装文件复制到要在其上安装的计算机。

2. 右键单击并以管理员身份运行**appv\_server\_setup.exe** ，启动 app-v 5.1 服务器安装，然后单击 "**安装**"。

3. 查看并接受许可条款，并选择是否启用 Microsoft 更新。

4. 在 "**功能选择**" 页面上，选择以下所有组件。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">组件</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>管理服务器</p></td>
   <td align="left"><p>提供 app-v 基础结构的总体管理功能。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>管理数据库</p></td>
   <td align="left"><p>为 App-v 管理简化数据库 predeployments。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>发布服务器</p></td>
   <td align="left"><p>提供虚拟应用程序的托管和流功能。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>报表服务器</p></td>
   <td align="left"><p>提供 app-v 5.1 reporting services。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>报告数据库</p></td>
   <td align="left"><p>为 App-v 报告简化数据库 predeployments。</p></td>
   </tr>
   </tbody>
   </table>

     

5. 在 "**安装位置**" 页面上，接受将安装所选组件的默认位置，或通过在 "**安装位置**" 行中键入新路径来更改位置。

6. 在初始的 "新建**管理数据库**" 页面上，通过选择相应的选项来配置**Microsoft SQL Server 实例**和**管理服务器数据库**。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">方法</th>
   <th align="left">需要执行的操作</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>你使用的是自定义 Microsoft SQL Server 实例。</p></td>
   <td align="left"><p>选择 <strong> "使用自定义实例" </strong> ，然后键入实例的名称。</p>
   <p>使用格式 " <strong> INSTANCENAME" </strong> 。 假定的安装位置是本地计算机。</p>
   <p>不支持：使用格式 <strong> ServerName </strong> &lt; 强 &gt; 实例的服务器名称 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>您使用的是自定义数据库名称。</p></td>
   <td align="left"><p>选择 <strong> "自定义配置 </strong> "，然后键入数据库名称。</p>
   <p>数据库名称必须是唯一的，否则安装将失败。</p></td>
   </tr>
   </tbody>
   </table>

     

7. 在 "**配置**" 页面上，接受默认值 "**使用此本地计算机**"。

   **注意**  
   如果并排安装管理服务器和管理数据库，则此页面上的某些选项不可用。 在这种情况下，默认情况下将选中相应的选项，并且不能更改。

     

8. 在初始的 "**创建新的报表数据库**" 页面上，通过选择相应的选项来配置**Microsoft SQL Server 实例**和**报告服务器数据库**。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">方法</th>
   <th align="left">需要执行的操作</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>你使用的是自定义 Microsoft SQL Server 实例。</p></td>
   <td align="left"><p>选择 <strong> "使用自定义实例" </strong> ，然后键入实例的名称。</p>
   <p>使用格式 " <strong> INSTANCENAME" </strong> 。 假定的安装位置是本地计算机。</p>
   <p>不支持：使用格式 <strong> ServerName </strong> &lt; 强 &gt; 实例的服务器名称 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>您使用的是自定义数据库名称。</p></td>
   <td align="left"><p>选择 <strong> "自定义配置 </strong> "，然后键入数据库名称。</p>
   <p>数据库名称必须是唯一的，否则安装将失败。</p></td>
   </tr>
   </tbody>
   </table>

     

9. 在 "**配置**" 页面上，接受默认值：**使用此本地计算机**。

   **注意**  
   如果并排安装管理服务器和管理数据库，则此页面上的某些选项不可用。 在这种情况下，默认情况下将选中相应的选项，并且不能更改。

     

10. 在 "**配置**（管理服务器配置）" 页面上，指定以下内容：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">要配置的项目</th>
    <th align="left">描述和示例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>键入具有管理 App-v 环境的足够权限的广告组。</p></td>
    <td align="left"><p>示例： MyDomain\MyUser</p>
    <p>安装后，你可以使用管理控制台添加其他用户或组。 但是，全局安全组和 Active Directory 域服务（AD DS）通讯组不受支持。 要 <strong> 执行此操作，必须使用域本地 </strong> 或 <strong> 通用 </strong> 组。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>网站名称 </strong> ：指定将用于运行发布服务的自定义名称。</p></td>
    <td align="left"><p>如果您没有自定义名称，请不要进行任何更改。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>端口绑定 </strong> ：指定将由 app-v 使用的唯一端口号。</p></td>
    <td align="left"><p>示例： <strong> 12345</strong></p>
    <p>确保指定的端口未被其他网站使用。</p></td>
    </tr>
    </tbody>
    </table>

     

11. 在 "**配置****发布服务器配置**" 页面上，指定以下内容：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">要配置的项目</th>
    <th align="left">描述和示例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>指定管理服务的 URL。</p></td>
    <td align="left"><p>上例<a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>网站名称 </strong> ：指定将用于运行发布服务的自定义名称。</p></td>
    <td align="left"><p>如果您没有自定义名称，请不要进行任何更改。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>端口绑定 </strong> ：指定将由 app-v 使用的唯一端口号。</p></td>
    <td align="left"><p>示例：54321</p>
    <p>确保指定的端口未被其他网站使用。</p></td>
    </tr>
    </tbody>
    </table>

     

12. 在 "**报告服务器**" 页面上，指定以下内容：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">要配置的项目</th>
    <th align="left">描述和示例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>网站名称 </strong> ：指定将用于运行报告服务的自定义名称。</p></td>
    <td align="left"><p>如果您没有自定义名称，请不要进行任何更改。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>端口绑定 </strong> ：指定将由 app-v 使用的唯一端口号。</p></td>
    <td align="left"><p>示例：55555</p>
    <p>确保指定的端口未被其他网站使用。</p></td>
    </tr>
    </tbody>
    </table>

     

13. 若要开始安装，请单击 "**准备就绪**" 页面上的 "**安装**"，然后单击 "**完成**" 页面上的 "**关闭**"。

14. 若要验证安装程序是否已成功完成，请打开 web 浏览器，然后键入以下 URL：

    **http:// &lt;管理服务器计算机名称 &gt; ： &lt; 管理服务端口号 &gt; /Console.html**。

    示例： **http://localhost:12345/console.html** 。 如果安装成功，将显示 app-v 管理控制台，没有任何错误。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[部署 App-V 5.1](deploying-app-v-51.md)

[如何在单独的计算机上从管理和报告服务安装管理和报告数据库](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[如何在远程计算机上安装发布服务器](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[如何使用脚本部署 App-V 5.1 Server](how-to-deploy-the-app-v-51-server-using-a-script.md)

 

 





