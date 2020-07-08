---
title: 如何使用 Setup.msi 安装 App-V Client
description: 如何使用 Setup.msi 安装 App-V Client
author: dansimp
ms.assetid: 7221f384-36d6-409a-94a2-86f54fd75322
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb3a145a6c57cccbae3f4e6b191b89d93278ff8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801375"
---
# 如何使用 Setup.msi 安装 App-V Client


本主题介绍了如何使用 setup.msi 程序安装 App-v 客户端。 在使用 setup.msi 程序安装 app-v 客户端之前，必须首先确定是否必须安装任何必备软件，然后必须安装它。 若要安装必备软件，请参阅本主题的[安装必备软件](#prereq-sw)部分。 若要安装客户端软件，请参阅使用本主题的[Setup.msi 程序部分安装 App-v 客户端](#msi-setup)。

## <a href="" id="prereq-sw"></a>安装必备软件


你可以使用以下过程来安装必备软件。 可以创建命令文件并从命令提示符运行命令，也可以使用脚本语言（如 VBScript 或 Windows PowerShell）运行命令。

**注意** 适用于 App-v 客户端的 x86 和 x64 版本都需要以下软件的 x86 版本。

 

**安装 Microsoft VisualC + + 2005SP1 可再发行程序包（x86）**

1. 从 Microsoft 下载中心下载[Microsoft Visual c + + 2005 SP1 可再发行程序包（x86）](https://go.microsoft.com/fwlink/?LinkId=119961)软件包（ <https://go.microsoft.com/fwlink/?LinkId=119961> ）。 \ [模板令牌值 \] 对于应用-V 客户端的版本 4.5 SP2 和更高版本，请从[Microsoft Visual c + + 2005 Service Pack 1 可再发行软件包 1](https://go.microsoft.com/fwlink/?LinkId=169360)下载 vcredist\_x86.exe （ https://go.microsoft.com/fwlink/?LinkId=169360).\ [Template Token Value \]）下载

2. 若要自行安装，请将命令行选项 "/Q" 与 vcredist\_x86.exe 结合使用，例如**vcredist\_x86.exe/q**。

3. 若要使用 vcredist\_x86.msi 文件安装软件，请使用命令行选项 "/C/T： &lt; fullpathtofolder &gt; " 提取文件 vcredist.msi 并 vcredis1.cab 从 vcredist\_x86.exe 到临时文件夹。 若要自行安装，请使用命令行选项/quiet，例如， **msiexec/i vcredist.msi** /quiet。

### 安装 Microsoft VisualC + + 2008SP1 可再发行程序包（x86）

**重要提示** 对于应用程序-V 客户端的版本4.6 和更高版本，你还必须安装 Microsoft Visual c + + 2008 Service Pack 1 可再发行程序包 "ATL 安全更新"。

 

****

1.  从 Microsoft 下载中心下载[Microsoft Visual c + + 2008 Service Pack 1 可再发行软件包 "ATL 安全更新](https://go.microsoft.com/fwlink/?LinkId=150700)软件包" （ https://go.microsoft.com/fwlink/?LinkId=150700) 。

2.  若要自行安装，请将命令行选项 "/Q" 与 vcredist\_x86.exe 结合使用，例如**vcredist\_x86.exe/q**。

### 安装 Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）

****

1.  从 Microsoft 下载中心下载[Microsoft CORE XML Services （MSXML） 6.0 sp1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266)软件包（ https://go.microsoft.com/fwlink/?LinkId=63266) 。

2.  若要自行安装，请使用命令行选项/quiet，例如， **msiexec/i msxml6\_x86.msi/quiet**。

### 安装 Microsoft 应用程序错误报告

安装 Microsoft 应用程序错误报告时，必须使用*APPGUID*参数来指定应用程序-V 产品代码。 产品代码对于每个 App-v 客户端类型和版本都是唯一的。 从下表中选择正确的产品代码。

**重要提示** 对于 app-v 4.6 SP2 及更高版本，不再需要安装 Microsoft 应用程序错误报告（dw20shared.msi）。 App-v 现在使用 Microsoft 错误报告。

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">版本</th>
<th align="left">桌面客户端的产品代码</th>
<th align="left">适用于远程桌面服务客户端的产品代码</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 4.5 CU1</p></td>
<td align="left"><p>FE495DBC-6D42-4698-B61F-86E655E0796D</p></td>
<td align="left"><p>8A97C241-D92A-47DC-B360-E716C1AAA929</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.5 SP1</p></td>
<td align="left"><p>93468B43-C19D-44F9-8BCC-114076DB0443</p></td>
<td align="left"><p>0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.5 SP2</p></td>
<td align="left"><p>C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</p></td>
<td align="left"><p>ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 x86</p></td>
<td align="left"><p>9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</p></td>
<td align="left"><p>439FAC21-B423-41D4-8126-54F9FCB70039</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.6 x64</p></td>
<td align="left"><p>E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</p></td>
<td align="left"><p>D2977C18-D88A-47CB-AFD8-652DD36F4D0D</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 x86 ¹</p></td>
<td align="left"><p>40C3258B-F9D1-46DF-AE97-72C1F86F2427</p></td>
<td align="left"><p>9915D911-CC73-4122-AF4F-564F89454655</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.6 x64 ¹</p></td>
<td align="left"><p>1650E31F-23B8-40B5-A60A-C5934F557E3B</p></td>
<td align="left"><p>7580D918-C621-49E7-9877-3CC59F9BD1DA</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 x86 SP1</p></td>
<td align="left"><p>DB9F70CD-29BC-480B-8BA2-C9C2232C4553</p></td>
<td align="left"><p>1354855A-2298-4C73-9022-EF0686C65991</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.6 x64 SP1</p></td>
<td align="left"><p>342C9BB8-65A0-46DE-AB7A-8031E151AF69</p></td>
<td align="left"><p>B2C6C8D5-FE76-4056-A326-EE5D633EA175</p></td>
</tr>
</tbody>
</table>

 

¹ App-V "语言" 发布。

**注意** 如果需要查找产品代码，可以使用 Orca.exe 数据库编辑器或类似工具检查 Windows 安装程序文件以查找*ProductCode*属性的值。 有关使用 Orca.exe 的详细信息，请参阅[Windows Installer 开发工具](https://go.microsoft.com/fwlink/?LinkId=150008)（ https://go.microsoft.com/fwlink/?LinkId=150008) 。

 

****

1.  找到 "Microsoft 应用程序错误报告安装程序" dw20shared.msi，可在发布媒体上的**Support\\Watson**文件夹中找到该程序。

2.  若要安装该软件，请运行以下命令：

         **msiexec /i dw20shared.msi APPGUID={valuefromtable} REBOOT=Suppress REINSTALL=ALL REINSTALLMODE=vomus**

## <a href="" id="msi-setup"></a>使用 Setup.msi 程序安装 App-v 客户端


使用以下过程安装 App-v 客户端。 确保已安装任何必需的必备软件。 \ [模板令牌值 \] 对于应用程序-V 客户端的版本4.6 和更高版本，setup.msi 程序检查系统，并且如果未安装必备软件，它会生成一条错误消息，指示安装无法继续。 \ [模板令牌值 \]

**使用 Setup.msi 安装应用程序虚拟化客户端**

1.  请确保使用具有计算机管理员权限的帐户登录。

2.  使用提升的权限打开命令提示符窗口，然后将目录更改为包含安装程序文件的文件夹。 在安装版本4.6 或更高版本的 App-v 客户端时，必须使用适用于计算机操作系统、32位或64位的正确安装程序。 如果你使用了错误的安装程序，安装将失败，并且将显示一条错误消息。

3.  在命令提示符处输入安装命令字符串。 或者，你可以创建一个命令文件并从命令提示符处运行它。 你还可以使用脚本语言（如 VBScript 或 Windows PowerShell）运行命令。

4.  下面的命令行示例演示如何将 setup.msi 用于许多可选参数。 有关这些参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。

    **msiexec.exe/i "setup.msi" SWICACHESIZE = "10240" SWIPUBSVRDISPLAY = "生产系统" SWIPUBSVRTYPE = "HTTP/secure" SWIPUBSVRHOST = "PRODSYS =" = "appsntype.xml SWIPUBSVRPORT =" SWIPUBSVRPATH = "/AppVirt/=" SWIPUBSVRREFRESH = "SWIGLOBALDATA =" D:\\AppVirt\\Global = "SWIUSERDATA =" LOCALAPPDATA = "S"%\\Windows\\Application ^ SWIFSDRIVE 虚拟化客户端 "=" S "/q**

    **重要提示**  
    -   Windows Installer 开关 "**/q**" 用于将其设置为静默式安装。

    -   " **%** **% HomeDrive%**" 中的 "" 字符必须前面有 " **^** " 转义字符。 否则，Windows 命令外壳程序会将值设置为执行安装的用户的值。

    -   若要启用安装日志记录，请使用 msiexec 开关 **/l\ * v 文件名 .log**。

     

## 相关主题


[如何使用命令行安装客户端](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





