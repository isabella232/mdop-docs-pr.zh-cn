---
title: Microsoft 高级组策略管理 4.0 分步指南
description: Microsoft 高级组策略管理 4.0 分步指南
author: dansimp
ms.assetid: dc6f9b16-b1d4-48f3-88bb-f29301f0131c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 567f9a8b14bc05a226b93947e6311ea93c0bf3b2
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910707"
---
# <a name="step-by-step-guide-for-microsoft-advanced-group-policy-management-40"></a>Microsoft 高级组策略管理 4.0 分步指南


本分步指南演示了使用组策略管理控制台 (GPMC) 和 Microsoft 高级组策略管理 (AGPM) 的组策略管理的高级技术。 AGPM 增加了 GPMC 的功能，从而提供：

-   用于将管理组策略对象 (GPO) 的权限委派给多个组策略管理员的标准角色，以及将访问权限委派给生产环境中的 GPO 的能力。

-   存档，使组策略管理员能够先脱机创建和修改 GPO，然后再将 GPO 部署到生产环境。

-   能够回滚到存档中任何早期版本的 GPO，并限制存储在存档中的版本数。

-   GPO 的签入和签出功能，以确保组策略管理员不会无意中覆盖彼此的工作。

-   能够搜索具有特定属性的 GPO 并筛选显示的 GPO 列表。

## <a name="agpm-scenario-overview"></a>AGPM 方案概述


对于此方案，你将为 AGPM 中每个角色使用单独的用户帐户，以演示如何在具有多个具有不同权限级别的组策略管理员的环境中管理组策略。 具体来说，您将执行以下任务：

-   使用 Domain Admins 组的成员帐户安装 AGPM Server 并将 AGPM 管理员角色分配给帐户或组。

-   使用将分配 AGPM 角色的帐户安装 AGPM 客户端。

-   使用具有 AGPM 管理员角色的帐户，通过向其他帐户分配角色来配置 AGPM 并委派对 GPO 的访问权限。

-   从具有"编辑者"角色的帐户，请求创建一个新 GPO，然后使用具有审批者角色的帐户批准该 GPO。 使用编辑器帐户将 GPO 从存档中签出，编辑 GPO，将 GPO 签入存档，然后请求部署。

-   使用具有审批者角色的帐户，查看 GPO，将其部署到生产环境。

-   使用具有编辑器角色的帐户，创建一个 GPO 模板，并使用它作为创建新 GPO 的起点。

-   使用具有审批者角色的帐户删除和还原 GPO。

![组策略对象开发过程。](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <a name="requirements"></a>要求


要安装 AGPM 的计算机必须满足以下要求，并且必须创建用于此方案的帐户。

**注意**  
如果已安装 AGPM 2.5，并且正在从 Windows Server® 2003 升级到 Windows Server 2008 R2 或 Windows Server 2008， 或者正在从未安装 Service Pack 1 (SP1) 的 Windows 7 或 Windows Vista ® Service Pack 从 Windows Vista 升级，则必须升级操作系统，然后才能升级到 AGPM 4.0。

如果已安装 AGPM 3.0，则升级到 AGPM 4.0 之前，不需要升级操作系统

 

在同时包含较新的和较旧的操作系统的混合环境中，功能存在一些限制，如下表所示。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">运行 AGPM Server 4.0 的操作系统</th>
<th align="left">运行 AGPM Client 4.0 的操作系统</th>
<th align="left">AGPM 4.0 支持的状态</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsServer 2008 R2 或 Windows 7</p></td>
<td align="left"><p>WindowsServer 2008 R2 或 Windows 7</p></td>
<td align="left"><p>支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer 2008 R2 或 Windows 7</p></td>
<td align="left"><p>WindowsServer 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>支持但无法编辑仅存在于 Windows Server 2008 R2 或 Windows 7 中的策略设置或首选项</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WindowsServer 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>WindowsServer 2008 R2 或 Windows 7</p></td>
<td align="left"><p>不支持</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>WindowsServer 2008 或 Windows Vista SP1</p></td>
<td align="left"><p>支持，但不能报告或编辑仅存在于 Windows Server 2008 R2 或 Windows 7 中的策略设置或首选项</p></td>
</tr>
</tbody>
</table>

 

### <a name="agpm-server-requirements"></a>AGPM 服务器要求

AGPM Server 4.0 需要远程服务器管理工具 (RSAT) Windows 或安装了 SP1 和 GPMC 的 Windows Server 2008 R2、Windows Server 2008、Windows 7 和 GPMC。 支持 32 位和 64 位版本。

在安装 AGPM Server 之前，您必须是 Domain Admins 组的成员，并且除非另有说明Windows以下组功能：

-   GPMC

    -   WindowsServer 2008 R2 或 Windows Server 2008：如果 GPMC 不存在，则 AGPM 会自动安装它。

    -   Windows 7：必须先从 RSAT 安装 GPMC，然后才能安装 AGPM。 有关详细信息，请参阅 Remote [Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280) 。

    -   WindowsVista SP1：必须先从 RSAT 安装 GPMC，然后才能安装 AGPM。 有关详细信息，请参阅 Remote [Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179) 。

-   版本.NET Framework 3.5 或更高版本

    -   Windows服务器 2008 R2 或 Windows 7：如果 .NET Framework 3.5 或更高版本不存在，AGPM 将自动安装 .NET Framework 3.5。

    -   WindowsServer 2008 或 Windows Vista SP1：必须先安装 .NET Framework 3.5 或更高版本，然后才能安装 AGPM。

AGPM Windows需要以下功能，并且这些功能将在不存在时自动安装：

-   WCF 激活;非 HTTP 激活

-   Windows Process Activation Service

    -   进程模型

    -   .NET 环境

    -   配置 API

### <a name="agpm-client-requirements"></a>AGPM 客户端要求

AGPM Client 4.0 需要 RSAT 中的 Windows Server 2008 R2、Windows Server 2008、Windows 7 和 GPMC，或者从 RSAT 安装了 SP1 和 GPMC 的 Windows Vista。 支持 32 位和 64 位版本。 AGPM 客户端可以安装在运行 AGPM Server 的计算机上。

AGPM 客户端Windows以下功能，除非另有说明，否则会自动安装这些功能（如果不存在）：

-   GPMC

    -   WindowsServer 2008 R2 或 Windows Server 2008：如果 GPMC 不存在，则 AGPM 会自动安装它。

    -   Windows 7：必须先从 RSAT 安装 GPMC，然后才能安装 AGPM。 有关详细信息，请参阅 Remote [Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280) 。

    -   WindowsVista SP1：必须先从 RSAT 安装 GPMC，然后才能安装 AGPM。 有关详细信息，请参阅 Remote [Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179) 。

-   3.0 .NET Framework 3.0 或更高版本

    -   Windows服务器 2008 R2 或 Windows 7：如果 .NET Framework 3.0 或更高版本不存在，AGPM 将自动安装 .NET Framework 3.5。

    -   WindowsServer 2008 或 Windows Vista SP1：如果 .NET Framework 3.0 或更高版本不存在，AGPM 将自动安装 .NET Framework 3.0。

### <a name="scenario-requirements"></a>方案要求

在开始此方案之前，请创建四个用户帐户。 在此方案中，你将为其中每个帐户分配以下 AGPM 角色之一：AGPM 管理员 (完全控制) 、审批者、编辑者和审阅者。 这些帐户必须能够发送和接收电子邮件。 将 **链接 GPO** 权限分配给具有 AGPM 管理员、审批者以及可以选择 (编辑) 的帐户。

**注意**  
**默认情况下，** 将链接 GPO 权限分配给域管理员Enterprise管理员的成员。 若要将**链接 GPO**权限分配给其他用户或组 (例如具有 AGPM 管理员或审批者) 角色的帐户，请单击域的节点，然后单击"委派"选项卡，选择"链接**** GPO"，单击 **"添加**"，然后选择要为其分配权限的用户或组。 ****

 

## <a name="steps-for-installing-and-configuring-agpm"></a>安装和配置 AGPM 的步骤


必须完成以下步骤来安装和配置 AGPM。

[步骤 1：安装 AGPM 服务器](#bkmk-config1)

[步骤 2：安装 AGPM 客户端](#bkmk-config2)

[步骤 3：配置 AGPM 服务器连接](#bkmk-config3)

[步骤 4：配置电子邮件通知](#bkmk-config4)

[步骤 5：委派访问权限](#bkmk-config5)

### <a name="step-1-install-agpm-server"></a><a href="" id="bkmk-config1"></a>步骤 1：安装 AGPM 服务器

在此步骤中，在将运行 AGPM 服务的成员服务器或域控制器上安装 AGPM Server，然后配置存档。 所有 AGPM 操作都通过此 Windows 服务进行管理，并且使用该服务的凭据执行。 AGPM 服务器管理的存档可以承载于该服务器上或同一林中的另一台服务器上。

**在将承载 AGPM 服务的计算机上安装 AGPM Server**

1.  使用 Domain Admins 组的成员帐户登录。

2.  启动 Microsoft 桌面优化包 CD 并按照屏幕上的说明选择"高级**组策略管理 - 服务器"。**

3.  在"**欢迎"** 对话框中，单击"下一**步"。**

4.  在 **"Microsoft 软件许可条款**"对话框中，接受这些条款，然后单击"下一步 **"。**

5.  在" **应用程序路径** "对话框中，选择要安装 AGPM 服务器的位置。 安装 AGPM Server 的计算机将承载 AGPM 服务并管理存档。 单击“下一步”****。

6.  在 **"存档路径** "对话框中，选择存档相对于 AGPM 服务器的位置。 存档路径可以指向 AGPM 服务器或其他位置中的文件夹。 但是，你应该选择一个有足够的空间来存储此 AGPM 服务器管理的所有 GPO 和历史记录数据的位置。 单击“下一步”****。

7.  在 **"AGPM 服务帐户**"对话框中，选择将运行 AGPM 服务的服务帐户，然后单击"下一步 **"。**

    此帐户必须是 Domain Admins 组的成员，或者对于最小特权配置，此帐户必须是 AGPM 服务器管理的每个域中的以下组的成员：

    -   组策略创建者所有者

    -   备份运算符

    此外，此帐户需要以下文件夹的完全控制权限：

    -   AGPM 存档文件夹，如果 AGPM Server 安装在本地驱动器上，将在安装 AGPM Server 期间自动授予该权限。

    -   本地系统临时文件夹，通常为 %windir%\\temp。

8.  在" **存档所有者** "对话框中，选择一个帐户或组，将 AGPM 管理员角色分配给 (完全控制) 组。 AGPM 管理员可以将 AGPM 角色和权限分配给其他组策略管理员，以便以后可以将 AGPM 管理员的角色分配给其他组策略管理员。 对于此方案，选择要在 AGPM 管理员角色中服务的帐户。 单击“下一步”****。

9.  在" **端口配置** "对话框中，键入 AGPM 服务应侦听的端口。 不要清除" **向防火墙添加** 端口例外"复选框，除非您手动配置端口例外或使用规则配置端口例外。 单击“下一步”****。

10. 在" **语言** "对话框中，选择要为 AGPM Server 安装的一个或多个显示语言。

11. 单击 **"安装**"，然后单击" **完成** "退出安装向导。

    **注意**  
    请勿通过操作系统中的管理工具和服务更改 AGPM **** **服务的**设置。 这样做可能会阻止 AGPM 服务启动。 若要了解如何更改服务设置，请参阅高级组策略管理帮助。

     

### <a name="step-2-install-agpm-client"></a><a href="" id="bkmk-config2"></a>步骤 2：安装 AGPM 客户端

每个组策略管理员（任何创建、编辑、部署、审阅或删除 GPO 的人）都必须在用于管理 GPO 的计算机上安装 AGPM 客户端。 "更改控制"节点（用于执行许多 GPO 管理任务）仅在安装 AGPM 客户端时显示在组策略管理控制台中。 对于此方案，您至少在一台计算机中安装 AGPM 客户端。 无需在不执行组策略管理的最终用户计算机上安装 AGPM 客户端。

**在组策略管理员的计算机上安装 AGPM 客户端**

1.  启动 Microsoft 桌面优化包 CD 并按照屏幕上的说明选择"高级**组策略管理 - 客户端"。**

2.  在"**欢迎"** 对话框中，单击"下一**步"。**

3.  在 **"Microsoft 软件许可条款**"对话框中，接受这些条款，然后单击"下一步 **"。**

4.  在" **应用程序路径** "对话框中，选择要安装 AGPM 客户端的位置。 单击“下一步”****。

5.  在 **"AGPM 服务器** "对话框中，键入 AGPM 服务器的 DNS 名称或 IP 地址以及要连接到的端口。 AGPM 服务的默认端口为 4600。 不要清除" **允许 Microsoft 管理** 控制台通过防火墙"复选框，除非您手动配置端口例外或使用规则配置端口例外。 单击“下一步”****。

6.  在" **语言** "对话框中，选择要为 AGPM 客户端安装的一个或多个显示语言。

7.  单击 **"安装**"，然后单击" **完成** "退出安装向导。

### <a name="step-3-configure-an-agpm-server-connection"></a><a href="" id="bkmk-config3"></a>步骤 3：配置 AGPM 服务器连接

AGPM 将每个受控组策略对象 (GPO) 的所有版本（即 AGPM 提供变更控制的每个 GPO）存储在中央存档中。 这使组策略管理员能够脱机查看和更改 GPO，而不会影响每个 GPO 的已部署版本。

在此步骤中，配置 AGPM 服务器连接，并确保所有组策略管理员都连接到同一 AGPM 服务器。  (若要了解如何配置多个 AGPM 服务器，请参阅高级组策略管理帮助) 

**配置所有组策略管理员的 AGPM Server 连接**

1.  在已安装 AGPM 客户端的计算机上，使用选择为存档所有者的用户帐户登录。 此用户具有 AGPM 管理员角色 (完全控制) 。

2.  单击 **"开始**"， **指向"管理工具**"，然后单击" **组策略管理** "以打开 GPMC。

3.  编辑应用于所有组策略管理员的 GPO。

4.  在组**策略管理编辑器**窗口中，双击用户配置、**** 策略、管理**** 模板、Windows**组件和** **AGPM。** ****

5.  在详细信息窗格中，双击**AGPM：指定默认 AGPM Server (所有域) 。 **

6.  在"**属性**"窗口中，**** 选择"已启用"，然后键入 DNS 名称或 IP 地址和端口**** (例如，server.contoso.com:4600) 存档服务器的域名。 默认情况下，AGPM 服务使用端口 4600。

7.  单击 **"确定**"，然后关闭 **"组策略管理编辑器"** 窗口。 更新组策略时，将配置每个组策略管理员的 AGPM Server 连接。

### <a name="step-4-configure-e-mail-notification"></a><a href="" id="bkmk-config4"></a>步骤 4：配置电子邮件通知

作为 AGPM 管理员 (完全控制) ，您可以指定审批者和 AGPM 管理员的电子邮件地址，当编辑器尝试创建、部署或删除 GPO 时，会向这些管理员发送包含请求的电子邮件。 您还可以确定发送这些邮件的别名。

**为 AGPM 配置电子邮件通知**

1.  在 **组策略管理编辑器中** ，导航到 **"更改控制"** 文件夹 

2.  在详细信息窗格中，单击" **域委派"** 选项卡。

3.  在 **"收件人电子邮件地址"** 字段中，键入应发送通知的 AGPM 的电子邮件别名。

4.  在 **"收件人电子邮件地址"** 字段中，键入要为其分配审批者角色的用户帐户的电子邮件地址。

5.  在 **"SMTP 服务器"** 字段中，键入有效的 SMTP 邮件服务器。

6.  在 **"用户名"** 和****"密码"字段中，键入有权访问 SMTP 服务的用户的凭据。 单击**应用**。

### <a name="step-5-delegate-access"></a><a href="" id="bkmk-config5"></a>步骤 5：委派访问权限

作为 AGPM 管理员 (完全控制) ，你可以委派对 GPO 的域级访问权限，并将角色分配给每个组策略管理员的帐户。

**注意**  
还可以在 GPO 级别而不是域级别委派访问权限。 有关详细信息，请参阅高级组策略管理帮助。

 

**重要提示**  
应限制组策略创建者所有者组的成员身份，以便它不能用于避开 AGPM 对 GPO 的访问管理。  (在组策略管理控制台中，单击要管理**** GPO 的林和域中的组策略对象，单击"委派"，然后**** 配置设置以满足组织的需要。) ****

 

**将访问权限委派给整个域中的所有 GPO**

1.  在"**域委派"** 选项卡上，**** 单击"添加"按钮，选择组策略管理员的用户帐户以充当审批者，然后单击"确定 **"。**

2.  在"**添加组或用户**"对话框中，选择"**审批者**"角色以将此角色分配给帐户，然后单击"确定 **"。**  (此角色包括审阅者角色。) 

3.  单击"**添加**"按钮，选择组策略管理员的用户帐户以用作编辑器，然后单击"确定 **"。**

4.  在"**添加组或用户**"对话框中，选择 **"** 编辑器"角色以将此角色分配给帐户，然后单击"确定 **"。**  (此角色包括审阅者角色。) 

5.  单击"**添加**"按钮，选择组策略管理员的用户帐户作为审阅者，然后单击"确定 **"。**

6.  在 **"添加组或用户** "对话框中，选择 **"审阅者** "角色以仅将此角色分配给帐户。

## <a name="steps-for-managing-gpos"></a>管理 GPO 的步骤


你必须完成以下步骤，以使用 AGPM 创建、编辑、查看和部署 GPO。 此外，你还将创建模板、删除 GPO 和还原已删除的 GPO。

[步骤 1：创建 GPO](#bkmk-manage1)

[步骤 2：编辑 GPO](#bkmk-manage2)

[步骤 3：查看和部署 GPO](#bkmk-manage3)

[步骤 4：使用模板创建 GPO](#bkmk-manage4)

[步骤 5：删除和还原 GPO](#bkmk-manage5)

### <a name="step-1-create-a-gpo"></a><a href="" id="bkmk-manage1"></a>步骤 1：创建 GPO

在具有多个组策略管理员的环境中，具有编辑器角色的管理员可以请求新建 GPO。 但是，该请求必须由具有审批者角色的人批准。

在此步骤中，使用具有编辑器角色的帐户请求创建一个新的 GPO。 使用具有审批者角色的帐户，可批准此请求以创建 GPO。

**请求通过 AGPM 创建和管理新 GPO**

1.  在已安装 AGPM 客户端的计算机上，使用在 AGPM 中分配了编辑器角色的用户帐户登录。

2.  在组**策略管理控制台树**中，单击**** 要管理 GPO 的林和域中的"更改控制"。

3.  右键单击"**更改控制"** 节点，然后单击"**新建受控 GPO"。**

4.  在" **新建受控 GPO"** 对话框中：

    1.  若要接收请求的副本，在"抄送"字段中键入 **您的电子邮件地址** 。

    2.  键入 **MyGPO** 作为新 GPO 的名称。

    3.  键入新 GPO 的注释。

    4.  单击 **"实时** 创建"，以便新 GPO 在批准后立即部署到生产环境。 单击**提交**。

5.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 新 GPO 显示在"待定 **"选项卡** 上。

**批准创建 GPO 的待定请求**

1.  在已安装 AGPM 客户端的计算机上，使用在 AGPM 中担任审批者角色的用户帐户登录。

2.  打开帐户的电子邮件收件箱，并请注意，您收到了来自 AGPM 别名的电子邮件以及编辑器创建 GPO 的请求。

3.  在组**策略管理控制台树**中，单击**** 要管理 GPO 的林和域中的"更改控制"。

4.  在" **内容"** 选项卡上，单击" **挂起** "选项卡以显示挂起的 GPO。

5.  右键单击 **"MyGPO"，** 然后单击"批准 **"。**

6.  单击 **"是** "确认批准，将 GPO 移动到 **"受控"** 选项卡。

### <a name="step-2-edit-a-gpo"></a><a href="" id="bkmk-manage2"></a>步骤 2：编辑 GPO

可以使用 GPO 配置计算机或用户设置，并部署到多台计算机或用户。 在此步骤中，使用具有编辑器角色的帐户从存档中签出 GPO、脱机编辑 GPO、将编辑的 GPO 签入存档，以及请求将 GPO 部署到生产环境。 对于此方案，在 GPO 中配置一个设置，要求密码至少为八个字符长。

**从存档中签出 GPO 进行编辑**

1.  在已安装 AGPM 客户端的计算机上，使用在 AGPM 中担任编辑器角色的用户帐户登录。

2.  在组**策略管理控制台树**中，单击**** 要管理 GPO 的林和域中的"更改控制"。

3.  在详细信息 **窗格的"** 内容"选项卡上， **单击"受控** "选项卡以显示受控 GPO。

4.  右键单击 **"MyGPO"，** 然后单击"**签出"。**

5.  键入要签出 GPO 时在 GPO 历史记录中显示的注释，然后单击"确定 **"。**

6.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 在"**受控**"选项卡上，GPO 的状态标识为 **"已签出"。**

**脱机编辑 GPO 并配置最小密码长度**

1.  在"**受控"** 选项卡上，右键单击 **"MyGPO"，** 然后单击"编辑"打开组策略管理**编辑器**窗口并更改 GPO 的脱机副本。 **** 对于此方案，请配置最小密码长度：

    1.  在 **"计算机配置"** 下，**** 双击"策略**Windows 设置、** 安全**设置、****帐户**策略和**密码策略**。

    2.  在详细信息窗格中，双击"最小**密码长度"。**

    3.  在"属性"窗口中，选中"**定义此策略**设置"复选框，将字符数设置为**8，** 然后单击"确定 **"。**

2.  关闭组 **策略管理编辑器** 窗口。

**将 GPO 签入存档**

1.  在"**受控"** 选项卡上，右键单击 **"MyGPO"，** 然后单击"**签入"。**

2.  键入注释，然后单击"确定 **"。**

3.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 在"**受控**"选项卡上，GPO 的状态标识为 **"已签入"。**

**请求将 GPO 部署到生产环境**

1.  在"**受控"** 选项卡上，右键单击 **"MyGPO"，** 然后单击"部署 **"。**

2.  由于此帐户不是审批者或 AGPM 管理员，因此您必须提交部署请求。 若要接收请求的副本，在"抄送"字段中键入 **您的电子邮件地址** 。 键入要显示在 GPO 历史记录中的注释，然后单击"提交 **"。**

3.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 **MyGPO** 显示在"待定"选项卡上的 GPO **列表上** 。

### <a name="step-3-review-and-deploy-a-gpo"></a><a href="" id="bkmk-manage3"></a>步骤 3：查看和部署 GPO

在此步骤中，您将充当审批者，创建报告并分析 GPO 中的设置和更改以确定您是否应批准它们。 评估 GPO 后，将其部署到生产环境，将 GPO 链接到使用 OU (域) 。 当刷新该域或 OU 中的计算机的组策略时，GPO 生效。

**查看 GPO 中的设置**

1. 在已安装 AGPM 客户端的计算机上，使用在 AGPM 中分配有审批者角色的用户帐户登录。 具有审阅者角色（包含在所有其他角色中）的任何组策略管理员都可以查看 GPO 中的设置。

2. 打开帐户的电子邮件收件箱，并注意你已收到来自 AGPM 别名的电子邮件以及编辑器请求部署 GPO。

3. 在组**策略管理控制台树**中，单击**** 要管理 GPO 的林和域中的"更改控制"。

4. 在详细信息 **窗格中的"** 内容"选项卡上，单击"挂起 **"** 选项卡。

5. 双击 **MyGPO** 以显示其历史记录。

6. 查看最新版本的 MyGPO 中的设置：

   1.  在 **"历史记录**"窗口中，右键单击具有最新时间戳的 GPO 版本，单击 **"设置"，** 然后单击 **"HTML**报告"以显示 GPO 设置的摘要。

   2.  在 Web 浏览器中，单击 **"显示全部** "以显示 GPO 中的所有设置。 关闭浏览器。

7. 将 MyGPO 的最新版本与签入存档的第一个版本进行比较：

   1. 在" **历史记录** "窗口中，单击具有最新时间戳的 GPO 版本。 按 Ctrl，然后单击计算机版本不是 **\\***的最**** 旧的 GPO 版本。

   2. 单击" **差异"** 按钮。 " **帐户策略/密码策略"** 部分以绿色突出显示，前面 **有 \[+\]**。 这表示仅在 GPO 的后一版本中配置该设置。

   3. 单击 **"帐户策略/密码策略"。** " **最小密码长度** "设置也以绿色突出显示，前面有 **\[+\]**，表示仅在 GPO 的后一版本中配置此设置。

   4. 关闭 Web 浏览器。

**将 GPO 部署到生产环境**

1.  在"**挂起"** 选项卡上，右键单击 **"MyGPO"，** 然后单击"批准 **"。**

2.  键入要包括在 GPO 历史记录中的注释。

3.  单击**是**。 当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 GPO 部署到生产环境。

**将 GPO 链接到域或组织单位**

1.  在 GPMC 中，右键单击要应用所配置的 GPO 的域或组织单位 (OU) ，然后单击"链接现有**GPO"。**

2.  在"**选择 GPO"** 对话框中，单击 **"MyGPO"，** 然后单击"确定 **"。**

### <a name="step-4-use-a-template-to-create-a-gpo"></a><a href="" id="bkmk-manage4"></a>步骤 4：使用模板创建 GPO

在此步骤中，使用具有编辑器角色的帐户来创建和使用模板。 该模板是 GPO 的静态版本，用作创建新 GPO 的起点。 虽然无法编辑模板，但可以基于模板创建新的 GPO。 模板对于快速创建包含多个相同策略设置的 GPO 非常有用。

**基于现有 GPO 创建模板**

1.  在已安装 AGPM 客户端的计算机上，使用分配了 AGPM 中的编辑器角色的用户帐户登录。

2.  在组**策略管理控制台树**中，单击**** 要管理 GPO 的林和域中的"更改控制"。

3.  在详细信息 **窗格的"** 内容"选项卡上，单击"受控 **"** 选项卡。

4.  右键单击 **"MyGPO"，** 然后单击"另 **存** 为模板"以创建包含 MyGPO 中当前的所有设置的模板。

5.  键入**MyTemplate**作为模板的名称和注释，**然后单击确定。**

6.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 新模板显示在"模板 **"选项卡** 上。

**请求通过 AGPM 创建和管理新 GPO**

1.  单击" **受控"** 选项卡。

2.  右键单击"**更改控制"** 节点，然后单击"**新建受控 GPO"。**

3.  在" **新建受控 GPO"** 对话框中：

    1.  若要接收请求的副本，在"抄送"字段中键入 **您的电子邮件地址** 。

    2.  键入 **MyOtherGPO** 作为新 GPO 的名称。

    3.  键入新 GPO 的注释。

    4.  单击 **"实时** 创建"，以便新 GPO 在批准后立即部署到生产环境。

    5.  对于 **"从 GPO 模板"，** 选择 **"MyTemplate"。** 单击**提交**。

4.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 新 GPO 显示在"待定 **"选项卡** 上。

使用分配了审批者角色的帐户批准待处理的请求以创建 GPO，就像在步骤 [1：创建 GPO 中所做的一样](#bkmk-manage1)。 MyTemplate 包含你在 MyGPO 中配置的所有设置。 由于 MyOtherGPO 是使用 MyTemplate 创建的，因此它最初包含创建 MyTemplate 时 MyGPO 包含的所有设置。 可以通过生成差异报告来将 MyOtherGPO 与 MyTemplate 进行比较来确认这一点。

**从存档中签出 GPO 进行编辑**

1.  在已安装 AGPM 客户端的计算机上，使用分配了 AGPM 中的编辑器角色的用户帐户登录。

2.  右键单击 **MyOtherGPO**，然后单击 **签出**。

3.  键入要签出 GPO 时在 GPO 历史记录中显示的注释，然后单击"确定 **"。**

4.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 在"**受控**"选项卡上，GPO 的状态标识为 **"已签出"。**

**脱机编辑 GPO 并配置帐户锁定持续时间**

1.  在"**受控"** 选项卡上，右键单击 **"MyOtherGPO"，** 然后单击"编辑"打开组策略管理**编辑器**窗口并更改 GPO 的脱机副本。 **** 对于此方案，请配置最小密码长度：

    1.  在**计算机配置下******，双击策略****、Windows 设置、设置、**帐户**策略**** 和**帐户锁定策略**。

    2.  在详细信息窗格中，双击"帐户**锁定持续时间"。**

    3.  在"属性"窗口中，选中"**定义此策略设置**"，将持续时间设置为**30**分钟，然后单击"确定 **"。**

2.  关闭组 **策略管理编辑器** 窗口。

像在步骤 [2：编辑 GPO](#bkmk-manage2)中对 MyGPO 所做的一样，将 MyOtherGPO 签入存档并请求部署。 可以使用差异报告将 MyOtherGPO 与 MyGPO 或 MyTemplate 进行比较。 包括 AGPM 管理员 \[Full Control\]、Approver、Editor 或 Reviewer (审阅者角色的任何帐户) 报告。

**将 GPO 与其他 GPO 和模板进行比较**

1.  若要比较 MyGPO 和 MyOtherGPO：

    1.  在"受控 **"选项卡**上，单击 **"MyGPO"。** 按 Ctrl，然后单击 **MyOtherGPO**。

    2.  右键单击 **"MyOtherGPO"，** 指向 **"差异**"，然后单击 **"HTML 报告"。**

2.  若要比较 MyOtherGPO 和 MyTemplate：

    1.  在"受控 **"选项卡**上，单击 **"MyOtherGPO"。**

    2.  右键单击 **"MyOtherGPO"，** 指向 **"差异**"，然后单击"模板 **"。**

    3.  选择 **"MyTemplate"** 和 **"HTML 报告**"，然后单击"确定 **"。**

### <a name="step-5-delete-and-restore-a-gpo"></a><a href="" id="bkmk-manage5"></a>步骤 5：删除和还原 GPO

在此步骤中，您将充当删除 GPO 的审批者。

**删除 GPO**

1.  在已安装 AGPM 客户端的计算机上，使用分配了审批者角色的用户帐户登录。

2.  在组**策略管理控制台树**中，单击**** 要管理 GPO 的林和域中的"更改控制"。

3.  在" **内容"** 选项卡上，单击" **受控** "选项卡以显示受控 GPO。

4.  右键单击 **"MyGPO"，** 然后单击"删除 **"。** 单击 **"从存档和生产中删除 GPO"** 以删除存档中的版本和生产环境中部署的 GPO 版本。

5.  键入要显示在 GPO 审核跟踪中的注释，然后单击"确定 **"。**

6.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 GPO 从"受控"**** 选项卡中删除，并显示在"回收**** 站"选项卡上，可在其中还原或销毁 GPO。

有时，你可能会在删除 GPO 后发现它仍然需要。 在此步骤中，您将充当审批者来还原已删除的 GPO。

**还原已删除的 GPO**

1.  在" **内容"** 选项卡上，单击 **"回收** 站"选项卡以显示已删除的 GPO。

2.  右键单击 **"MyGPO"，** 然后单击"还原 **"。**

3.  键入要显示在 GPO 历史记录中的注释，然后单击"确定 **"。**

4.  当 **AGPM 进度窗口** 指示整个进度已完成时， **单击关闭**。 GPO 从"回收站 **"选项卡中删除** ，并显示在"受控 **"选项卡** 上。

    **注意**  
    将 GPO 还原到存档不会自动将其重新部署到生产环境。 若要将 GPO 返回到生产环境，请部署 GPO，如步骤 [3：查看和部署 GPO 一样](#bkmk-manage3)。

     

编辑和部署 GPO 后，你可能会发现最近对 GPO 所做的更改导致出现问题。 在此步骤中，您将充当要回滚到早期版本的 GPO 的审批者。 你可以回滚到 GPO 历史记录中的任意版本。 可以使用注释和标签来标识已知良好的版本以及进行特定更改时。

**回滚到早期版本的 GPO**

1.  在" **内容"** 选项卡上，单击" **受控** "选项卡以显示受控 GPO。

2.  双击 **MyGPO** 以显示其历史记录。

3.  右键单击要部署的版本，单击部署 **，然后单击****是。**

4.  当"**进度"** 窗口指示整个进度已完成时，单击"关闭 **"。** 在"**历史记录"** 窗口中，单击"关闭 **"。**

    **注意**  
    若要验证重新部署的版本是预期版本，请检查两个版本的差异报告。 在**GPO**的"历史记录"窗口中，选择两个版本，右键单击它们，指向"**差异**"，然后单击 **"HTML 报告**"或 **"XML 报告"。**

     

 

 





