---
title: App-V 升级清单
description: App-V 升级清单
author: dansimp
ms.assetid: 64e317d2-d260-4b67-8a49-ba9ac513087a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad856ce3067c327f3e604f9269ee384a66a1675a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802336"
---
# <span data-ttu-id="f3964-103">App-V 升级清单</span><span class="sxs-lookup"><span data-stu-id="f3964-103">App-V Upgrade Checklist</span></span>


<span data-ttu-id="f3964-104">在尝试升级到 Microsoft Application Virtualization （App-v）4.5 或更高版本之前，任何早于 app-v 4.1 的版本都必须升级到 App-v 4.1。</span><span class="sxs-lookup"><span data-stu-id="f3964-104">Before trying to upgrade to Microsoft Application Virtualization (App-V) 4.5 or later versions, any version earlier than App-V 4.1 must be upgraded to App-V 4.1.</span></span> <span data-ttu-id="f3964-105">你应该首先计划升级客户端，然后升级服务器组件。</span><span class="sxs-lookup"><span data-stu-id="f3964-105">You should plan to upgrade clients first, and then upgrade the server components.</span></span> <span data-ttu-id="f3964-106">已升级到 app-v 4.5 的 app-v 客户端将继续处理尚未升级的 app-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="f3964-106">App-V clients that have been upgraded to App-V 4.5 continue to work with App-V servers that have not yet been upgraded.</span></span> <span data-ttu-id="f3964-107">已升级到 app-v 4.5 的服务器不支持早期版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="f3964-107">Earlier versions of the client are not supported on servers that have been upgraded to App-V 4.5.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f3964-108">步骤</span><span class="sxs-lookup"><span data-stu-id="f3964-108">Step</span></span></th>
<th align="left"><span data-ttu-id="f3964-109">参考</span><span class="sxs-lookup"><span data-stu-id="f3964-109">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-110">升级 app-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="f3964-110">Upgrade the App-V clients.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-client.md" data-raw-source="[How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)"><span data-ttu-id="f3964-111">如何升级 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="f3964-111">How to Upgrade the Application Virtualization Client</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-112">升级 app-v 服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="f3964-112">Upgrade the App-V servers and database.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="f3964-113">重要提示</span><span class="sxs-lookup"><span data-stu-id="f3964-113">Important</span></span></strong><br/><p><span data-ttu-id="f3964-114">如果你有多个对 App-v 数据库的服务器共享访问权限，则所有这些服务器都必须在数据库升级时联机。</span><span class="sxs-lookup"><span data-stu-id="f3964-114">If you have more than one server sharing access to the App-V database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="f3964-115">你应遵循数据库升级的常规业务做法，但我们建议你先在测试服务器上使用数据库的备份副本测试数据库升级。</span><span class="sxs-lookup"><span data-stu-id="f3964-115">You should follow your regular business practices for the database upgrade, but we recommend that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="f3964-116">然后，你应该选择其中一个服务器进行首次升级，这将升级数据库架构。</span><span class="sxs-lookup"><span data-stu-id="f3964-116">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="f3964-117">成功升级生产数据库后，您可以在其他服务器上升级 app-v 软件。</span><span class="sxs-lookup"><span data-stu-id="f3964-117">After the production database has been successfully upgraded, you can upgrade the App-V software on the other servers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="f3964-118">如何升级服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="f3964-118">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-119">升级 app-v Management Web 服务。</span><span class="sxs-lookup"><span data-stu-id="f3964-119">Upgrade the App-V Management Web Service.</span></span></p>
<p><span data-ttu-id="f3964-120">仅当管理 Web 服务位于单独的服务器上时才适用此步骤，这将要求你在单独的服务器上运行服务器安装程序以升级管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="f3964-120">This step applies only if the Management Web Service is on a separate server, which would require that you run the server installer program on that separate server to upgrade the Management Web service.</span></span> <span data-ttu-id="f3964-121">否则，以前的服务器升级步骤将自动升级管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="f3964-121">Otherwise, the previous server upgrade step will automatically upgrade the Management Web Service.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="f3964-122">如何升级服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="f3964-122">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-123">升级 app-v 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f3964-123">Upgrade the App-V Management Console.</span></span></p>
<p><span data-ttu-id="f3964-124">此步骤仅适用于管理控制台位于单独计算机上的情况，这需要你在单独的计算机上运行服务器安装程序才能升级该控制台。</span><span class="sxs-lookup"><span data-stu-id="f3964-124">This step applies only if the Management Console is on a separate computer, which would require that you run the server installer program on that separate computer to upgrade the console.</span></span> <span data-ttu-id="f3964-125">否则，以前的服务器升级步骤将升级管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f3964-125">Otherwise, the previous server upgrade step will upgrade the Management Console.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="f3964-126">如何升级服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="f3964-126">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-127">升级 app-v Sequencer。</span><span class="sxs-lookup"><span data-stu-id="f3964-127">Upgrade the App-V Sequencer.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-sequencer.md" data-raw-source="[How to Upgrade the Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)"><span data-ttu-id="f3964-128">如何升级 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="f3964-128">How to Upgrade the Application Virtualization Sequencer</span></span></a></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="f3964-129">其他升级注意事项</span><span class="sxs-lookup"><span data-stu-id="f3964-129">Additional Upgrade Considerations</span></span>


-   <span data-ttu-id="f3964-130">不需要再次对版本4.2 中的任何虚拟应用程序包进行排序，即可与版本4.5 一起使用。</span><span class="sxs-lookup"><span data-stu-id="f3964-130">Any virtual application packages sequenced in version 4.2 will not have to be sequenced again for use with version 4.5.</span></span> <span data-ttu-id="f3964-131">但是，如果你希望应用默认的访问控制列表（Acl）或生成 Windows Installer 文件，应考虑将虚拟程序包升级为 Microsoft Application Virtualization 4.5 格式。</span><span class="sxs-lookup"><span data-stu-id="f3964-131">However, you should consider upgrading the virtual packages to the Microsoft Application Virtualization 4.5 format if you want to apply default access control lists (ACLs) or generate a Windows Installer file.</span></span> <span data-ttu-id="f3964-132">这是一个简单的过程，只需要使用 App-v 4.5 Sequencer 打开和保存现有虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="f3964-132">This is a simple process and requires only that the existing virtual application package be opened and saved with the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="f3964-133">这可以通过使用 VSequencer 命令行界面自动执行。</span><span class="sxs-lookup"><span data-stu-id="f3964-133">This can be automated by using the App-VSequencer command-line interface.</span></span> <span data-ttu-id="f3964-134">有关详细信息，请参阅[如何使用 App-v Sequencer 创建或升级虚拟应用程序](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)</span><span class="sxs-lookup"><span data-stu-id="f3964-134">For more information, see [How to Create or Upgrade Virtual Applications Using the App-V Sequencer](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)</span></span>

-   <span data-ttu-id="f3964-135">4.5 Sequencer 的功能之一是创建 Windows Installer （.msi）文件的功能，作为虚拟应用程序包与电子软件分发（ESD）系统（如 Microsoft 终结点配置管理器）的互操作性的控制点。</span><span class="sxs-lookup"><span data-stu-id="f3964-135">One of the features of the 4.5 Sequencer is the ability to create Windows Installer (.msi) files as control points for virtual application package interoperability with electronic software distribution (ESD) systems, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="f3964-136">以前升级到 app-v 4.5 的 App-v 4.1 或4.2 客户端上安装的用于应用程序虚拟化的以前升级到 app-v 的应用程序虚拟化的 Windows 安装程序文件将继续正常运行，但它们不能安装在 App-v 4.5 客户端上。</span><span class="sxs-lookup"><span data-stu-id="f3964-136">Previous Windows Installer files created with the MSI tool for Application Virtualization that were installed on a App-V 4.1 or 4.2 client that is subsequently upgraded to App-V 4.5 will continue to work, although they cannot be installed on the App-V 4.5 client.</span></span> <span data-ttu-id="f3964-137">但是，除非在 App-v 4.5 Sequencer 中升级，否则无法删除或升级它们。</span><span class="sxs-lookup"><span data-stu-id="f3964-137">However, they cannot be removed or upgraded unless they are upgraded in the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="f3964-138">早于4.5 的原始 App-v 包必须在 App-v 4.5 Sequencer 中打开，然后另存为 Windows Installer 文件。</span><span class="sxs-lookup"><span data-stu-id="f3964-138">The original App-V package earlier than 4.5 has to be opened in the App-V 4.5 Sequencer and then saved as a Windows Installer File.</span></span>

    **<span data-ttu-id="f3964-139">注意</span><span class="sxs-lookup"><span data-stu-id="f3964-139">Note</span></span>**  
    <span data-ttu-id="f3964-140">如果 app-v 4.2 客户端已升级到 App-v 4.5，则可以通过脚本解决方法来保留版本4.5 客户端上的版本4.2 程序包，并允许对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="f3964-140">If the App-V 4.2 Client has already been upgraded to App-V 4.5, it is possible to script a workaround to preserve the version 4.2 packages on version 4.5 clients and allow them to be managed.</span></span> <span data-ttu-id="f3964-141">此脚本必须将两个文件（msvcp71.dll 和 msvcr71.dll）复制到 App-v 安装文件夹，并在注册表项下设置以下注册表项值： \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]：</span><span class="sxs-lookup"><span data-stu-id="f3964-141">This script must copy two files, msvcp71.dll and msvcr71.dll, to the App-V installation folder and set the following registry key values under the registry key:\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]:</span></span>

    <span data-ttu-id="f3964-142">"ClientVersion" = "4.2.1.20"</span><span class="sxs-lookup"><span data-stu-id="f3964-142">"ClientVersion"="4.2.1.20"</span></span>

    <span data-ttu-id="f3964-143">"GlobalDataDirectory" = "C:\\\\Documents 和 Settings\\\\All Users\\\\Documents\\\\" （全局可写位置）</span><span class="sxs-lookup"><span data-stu-id="f3964-143">"GlobalDataDirectory"="C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (a globally writeable location)</span></span>



-   <span data-ttu-id="f3964-144">当尝试在 App-v 4.6 客户端上运行时，由 app-v 4.5 Sequencer 生成的 Windows Installer 文件将显示错误消息 "此程序包需要 Microsoft Application Virtualization 客户端4.5 或更高版本"。</span><span class="sxs-lookup"><span data-stu-id="f3964-144">Windows Installer files generated by the App-V 4.5 Sequencer display the error message "This package requires Microsoft Application Virtualization Client 4.5 or later" when trying to run them on an App-V 4.6 Client.</span></span> <span data-ttu-id="f3964-145">使用 app-v 4.5 SP1 Sequencer 或 App-v 4.6 排序器打开旧程序包，并为程序包生成新的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="f3964-145">Open the old package with either the App-V 4.5 SP1 Sequencer or the App-V 4.6 Sequencer and generate a new .msi file for the package.</span></span>

-   <span data-ttu-id="f3964-146">当服务器升级到版本4.5 时，将覆盖创建和保存的任何版本4.2 报告。</span><span class="sxs-lookup"><span data-stu-id="f3964-146">Any version 4.2 reports that were created and saved will be overwritten when the server is upgraded to version 4.5.</span></span> <span data-ttu-id="f3964-147">如果必须保留这些报表，则必须保存位于服务器的 SoftGrid 管理控制台文件夹中的 SftMMC 文件的备份副本，然后使用该副本替换升级期间安装的新 SftMMC。</span><span class="sxs-lookup"><span data-stu-id="f3964-147">If you have to keep these reports, you must save a backup copy of the SftMMC.msc file located in the SoftGrid Management Console folder on the server and use that copy to replace the new SftMMC.msc that is installed during the upgrade.</span></span>

-   <span data-ttu-id="f3964-148">有关从早期版本升级的其他信息，请参阅[升级到 Microsoft Application Virtualization 4.5 常见问题](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。</span><span class="sxs-lookup"><span data-stu-id="f3964-148">For additional information about upgrading from previous versions, see [Upgrading to Microsoft Application Virtualization 4.5 FAQ](https://go.microsoft.com/fwlink/?LinkId=120358) (https://go.microsoft.com/fwlink/?LinkId=120358).</span></span>

## <a href="" id="app-v-4-6-client-package-support-"></a><span data-ttu-id="f3964-149">App-v 4.6 客户端软件包支持</span><span class="sxs-lookup"><span data-stu-id="f3964-149">App-V 4.6 Client Package Support</span></span>


<span data-ttu-id="f3964-150">你可以将在早期版本的 app-v 中创建的程序包部署到 app-v 4.6 客户端。</span><span class="sxs-lookup"><span data-stu-id="f3964-150">You can deploy packages created in previous versions of App-V to App-V 4.6 clients.</span></span> <span data-ttu-id="f3964-151">但是，你必须修改关联的 .osd 文件，以便它包括相应的操作系统和芯片体系结构信息。</span><span class="sxs-lookup"><span data-stu-id="f3964-151">However, you must modify the associated .osd file so that it includes the appropriate operating system and chip architecture information.</span></span> <span data-ttu-id="f3964-152">可以使用以下值：</span><span class="sxs-lookup"><span data-stu-id="f3964-152">The following values can be used:</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f3964-153">操作系统值</span><span class="sxs-lookup"><span data-stu-id="f3964-153">OS Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-154">&lt;OS 值 = "Win2003TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-154">&lt;OS VALUE=”Win2003TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-155">&lt;OS 值 = "Win2003TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-155">&lt;OS VALUE=”Win2003TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-156">&lt;OS 值 = "Win2008TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-156">&lt;OS VALUE=”Win2008TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-157">&lt;OS 值 = "Win2008TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-157">&lt;OS VALUE=”Win2008TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-158">&lt;OS 值 = "Win2008R2TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-158">&lt;OS VALUE=”Win2008R2TS64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-159">&lt;OS 值 = "Win7"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-159">&lt;OS VALUE=”Win7”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-160">&lt;OS 值 = "Win764"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-160">&lt;OS VALUE=”Win764”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-161">&lt;OS 值 = "WinVista"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-161">&lt;OS VALUE=”WinVista”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-162">&lt;OS 值 = "WinVista64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-162">&lt;OS VALUE=”WinVista64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-163">&lt;OS 值 = "WinXP"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-163">&lt;OS VALUE=”WinXP”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-164">&lt;OS 值 = "WinXP64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="f3964-164">&lt;OS VALUE=”WinXP64”/&gt;</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="f3964-165">若要运行新创建的32位程序包，必须在运行32位操作系统的计算机上对应用程序进行排序，安装了 App-v 4.6 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="f3964-165">To run a newly created 32-bit package, you must sequence the application on a computer running a 32-bit operating system with the App-V 4.6 Sequencer installed.</span></span> <span data-ttu-id="f3964-166">对应用程序进行排序后，在 Sequencer 控制台中，单击 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。</span><span class="sxs-lookup"><span data-stu-id="f3964-166">After you have sequenced the application, in the Sequencer console, click the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

**<span data-ttu-id="f3964-167">重要提示</span><span class="sxs-lookup"><span data-stu-id="f3964-167">Important</span></span>**  
<span data-ttu-id="f3964-168">在运行64位操作系统的计算机上排序的应用程序必须部署到运行64位操作系统的计算机上。</span><span class="sxs-lookup"><span data-stu-id="f3964-168">Applications sequenced on a computer running a 64-bit operating system must be deployed to computers running a 64-bit operating system.</span></span> <span data-ttu-id="f3964-169">使用 app-v 4.6 Sequencer 创建的新32位程序包不会在运行 App-v 4.5 客户端的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="f3964-169">New 32-bit packages created by using the App-V 4.6 Sequencer do not run on computers running the App-V 4.5 client.</span></span>



<span data-ttu-id="f3964-170">若要在 App-V 4.6 客户端上运行新的64位程序包，你必须在运行 App-v 4.6 Sequencer 且运行了64位操作系统的计算机上对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="f3964-170">To run new 64-bit packages on the App-V 4.6 Client, you must sequence the application on a computer running the App-V 4.6 Sequencer and that is running a 64-bit operating system.</span></span> <span data-ttu-id="f3964-171">对应用程序进行排序后，在 Sequencer 控制台中，单击 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。</span><span class="sxs-lookup"><span data-stu-id="f3964-171">After you have sequenced the application, in the Sequencer console, click the **Deployment** tab, and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="f3964-172">下表列出了哪些客户端版本将运行使用各种版本的 sequencer 创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="f3964-172">The following table lists which client versions will run packages created by using the various versions of the sequencer.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="f3964-173">使用 app-v 4.2 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="f3964-173">Sequenced by using the App-V 4.2 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="f3964-174">使用 app-v 4.5 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="f3964-174">Sequenced by using the App-V 4.5 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="f3964-175">使用32位 App-v 4.6 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="f3964-175">Sequenced by using the 32-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="f3964-176">使用64位 App-v 4.6 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="f3964-176">Sequenced by using the 64-bit App-V 4.6 Sequencer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-177">4.2 客户端</span><span class="sxs-lookup"><span data-stu-id="f3964-177">4.2 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-178">是</span><span class="sxs-lookup"><span data-stu-id="f3964-178">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-179">否</span><span class="sxs-lookup"><span data-stu-id="f3964-179">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-180">否</span><span class="sxs-lookup"><span data-stu-id="f3964-180">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-181">否</span><span class="sxs-lookup"><span data-stu-id="f3964-181">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-182">4.5 客户端¹</span><span class="sxs-lookup"><span data-stu-id="f3964-182">4.5 Client ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-183">是</span><span class="sxs-lookup"><span data-stu-id="f3964-183">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-184">是</span><span class="sxs-lookup"><span data-stu-id="f3964-184">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-185">否</span><span class="sxs-lookup"><span data-stu-id="f3964-185">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-186">否</span><span class="sxs-lookup"><span data-stu-id="f3964-186">No</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3964-187">4.6 客户端（32位）</span><span class="sxs-lookup"><span data-stu-id="f3964-187">4.6 Client (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-188">是</span><span class="sxs-lookup"><span data-stu-id="f3964-188">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-189">是</span><span class="sxs-lookup"><span data-stu-id="f3964-189">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-190">是</span><span class="sxs-lookup"><span data-stu-id="f3964-190">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-191">否</span><span class="sxs-lookup"><span data-stu-id="f3964-191">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3964-192">4.6 客户端（64位）</span><span class="sxs-lookup"><span data-stu-id="f3964-192">4.6 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-193">是</span><span class="sxs-lookup"><span data-stu-id="f3964-193">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-194">是</span><span class="sxs-lookup"><span data-stu-id="f3964-194">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-195">是</span><span class="sxs-lookup"><span data-stu-id="f3964-195">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3964-196">是</span><span class="sxs-lookup"><span data-stu-id="f3964-196">Yes</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="f3964-197">¹适用于应用-v 4.5 客户端的所有版本，包括 App-v 4.5、App-v 4.5 CU1 和 App-v 4.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="f3964-197">¹Applies to all versions of the App-V 4.5 client, including App-V 4.5, App-V 4.5 CU1, and App-V 4.5 SP1.</span></span>









