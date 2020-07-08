---
title: 如何使用 DaRT 恢复映像恢复远程计算机
description: 如何使用 DaRT 恢复映像恢复远程计算机
author: dansimp
ms.assetid: 66bc45fb-dc40-4d47-b583-5bb1ff5c97a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 885ab1d1cf8f51dc4fd4613e41a20a2525ea7d6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803239"
---
# 如何使用 DaRT 恢复映像恢复远程计算机


Microsoft Diagnostics 和恢复工具集中的 "远程连接" 功能（DaRT）7允许 IT 管理员在最终用户计算机上远程运行 DaRT 工具。 当最终用户（或由支持最终用户计算机的技术支持人员）提供某些信息后，IT 管理员或支持人员可以控制最终用户的计算机并远程运行必要的 DaRT 工具。

**重要提示**  
建立远程连接的两台计算机必须是同一网络的一部分。



**使用 DaRT 恢复远程计算机**

1.  使用 DaRT 恢复映像启动最终用户计算机。

    通常，你可以使用以下方法之一启动到 DaRT 以恢复远程计算机，具体取决于你部署 DaRT 恢复映像的方式。 有关部署 DaRT 恢复映像的详细信息，请参阅[部署 dart 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)。

    -   从有问题的计算机上的恢复分区启动到 DaRT。

    -   从网络上的远程分区启动到 DaRT。

    有关每种方法的优点和缺点的信息，请参阅[规划如何保存和部署 DaRT 7.0 恢复映像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)。

    无论使用哪种方法启动到 DaRT，您都必须在 BIOS 中为启动选项启用启动设备，或者您希望向最终用户提供的选项。

    **注意**  
    配置 BIOS 是唯一的，具体取决于您的组织中使用的硬盘驱动器、网络适配器和其他硬件的类型。



2.  当计算机启动到 DaRT 恢复映像时，将出现 " **NetStart** " 对话框。 系统将询问您是否要初始化网络服务。 如果单击 **"是**"，则假设网络上存在 DHCP 服务器，并尝试从服务器获取 IP 地址。 如果网络使用静态 IP 地址而不是 DHCP，则可以在以后使用 DaRT 中的**Tcp/ip 配置**工具指定静态 ip 地址。

    若要跳过网络初始化过程，请单击 "**否**"。

3.  在 "网络初始化" 对话框中，系统会询问你是否要重新映射驱动器号。 当您运行 Windows online 时，系统卷通常映射到驱动器 C。但是，当你在 WinRE 下运行 Windows 时，原始系统卷可能会映射到其他驱动器，这可能会引起混淆。 如果您决定重新映射，DaRT 将尝试映射脱机驱动器号以匹配联机驱动器号。 仅在启动过程中稍后选择了脱机操作系统时，才会执行重映射。

4.  在 "重新映射" 对话框中，将出现 "**系统恢复选项**" 对话框，要求你选择键盘布局。 然后，它显示系统根目录、所安装的操作系统类型和分区大小。 如果您没有看到您的操作系统列出，并且怀疑缺少驱动程序可能导致故障，请单击 "**加载驱动程序**" 以加载可疑驱动程序。 这将提示您插入设备的安装媒体并选择驱动程序。 选择要修复或诊断的安装，然后单击 "**下一步**"。

    **注意**  
    如果 Windows 恢复环境（WinRE）检测到或怀疑 Windows 7 未在上次尝试时正常启动，则**启动修复**可能会开始自动运行。 有关此情况的信息，包括如何解决此问题，请参阅[DaRT 7.0 的疑难解答](troubleshooting-dart-70-new-ia.md)。



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

5. 在 "**系统恢复选项**" 窗口中，选择 " **Microsoft 诊断和恢复工具集**" 以打开 "**诊断和恢复工具**集" 窗口。

6. 在 "**诊断和恢复工具集**" 窗口中，单击 "**远程连接**" 以打开 " **DaRT 远程连接**" 窗口。 如果系统提示您提供帮助台远程访问，请单击 **"确定"**。

   将打开 "DaRT 远程连接" 窗口，并显示票证编号、IP 地址和端口信息。

7. 在 "帮助台" 代理计算机上，打开 " **DaRT 远程连接查看器**"。

   单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft dart 7**"，然后单击 " **DaRT 远程连接查看器**"。

8. 在 " **DaRT 远程连接**" 窗口中，输入所需的票证、IP 地址和端口信息。

   **注意**  
   此信息在最终用户计算机上创建，并且必须由最终用户提供。 可能有多个 IP 地址可供选择，具体取决于最终用户计算机上可用的数量。



9. 单击**连接**。

IT 管理员现在假定控制最终用户计算机，并且可以远程运行 DaRT 工具。

**注意**  
提供了名为 inv32.xml 的文件，其中包含远程连接信息，例如端口号和 IP 地址。 默认情况下，该文件通常位于%windir%\\system32。



**自定义远程连接过程**

1. 您可以通过编辑 winpeshl.ini 文件来自定义远程连接过程。 有关如何编辑 winpeshl.ini 文件的详细信息，请参阅[Winpeshl.ini 文件](https://go.microsoft.com/fwlink/?LinkId=219413)。

   指定以下命令和参数以自定义如何与最终用户计算机建立远程连接：

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">命令</th>
   <th align="left">参数</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>RemoteRecovery.exe</strong></p></td>
   <td align="left"><p>-nomessage</p></td>
   <td align="left"><p>指定不显示确认提示。 <strong>远程连接 </strong> 继续执行，就像最终用户 &quot; &quot; 对确认提示做出响应一样。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>WaitForConnection.exe</strong></p></td>
   <td align="left"><p>无</p></td>
   <td align="left"><p>防止自定义脚本在 <strong> 远程连接 </strong> 未运行或与最终用户计算机建立有效连接的情况下继续进行。</p>
   <div class="alert">
   <strong>重要提示</strong><br/><p>如果单独指定此命令，此命令将不起作用。 必须在脚本中指定它才能正常工作。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. 以下是自定义的 winpeshl.ini 文件的一个示例，在尝试启动到 DaRT 后立即打开**远程连接**工具：

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

**在命令提示符处运行远程连接查看器**

1.  你可以通过指定**DartRemoteViewer.exe**命令并使用以下参数，在命令提示符处运行**DaRT 远程连接查看器**：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>-票证 = &lt; <em> ticketnumber</em>&gt;</p></td>
    <td align="left"><p>其中， &lt; <em> ticketnumber </em> &gt; 是由远程连接生成的票据号码，包括短划线。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>-ipaddress = &lt; <em> ipaddress</em>&gt;</p></td>
    <td align="left"><p>其中 ip &lt; <em> </em> &gt; 地址是由远程连接生成的 IP 地址。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>-port = &lt; <em> 端口</em>&gt;</p></td>
    <td align="left"><p>其中 &lt; <em> 端口 </em> &gt; 是对应于指定 IP 地址的端口。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. 如果所有三个参数均已指定且数据有效，则会在程序启动时立即尝试连接。 如果任何参数无效，程序将在未指定参数的情况下启动。

## 相关主题


[使用 DaRT 7.0 恢复计算机](recovering-computers-using-dart-70-dart-7.md)









