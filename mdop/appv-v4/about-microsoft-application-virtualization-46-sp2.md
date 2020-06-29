---
title: 关于 Microsoft Application Virtualization 4.6 SP2
description: 关于 Microsoft Application Virtualization 4.6 SP2
author: dansimp
ms.assetid: 1429e314-9c38-472b-8687-3bed6cf0015c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 16303380782a086cfd750c7a8b2f99bf4f4c8b5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802448"
---
# <span data-ttu-id="a96e7-103">关于 Microsoft Application Virtualization 4.6 SP2</span><span class="sxs-lookup"><span data-stu-id="a96e7-103">About Microsoft Application Virtualization 4.6 SP2</span></span>


<span data-ttu-id="a96e7-104">Microsoft Application Virtualization （App-v） 4.6 SP2 提供了一些增强功能和新功能，本主题中将介绍这些功能。</span><span class="sxs-lookup"><span data-stu-id="a96e7-104">Microsoft Application Virtualization (App-V)4.6 SP2 provides several enhancements and new features, which are described in this topic.</span></span>

<span data-ttu-id="a96e7-105">**小心** 本主题介绍如何使用注册表编辑器更改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="a96e7-105">**Caution** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="a96e7-106">如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="a96e7-106">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="a96e7-107">在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。</span><span class="sxs-lookup"><span data-stu-id="a96e7-107">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="a96e7-108">Microsoft 无法保证更改注册表时可能出现的问题可以解决。</span><span class="sxs-lookup"><span data-stu-id="a96e7-108">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="a96e7-109">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="a96e7-109">Change the registry at your own risk.</span></span>

 

**<span data-ttu-id="a96e7-110">Windows 8 和 Windows Server 2012 支持</span><span class="sxs-lookup"><span data-stu-id="a96e7-110">Support for Windows 8 and Windows Server 2012</span></span>**

<span data-ttu-id="a96e7-111">App-v 4.6 SP2 添加了对 Windows 8 和 Windows Server 2012 远程桌面服务的支持。</span><span class="sxs-lookup"><span data-stu-id="a96e7-111">App-V4.6SP2 adds support for Windows 8 and Windows Server 2012 Remote Desktop Services.</span></span>

**<span data-ttu-id="a96e7-112">支持与 App-v 5.0 客户端共存</span><span class="sxs-lookup"><span data-stu-id="a96e7-112">Support for coexistence with App-V 5.0 client</span></span>**

<span data-ttu-id="a96e7-113">App-v 4.6 SP2 为与 Microsoft Application Virtualization 5.0 客户端的共存提供支持。</span><span class="sxs-lookup"><span data-stu-id="a96e7-113">App-V4.6SP2 provides support for coexistence with the Microsoft Application Virtualization 5.0 client.</span></span> <span data-ttu-id="a96e7-114">有关如何将 app-v 5.0 客户端配置为与 app-v 4.6 SP2 客户端共存的说明，请查看 app-v 5.0 文档。</span><span class="sxs-lookup"><span data-stu-id="a96e7-114">Review the App-V 5.0 documentation for instructions on how to configure the App-V 5.0 client for coexistence with the App-V4.6SP2 client.</span></span> <span data-ttu-id="a96e7-115">有关 App-V 5.0 的详细信息，请参阅 TechNet 上的[应用程序虚拟化 5](https://go.microsoft.com/fwlink/?LinkId=267599) 。</span><span class="sxs-lookup"><span data-stu-id="a96e7-115">For more information about App-V 5.0, see [Application Virtualization 5](https://go.microsoft.com/fwlink/?LinkId=267599) on TechNet.</span></span>

**<span data-ttu-id="a96e7-116">使 Adobe Reader X 与受保护模式的虚拟化的能力</span><span class="sxs-lookup"><span data-stu-id="a96e7-116">Ability to virtualize Adobe Reader X with Protected Mode</span></span>**

<span data-ttu-id="a96e7-117">你可以通过使用以下过程来虚拟化 Adobe Reader X，其保护模式功能处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="a96e7-117">You can virtualize Adobe Reader X with its Protected Mode feature turned on by using the following procedures.</span></span> <span data-ttu-id="a96e7-118">以前，您必须禁用保护模式才能虚拟化 Adobe Reader X。</span><span class="sxs-lookup"><span data-stu-id="a96e7-118">Previously you had to disable Protected Mode in order to virtualize Adobe Reader X.</span></span>

<span data-ttu-id="a96e7-119">在启动 App-v 排序器之前，在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE \\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides 下创建以下注册表值：</span><span class="sxs-lookup"><span data-stu-id="a96e7-119">Before launching the App-V Sequencer, create the following registry value under HKEY\_LOCAL\_MACHINE\\SOFTWARE \\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a96e7-120">名称</span><span class="sxs-lookup"><span data-stu-id="a96e7-120">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a96e7-121">类型</span><span class="sxs-lookup"><span data-stu-id="a96e7-121">Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="a96e7-122">数据</span><span class="sxs-lookup"><span data-stu-id="a96e7-122">Data</span></span></p></td>
<td align="left"><p><span data-ttu-id="a96e7-123">描述</span><span class="sxs-lookup"><span data-stu-id="a96e7-123">Description</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a96e7-124">EnableVFSPassthrough</span><span class="sxs-lookup"><span data-stu-id="a96e7-124">EnableVFSPassthrough</span></span></p></td>
<td align="left"><p><span data-ttu-id="a96e7-125">DWORD</span><span class="sxs-lookup"><span data-stu-id="a96e7-125">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="a96e7-126">raid-1</span><span class="sxs-lookup"><span data-stu-id="a96e7-126">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="a96e7-127">将此值设置为 <strong> 1， </strong> 以便在启动阶段，在保护模式下启动 Adobe Reader X。</span><span class="sxs-lookup"><span data-stu-id="a96e7-127">Set this value to <strong>1</strong> in order to start Adobe Reader X in Protected Mode during the launch phase.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a96e7-128">**注意** 在运行64位操作系统的计算机上，创建 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides. 的注册表值</span><span class="sxs-lookup"><span data-stu-id="a96e7-128">**Note** On a computer running a 64-bit operating system, create the registry value under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides.</span></span>

 

<span data-ttu-id="a96e7-129">对于 Adobe Reader X 程序包中的每个 OSD 文件，在 "策略" 元素下添加以下项目 &lt; &gt; ：</span><span class="sxs-lookup"><span data-stu-id="a96e7-129">For each OSD-file in your Adobe Reader X package, add the following items under the &lt;POLICIES&gt; element:</span></span>

`<VIRTUAL_FILE_SYSTEM_PASS_THROUGH>TRUE</VIRTUAL_FILE_SYSTEM_PASS_THROUGH>`

`<VIRTUAL_REGISTRY_PASS_THROUGH>TRUE</VIRTUAL_REGISTRY_PASS_THROUGH>`

`<ENFORCE_ACLS_ON_VREG_MODIFY>TRUE</ENFORCE_ACLS_ON_VREG_MODIFY>`

**<span data-ttu-id="a96e7-130">新的 Sequencer 命令行参数</span><span class="sxs-lookup"><span data-stu-id="a96e7-130">New Sequencer command-line parameter</span></span>**

<span data-ttu-id="a96e7-131">通过 Sequencer GUI 创建程序包加速器（PA）时，你可以选择为将应用包加速器的管理员提供打包和部署指南的 RTF 或 TXT 文件。</span><span class="sxs-lookup"><span data-stu-id="a96e7-131">When you create a Package Accelerator (PA) through the Sequencer GUI, you can select an RTF or TXT file that provides packaging and deployment guidance to the administrators who will apply the Package Accelerator.</span></span> <span data-ttu-id="a96e7-132">此功能现在可使用 Sequencer CLI 使用。</span><span class="sxs-lookup"><span data-stu-id="a96e7-132">This functionality is now available using the Sequencer CLI.</span></span>

`/ACCELERATORDESCRIPTIONFILE:PathToDescriptionFile`

<span data-ttu-id="a96e7-133">指定在创建包加速器时提供打包和部署指南的 RTF 或 TXT 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a96e7-133">Specify a path to an RTF or TXT file that provides packaging and deployment guidance when creating a Package Accelerator.</span></span>

**<span data-ttu-id="a96e7-134">不再需要安装 Microsoft 应用程序错误报告</span><span class="sxs-lookup"><span data-stu-id="a96e7-134">Microsoft Application Error Reporting no longer needs to be installed</span></span>**

<span data-ttu-id="a96e7-135">当你使用 setup.msi 安装 app-v 4.6 SP2 客户端时，不再需要安装 Microsoft 应用程序错误报告（dw20shared.msi）。</span><span class="sxs-lookup"><span data-stu-id="a96e7-135">When you are installing the App-V4.6SP2 client by using setup.msi, you no longer need to install Microsoft Application Error Reporting (dw20shared.msi).</span></span> <span data-ttu-id="a96e7-136">现在，app-v 4.6 SP2 使用 Microsoft 错误报告。</span><span class="sxs-lookup"><span data-stu-id="a96e7-136">App-V4.6SP2 now uses Microsoft Error Reporting.</span></span> <span data-ttu-id="a96e7-137">有关详细信息，请参阅[如何使用 Setup.msi安装 App-v 客户端](https://go.microsoft.com/fwlink/?LinkId=267237)。</span><span class="sxs-lookup"><span data-stu-id="a96e7-137">For more information, see [How to Install the App-V Client by Using Setup.msi](https://go.microsoft.com/fwlink/?LinkId=267237).</span></span>

**<span data-ttu-id="a96e7-138">客户反馈和修补程序汇总</span><span class="sxs-lookup"><span data-stu-id="a96e7-138">Customer feedback and hotfix rollup</span></span>**

<span data-ttu-id="a96e7-139">App-v 4.6 SP2 包括自 app-v 4.6 SP1 发布以来发现的解决问题的修补程序汇总。</span><span class="sxs-lookup"><span data-stu-id="a96e7-139">App-V4.6SP2 includes a rollup of fixes to address issues found since the App-V 4.6 SP1 release.</span></span> <span data-ttu-id="a96e7-140">App-v 4.6 SP2 包含 Microsoft Application Virtualization 4.6 SP1 修补程序（包括 Microsoft Application Virtualization SP1）的最新修补程序。</span><span class="sxs-lookup"><span data-stu-id="a96e7-140">App-V4.6SP2 contains the latest fixes up to and including Microsoft Application Virtualization 4.6 SP1 Hotfix 6.</span></span>

## <span data-ttu-id="a96e7-141">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a96e7-141">In This Section</span></span>


<a href="" id="app-v-4-6-sp2-release-notes"></a>[<span data-ttu-id="a96e7-142">App-V 4.6 SP2 发行说明</span><span class="sxs-lookup"><span data-stu-id="a96e7-142">App-V 4.6 SP2 Release Notes</span></span>](https://go.microsoft.com/fwlink/?LinkId=267600)  
<span data-ttu-id="a96e7-143">提供有关 app-v 4.6 SP2 的已知问题的最新信息。</span><span class="sxs-lookup"><span data-stu-id="a96e7-143">Provides the most up-to-date information about known issues with App-V4.6SP2.</span></span>

 

 





