---
title: 如何将服务器配置为受信任以进行委派
description: 如何将服务器配置为受信任以进行委派
author: dansimp
ms.assetid: d8d11588-17c0-4bcb-a7e6-86b5e4ba7e1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7164b3046671853216b870d68e651fed4fd84695
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801540"
---
# 如何将服务器配置为受信任以进行委派


安装 Microsoft Application Virtualization （App-v）管理服务器软件时，可以选择使用分布式系统体系结构安装它。 如果在不同计算机上安装控制台、管理 Web 服务和数据库，则必须将 Internet information Services （IIS）服务器配置为受信任的委派。 这是必需的，因为管理 Web 服务将尝试使用使用该控制台的 App-v 管理员的凭据连接到 App-v 数据存储。 在其上安装数据存储的数据库服务器将不接受来自 IIS 服务器的管理员凭据，除非将 IIS 服务器配置为受信任的委派，并且管理 Web 服务将无法连接到 app-v 数据存储。

**注意** 如果在单个服务器上安装 app-v 管理服务器软件并将数据存储放置在单独的服务器上，则你仍然必须将服务器配置为受信任的委派，即使管理 Web 服务和管理控制台位于同一台服务器上也是如此。 如果需要使用 "**使用备用凭据**" 选项连接到控制台中的管理 Web 服务，则会出现此情况。

 

你可以使用的委派类型取决于你在 Active Directory 域服务（添加）基础结构中配置的域功能级别。 下表列出了可以为 App-v 的每个域功能级别配置的委派类型。 表格后面的详细说明。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">域功能级别</th>
<th align="left">可用委派级别</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 2000 本机</p></td>
<td align="left"><ul>
<li><p>无委派（默认）</p></li>
<li><p>无约束委派</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2</p></td>
<td align="left"><ul>
<li><p>无委派（默认）</p></li>
<li><p>无约束委派¹</p></li>
<li><p>约束委派（仅使用 Kerberos 协议）</p></li>
<li><p>约束委派（使用任何身份验证协议）¹</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

¹不要使用。

## 在域功能级别为 Windows 2000 native 时配置无约束的委派


在 Web 服务器域的域控制器上，完成以下步骤。

****

1.  单击 "**开始**"、"**管理工具**"，然后单击 " **Active Directory 用户和计算机**"。

2.  展开 "域"，然后展开 "计算机" 文件夹。

3.  在右窗格中，右键单击 Web 服务器的计算机名称，然后单击 "**属性**"。

4.  在 "**常规**" 选项卡上，确保选中 "**信任计算机作为委派**" 复选框。

5.  单击“确定”****。

## 在域功能级别为 Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2 时配置无约束的委派


在 Web 服务器域的域控制器上，完成以下步骤。

****

1.  单击 "**开始**"，单击 "**管理工具**"，然后单击 " **Active Directory 用户和计算机**"。

2.  展开 "域"，然后展开 "计算机" 文件夹。

3.  在右窗格中，右键单击 Web 服务器的计算机名称，选择 "**属性**"，然后单击 "**委派**" 选项卡。

4.  单击以选择 "**信任此计算机以委派到任何服务（仅限 Kerberos）**"。

5.  单击“确定”****。

## 在域功能级别为 Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2 时配置受限委派


在 Web 服务器域的域控制器上，完成以下步骤。

****

1.  单击 "**开始**"，单击 "**管理工具**"，然后单击 " **Active Directory 用户和计算机**"。

2.  展开 "域"，然后展开 "计算机" 文件夹。

3.  在右窗格中，右键单击 Web 服务器的计算机名称，选择 "**属性**"，然后单击 "**委派**" 选项卡。

4.  单击以选择 "**信任此计算机仅委派指定的服务**"。

5.  确保选中 "**仅使用 Kerberos** "，然后单击 **"确定"**。

6.  单击“添加”**** 按钮。 在 "**添加服务**" 对话框中，单击 "**用户" 或 "计算机**"，然后浏览到包含应用 V 数据存储的 Microsoft SQL server 的名称，然后单击 "从 IIS 接收用户凭据"。 单击“确定”****。

7.  在 "**可用服务**" 列表中，选择列出端口号的 MSSQLSvc 服务，Microsoft SQL Server 在该端口上接受 app-v 数据库的连接（默认端口为1433）。 单击“确定”****。

### 为受限制的委派配置 IIS 7 的其他步骤

如果在 IIS 7 服务器上运行管理 Web 服务，则必须完成以下步骤以将 IIS 7 *useAppPoolCredentials*变量设置为 True。

1.  打开提升的命令提示符窗口。 若要打开提升的命令提示符窗口，请单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。

2.  导航到%windir%\\system32\\inetsrv。

3.  键入**appcmd.exe set config-section： system.webserver/security/authentication/windowsAuthentication-useAppPoolCredentials： true**，然后按 ENTER。

 

 





