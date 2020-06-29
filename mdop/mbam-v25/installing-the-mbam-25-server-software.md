---
title: 安装 MBAM 2.5 服务器软件
description: 安装 MBAM 2.5 服务器软件
author: dansimp
ms.assetid: b9dbe697-5400-4bac-acfb-ee6dc6586c30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6612bf52aa53ae693694d7ac02c5cab212d4e24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803359"
---
# <span data-ttu-id="c53dc-103">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="c53dc-103">Installing the MBAM 2.5 Server Software</span></span>


<span data-ttu-id="c53dc-104">本主题介绍了如何使用 Microsoft BitLocker 管理和监视设置向导或使用命令行参数安装 Microsoft BitLocker 管理和监视（MBAM）2.5 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="c53dc-104">This topic describes how to install the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard or by using command-line parameters.</span></span> <span data-ttu-id="c53dc-105">对配置 MBAM 2.5 服务器功能的每台服务器重复服务器安装过程。</span><span class="sxs-lookup"><span data-stu-id="c53dc-105">Repeat the server installation process for each server on which you are configuring MBAM 2.5 Server features.</span></span> <span data-ttu-id="c53dc-106">安装完成后，有关配置服务器功能的步骤，请参阅[配置 MBAM 2.5 服务器功能](configuring-the-mbam-25-server-features.md)。</span><span class="sxs-lookup"><span data-stu-id="c53dc-106">After you finish the installation, see [Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md) for steps about configuring the Server features.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c53dc-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="c53dc-107">Before you start</span></span></th>
<th align="left"><span data-ttu-id="c53dc-108">描述</span><span class="sxs-lookup"><span data-stu-id="c53dc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c53dc-109">查看 MBAM 2.5 规划信息</span><span class="sxs-lookup"><span data-stu-id="c53dc-109">Review the MBAM 2.5 planning information</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="c53dc-110">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="c53dc-110">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="c53dc-111">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="c53dc-111">MBAM 2.5 Supported Configurations</span></span></a></p></li>
<li><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="c53dc-112">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="c53dc-112">High-Level Architecture for MBAM 2.5</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c53dc-113">阅读如何获取日志文件</span><span class="sxs-lookup"><span data-stu-id="c53dc-113">Read how to get log files</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-114">默认情况下，将在本地计算机的% temp% 文件夹中创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="c53dc-114">By default, log files are created in the local computer’s %temp% folder.</span></span> <span data-ttu-id="c53dc-115">若要将日志文件写入特定位置而不是 <strong> % temp </strong> % 文件夹，请使用 <strong> /log </strong> &lt; <em> 位置 </em> &gt; 参数。</span><span class="sxs-lookup"><span data-stu-id="c53dc-115">To write the log files to a specific location rather than to the <strong>%temp</strong>% folder, use the <strong>/log</strong> &lt;<em>location</em>&gt; argument.</span></span></p>
<p><span data-ttu-id="c53dc-116">在 " <strong> </strong> <strong> </strong> <strong> 应用程序和服务日志" 下 &gt; &gt; </strong> 的 "MBAM-设置" 或 "MBAM" 子节点下，可能会在事件查看器中记录其他事件。</span><span class="sxs-lookup"><span data-stu-id="c53dc-116">Additional events might be logged in Event Viewer in the <strong>MBAM-Setup</strong> or <strong>MBAM-Web</strong> nodes under <strong>Applications and Services Logs &gt; Microsoft &gt; Windows</strong>.</span></span> <span data-ttu-id="c53dc-117">例如，如果卸载 MBAM，卸载程序还将卸载 EventViewer 中的 MBAM 和 MBAM Web 日志。</span><span class="sxs-lookup"><span data-stu-id="c53dc-117">For example, if you uninstall MBAM, the uninstaller will also uninstall the MBAM-Setup and MBAM-Web logs in EventViewer.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c53dc-118">使用 Microsoft BitLocker 管理和监视设置向导安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="c53dc-118">Installing the MBAM 2.5 Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard</span></span>


<span data-ttu-id="c53dc-119">使用以下步骤，通过使用 Microsoft BitLocker 管理和监视设置向导安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="c53dc-119">Use these steps to install the MBAM Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="c53dc-120">使用向导安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="c53dc-120">To install the MBAM 2.5 Server software by using the wizard</span></span>**

1.  <span data-ttu-id="c53dc-121">在要安装 MBAM 的服务器上，运行**MBAMserversetup.exe**以启动 Microsoft BitLocker 管理和监视设置向导。</span><span class="sxs-lookup"><span data-stu-id="c53dc-121">On the server where you want to install MBAM, run **MBAMserversetup.exe** to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2.  <span data-ttu-id="c53dc-122">在 "**欢迎**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c53dc-122">On the **Welcome** page, click **Next**.</span></span>

3.  <span data-ttu-id="c53dc-123">阅读并接受 Microsoft 软件许可协议，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="c53dc-123">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="c53dc-124">选择在检查更新时是否使用 Microsoft Update，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c53dc-124">Choose whether to use Microsoft Update when you check for updates, and then click **Next**.</span></span>

5.  <span data-ttu-id="c53dc-125">选择是否参与 "客户体验改善计划"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c53dc-125">Choose whether to participate in the Customer Experience Improvement Program, and then click **Next**.</span></span>

6.  <span data-ttu-id="c53dc-126">若要开始安装，请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="c53dc-126">To start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="c53dc-127">若要在 MBAM 服务器软件完成安装后配置服务器功能，请选择 "在**向导关闭后运行 MBAM 服务器配置**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c53dc-127">To configure the server features after the MBAM Server software finishes installing, select the **Run MBAM Server Configuration after the wizard closes** check box.</span></span> <span data-ttu-id="c53dc-128">或者，你可以稍后通过使用服务器安装在 "**开始**" 菜单上创建的**MBAM 服务器配置**快捷方式来配置 MBAM。</span><span class="sxs-lookup"><span data-stu-id="c53dc-128">Alternatively, you can configure MBAM later by using the **MBAM Server Configuration** shortcut that the server installation creates on your **Start** menu.</span></span>

8.  <span data-ttu-id="c53dc-129">单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="c53dc-129">Click **Finish**.</span></span>

## <span data-ttu-id="c53dc-130">使用命令提示符窗口安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="c53dc-130">Installing the MBAM 2.5 Server software by using a Command Prompt window</span></span>


<span data-ttu-id="c53dc-131">在命令提示符处，键入类似于以下命令的命令来安装 MBAM Server 软件。</span><span class="sxs-lookup"><span data-stu-id="c53dc-131">At a command prompt, type a command similar to the following command to install the MBAM Server software.</span></span>

``` syntax
MbamServerSetup.exe MBAMServerInstall.log
CEIPENABLED=True OPTIN_FOR_MICROFOST_UPDATES=True INSTALLDIR=c:\mbaminstall
```

<span data-ttu-id="c53dc-132">下表介绍了用于安装 MBAM 2.5 服务器软件的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="c53dc-132">The following table describes the command-line parameters for installing the MBAM 2.5 Server software.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c53dc-133">参数</span><span class="sxs-lookup"><span data-stu-id="c53dc-133">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c53dc-134">参数值</span><span class="sxs-lookup"><span data-stu-id="c53dc-134">Parameter value</span></span></th>
<th align="left"><span data-ttu-id="c53dc-135">描述</span><span class="sxs-lookup"><span data-stu-id="c53dc-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c53dc-136">CEIPENABLED</span><span class="sxs-lookup"><span data-stu-id="c53dc-136">CEIPENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-137">真假</span><span class="sxs-lookup"><span data-stu-id="c53dc-137">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-138">True-参与 "客户改善体验计划"，该计划可帮助 Microsoft 识别要改进的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="c53dc-138">True - participate in the Customer Improvement Experience Program, which helps Microsoft identify which MBAM features to improve.</span></span></p>
<p><span data-ttu-id="c53dc-139">False-不参与 "客户改善体验计划"。</span><span class="sxs-lookup"><span data-stu-id="c53dc-139">False – do not participate in the Customer Improvement Experience Program.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c53dc-140">OPTIN_FOR_MICROSOFT_UPDATES</span><span class="sxs-lookup"><span data-stu-id="c53dc-140">OPTIN_FOR_MICROSOFT_UPDATES</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-141">真假</span><span class="sxs-lookup"><span data-stu-id="c53dc-141">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-142">True-使用 Microsoft Update 保持计算机的安全和最新的 Windows 和其他 Microsoft 产品，包括 MBAM。</span><span class="sxs-lookup"><span data-stu-id="c53dc-142">True - use Microsoft Update to keep your computer secure and up-to-date for Windows and other Microsoft products, including MBAM.</span></span></p>
<p><span data-ttu-id="c53dc-143">False-不使用 Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="c53dc-143">False – do not use Microsoft Update</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c53dc-144">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="c53dc-144">INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-145">&lt;路径&gt;</span><span class="sxs-lookup"><span data-stu-id="c53dc-145">&lt;Path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-146">要在其中安装 MBAM 的位置。</span><span class="sxs-lookup"><span data-stu-id="c53dc-146">Location where you want to install MBAM.</span></span></p>
<p><span data-ttu-id="c53dc-147">示例：</span><span class="sxs-lookup"><span data-stu-id="c53dc-147">Example:</span></span></p>
<p><span data-ttu-id="c53dc-148">INSTALLDIR = c:\mbaminstall</span><span class="sxs-lookup"><span data-stu-id="c53dc-148">INSTALLDIR=c:\mbaminstall</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c53dc-149">FORCE_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="c53dc-149">FORCE_UNINSTALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-150">真假</span><span class="sxs-lookup"><span data-stu-id="c53dc-150">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="c53dc-151">True-继续卸载 MBAM 的过程，即使无法删除任何功能也是如此。</span><span class="sxs-lookup"><span data-stu-id="c53dc-151">True - continue the process of uninstalling MBAM, even if any features fail to be removed.</span></span></p>
<p><span data-ttu-id="c53dc-152">False （默认值）如果卸载自定义操作无法删除添加的 MBAM 服务器功能，则卸载将失败，并且 MBAM 将保持安装状态。</span><span class="sxs-lookup"><span data-stu-id="c53dc-152">False (default) if the uninstallation custom action fails to remove an added MBAM Server feature, the uninstallation fails, and MBAM remains installed.</span></span></p>
<p><span data-ttu-id="c53dc-153">在这两种情况下，在尝试卸载 MBAM 期间成功删除的所有功能将保持删除。</span><span class="sxs-lookup"><span data-stu-id="c53dc-153">In both instances, any features that were successfully removed during the attempt to uninstall MBAM stay removed.</span></span></p></td>
</tr>
</tbody>
</table>

 



## <span data-ttu-id="c53dc-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="c53dc-154">Related topics</span></span>


[<span data-ttu-id="c53dc-155">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="c53dc-155">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="c53dc-156">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="c53dc-156">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

 

## <span data-ttu-id="c53dc-157">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="c53dc-157">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="c53dc-158">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="c53dc-158">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="c53dc-159">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="c53dc-159">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





