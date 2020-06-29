---
title: 如何部署 App-V Client
description: 如何部署 App-V Client
author: dansimp
ms.assetid: 981f57c9-56c3-45da-8261-0972bfad3e5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: ea216f6b86820f752e0c0ac693470eac72cb847a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798467"
---
# <span data-ttu-id="73ab0-103">如何部署 App-V Client</span><span class="sxs-lookup"><span data-stu-id="73ab0-103">How to Deploy the App-V Client</span></span>


<span data-ttu-id="73ab0-104">使用以下过程安装 Microsoft Application Virtualization （App-v）5.1 客户端和远程桌面服务客户端。</span><span class="sxs-lookup"><span data-stu-id="73ab0-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.1 client and Remote Desktop Services client.</span></span> <span data-ttu-id="73ab0-105">必须安装与目标计算机的操作系统匹配的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="73ab0-105">You must install the version of the client that matches the operating system of the target computer.</span></span>

<a href="" id="bkmk-clt-install-prereqs"></a>**<span data-ttu-id="73ab0-106">开始之前应执行的操作</span><span class="sxs-lookup"><span data-stu-id="73ab0-106">What to do before you start</span></span>**

1. <span data-ttu-id="73ab0-107">查看和安装软件必备条件：</span><span class="sxs-lookup"><span data-stu-id="73ab0-107">Review and install the software prerequisites:</span></span>

   <span data-ttu-id="73ab0-108">安装与要安装的 App-v 版本对应的必备软件：</span><span class="sxs-lookup"><span data-stu-id="73ab0-108">Install the prerequisite software that corresponds to the version of App-V that you are installing:</span></span>

   -   [<span data-ttu-id="73ab0-109">关于 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="73ab0-109">About App-V 5.1</span></span>](about-app-v-51.md)

   -   [<span data-ttu-id="73ab0-110">App-V 5.1 先决条件</span><span class="sxs-lookup"><span data-stu-id="73ab0-110">App-V 5.1 Prerequisites</span></span>](app-v-51-prerequisites.md)

2. <span data-ttu-id="73ab0-111">查看适用于你的安装的客户端共存和不受支持的方案：</span><span class="sxs-lookup"><span data-stu-id="73ab0-111">Review the client coexistence and unsupported scenarios, as applicable to your installation:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-112">部署共存的应用程序-V 客户端</span><span class="sxs-lookup"><span data-stu-id="73ab0-112">Deploying coexisting App-V clients</span></span></p></td>
   <td align="left"><p><a href="planning-for-the-app-v-51-sequencer-and-client-deployment.md" data-raw-source="[Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md)"><span data-ttu-id="73ab0-113">计划 App-V 5.1 Sequencer 和 Client 部署</span><span class="sxs-lookup"><span data-stu-id="73ab0-113">Planning for the App-V 5.1 Sequencer and Client Deployment</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-114">不受支持或受限的安装方案</span><span class="sxs-lookup"><span data-stu-id="73ab0-114">Unsupported or limited installation scenarios</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-115">请参阅 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> 应用 V 5.1 支持的配置中的客户端部分</span><span class="sxs-lookup"><span data-stu-id="73ab0-115">See the client section in <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)">App-V 5.1 Supported Configurations</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="73ab0-116">查看客户端注册表、日志和疑难解答信息的位置：</span><span class="sxs-lookup"><span data-stu-id="73ab0-116">Review the locations for client registry, log, and troubleshooting information:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="73ab0-117">客户端注册信息</span><span class="sxs-lookup"><span data-stu-id="73ab0-117">Client registry information</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="73ab0-118">默认情况下，在安装 app-v 5.1 客户端之后，客户端信息将存储在注册表中的以下注册表项中：</span><span class="sxs-lookup"><span data-stu-id="73ab0-118">By default, after you install the App-V 5.1 client, the client information is stored in the registry in the following registry key:</span></span></p>
<p><strong><span data-ttu-id="73ab0-119">HKEY_LOCAL_MACHINE \ 软件 \ MICROSOFT \ APPV \ 客户端</span><span class="sxs-lookup"><span data-stu-id="73ab0-119">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ APPV \ CLIENT</span></span></strong></p></li>
<li><p><span data-ttu-id="73ab0-120">将虚拟化程序包部署到运行 App-v 客户端的计算机时，关联的程序包数据存储在以下位置：</span><span class="sxs-lookup"><span data-stu-id="73ab0-120">When you deploy a virtualized package to a computer that is running the App-V client, the associated package data is stored in the following location:</span></span></p>
<p><strong><span data-ttu-id="73ab0-121">C： \ ProgramData \ App-V</span><span class="sxs-lookup"><span data-stu-id="73ab0-121">C: \ ProgramData \ App-V</span></span></strong></p>
<p><span data-ttu-id="73ab0-122">但是，你可以通过以下注册表项重新配置此位置：</span><span class="sxs-lookup"><span data-stu-id="73ab0-122">However, you can reconfigure this location with the following registry key:</span></span></p>
<p><strong><span data-ttu-id="73ab0-123">HKEY_LOCAL_MACHINE \ 软件 \ MICROSOFT \ 软件 \ MICROSOFT \ APPV \ 客户端 \ 流 \ PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="73ab0-123">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ SOFTWARE \ MICROSOFT \ APPV \ CLIENT \ STREAMING \ PACKAGEINSTALLATIONROOT</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="73ab0-124">客户端日志文件</span><span class="sxs-lookup"><span data-stu-id="73ab0-124">Client log files</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="73ab0-125">对于与 App-v 5.1 客户端相关联的日志文件信息，请在以下日志中搜索：</span><span class="sxs-lookup"><span data-stu-id="73ab0-125">For log file information that is associated with the App-V 5.1 Client, search in the following log:</span></span></p>
<p><strong><span data-ttu-id="73ab0-126">事件日志/应用程序和服务日志/Microsoft/AppV</span><span class="sxs-lookup"><span data-stu-id="73ab0-126">Event logs / Applications and Services Logs / Microsoft / AppV</span></span></strong></p></li>
<li><p><span data-ttu-id="73ab0-127">在 App-v 5.0 SP3 中，某些日志已合并并移动到以下位置：</span><span class="sxs-lookup"><span data-stu-id="73ab0-127">In App-V 5.0 SP3, some logs were consolidated and moved to the following location:</span></span></p>
<p><strong><span data-ttu-id="73ab0-128">事件日志/应用程序和服务日志/Microsoft/AppV/ServiceLog</span><span class="sxs-lookup"><span data-stu-id="73ab0-128">Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog</span></span></strong></p>
<p><span data-ttu-id="73ab0-129">有关已移动日志的列表，请参阅 <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)"> 关于 App-V 5.0 SP3 </a> 。</span><span class="sxs-lookup"><span data-stu-id="73ab0-129">For a list of the moved logs, see <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)">About App-V 5.0 SP3</a>.</span></span></p></li>
<li><p><span data-ttu-id="73ab0-130">当前存储在运行 App-v 5.1 客户端的计算机上的程序包将保存到以下位置：</span><span class="sxs-lookup"><span data-stu-id="73ab0-130">Packages that are currently stored on computers that run the App-V 5.1 Client are saved to the following location:</span></span></p>
<p><strong><span data-ttu-id="73ab0-131">C:\ProgramData\App-V &amp; lt; 程序包 id &gt; &amp; lt; 版本 id&gt;</span><span class="sxs-lookup"><span data-stu-id="73ab0-131">C:\ProgramData\App-V&amp;lt;package id&gt;&amp;lt;version id&gt;</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="73ab0-132">客户端安装疑难解答信息</span><span class="sxs-lookup"><span data-stu-id="73ab0-132">Client installation troubleshooting information</span></span></p></td>
<td align="left"><p><span data-ttu-id="73ab0-133">请参阅 <strong> % temp% 文件夹中的错误日志 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="73ab0-133">See the error log in the <strong>%temp%</strong> folder.</span></span> <span data-ttu-id="73ab0-134">若要查看日志文件，请单击 " <strong> 开始 </strong> "，键入 <strong> % temp% </strong> ，然后查找 " <strong> appv_ 日志" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="73ab0-134">To review the log files, click <strong>Start</strong>, type <strong>%temp%</strong>, and then look for the <strong>appv_ log</strong>.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="73ab0-135">安装 app-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="73ab0-135">To install the App-V 5.1 Client</span></span>**

1.  <span data-ttu-id="73ab0-136">将 app-v 5.1 客户端安装文件复制到将在其上安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="73ab0-136">Copy the App-V 5.1 client installation file to the computer on which it will be installed.</span></span> <span data-ttu-id="73ab0-137">从以下客户端类型中进行选择：</span><span class="sxs-lookup"><span data-stu-id="73ab0-137">Choose from the following client types:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="73ab0-138">客户端类型</span><span class="sxs-lookup"><span data-stu-id="73ab0-138">Client type</span></span></th>
    <th align="left"><span data-ttu-id="73ab0-139">要使用的文件</span><span class="sxs-lookup"><span data-stu-id="73ab0-139">File to use</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="73ab0-140">客户端的标准版本</span><span class="sxs-lookup"><span data-stu-id="73ab0-140">Standard version of the client</span></span></p></td>
    <td align="left"><p><strong><span data-ttu-id="73ab0-141">appv_client_setup.exe</span><span class="sxs-lookup"><span data-stu-id="73ab0-141">appv_client_setup.exe</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="73ab0-142">客户端的远程桌面服务版本</span><span class="sxs-lookup"><span data-stu-id="73ab0-142">Remote Desktop Services version of the client</span></span></p></td>
    <td align="left"><p><strong><span data-ttu-id="73ab0-143">appv_client_setup_rds.exe</span><span class="sxs-lookup"><span data-stu-id="73ab0-143">appv_client_setup_rds.exe</span></span></strong></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="73ab0-144">双击安装文件，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="73ab0-144">Double-click the installation file, and click **Install**.</span></span> <span data-ttu-id="73ab0-145">安装开始之前，安装程序会检查计算机上是否缺少任何缺少[的 app-v 5.1 先决条件](app-v-51-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="73ab0-145">Before the installation begins, the installer checks the computer for any missing [App-V 5.1 Prerequisites](app-v-51-prerequisites.md).</span></span>

3.  <span data-ttu-id="73ab0-146">查看并接受软件许可条款，选择是否使用 Microsoft 更新以及是否参与 Microsoft 客户体验改善计划，并单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="73ab0-146">Review and accept the Software License Terms, choose whether to use Microsoft Update and whether to participate in the Microsoft Customer Experience Improvement Program, and click **Install**.</span></span>

4.  <span data-ttu-id="73ab0-147">在 "**安装成功完成**" 页面上，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="73ab0-147">On the **Setup completed successfully** page, click **Close**.</span></span>

    <span data-ttu-id="73ab0-148">安装过程将在**程序**中为 app-v 客户端创建以下条目：</span><span class="sxs-lookup"><span data-stu-id="73ab0-148">The installation creates the following entries for the App-V client in **Programs**:</span></span>

    -   **<span data-ttu-id="73ab0-149">.exe</span><span class="sxs-lookup"><span data-stu-id="73ab0-149">.exe</span></span>**

    -   **<span data-ttu-id="73ab0-150">.msi</span><span class="sxs-lookup"><span data-stu-id="73ab0-150">.msi</span></span>**

    -   **<span data-ttu-id="73ab0-151">语言包</span><span class="sxs-lookup"><span data-stu-id="73ab0-151">language pack</span></span>**

        **<span data-ttu-id="73ab0-152">注意</span><span class="sxs-lookup"><span data-stu-id="73ab0-152">Note</span></span>**  
        <span data-ttu-id="73ab0-153">安装后，仅可卸载 .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="73ab0-153">After the installation, only the .exe file can be uninstalled.</span></span>



**<span data-ttu-id="73ab0-154">使用脚本安装 app-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="73ab0-154">To install the App-V 5.1 client using a script</span></span>**

1. <span data-ttu-id="73ab0-155">在目标计算机上安装所有必需的必备软件。</span><span class="sxs-lookup"><span data-stu-id="73ab0-155">Install all of the required prerequisite software on the target computers.</span></span> <span data-ttu-id="73ab0-156">[在开始之前，请查看要执行的操作](#bkmk-clt-install-prereqs)。</span><span class="sxs-lookup"><span data-stu-id="73ab0-156">See [What to do before you start](#bkmk-clt-install-prereqs).</span></span> <span data-ttu-id="73ab0-157">如果使用 .msi 文件安装客户端，则如果缺少任何先决条件，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="73ab0-157">If you install the client by using an .msi file, the installation will fail if any prerequisites are missing.</span></span>

2. <span data-ttu-id="73ab0-158">若要使用脚本安装 App-v 5.1 客户端，请将以下参数与**appv\_client\_setup.exe**结合使用。</span><span class="sxs-lookup"><span data-stu-id="73ab0-158">To use a script to install the App-V 5.1 client, use the following parameters with **appv\_client\_setup.exe**.</span></span>

   **<span data-ttu-id="73ab0-159">注意</span><span class="sxs-lookup"><span data-stu-id="73ab0-159">Note</span></span>**  
   <span data-ttu-id="73ab0-160">除了 **/log**参数外，客户端 Windows Installer （.msi）支持相同的开关集。</span><span class="sxs-lookup"><span data-stu-id="73ab0-160">The client Windows Installer (.msi) supports the same set of switches, except for the **/LOG** parameter.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-161">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="73ab0-161">/INSTALLDIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-162">指定安装目录。</span><span class="sxs-lookup"><span data-stu-id="73ab0-162">Specifies the installation directory.</span></span> <span data-ttu-id="73ab0-163">示例用法： <strong> /INSTALLDIR = C:\Program Files\AppV 客户端</span><span class="sxs-lookup"><span data-stu-id="73ab0-163">Example usage: <strong>/INSTALLDIR=C:\Program Files\AppV Client</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-164">/CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="73ab0-164">/CEIPOPTIN</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-165">允许参与客户体验改善计划。</span><span class="sxs-lookup"><span data-stu-id="73ab0-165">Enables participation in the Customer Experience Improvement Program.</span></span> <span data-ttu-id="73ab0-166">示例用法： <strong> /CEIPOPTIN = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-166">Example usage: <strong>/CEIPOPTIN=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-167">/MUOPTIN</span><span class="sxs-lookup"><span data-stu-id="73ab0-167">/MUOPTIN</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-168">启用 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="73ab0-168">Enables Microsoft Update.</span></span> <span data-ttu-id="73ab0-169">示例用法： <strong> /MUOPTIN = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-169">Example usage: <strong>/MUOPTIN=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-170">/PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="73ab0-170">/PACKAGEINSTALLATIONROOT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-171">指定要在其中安装所有新应用程序和更新的目录。</span><span class="sxs-lookup"><span data-stu-id="73ab0-171">Specifies the directory in which to install all new applications and updates.</span></span> <span data-ttu-id="73ab0-172">示例用法： <strong> /PACKAGEINSTALLATIONROOT =&#39;C:\App-V 程序包&#39;</span><span class="sxs-lookup"><span data-stu-id="73ab0-172">Example usage: <strong>/PACKAGEINSTALLATIONROOT=&#39;C:\App-V Packages&#39;</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-173">/PACKAGESOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="73ab0-173">/PACKAGESOURCEROOT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-174">替代用于下载软件包内容的源位置。</span><span class="sxs-lookup"><span data-stu-id="73ab0-174">Overrides the source location for downloading package content.</span></span> <span data-ttu-id="73ab0-175">示例用法： <strong> /PACKAGESOURCEROOT =&#39;<a href="http://packageStore" data-raw-source="http://packageStore"> http://packageStore </a>&#39;</span><span class="sxs-lookup"><span data-stu-id="73ab0-175">Example usage: <strong>/PACKAGESOURCEROOT=&#39;<a href="http://packageStore" data-raw-source="http://packageStore">http://packageStore</a>&#39;</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-176">/AUTOLOAD</span><span class="sxs-lookup"><span data-stu-id="73ab0-176">/AUTOLOAD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-177">指定在特定计算机上由 app-v 5.1 加载新程序包的方式。</span><span class="sxs-lookup"><span data-stu-id="73ab0-177">Specifies how new packages will be loaded by App-V 5.1 on a specific computer.</span></span> <span data-ttu-id="73ab0-178">启用以下选项： [1];自动加载所有程序包 [2];或自动加载 "无程序包" [0]。 <strong>示例用法：/AUTOLOAD = [0 | 1 | 2]</span><span class="sxs-lookup"><span data-stu-id="73ab0-178">The following options are enabled: [1]; automatically load all packages [2]; or automatically load no packages [0].<strong>Example usage: /AUTOLOAD=[0|1|2]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-179">/SHAREDCONTENTSTOREMODE</span><span class="sxs-lookup"><span data-stu-id="73ab0-179">/SHAREDCONTENTSTOREMODE</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-180">指定流式处理的程序包内容将不会保存到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="73ab0-180">Specifies that streamed package contents will be not be saved to the local hard disk.</span></span> <span data-ttu-id="73ab0-181">示例用法： <strong> /SHAREDCONTENTSTOREMODE = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-181">Example usage: <strong>/SHAREDCONTENTSTOREMODE=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-182">/MIGRATIONMODE</span><span class="sxs-lookup"><span data-stu-id="73ab0-182">/MIGRATIONMODE</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-183">允许 App-v 5.1 客户端修改与使用早期版本创建的程序包相关联的快捷方式和 FTAs。</span><span class="sxs-lookup"><span data-stu-id="73ab0-183">Allows the App-V 5.1 client to modify the shortcuts and FTAs that are associated with the packages that are created with a previous version.</span></span> <span data-ttu-id="73ab0-184">示例用法： <strong> /MIGRATIONMODE = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-184">Example usage: <strong>/MIGRATIONMODE=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-185">/ENABLEPACKAGESCRIPTS</span><span class="sxs-lookup"><span data-stu-id="73ab0-185">/ENABLEPACKAGESCRIPTS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-186">启用应运行的程序包清单文件或配置文件中定义的脚本。</span><span class="sxs-lookup"><span data-stu-id="73ab0-186">Enables the scripts that are defined in the package manifest file or configuration files that should run.</span></span> <span data-ttu-id="73ab0-187">示例用法： <strong> /ENABLEPACKAGESCRIPTS = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-187">Example usage: <strong>/ENABLEPACKAGESCRIPTS=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-188">/ROAMINGREGISTRYEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="73ab0-188">/ROAMINGREGISTRYEXCLUSIONS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-189">指定将不随用户配置文件漫游的注册表路径。</span><span class="sxs-lookup"><span data-stu-id="73ab0-189">Specifies the registry paths that will not roam with a user profile.</span></span> <span data-ttu-id="73ab0-190">示例用法： <strong> /ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</span><span class="sxs-lookup"><span data-stu-id="73ab0-190">Example usage: <strong>/ROAMINGREGISTRYEXCLUSIONS=software\classes;software\clients</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-191">/ROAMINGFILEEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="73ab0-191">/ROAMINGFILEEXCLUSIONS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-192">指定相对于% userprofile% 的文件路径，不要与用户&#39;s 配置文件一起漫游。</span><span class="sxs-lookup"><span data-stu-id="73ab0-192">Specifies the file paths relative to %userprofile% that do not roam with a user&#39;s profile.</span></span> <span data-ttu-id="73ab0-193">示例用法： <strong> /ROAMINGFILEEXCLUSIONS &#39;桌面; "我的图片"&#39;</span><span class="sxs-lookup"><span data-stu-id="73ab0-193">Example usage: <strong>/ROAMINGFILEEXCLUSIONS &#39;desktop;my pictures&#39;</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-194">/S [1-5] PUBLISHINGSERVERNAME</span><span class="sxs-lookup"><span data-stu-id="73ab0-194">/S[1-5]PUBLISHINGSERVERNAME</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-195">显示发布服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="73ab0-195">Displays the name of the publishing server.</span></span> <span data-ttu-id="73ab0-196">示例用法： <strong> /S2PUBLISHINGSERVERNAME = MyPublishingServer</span><span class="sxs-lookup"><span data-stu-id="73ab0-196">Example usage: <strong>/S2PUBLISHINGSERVERNAME=MyPublishingServer</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-197">/S [1-5] PUBLISHINGSERVERURL</span><span class="sxs-lookup"><span data-stu-id="73ab0-197">/S[1-5]PUBLISHINGSERVERURL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-198">显示发布服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="73ab0-198">Displays the URL of the publishing server.</span></span> <span data-ttu-id="73ab0-199">示例用法： <strong> /S2PUBLISHINGSERVERURL = \pubserver</span><span class="sxs-lookup"><span data-stu-id="73ab0-199">Example usage: <strong>/S2PUBLISHINGSERVERURL=\pubserver</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-200">/S [1-5] GLOBALREFRESHENABLED-</span><span class="sxs-lookup"><span data-stu-id="73ab0-200">/S[1-5]GLOBALREFRESHENABLED -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-201">启用全局发布刷新。</span><span class="sxs-lookup"><span data-stu-id="73ab0-201">Enables a global publishing refresh.</span></span> <span data-ttu-id="73ab0-202">示例用法： <strong> /S2GLOBALREFRESHENABLED = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-202">Example usage: <strong>/S2GLOBALREFRESHENABLED=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-203">/S [1-5] GLOBALREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="73ab0-203">/S[1-5]GLOBALREFRESHONLOGON</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-204">当用户登录时启动全局发布刷新。</span><span class="sxs-lookup"><span data-stu-id="73ab0-204">Initiates a global publishing refresh when a user logs on.</span></span> <span data-ttu-id="73ab0-205">示例用法： <strong> /S2LOGONREFRESH = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-205">Example usage: <strong>/S2LOGONREFRESH=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-206">/S [1-5] GLOBALREFRESHINTERVAL-</span><span class="sxs-lookup"><span data-stu-id="73ab0-206">/S[1-5]GLOBALREFRESHINTERVAL -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-207">指定发布刷新间隔，其中 <strong> 0 </strong> 表示不定期刷新。</span><span class="sxs-lookup"><span data-stu-id="73ab0-207">Specifies the publishing refresh interval, where <strong>0</strong> indicates do not periodically refresh.</span></span> <span data-ttu-id="73ab0-208">示例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</span><span class="sxs-lookup"><span data-stu-id="73ab0-208">Example usage: <strong>/S2PERIODICREFRESHINTERVAL=[0-744]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-209">/S [1-5] GLOBALREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="73ab0-209">/S[1-5]GLOBALREFRESHINTERVALUNIT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-210">指定间隔单位（小时 [0]，天 [1]）。</span><span class="sxs-lookup"><span data-stu-id="73ab0-210">Specifies the interval unit (Hours[0], Days[1]).</span></span> <span data-ttu-id="73ab0-211">示例用法： <strong> /S2GLOBALREFRESHINTERVALUNIT = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-211">Example usage: <strong>/S2GLOBALREFRESHINTERVALUNIT=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-212">/S [1-5] USERREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="73ab0-212">/S[1-5]USERREFRESHENABLED</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-213">启用用户发布刷新。</span><span class="sxs-lookup"><span data-stu-id="73ab0-213">Enables user publishing refresh.</span></span> <span data-ttu-id="73ab0-214">示例用法： <strong> /S2USERREFRESHENABLED = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-214">Example usage: <strong>/S2USERREFRESHENABLED=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-215">/S [1-5] USERREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="73ab0-215">/S[1-5]USERREFRESHONLOGON</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-216">用户登录时启动用户发布刷新。</span><span class="sxs-lookup"><span data-stu-id="73ab0-216">Initiates a user publishing refresh when a user logs on.</span></span> <span data-ttu-id="73ab0-217">示例用法： <strong> /S2LOGONREFRESH = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-217">Example usage: <strong>/S2LOGONREFRESH=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-218">/S [1-5] USERREFRESHINTERVAL-</span><span class="sxs-lookup"><span data-stu-id="73ab0-218">/S[1-5]USERREFRESHINTERVAL -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-219">指定发布刷新间隔，其中 <strong> 0 </strong> 表示不定期刷新。</span><span class="sxs-lookup"><span data-stu-id="73ab0-219">Specifies the publishing refresh interval, where <strong>0</strong> indicates do not periodically refresh.</span></span> <span data-ttu-id="73ab0-220">示例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</span><span class="sxs-lookup"><span data-stu-id="73ab0-220">Example usage: <strong>/S2PERIODICREFRESHINTERVAL=[0-744]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-221">/S [1-5] USERREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="73ab0-221">/S[1-5]USERREFRESHINTERVALUNIT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-222">指定间隔单位（小时 [0]，天 [1]）。</span><span class="sxs-lookup"><span data-stu-id="73ab0-222">Specifies the interval unit (Hours[0], Days[1]).</span></span> <span data-ttu-id="73ab0-223">示例用法： <strong> /S2USERREFRESHINTERVALUNIT = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="73ab0-223">Example usage: <strong>/S2USERREFRESHINTERVALUNIT=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-224">/Log</span><span class="sxs-lookup"><span data-stu-id="73ab0-224">/Log</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-225">指定保存日志信息的位置。</span><span class="sxs-lookup"><span data-stu-id="73ab0-225">Specifies a location where the log information is saved.</span></span> <span data-ttu-id="73ab0-226">默认位置为% Temp%。</span><span class="sxs-lookup"><span data-stu-id="73ab0-226">The default location is %Temp%.</span></span> <span data-ttu-id="73ab0-227">示例用法： <strong> /Log C:\logs\log.log</span><span class="sxs-lookup"><span data-stu-id="73ab0-227">Example usage: <strong>/log C:\logs\log.log</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-228">/q</span><span class="sxs-lookup"><span data-stu-id="73ab0-228">/q</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-229">指定无人参与安装。</span><span class="sxs-lookup"><span data-stu-id="73ab0-229">Specifies an unattended installation.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-230">/REPAIR</span><span class="sxs-lookup"><span data-stu-id="73ab0-230">/REPAIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-231">修复以前的客户端安装。</span><span class="sxs-lookup"><span data-stu-id="73ab0-231">Repairs a previous client installation.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-232">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="73ab0-232">/NORESTART</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-233">阻止计算机在客户端安装后重新启动。</span><span class="sxs-lookup"><span data-stu-id="73ab0-233">Prevents the computer from rebooting after the client installation.</span></span></p>
   <p><span data-ttu-id="73ab0-234">该参数可防止最终用户计算机在安装每个更新后重新启动，并允许你在方便时计划重启。</span><span class="sxs-lookup"><span data-stu-id="73ab0-234">The parameter prevents the end-user computer from rebooting after each update is installed and lets you schedule the reboot at your convenience.</span></span> <span data-ttu-id="73ab0-235">例如，你可以安装 app-v 5.1，然后安装修补程序包 Y，而无需在安装 Service Pack 后重新启动。</span><span class="sxs-lookup"><span data-stu-id="73ab0-235">For example, you can install App-V 5.1 and then install Hotfix Package Y without rebooting after the Service Pack installation.</span></span> <span data-ttu-id="73ab0-236">安装完成后，必须重新启动才能开始使用 app-v。</span><span class="sxs-lookup"><span data-stu-id="73ab0-236">After the installation, you must reboot before you start using App-V.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-237">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="73ab0-237">/UNINSTALL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-238">卸载客户端。</span><span class="sxs-lookup"><span data-stu-id="73ab0-238">Uninstalls the client.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-239">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="73ab0-239">/ACCEPTEULA</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-240">接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="73ab0-240">Accepts the license agreement.</span></span> <span data-ttu-id="73ab0-241">这是无人参与安装所必需的。</span><span class="sxs-lookup"><span data-stu-id="73ab0-241">This is required for an unattended installation.</span></span> <span data-ttu-id="73ab0-242">示例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="73ab0-242">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-243">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="73ab0-243">/LAYOUT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-244">指定关联的布局操作。</span><span class="sxs-lookup"><span data-stu-id="73ab0-244">Specifies the associated layout action.</span></span> <span data-ttu-id="73ab0-245">它还将 Windows Installer （.msi）和脚本文件提取到文件夹中，但不安装 app-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="73ab0-245">It also extracts the Windows Installer (.msi) and script files to a folder without installing App-V 5.1.</span></span> <span data-ttu-id="73ab0-246">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="73ab0-246">No value is expected.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="73ab0-247">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="73ab0-247">/LAYOUTDIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-248">指定布局目录。</span><span class="sxs-lookup"><span data-stu-id="73ab0-248">Specifies the layout directory.</span></span> <span data-ttu-id="73ab0-249">需要字符串值。</span><span class="sxs-lookup"><span data-stu-id="73ab0-249">Requires a string value.</span></span> <span data-ttu-id="73ab0-250">示例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 客户端" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="73ab0-250">Example usage: <strong>/LAYOUTDIR=”C:\Application Virtualization Client”</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="73ab0-251">/？、/h、/help</span><span class="sxs-lookup"><span data-stu-id="73ab0-251">/?, /h, /help</span></span></p></td>
   <td align="left"><p><span data-ttu-id="73ab0-252">请求有关以前的安装参数的帮助。</span><span class="sxs-lookup"><span data-stu-id="73ab0-252">Requests help about the previous installation parameters.</span></span></p></td>
   </tr>
   </tbody>
   </table>



**<span data-ttu-id="73ab0-253">使用 Windows Installer （.msi）文件安装 App-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="73ab0-253">To install the App-V 5.1 client by using the Windows Installer (.msi) file</span></span>**

1.  <span data-ttu-id="73ab0-254">在目标计算机上安装所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="73ab0-254">Install the required prerequisites on the target computers.</span></span> <span data-ttu-id="73ab0-255">[在开始之前，请查看要执行的操作](#bkmk-clt-install-prereqs)。</span><span class="sxs-lookup"><span data-stu-id="73ab0-255">See [What to do before you start](#bkmk-clt-install-prereqs).</span></span> <span data-ttu-id="73ab0-256">如果未满足任何先决条件，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="73ab0-256">If any prerequisites are not met, the installation will fail.</span></span>

2.  <span data-ttu-id="73ab0-257">在使用 App-v 5.1 Windows Installer （.msi）文件安装客户端之前，请确保目标计算机没有任何挂起的重启。</span><span class="sxs-lookup"><span data-stu-id="73ab0-257">Ensure that the target computers do not have any pending restarts before you install the client using the App-V 5.1 Windows Installer (.msi) files.</span></span> <span data-ttu-id="73ab0-258">Windows Installer 文件不会标记待重启。</span><span class="sxs-lookup"><span data-stu-id="73ab0-258">The Windows Installer files do not flag a pending restart.</span></span>

3.  <span data-ttu-id="73ab0-259">将以下 Windows Installer 文件之一部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="73ab0-259">Deploy one of the following Windows Installer files to the target computer.</span></span> <span data-ttu-id="73ab0-260">你指定的文件必须与目标计算机的配置相匹配。</span><span class="sxs-lookup"><span data-stu-id="73ab0-260">The file that you specify must match the configuration of the target computer.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="73ab0-261">部署类型</span><span class="sxs-lookup"><span data-stu-id="73ab0-261">Type of deployment</span></span></th>
    <th align="left"><span data-ttu-id="73ab0-262">部署此文件</span><span class="sxs-lookup"><span data-stu-id="73ab0-262">Deploy this file</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="73ab0-263">计算机运行的是32位 Microsoft Windows 操作系统</span><span class="sxs-lookup"><span data-stu-id="73ab0-263">Computer is running a 32-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="73ab0-264">appv_client_MSI_x86.msi</span><span class="sxs-lookup"><span data-stu-id="73ab0-264">appv_client_MSI_x86.msi</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="73ab0-265">计算机运行的是64位 Microsoft Windows 操作系统</span><span class="sxs-lookup"><span data-stu-id="73ab0-265">Computer is running a 64-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="73ab0-266">appv_client_MSI_x64.msi</span><span class="sxs-lookup"><span data-stu-id="73ab0-266">appv_client_MSI_x64.msi</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="73ab0-267">你正在部署 app-v 5.1 远程桌面服务客户端</span><span class="sxs-lookup"><span data-stu-id="73ab0-267">You are deploying the App-V 5.1 Remote Desktop Services client</span></span></p></td>
    <td align="left"><p><span data-ttu-id="73ab0-268">appv_client_rds_MSI_x64.msi</span><span class="sxs-lookup"><span data-stu-id="73ab0-268">appv_client_rds_MSI_x64.msi</span></span></p></td>
    </tr>
    </tbody>
    </table>



4.  <span data-ttu-id="73ab0-269">使用下表中的信息，根据目标计算机所需的语言选择要安装的相应语言包 **。**</span><span class="sxs-lookup"><span data-stu-id="73ab0-269">Using the information in the following table, select the appropriate language pack **.msi** to install, based on the desired language for the target computer.</span></span> <span data-ttu-id="73ab0-270">表中的**xxxx**指语言包的目标区域设置。</span><span class="sxs-lookup"><span data-stu-id="73ab0-270">The **xxxx** in the table refers to the target locale of the language pack.</span></span>

    **<span data-ttu-id="73ab0-271">开始之前应了解的事项：</span><span class="sxs-lookup"><span data-stu-id="73ab0-271">What to know before you start:</span></span>**

    -   <span data-ttu-id="73ab0-272">标准 App-v 5.1 客户端和 app-v 5.1 客户端的远程桌面服务版本均共有语言包。</span><span class="sxs-lookup"><span data-stu-id="73ab0-272">The language packs are common to both the standard App-V 5.1 client and the Remote Desktop Services version of the App-V 5.1 client.</span></span>

    -   <span data-ttu-id="73ab0-273">如果您使用 **.exe**安装 app-v 5.1 客户端，安装程序将仅部署与目标计算机上运行的操作系统匹配的语言包。</span><span class="sxs-lookup"><span data-stu-id="73ab0-273">If you install the App-V 5.1 client using the **.exe**, the installer will deploy only the language pack that matches the operating system running on the target computer.</span></span>

    -   <span data-ttu-id="73ab0-274">若要在目标计算机上部署其他语言包，请使用**Windows Installer （.msi）文件中的步骤安装 app-v 5.1 客户端**。</span><span class="sxs-lookup"><span data-stu-id="73ab0-274">To deploy additional language packs on a target computer, use the procedure **To install the App-V 5.1 client by using Windows Installer (.msi) file**.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="73ab0-275">部署类型</span><span class="sxs-lookup"><span data-stu-id="73ab0-275">Type of deployment</span></span></th>
    <th align="left"><span data-ttu-id="73ab0-276">部署此文件</span><span class="sxs-lookup"><span data-stu-id="73ab0-276">Deploy this file</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="73ab0-277">计算机运行的是32位 Microsoft Windows 操作系统</span><span class="sxs-lookup"><span data-stu-id="73ab0-277">Computer is running a 32-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="73ab0-278">appv_client_LP_xxxx_ x86.msi</span><span class="sxs-lookup"><span data-stu-id="73ab0-278">appv_client_LP_xxxx_ x86.msi</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="73ab0-279">计算机运行的是64位 Microsoft Windows 操作系统</span><span class="sxs-lookup"><span data-stu-id="73ab0-279">Computer is running a 64-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="73ab0-280">appv_client_LP_xxxx_ x64.msi</span><span class="sxs-lookup"><span data-stu-id="73ab0-280">appv_client_LP_xxxx_ x64.msi</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="73ab0-281">相关主题</span><span class="sxs-lookup"><span data-stu-id="73ab0-281">Related topics</span></span>


[<span data-ttu-id="73ab0-282">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="73ab0-282">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="73ab0-283">关于 Client 配置设置</span><span class="sxs-lookup"><span data-stu-id="73ab0-283">About Client Configuration Settings</span></span>](about-client-configuration-settings51.md)

[<span data-ttu-id="73ab0-284">如何卸载 App-V 5.1 Client</span><span class="sxs-lookup"><span data-stu-id="73ab0-284">How to Uninstall the App-V 5.1 Client</span></span>](how-to-uninstall-the-app-v-51-client.md)









