---
title: 创建 MED-V 工作区程序包
description: 创建 MED-V 工作区程序包
author: dansimp
ms.assetid: 3f75fe73-41ac-4389-ae21-5efb2d437f4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e20cf4cc9394c4a5e90178fff4fc36ed83c12d60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803333"
---
# 创建 MED-V 工作区程序包


MED-V 工作区是 Windows XP 桌面环境，最终用户与 MED-V 提供的虚拟机交互。 管理员创建和自定义 MED-V 工作区。 工作区包含一个图像和组策略，用于定义 MED-V 工作区的规则和功能。

你可以创建多个 MED-V 工作区，每个都具有其自己的配置、设置和规则进行自定义。 用户、组或多个用户或组可以与每个 MED-V 工作区相关联。 自定义使该 MED-V 工作区仅适用于该用户或组。

使用**Med-v 工作区包装**程序创建 med-v 工作区。 **Med-v 工作区包装**程序分为两个主要部分：

-   主面板，其中包含用于创建和管理 MED-V 工作区的三个按钮。 "**创建 Med-v 工作区程序包**" 按钮可打开用于创建 med-v 工作区的 "**创建 Med-v 工作区程序包" 向导**。

-   窗口右侧的**帮助中心**，提供帮助你创建、测试和管理 med-v 工作区的信息和指南。

**重要提示**  
在可以使用**Med-v 工作区包装程序**之前，必须首先确保 Windows PowerShell 执行策略设置为 "无限制"。

`Set-ExecutionPolicy Unrestricted`

此外，运行**Med-v 工作区包装**程序的计算机的 SAN 策略必须设置为 "全部联机"。 若要检查 SAN 策略的设置，请使用管理凭据在命令提示符处运行以下命令：

`diskpart.exe`

`DISKPART> san`

`DISKPART> exit`

如有必要，请在命令提示符下通过使用管理凭据键入以下命令，将 SAN 策略更改为 "联机"。

`diskpart.exe`

`DISKPART> san policy=onlineall`

`DISKPART> exit`



**重要提示**  
如果在用于装载虚拟硬盘和构建 MED-V 工作区程序包的计算机上安装了自动磁盘加密软件，则必须在开始之前禁用该软件。 否则，不能在任何其他计算机上使用 MED-V 工作区。



我们在此处提供的信息可帮助你创建 MED-V 工作区部署包。

## <a href="" id="bkmk-prereq"></a>必备条件


开始构建 MED-V 工作区部署程序包之前，请验证你是否具有以下项目的访问权限：

-   **已准备好的 Windows XP 映像**

    有关如何创建与 MED-V 配合使用的 Windows XP 映像的详细信息，请参阅[准备 Med-v 映像](prepare-a-med-v-image.md)。

-   **包含 URL 重定向信息的文本文件或列表**

    你的 URL 重定向文本文件或列表包含你希望从主机计算机重定向到 MED-V 工作区中的 Internet Explorer 的 Url。 使用打包向导创建 MED-V 工作区时，可导入、键入或复制并粘贴该重定向信息作为程序包创建过程中的步骤之一。

    **注意**  
    MED-V 中的 URL 重定向仅支持 HTTP 和 HTTPS 协议。 MED-V 不提供对 FTP 或任何其他协议的支持。



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



## 将 MED-V 工作区与 MED-V 工作区包装计算机的语言之外的其他语言打包


默认情况下，MED-V 工作区支持计算机语言和英语中的字符。 若要为计算机上安装的另一种语言创建 MED-V 工作区，请在位于 MED-V 工作区名称后的 PowerShell 脚本（ps1）中指定**loc \ [locale \]** 。

若要使用除 MED-V 工作区包装计算机的默认语言之外的其他语言创建 MED-V 工作区程序包，请运行 MED-V 工作区包装器，然后根据你的区域设置所需修改输出脚本，以默认语言生成脚本。 该脚本位于打包期间指定的 MED-V 工作区输出目录中。 区域设置的名称位于 ""。以下目录中的 WXL 文件：

C:\\program files Files\\Microsoft 企业版桌面 Virtualization\\WindowsPowerShell\\Modules\\Microsoft.Medv.Administration.Commands.WorkspacePackager\\locale

## 创建 MED-V 工作区程序包


若要创建 MED-V 工作区程序包，请按照下列步骤操作：

****

1.  若要打开**Med-v 工作区包装程序**，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 工作区包装程序**"。

2.  在**Med-v 工作区包装**程序主面板上，单击 "**创建 Med-v 工作区程序包**"。

    将显示 "MED-V**创建 Med-v 工作区程序包" 向导**。 向导包含以下页面：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>程序包信息</strong></p></td>
    <td align="left"><p>为 MED-V 工作区指定一个名称，并选择保存 MED-V 工作区包文件的文件夹。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>选择 Windows XP 映像</strong></p></td>
    <td align="left"><p>指定准备好的 Windows XP 虚拟 PC 映像。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>首次设置</strong></p></td>
    <td align="left"><p>指定首次设置时的 MED-V 所遵循的设置过程。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>MED-V 消息</strong></p></td>
    <td align="left"><p>为最终用户首次设置时看到的帮助信息指定消息和可选 URL。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>命名计算机</strong></p></td>
    <td align="left"><p>指定如何命名 MED-V 虚拟机。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>从主机复制设置</strong></p></td>
    <td align="left"><p>指定如何定义 MED-V 工作区的设置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>启动和网络</strong></p></td>
    <td align="left"><p>指定启动 MED-V 工作区、网络和用户凭据的设置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>Web 重定向</strong></p></td>
    <td align="left"><p>指定要在 MED-V 工作区中重定向到 Internet Explorer 的 Url 的文本文件或 Url 列表。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>摘要</strong></p></td>
    <td align="left"><p>验证你的 MED-V 工作区设置，并开始构建你的 MED-V 工作区部署包。</p></td>
    </tr>
    </tbody>
    </table>



3.  在 "**程序包信息**" 页面上，输入 med-v 工作区的名称，并选择保存 med-v 工作区包文件的文件夹。

    **警告**  
    你必须命名 MED-V 工作区并指定一个文件夹以继续。



~~~
After you have finished, click **Next**.
~~~

4. 在 "**选择 WINDOWS XP 映像**" 页面上，指定准备好的 MED-V Windows XP 虚拟 PC 映像（.vhd 文件）的位置。

   **警告**  
   必须指定 Windows XP VHD 映像才能继续。



~~~
After you have finished, click **Next**.
~~~

5. 在 "**首次设置**" 页面上，选择是希望首次设置在参与还是无人参与时运行，以及是希望在共享计算机上的所有最终用户分别使用还是使用 med-v 工作区。

   如果你选择**无人参与安装，而不发送任何通知**，则在首次运行设置之前不会通知最终用户，并且首次设置期间，虚拟机不会显示给最终用户。 此外，向导的 " **Med-v 消息**" 页面是隐藏的，因为首次设置在完全无人参与的模式下运行时不需要任何消息。

   如果选择了 **"无人参与安装"，但在首次设置开始之前通知最终用户**，则会在首次运行设置之前通知最终用户。 但是，首次设置时，虚拟机不会显示给最终用户。

   如果最终用户在首次设置时必须输入信息，请选择 "**有人参与的设置**"。

   默认行为是**无人参与安装，但在首次开始设置之前通知最终用户**。

   **注意**  
   如果你创建了 Sysprep.inf 文件，以便最小化安装需要用户输入才能完成，则必须选择 "**有人参与设置**" 或 "首次设置时可能出现问题"。



~~~
You can also specify how a MED-V workspace is used on computers that are shared by multiple end users. You can decide that you want to create a unique MED-V workspace for each end user or that you want the MED-V workspace made available to all end users who share the computer. The default is that the MED-V workspace is unique for each end user.

**Important**  
We recommend that you disable the fast user switching feature in Windows if you configure the MED-V workspace to be accessed by all users on a shared computer. Problems can occur if an end user logs on by using the fast user switching feature in Windows when another user is still logged on.



**Tip**  
When you create a name mask for the MED-V workspace on the **Naming Computers** page, make sure that each virtual machine on a shared computer has a unique computer name.



You can also specify whether the MED-V workspace is added to the Administrators group or administrator credentials are managed outside MED-V. By default, the MED-V workspace is not automatically added to the Administrators group.

After you have finished, click **Next**.
~~~

6. 在 " **Med-v 消息**" 页面上，指定首次设置时最终用户看到的以下消息：

   -   第一次启动时，最终用户看到的消息。

   -   最终用户第一次设置失败或出现错误时所看到的消息。

   **注意**  
   如果您选择了 **"无人参与安装"，并且**在**首次设置**页面上没有任何通知，向导的 " **med-v 消息**" 页面将被隐藏。



~~~
You can also specify an optional URL location for help information that is provided to the end user when first time setup is running.

For example, the URL can point to an internal IT webpage with answers to questions such as "How long will this take and how will I know when it has completed?" or "What do you do if you get an error message?"

**Note**  
If you specify a URL, a link is shown during first time setup that points the end user to this help information. If you do not specify a URL, no link is provided.



After you have finished, click **Next**.
~~~

7. 在 "**命名计算机**" 页面上，可以指定由 med-v 或系统管理工具（如 Sysprep）管理计算机命名。 默认情况下，计算机命名由系统管理工具管理。

   如果你指定由 MED-V 管理计算机命名，请从下拉列表中选择预定义的计算机命名约定（掩码）。 将显示一个示例计算机名的预览，它基于你用于构建 MED-V 工作区程序包的计算机。

   如果选择其中一个自定义命名约定，则可以指定的字段限制为以下字符：

   -   前缀和后缀字段限制为字符 A-z、A-z、0-9 和特殊字符！ @ \ # $% ^ & （）-\ _ "{}。 和 ~。

   -   "主机名" 和 "用户名" 字段限制为0到9的数字。

   **重要提示**  
   计算机名必须是唯一的，并且最多只能有15个字符。 确定计算机命名方法时，请考虑拥有多台计算机或共享计算机的最终用户，避免使用可能导致网络冲突的计算机名称掩码。



~~~
**Caution**  
The computer name settings that you specify on this page override those specified in the Sysprep.inf answer file.



After you have finished, click **Next**.
~~~

8. 在 "**从主机复制设置**" 页面上，你可以选择以下设置来指定 med-v 工作区的配置方式：

   **注意**  
   在此页面上指定的、从主机复制到 MED-V 工作区的设置将替代在 Sysprep.inf 应答文件中指定的设置。



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Copy regional settings</strong></p></td>
<td align="left"><p>Select this check box to copy the regional settings from the host computer to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[RegionalSettings]
Language
SystemLocale
UserLocale
UserLocale_DefaultUser
InputLocale
InputLocale_DefaultUser
</code></pre></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy user settings</strong></p></td>
<td align="left"><p>Select this check box to copy certain user settings, such as user name and company name, from the host to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[UserData]
OrgName
FullName</code></pre>
<div class="alert">
<strong>Note</strong>  
<p>Personal settings, such as Internet browsing history, are not copied over to the MED-V workspace.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain name</strong></p></td>
<td align="left"><p>Select this check box to let the guest join the same domain as the host.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><div class="alert">
<strong>Important</strong>  
<p>The MED-V guest must be configured to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain organizational unit</strong></p></td>
<td align="left"><p>Select this check box to copy the domain organizational unit from the host computer to the MED-V workspace. This check box is only enabled if you select to copy the domain name from the host computer.</p></td>
</tr>
</tbody>
</table>



After you have finished, click **Next**.
~~~

9. 在 "**启动和网络**" 页面上，可以更改以下设置的默认行为：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>启动 MED-V-V 工作区</strong></p></td>
   <td align="left"><p>选择是在用户登录时启动 MED-V 工作区还是首次使用，或者让最终用户决定 MED-V 工作区何时启动。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>MED-V 工作区通过以下两种方式之一启动：最终用户登录时或首次启动需要 MED-V 的操作时，例如打开已发布的应用程序或输入需要重定向的 URL。</p>
   <p>你可以为最终用户定义此设置，也可以让最终用户控制 MED-V 的启动方式。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果你指定最终用户决定，其体验的默认行为是 MED-V 工作区在登录时启动。 用户可以通过右键单击通知区域中的 MED-V 图标并选择 "Med-v 用户设置" 来更改默认值 <strong> </strong> 。 如果为最终用户定义此设置，则无法更改 MED-V 的启动方式。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>网络</strong></p></td>
   <td align="left"><p><strong> </strong> <strong> </strong> 为您的网络设置选择 "共享" 或 "桥接"。 默认值为 " <strong> 共享" </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong>共享 </strong> - 的 med-v 工作区使用网络地址转换（NAT）将主机&#39;s IP 用于传出通信。</p>
   <p><strong>已桥接 </strong> - med-v 工作区有自己的网络地址，通常通过 DHCP 获得。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>存储凭据</strong></p></td>
   <td align="left"><p>选择是否要存储最终用户凭据。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>默认行为是禁用凭据存储，以便最终用户必须在每次登录时进行身份验证。</p>
   <div class="alert">
   <strong>重要提示</strong><br/><p>即使缓存最终用户的凭据可提供最佳用户体验，你也应该知道所涉及的风险。</p>
   <p>最终用户的域凭据以一种可还原的格式存储在 Windows 凭据管理器中。 因此，攻击者可以编写一个用于检索密码的程序，并可以获取用户凭据的访问权限。 您只能通过禁用终端用户凭据的存储来减少这种风险。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



~~~
After you have finished, click **Next**.
~~~

10. 在**Web 重定向**页面上，你可以在 med-v 工作区中输入、粘贴或导入已重定向到 Internet Explorer 的 url 的列表。 有关如何配置 URL 重定向信息的详细信息，请参阅[先决条件](#bkmk-prereq)。

   你还可以指定如何为最终用户配置 MED-V 工作区中的 Internet Explorer。 默认情况下，Internet 区域安全级别设置为 "高"。 此外，还会删除某些默认浏览功能，例如地址栏。 在 MED-V 工作区中，此 Internet Explorer 默认配置为最终用户提供更安全的浏览环境。

   **注意**  
   通过更改默认设置，你可以在 MED-V 工作区中自定义 Internet Explorer。 但是，请注意，如果你更改默认设置以降低安全性，你可以将组织暴露给较早版本的 Internet Explorer 中提供的安全风险。 有关详细信息，请参阅[Med-v 操作的安全最佳做法](security-best-practices-for-med-v-operations.md)。



~~~
After you have finished, click **Next**.
~~~

11. 在 "**摘要**" 页面上，您可以查看此 med-v 工作区的包装设置。 如果要更改任何设置，请单击 "**上一步**" 按钮以返回到相关页面。 查看完设置后，单击 "**创建**"。

   将打开 "**创建 Med-v 工作区程序包" 向导**的 "**完成**" 页面，显示程序包创建的进度。

   **注意**  
   MED-V 工作区程序包的创建过程可能需要几分钟才能完成，具体取决于指定 VHD 的大小。



~~~
If the MED-V workspace package is created successfully, the **Completion** page displays a list of the files that you created and their respective locations. The following is a list of the files that are created and their descriptions:

-   **setup.exe**—an installation program that you deploy and run on end-user computers to install the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.msi**—an installer file that you deploy to the end-user computers. The setup.exe file will run this file to install the MED-V workspaces.

-   **&lt;*vhd\_name*&gt;.medv**—a compressed VHD file that you deploy to the end-user computers. The setup.exe file uses it when it installs the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.reg**—the configuration settings that are installed when the setup.exe, &lt;*workspace\_name*&gt;.msi, and &lt;*vhd\_name*&gt;.medv files are deployed and setup.exe is run.

-   **&lt;*workspace\_name*&gt;.ps1**—a Windows PowerShell script that you can use to rebuild the registry file and re-build the MED-V workspace package.

    **Important**  
    Before deployment, you can edit configuration settings by updating the .ps1 file that has your preferred method of script editing, such as Windows PowerShell. After you change the .ps1 file, use that file to rebuild the MED-V workspace package that you deploy to your enterprise. For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).

    However, after the MED-V workspace is deployed, you must edit configuration settings through the registry. For a list and description of the configuration settings, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).
~~~



12. 单击 "**关闭**" 关闭打包向导并返回到**Med-v 工作区包装程序**。

现在，你的 MED-V 工作区程序包已准备好在部署之前进行测试。

## 相关主题


[使用 Windows PowerShell 配置高级设置](configuring-advanced-settings-by-using-windows-powershell.md)

[测试 MED-V 工作区程序包](testing-the-med-v-workspace-package.md)

[准备 MED-V 映像](prepare-a-med-v-image.md)









