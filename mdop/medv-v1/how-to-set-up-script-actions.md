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
# <span data-ttu-id="0e7b2-103">如何设置脚本操作</span><span class="sxs-lookup"><span data-stu-id="0e7b2-103">How to Set Up Script Actions</span></span>


<span data-ttu-id="0e7b2-104">脚本操作编辑器允许管理员创建在 MED-V 工作区设置过程中要执行的操作，并定义执行顺序。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-104">The script actions editor allows the administrator to create actions to be performed during MED-V workspace setup, as well as to define the order in which they are performed.</span></span>

<span data-ttu-id="0e7b2-105">下面是可添加到域设置脚本的操作列表：</span><span class="sxs-lookup"><span data-stu-id="0e7b2-105">The following is a list of actions that can be added to the domain setup script:</span></span>

-   <span data-ttu-id="0e7b2-106">**重启 windows**—重新启动 windows。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-106">**Restart Windows**—Restart Windows.</span></span>

-   <span data-ttu-id="0e7b2-107">**加入域**-如果加入域，请包含此操作并配置用户名、密码、完全限定的域名、NetBIOS 域名和组织单位（可选）。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-107">**Join Domain**—If joining a domain, include this action and configure the user name, password, fully qualified domain name, NetBIOS domain name, and organization unit (optional).</span></span>

-   <span data-ttu-id="0e7b2-108">**检查连接**-配置服务器以连接到并验证 med-v 工作区是否可以连接到网络资源（如域服务器）。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-108">**Check Connectivity**—Configure a server to connect to and verify that the MED-V workspace can connect to a network resource (such as the domain server).</span></span>

-   <span data-ttu-id="0e7b2-109">**命令行**-在 med-v 工作区中配置脚本，并输入包含脚本路径和脚本参数的命令行。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-109">**Command Line**—Configure a script in the MED-V workspace, and enter a command line that includes the path of the script and the script arguments.</span></span>

-   <span data-ttu-id="0e7b2-110">**重命名计算机**—基于已定义的设置重命名虚拟机计算机。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-110">**Rename Computer**—Rename the virtual machine computer based on the defined settings.</span></span>

-   <span data-ttu-id="0e7b2-111">**禁用自动登录**—禁用 Windows 自动登录。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-111">**Disable Auto-Logon**—Disable Windows Auto-Logon.</span></span> <span data-ttu-id="0e7b2-112">应在将计算机添加到域的脚本结束时添加此操作。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-112">This action should be added at the end of scripts that add the computer to the domain.</span></span>

## <a href="" id="how-to-set-up-script-actions-"></a><span data-ttu-id="0e7b2-113">如何设置脚本操作</span><span class="sxs-lookup"><span data-stu-id="0e7b2-113">How to Set Up Script Actions</span></span>


**<span data-ttu-id="0e7b2-114">设置脚本操作</span><span class="sxs-lookup"><span data-stu-id="0e7b2-114">To set up script actions</span></span>**

1.  <span data-ttu-id="0e7b2-115">在 " **VM 设置**" 选项卡上，单击 "**脚本编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-115">On the **VM Setup** tab, click **Script Editor**.</span></span>

2.  <span data-ttu-id="0e7b2-116">在 "**脚本操作**" 对话框中，单击 "**添加**"，然后在子菜单上单击所需的操作。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-116">In the **Script Actions** dialog box, click **Add**, and on the submenu, click the desired actions.</span></span>

3.  <span data-ttu-id="0e7b2-117">按下表中所述配置操作。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-117">Configure the actions as described in the following tables.</span></span>

    <span data-ttu-id="0e7b2-118">**注意** 
    在 " **VM 设置**" 选项卡中配置 "**重命名计算机**"。有关详细信息，请参阅[如何配置 VM 计算机名称模式属性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-118">**Note**
**Rename Computer** is configured in the **VM Settings** tab. For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

     

~~~
**Note**  
To rename a computer, Windows must be restarted. It is recommended to add a Restart Windows action following a Rename Computer action.
~~~



4. <span data-ttu-id="0e7b2-119">通过选择操作并单击 "**向上**" 或 "**向下**" 来设置操作顺序。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-119">Set the order of the actions by selecting an action and clicking **Up** or **Down**.</span></span>

5. <span data-ttu-id="0e7b2-120">单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-120">Click **OK**.</span></span>

**<span data-ttu-id="0e7b2-121">注意</span><span class="sxs-lookup"><span data-stu-id="0e7b2-121">Note</span></span>**  
<span data-ttu-id="0e7b2-122">运行加入域脚本时，要使脚本正常工作，登录到 MED-V 工作区虚拟机的用户必须具有本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-122">When running the Join Domain script, for the script to work, the user logged into the MED-V workspace virtual machine must have local administrator rights.</span></span>



**<span data-ttu-id="0e7b2-123">注意</span><span class="sxs-lookup"><span data-stu-id="0e7b2-123">Note</span></span>**  
<span data-ttu-id="0e7b2-124">运行 "禁用自动登录脚本" 时，建议在初始设置完成后禁用用于自动登录的本地来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-124">When running the Disable Auto-Logon script, it is recommended to disable the local guest account used for the auto-logon once the initial setup is complete.</span></span>



### <a href="" id="bkmk-joindomainproperties"></a>

**<span data-ttu-id="0e7b2-125">加入域属性</span><span class="sxs-lookup"><span data-stu-id="0e7b2-125">Join Domain Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e7b2-126">属性</span><span class="sxs-lookup"><span data-stu-id="0e7b2-126">Property</span></span></th>
<th align="left"><span data-ttu-id="0e7b2-127">描述</span><span class="sxs-lookup"><span data-stu-id="0e7b2-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-128">将 VM 加入域时要使用的凭据</span><span class="sxs-lookup"><span data-stu-id="0e7b2-128">Credentials to use when joining the VM to the domain</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-129">选择以下凭据之一以在将 VM 加入到域时使用：</span><span class="sxs-lookup"><span data-stu-id="0e7b2-129">Select one of the following credentials to use when joining the VM to the domain:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="0e7b2-130">使用 MED-V 凭据 </strong> -最终用户凭据。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-130">Use MED-V credentials</strong>—The end-user credentials.</span></span></p></li>
<li><p><strong><span data-ttu-id="0e7b2-131">使用以下凭据 </strong> -指定的凭据; 在对应字段中输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-131">Use the following credentials</strong>—The credentials specified; enter a user name and password in the corresponding fields.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="0e7b2-132">注意</span><span class="sxs-lookup"><span data-stu-id="0e7b2-132">Note</span></span></strong><br/><p><span data-ttu-id="0e7b2-133">你输入的凭据将对所有 MED-V 工作区用户可见。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-133">The credentials you enter are visible to all MED-V workspace users.</span></span> <span data-ttu-id="0e7b2-134">建议不要提供域管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-134">It is not recommended to provide domain administrator credentials.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-135">要加入的域</span><span class="sxs-lookup"><span data-stu-id="0e7b2-135">Domain to join</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-136">选择以下其中一项：</span><span class="sxs-lookup"><span data-stu-id="0e7b2-136">Select one of the following:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="0e7b2-137">使用域名在启动工作区 </strong> 时使用，即在登录到 med-v 客户端时加入最终用户输入的域。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-137">Use the domain name utilized in starting the Workspace</strong>—Join the domain entered by the end user when logging into the MED-V client.</span></span></p>
<p><span data-ttu-id="0e7b2-138">若要定义从 NetBIOS 到完全限定的域名的映射，请单击 " <strong> 全局域映射表" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-138">To define the mapping from NetBIOS to fully qualified domain names, click <strong>Global domain mapping table</strong>.</span></span> <span data-ttu-id="0e7b2-139">在全局域映射表中，单击 <strong> </strong> "添加"，输入 <strong> NetBIOS 域名 </strong> 和 <strong> 完全限定的域名 </strong> ，然后单击 <strong> "确定" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-139">In the global domain mapping table, click <strong>Add</strong>, enter a <strong>NetBIOS domain name</strong> and a <strong>Fully qualified domain name</strong>, and click <strong>OK</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="0e7b2-140">使用以下域名 </strong> -加入指定域; 在对应字段中输入域名和 NetBIOS 域名。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-140">Use the following domain name</strong>—Join the domain specified; enter a domain name and NetBIOS domain name in the corresponding fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-141">组织单位</span><span class="sxs-lookup"><span data-stu-id="0e7b2-141">Organization Unit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-142">可以指定组织单位（OU）将计算机加入特定的 OU。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-142">An organization unit (OU) may be specified to join the computer to a specific OU.</span></span> <span data-ttu-id="0e7b2-143">格式必须遵循 OU 可分辨名称： OU = &lt; 组织单位 &gt; 、 &lt; 域控制器 &gt; （例如 OU = QATest、DC = IL、dc = med-v、dc = com）。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-143">The format must follow an OU distinguished name: OU=&lt;Organization Unit&gt;,&lt;Domain Controller&gt; (for example, OU=QATest, DC=il, DC=MED-V, DC=com).</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0e7b2-144">警告</span><span class="sxs-lookup"><span data-stu-id="0e7b2-144">Warning</span></span></strong><br/><p><span data-ttu-id="0e7b2-145">仅支持单个级别的 OU，如上例中所示。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-145">Only a single level OU is supported as is shown in the example above.</span></span></p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-checkconnectivityproperties"></a>

**<span data-ttu-id="0e7b2-146">检查连接属性</span><span class="sxs-lookup"><span data-stu-id="0e7b2-146">Check Connectivity Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e7b2-147">属性</span><span class="sxs-lookup"><span data-stu-id="0e7b2-147">Property</span></span></th>
<th align="left"><span data-ttu-id="0e7b2-148">描述</span><span class="sxs-lookup"><span data-stu-id="0e7b2-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-149">IP 地址</span><span class="sxs-lookup"><span data-stu-id="0e7b2-149">IP Address</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-150">要验证连接到的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-150">The IP Address of the server that you are verifying connection to.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-151">端口</span><span class="sxs-lookup"><span data-stu-id="0e7b2-151">Port</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-152">要验证其连接的服务器的端口。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-152">The port of the server that you are verifying connection to.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-153">超时</span><span class="sxs-lookup"><span data-stu-id="0e7b2-153">Timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-154">超时前等待响应的秒数。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-154">The number of seconds to wait for a response before timing out.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-commandlineproperties"></a>

**<span data-ttu-id="0e7b2-155">命令行属性</span><span class="sxs-lookup"><span data-stu-id="0e7b2-155">Command-Line Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e7b2-156">属性</span><span class="sxs-lookup"><span data-stu-id="0e7b2-156">Property</span></span></th>
<th align="left"><span data-ttu-id="0e7b2-157">说明</span><span class="sxs-lookup"><span data-stu-id="0e7b2-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-158">Path</span><span class="sxs-lookup"><span data-stu-id="0e7b2-158">Path</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-159">命令行的路径。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-159">The path of the command line.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-160">Arguments</span><span class="sxs-lookup"><span data-stu-id="0e7b2-160">Arguments</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-161">命令行参数。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-161">Command-line arguments.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-162">等待退出</span><span class="sxs-lookup"><span data-stu-id="0e7b2-162">Wait for exit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-163">选中复选框以等待返回，然后再继续执行脚本操作。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-163">Select the check box to wait for a return before continuing with the script actions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-164">出现错误时出错</span><span class="sxs-lookup"><span data-stu-id="0e7b2-164">Fail on error</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-165">如果返回值为除指定值之外的任何值，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-165">Select this check box if the return is anything but the value specified.</span></span></p>
<p><span data-ttu-id="0e7b2-166">输入将指示该命令成功的值。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-166">Enter the value that will indicate the command as a success.</span></span></p>
<p><span data-ttu-id="0e7b2-167">默认值： <strong> 0</span><span class="sxs-lookup"><span data-stu-id="0e7b2-167">Default: <strong>0</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-168">只执行一次</span><span class="sxs-lookup"><span data-stu-id="0e7b2-168">Perform only once</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-169">选中此复选框以仅运行命令行一次。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-169">Select this check box to run the command line only once.</span></span> <span data-ttu-id="0e7b2-170">如果脚本失败或被取消，则不会再次执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-170">If the script fails or is canceled, this command will not be performed again.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-171">此命令行导致工作区中的 Windows 重启</span><span class="sxs-lookup"><span data-stu-id="0e7b2-171">This command line causes a restart of Windows in the Workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-172">如果命令行在完成后导致重新启动，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-172">Select this check box if the command line causes a restart after completion.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-173">允许交互</span><span class="sxs-lookup"><span data-stu-id="0e7b2-173">Allow interaction</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-174">如果命令将需要用户交互，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-174">Select this check box if the command will require user interaction.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-175">进度消息</span><span class="sxs-lookup"><span data-stu-id="0e7b2-175">Progress message</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-176">运行命令时向用户显示的消息。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-176">Message to be displayed to the user while the command is running.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-177">失败消息</span><span class="sxs-lookup"><span data-stu-id="0e7b2-177">Failure message</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-178">如果命令失败，将向用户显示消息。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-178">Message to be displayed to the user if the command fails.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0e7b2-179">配置命令行操作时，可以按下表中定义的方式使用几个变量。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-179">When configuring the command-line action, several variables can be used as defined in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e7b2-180">参数</span><span class="sxs-lookup"><span data-stu-id="0e7b2-180">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0e7b2-181">值</span><span class="sxs-lookup"><span data-stu-id="0e7b2-181">Value</span></span></th>
<th align="left"><span data-ttu-id="0e7b2-182">描述</span><span class="sxs-lookup"><span data-stu-id="0e7b2-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-183">%MEDVUser%</span><span class="sxs-lookup"><span data-stu-id="0e7b2-183">%MEDVUser%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-184">经过身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-184">An authenticated user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-185">MED-V 身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-185">MED-V authenticated user name.</span></span> <span data-ttu-id="0e7b2-186">用户名和密码可在 "加入域 VM 设置" 脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-186">The user name and password can be used in the join domain VM setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-187">%MEDVPassword%</span><span class="sxs-lookup"><span data-stu-id="0e7b2-187">%MEDVPassword%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-188">经过身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-188">An authenticated password.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-189">MED-V 身份验证密码。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-189">MED-V authenticated password.</span></span> <span data-ttu-id="0e7b2-190">用户名和密码可在 "加入域 VM 设置" 脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-190">The user name and password can be used in the join domain VM setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e7b2-191">%MEDVDomain%</span><span class="sxs-lookup"><span data-stu-id="0e7b2-191">%MEDVDomain%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-192">配置的域。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-192">Configured domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-193">在 MED-V 身份验证中配置的域。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-193">The domain configured in the MED-V authentication.</span></span> <span data-ttu-id="0e7b2-194">它可以在 VM 设置脚本上使用。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-194">It can be used on the VM setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e7b2-195">%DesiredMachineName%</span><span class="sxs-lookup"><span data-stu-id="0e7b2-195">%DesiredMachineName%</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-196">计算机名。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-196">Computer name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e7b2-197">管理应用程序中配置的唯一计算机名。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-197">The unique computer name configured in the management application.</span></span> <span data-ttu-id="0e7b2-198">它可以在 VM 安装脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="0e7b2-198">It can be used in the VM setup script.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0e7b2-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="0e7b2-199">Related topics</span></span>


[<span data-ttu-id="0e7b2-200">如何为 MED-V 工作区配置虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="0e7b2-200">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[<span data-ttu-id="0e7b2-201">如何配置 VM 计算机名称模式属性</span><span class="sxs-lookup"><span data-stu-id="0e7b2-201">How to Configure VM Computer Name Pattern Properties</span></span>](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

 

 





