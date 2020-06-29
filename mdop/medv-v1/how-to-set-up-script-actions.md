---
title: 如何设置脚本操作
description: 如何设置脚本操作
author: dansimp
ms.assetid: 367e28f1-d8c2-4845-a01b-2fff9128ccfd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bfa264be447a0a8560e4af16ccaadc2ec1db3f6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798033"
---
# 如何设置脚本操作


脚本操作编辑器允许管理员创建在 MED-V 工作区设置过程中要执行的操作，并定义执行顺序。

下面是可添加到域设置脚本的操作列表：

-   **重启 windows**—重新启动 windows。

-   **加入域**-如果加入域，请包含此操作并配置用户名、密码、完全限定的域名、NetBIOS 域名和组织单位（可选）。

-   **检查连接**-配置服务器以连接到并验证 med-v 工作区是否可以连接到网络资源（如域服务器）。

-   **命令行**-在 med-v 工作区中配置脚本，并输入包含脚本路径和脚本参数的命令行。

-   **重命名计算机**—基于已定义的设置重命名虚拟机计算机。

-   **禁用自动登录**—禁用 Windows 自动登录。 应在将计算机添加到域的脚本结束时添加此操作。

## <a href="" id="how-to-set-up-script-actions-"></a>如何设置脚本操作


**设置脚本操作**

1.  在 " **VM 设置**" 选项卡上，单击 "**脚本编辑器**"。

2.  在 "**脚本操作**" 对话框中，单击 "**添加**"，然后在子菜单上单击所需的操作。

3.  按下表中所述配置操作。

    **注意** 
    在 " **VM 设置**" 选项卡中配置 "**重命名计算机**"。有关详细信息，请参阅[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。

     

~~~
**Note**  
To rename a computer, Windows must be restarted. It is recommended to add a Restart Windows action following a Rename Computer action.
~~~



4. 通过选择操作并单击 "**向上**" 或 "**向下**" 来设置操作顺序。

5. 单击**确定**。

**注意**  
运行加入域脚本时，要使脚本正常工作，登录到 MED-V 工作区虚拟机的用户必须具有本地管理员权限。



**注意**  
运行 "禁用自动登录脚本" 时，建议在初始设置完成后禁用用于自动登录的本地来宾帐户。



### <a href="" id="bkmk-joindomainproperties"></a>

**加入域属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>将 VM 加入域时要使用的凭据</p></td>
<td align="left"><p>选择以下凭据之一以在将 VM 加入到域时使用：</p>
<ul>
<li><p><strong>使用 MED-V 凭据 </strong> -最终用户凭据。</p></li>
<li><p><strong>使用以下凭据 </strong> -指定的凭据; 在对应字段中输入用户名和密码。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>你输入的凭据将对所有 MED-V 工作区用户可见。 建议不要提供域管理员凭据。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>要加入的域</p></td>
<td align="left"><p>选择以下其中一项：</p>
<ul>
<li><p><strong>使用域名在启动工作区 </strong> 时使用，即在登录到 med-v 客户端时加入最终用户输入的域。</p>
<p>若要定义从 NetBIOS 到完全限定的域名的映射，请单击 " <strong> 全局域映射表" </strong> 。 在全局域映射表中，单击 <strong> </strong> "添加"，输入 <strong> NetBIOS 域名 </strong> 和 <strong> 完全限定的域名 </strong> ，然后单击 <strong> "确定" </strong> 。</p></li>
<li><p><strong>使用以下域名 </strong> -加入指定域; 在对应字段中输入域名和 NetBIOS 域名。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>组织单位</p></td>
<td align="left"><p>可以指定组织单位（OU）将计算机加入特定的 OU。 格式必须遵循 OU 可分辨名称： OU = &lt; 组织单位 &gt; 、 &lt; 域控制器 &gt; （例如 OU = QATest、DC = IL、dc = med-v、dc = com）。</p>
<div class="alert">
<strong>警告</strong><br/><p>仅支持单个级别的 OU，如上例中所示。</p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-checkconnectivityproperties"></a>

**检查连接属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IP 地址</p></td>
<td align="left"><p>要验证连接到的服务器的 IP 地址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>端口</p></td>
<td align="left"><p>要验证其连接的服务器的端口。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>超时</p></td>
<td align="left"><p>超时前等待响应的秒数。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-commandlineproperties"></a>

**命令行属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Path</p></td>
<td align="left"><p>命令行的路径。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Arguments</p></td>
<td align="left"><p>命令行参数。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>等待退出</p></td>
<td align="left"><p>选中复选框以等待返回，然后再继续执行脚本操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>出现错误时出错</p></td>
<td align="left"><p>如果返回值为除指定值之外的任何值，请选中此复选框。</p>
<p>输入将指示该命令成功的值。</p>
<p>默认值： <strong> 0</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>只执行一次</p></td>
<td align="left"><p>选中此复选框以仅运行命令行一次。 如果脚本失败或被取消，则不会再次执行此命令。</p></td>
</tr>
<tr class="even">
<td align="left"><p>此命令行导致工作区中的 Windows 重启</p></td>
<td align="left"><p>如果命令行在完成后导致重新启动，请选中此复选框。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允许交互</p></td>
<td align="left"><p>如果命令将需要用户交互，请选中此复选框。</p></td>
</tr>
<tr class="even">
<td align="left"><p>进度消息</p></td>
<td align="left"><p>运行命令时向用户显示的消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>失败消息</p></td>
<td align="left"><p>如果命令失败，将向用户显示消息。</p></td>
</tr>
</tbody>
</table>

 

配置命令行操作时，可以按下表中定义的方式使用几个变量。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">参数</th>
<th align="left">值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>%MEDVUser%</p></td>
<td align="left"><p>经过身份验证的用户名。</p></td>
<td align="left"><p>MED-V 身份验证的用户名。 用户名和密码可在 "加入域 VM 设置" 脚本中使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>%MEDVPassword%</p></td>
<td align="left"><p>经过身份验证的密码。</p></td>
<td align="left"><p>MED-V 身份验证密码。 用户名和密码可在 "加入域 VM 设置" 脚本中使用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>%MEDVDomain%</p></td>
<td align="left"><p>配置的域。</p></td>
<td align="left"><p>在 MED-V 身份验证中配置的域。 它可以在 VM 设置脚本上使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>%DesiredMachineName%</p></td>
<td align="left"><p>计算机名。</p></td>
<td align="left"><p>管理应用程序中配置的唯一计算机名。 它可以在 VM 安装脚本中使用。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[如何为 MED-V 工作区配置虚拟机设置](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

 

 





