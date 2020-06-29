---
title: 关于 MBAM 2.0 SP1
description: 关于 MBAM 2.0 SP1
author: dansimp
ms.assetid: 5ba89ed8-bb6e-407b-82c2-e2e36dd1078e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 73b92cd852d4f75f63f3dcba9f18167012b61401
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803391"
---
# <span data-ttu-id="05f28-103">关于 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="05f28-103">About MBAM 2.0 SP1</span></span>

<span data-ttu-id="05f28-104">本主题介绍 Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）中的更改。</span><span class="sxs-lookup"><span data-stu-id="05f28-104">This topic describes the changes in Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1).</span></span> <span data-ttu-id="05f28-105">有关 MBAM 的一般说明，请参阅[MBAM 2.0 入门](getting-started-with-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="05f28-105">For a general description of MBAM, see [Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md).</span></span>

## <a href="" id="what-s-new-in-mbam-2-0-sp1"></a><span data-ttu-id="05f28-106">MBAM 2.0 SP1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="05f28-106">What’s new in MBAM 2.0 SP1</span></span>

<span data-ttu-id="05f28-107">此版本的 MBAM 提供以下新特性和功能。</span><span class="sxs-lookup"><span data-stu-id="05f28-107">This version of MBAM provides the following new features and functionality.</span></span>

### <span data-ttu-id="05f28-108">Windows 8.1、Windows Server 2012 R2 和 System Center 的支持 2012 R2 配置管理器</span><span class="sxs-lookup"><span data-stu-id="05f28-108">Support for Windows 8.1, Windows Server 2012 R2, and System Center 2012 R2 Configuration Manager</span></span>

<span data-ttu-id="05f28-109">Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）添加了对 Windows 8.1、Windows Server 2012 R2 和 System Center 2012 R2 配置管理器的支持。</span><span class="sxs-lookup"><span data-stu-id="05f28-109">Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1) adds support for Windows 8.1, Windows Server 2012 R2, and System Center 2012 R2 Configuration Manager.</span></span>

### <span data-ttu-id="05f28-110">Microsoft SQL Server 2008 R2 SP2 的支持</span><span class="sxs-lookup"><span data-stu-id="05f28-110">Support for Microsoft SQL Server 2008 R2 SP2</span></span>

<span data-ttu-id="05f28-111">Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）添加对 Microsoft SQL Server 2008 R2 SP2 的支持。</span><span class="sxs-lookup"><span data-stu-id="05f28-111">Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1) adds support for Microsoft SQL Server 2008 R2 SP2.</span></span> <span data-ttu-id="05f28-112">如果你运行的是 Microsoft System Center Configuration Manager 2007 R2，则必须使用 Microsoft SQL Server 2008 R2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="05f28-112">You must use Microsoft SQL Server 2008 R2 or higher if you are running Microsoft System Center Configuration Manager 2007 R2.</span></span>

### <span data-ttu-id="05f28-113">客户反馈汇总</span><span class="sxs-lookup"><span data-stu-id="05f28-113">Customer feedback rollup</span></span>

<span data-ttu-id="05f28-114">MBAM 2.0 SP1 包括一个修补程序，用于解决自 Microsoft BitLocker 管理和监视（MBAM）2.0 版本以来发现的问题。</span><span class="sxs-lookup"><span data-stu-id="05f28-114">MBAM 2.0 SP1 includes a rollup of fixes to address issues that were found since the Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 release.</span></span> <span data-ttu-id="05f28-115">作为这些更改的一部分，在运行 MBAM 与 Microsoft System Center Configuration Manager 2007 时，计算机名称字段现在将显示在 BitLocker 计算机合规性和 BitLocker 企业合规性详细信息报告中。</span><span class="sxs-lookup"><span data-stu-id="05f28-115">As part of these changes, the Computer Name field now appears in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you run MBAM with Microsoft System Center Configuration Manager 2007.</span></span>

### <span data-ttu-id="05f28-116">必须在自助服务门户和管理和监视网站的端口上设置防火墙例外</span><span class="sxs-lookup"><span data-stu-id="05f28-116">Firewall exception must be set on ports for the Self-Service Portal and the Administration and Monitoring website</span></span>

<span data-ttu-id="05f28-117">配置自助服务门户和管理和监视网站时，必须设置防火墙例外以通过指定的端口启用通信。</span><span class="sxs-lookup"><span data-stu-id="05f28-117">When you configure the Self-Service Portal and the Administration and Monitoring website, you must set a firewall exception to enable communication through the specified ports.</span></span> <span data-ttu-id="05f28-118">以前，MBAM 服务器安装会在 Windows 防火墙中自动打开端口。</span><span class="sxs-lookup"><span data-stu-id="05f28-118">Previously, the MBAM server installation opened the ports automatically in Windows Firewall.</span></span>

### <span data-ttu-id="05f28-119">配置管理器中 MBAM 报表的位置已更改</span><span class="sxs-lookup"><span data-stu-id="05f28-119">Location of MBAM reports has changed in Configuration Manager</span></span>

<span data-ttu-id="05f28-120">Configuration Manager 集成拓扑的 MBAM 报表现在位于 MBAM 节点内的子文件夹下。</span><span class="sxs-lookup"><span data-stu-id="05f28-120">MBAM reports for the Configuration Manager integrated topology are now available under subfolders within the MBAM node.</span></span> <span data-ttu-id="05f28-121">子文件夹名称表示子文件夹中报表的语言。</span><span class="sxs-lookup"><span data-stu-id="05f28-121">The subfolder names represent the language of the reports within the subfolder.</span></span>

### <span data-ttu-id="05f28-122">使用 Configuration Manager 安装 MBAM 时，在主站点服务器上安装 MBAM 的功能</span><span class="sxs-lookup"><span data-stu-id="05f28-122">Ability to install MBAM on a primary site server when you install MBAM with Configuration Manager</span></span>

<span data-ttu-id="05f28-123">在使用 Configuration Manager 集成拓扑安装 MBAM 时，可以在主站点服务器或管理中心网站服务器上安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="05f28-123">You can install MBAM on a primary site server or a central administration site server when you install MBAM with the Configuration Manager integrated topology.</span></span> <span data-ttu-id="05f28-124">以前，您需要在管理中心网站服务器上安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="05f28-124">Previously, you were required to install MBAM on a central administration site server.</span></span>

**<span data-ttu-id="05f28-125">重要提示</span><span class="sxs-lookup"><span data-stu-id="05f28-125">Important</span></span>**  
<span data-ttu-id="05f28-126">在其上安装 MBAM 的服务器必须是你的层次结构中的顶层服务器。</span><span class="sxs-lookup"><span data-stu-id="05f28-126">The server on which you install MBAM must be the top-tier server in your hierarchy.</span></span>



<span data-ttu-id="05f28-127">对于 Microsoft System Center Configuration Manager 2007 和 Microsoft System Center 2012 配置管理器，MBAM 安装的运行方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="05f28-127">The MBAM installation works differently for Microsoft System Center Configuration Manager 2007 and Microsoft System Center 2012 Configuration Manager as follows:</span></span>

-   <span data-ttu-id="05f28-128">**配置管理器 2007** ：如果在属于较大配置管理器层次结构的主站点服务器上安装 MBAM，并且具有中心网站父服务器，则 MBAM 将解析中心网站父服务器，并在该父服务器上执行所有安装操作。</span><span class="sxs-lookup"><span data-stu-id="05f28-128">**Configuration Manager 2007** : If you install MBAM on a primary site server that is part of a larger Configuration Manager hierarchy and has a central site parent server, MBAM resolves the central site parent server and performs all of the installation actions on that parent server.</span></span> <span data-ttu-id="05f28-129">安装操作包括检查先决条件以及安装 Configuration Manager 对象和报告。</span><span class="sxs-lookup"><span data-stu-id="05f28-129">The installation actions include checking prerequisites and installing the Configuration Manager objects and reports.</span></span> <span data-ttu-id="05f28-130">例如，如果在作为中心站点父服务器的子站点的主站点服务器上安装 MBAM，则 MBAM 将在父服务器上安装所有 Configuration Manager 对象和报告。</span><span class="sxs-lookup"><span data-stu-id="05f28-130">For example, if you install MBAM on a primary site server that is a child of a central site parent server, MBAM installs all of the Configuration Manager objects and reports on the parent server.</span></span> <span data-ttu-id="05f28-131">如果在父服务器上安装 MBAM，MBAM 将在该父服务器上执行所有安装操作。</span><span class="sxs-lookup"><span data-stu-id="05f28-131">If you install MBAM on the parent server, MBAM performs all of the installation actions on that parent server.</span></span>

-   <span data-ttu-id="05f28-132">**System Center 2012 配置管理器**：如果在主站点服务器或中央管理服务器上安装 MBAM，MBAM 将在该网站服务器上执行所有安装操作。</span><span class="sxs-lookup"><span data-stu-id="05f28-132">**System Center 2012 Configuration Manager** : If you install MBAM on a primary site server or on a central administration server, MBAM performs all of the installation actions on that site server.</span></span>

### <a href="" id="-------------configuration-manager-console-must-be-installed-on-the--computer-on-which-you-install-the-mbam-server"></a> <span data-ttu-id="05f28-133">Configuration Manager 控制台必须安装在安装了 MBAM Server 的计算机上</span><span class="sxs-lookup"><span data-stu-id="05f28-133">Configuration Manager Console must be installed on the computer on which you install the MBAM Server</span></span>

<span data-ttu-id="05f28-134">当你通过 Configuration Manager 集成拓扑安装 MBAM 时，你必须在将安装 MBAM 的同一台计算机上安装 Configuration Manager 控制台。</span><span class="sxs-lookup"><span data-stu-id="05f28-134">When you install MBAM with the Configuration Manager integrated topology, you must install the Configuration Manager Console on the same computer on which MBAM will be installed.</span></span> <span data-ttu-id="05f28-135">如果你使用建议的体系结构（将在[入门中使用 MBAM 和配置管理器](getting-started---using-mbam-with-configuration-manager.md)中所述），请在 Configuration Manager 主站点服务器上安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="05f28-135">If you use the recommended architecture, which is described in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md), you would install MBAM on the Configuration Manager Primary Site Server.</span></span>

### <span data-ttu-id="05f28-136">Configuration Manager 集成拓扑的新设置命令行参数</span><span class="sxs-lookup"><span data-stu-id="05f28-136">New setup command-line parameters for the Configuration Manager integrated topology</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="05f28-137">命令行参数</span><span class="sxs-lookup"><span data-stu-id="05f28-137">Command-Line Parameter</span></span></th>
<th align="left"><span data-ttu-id="05f28-138">说明</span><span class="sxs-lookup"><span data-stu-id="05f28-138">Description</span></span></th>
<th align="left"><span data-ttu-id="05f28-139">示例</span><span class="sxs-lookup"><span data-stu-id="05f28-139">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05f28-140">CM_SSRS_REMOTE_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="05f28-140">CM_SSRS_REMOTE_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="05f28-141">使你能够在远程 SQL Server Reporting Services （SSRS）服务器上安装 Configuration Manager 报告，该服务器属于安装了 MBAM 的同一 Configuration Manager 站点。</span><span class="sxs-lookup"><span data-stu-id="05f28-141">Enables you to install the Configuration Manager reports on a remote SQL Server Reporting Services (SSRS) server that is part of the same Configuration Manager site to which MBAM is installed.</span></span> <span data-ttu-id="05f28-142">你可以将值设置为远程 SSRS 点角色服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="05f28-142">You can set the value to the fully qualified domain name of the remote SSRS point role server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="05f28-143">MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME = ssrsServer</span><span class="sxs-lookup"><span data-stu-id="05f28-143">MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME=ssrsServer.Contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="05f28-144">CM_REPORTS_ONLY</span><span class="sxs-lookup"><span data-stu-id="05f28-144">CM_REPORTS_ONLY</span></span></p></td>
<td align="left"><p><span data-ttu-id="05f28-145">使你可以仅安装配置管理器报表，而无需其他 Configuration Manager 对象，如基线、集合和配置项目。</span><span class="sxs-lookup"><span data-stu-id="05f28-145">Enables you to install only the Configuration Manager reports, without other Configuration Manager objects, such as the baseline, collection, and configuration items.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="05f28-146">注意</span><span class="sxs-lookup"><span data-stu-id="05f28-146">Note</span></span></strong><br/><p><span data-ttu-id="05f28-147">必须将此参数与 CM_REPORTS_COLLECTION_ID 参数结合。</span><span class="sxs-lookup"><span data-stu-id="05f28-147">You must combine this parameter with the CM_REPORTS_COLLECTION_ID parameter.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="05f28-148">有效参数值：</span><span class="sxs-lookup"><span data-stu-id="05f28-148">Valid parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="05f28-149">True</span><span class="sxs-lookup"><span data-stu-id="05f28-149">True</span></span></p></li>
<li><p><span data-ttu-id="05f28-150">False</span><span class="sxs-lookup"><span data-stu-id="05f28-150">False</span></span></p></li>
</ul>
<p><span data-ttu-id="05f28-151">如果要将报表仅安装到远程 SSRS 点角色服务器，则可以将此参数与 CM_SSRS_REMOTE_SERVER_NAME 参数结合使用。</span><span class="sxs-lookup"><span data-stu-id="05f28-151">You can combine this parameter with the CM_SSRS_REMOTE_SERVER_NAME parameter if you want to install the reports only to a remote SSRS point role server.</span></span></p>
<p><span data-ttu-id="05f28-152">如果不设置该参数或将其设置为 False，MBAM 安装程序将安装所有配置管理器对象，包括报告。</span><span class="sxs-lookup"><span data-stu-id="05f28-152">If you do not set the parameter or if you set it to False, MBAM Setup installs all of the Configuration Manager objects, including the reports.</span></span></p></td>
<td align="left"><p><span data-ttu-id="05f28-153">MbamSetup.exe CM_REPORTS_ONLY = True</span><span class="sxs-lookup"><span data-stu-id="05f28-153">MbamSetup.exe CM_REPORTS_ONLY=True</span></span></p>
<p><span data-ttu-id="05f28-154">CM_REPORTS_COLLECTION_ID = SMS00001</span><span class="sxs-lookup"><span data-stu-id="05f28-154">CM_REPORTS_COLLECTION_ID=SMS00001</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05f28-155">CM_REPORTS_COLLECTION_ID</span><span class="sxs-lookup"><span data-stu-id="05f28-155">CM_REPORTS_COLLECTION_ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="05f28-156">一个现有的集合 ID，用于标识报告合规性数据将显示的集合。</span><span class="sxs-lookup"><span data-stu-id="05f28-156">An existing collection ID that identifies the collection for which reporting compliance data will be displayed.</span></span> <span data-ttu-id="05f28-157">你可以指定任何集合 ID。</span><span class="sxs-lookup"><span data-stu-id="05f28-157">You can specify any collection ID.</span></span> <span data-ttu-id="05f28-158">您无需使用 "MBAM 支持的计算机" 集合 ID。</span><span class="sxs-lookup"><span data-stu-id="05f28-158">You are not required to use the “MBAM Supported Computers” collection ID.</span></span></p></td>
<td align="left"><p><span data-ttu-id="05f28-159">MbamSetup.exe CM_REPORTS_ONLY = True</span><span class="sxs-lookup"><span data-stu-id="05f28-159">MbamSetup.exe CM_REPORTS_ONLY=True</span></span></p>
<p><span data-ttu-id="05f28-160">CM_REPORTS_COLLECTION_ID = SMS00001</span><span class="sxs-lookup"><span data-stu-id="05f28-160">CM_REPORTS_COLLECTION_ID=SMS00001</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="05f28-161">打开或关闭自助门户通知文本的功能</span><span class="sxs-lookup"><span data-stu-id="05f28-161">Ability to turn Self-Service Portal notice text on or off</span></span>

<span data-ttu-id="05f28-162">MBAM 2.0 SP1 使你能够在自助服务门户上关闭声明文本。</span><span class="sxs-lookup"><span data-stu-id="05f28-162">MBAM 2.0 SP1 enables you to turn off the notice text on the Self-Service Portal.</span></span> <span data-ttu-id="05f28-163">以前，默认情况下显示通知文本，您无法将其关闭。</span><span class="sxs-lookup"><span data-stu-id="05f28-163">Previously, the notice text displayed by default, and you could not turn it off.</span></span>

**<span data-ttu-id="05f28-164">关闭声明文本</span><span class="sxs-lookup"><span data-stu-id="05f28-164">To turn off the notice text</span></span>**

1.  <span data-ttu-id="05f28-165">在安装了自助服务门户的服务器上，打开 "Internet 信息服务（IIS）"，然后浏览到 " \*\* &gt; Microsoft BitLocker 管理和监视网站" &gt; SelfService &gt; 应用程序设置\*\*。</span><span class="sxs-lookup"><span data-stu-id="05f28-165">On the server where you installed the Self-Service Portal, open Internet Information Services (IIS) and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="05f28-166">在 "**名称**" 列中，选择 " **DisplayNotice**"，然后将值设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="05f28-166">From the **Name** column, select **DisplayNotice**, and set the value to **false**.</span></span>

### <span data-ttu-id="05f28-167">能够本地化将用户指向更多自助服务门户信息的 HelpdeskText 语句</span><span class="sxs-lookup"><span data-stu-id="05f28-167">Ability to localize the HelpdeskText statement that points users to more Self-Service Portal information</span></span>

<span data-ttu-id="05f28-168">你可以配置自助服务门户 "HelpdeskText" 语句的本地化版本，这将告知最终用户使用自助服务门户时如何获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="05f28-168">You can configure a localized version of the Self-Service Portal “HelpdeskText” statement, which tells end users how to get additional help when they are using the Self-Service Portal.</span></span> <span data-ttu-id="05f28-169">如果为语句配置本地化的文本，如以下说明中所述，MBAM 将显示本地化版本。</span><span class="sxs-lookup"><span data-stu-id="05f28-169">If you configure localized text for the statement, as described in the following instructions, MBAM will display the localized version.</span></span> <span data-ttu-id="05f28-170">如果 MBAM 未找到本地化版本，它将显示**HelpdeskText**参数中的值。</span><span class="sxs-lookup"><span data-stu-id="05f28-170">If MBAM does not find the localized version, it displays the value that is in the **HelpdeskText** parameter.</span></span>

**<span data-ttu-id="05f28-171">显示 HelpdeskText 语句的本地化版本</span><span class="sxs-lookup"><span data-stu-id="05f28-171">To display a localized version of the HelpdeskText statement</span></span>**

1.  <span data-ttu-id="05f28-172">在安装了自助服务门户的服务器上，打开 IIS 并浏览到 " \*\* &gt; Microsoft BitLocker 管理和监视网站" &gt; SelfService &gt; 应用程序设置\*\*。</span><span class="sxs-lookup"><span data-stu-id="05f28-172">On the server where you installed the Self-Service Portal, open IIS and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="05f28-173">在 "**操作**" 窗格中，单击 "**添加**" 以打开 "**添加应用程序设置**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="05f28-173">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="05f28-174">在 "**名称**" 字段中，键入**HelpdeskText**\ _ &lt; *语言* &gt; ，其中 &lt; *语言* &gt; 是文本的相应语言代码。</span><span class="sxs-lookup"><span data-stu-id="05f28-174">In the **Name** field, type **HelpdeskText**\_&lt;*language*&gt;, where &lt;*language*&gt; is the appropriate language code for the text.</span></span> <span data-ttu-id="05f28-175">例如，若要使用西班牙语创建本地化的 HelpdeskText 语句，请将参数命名为 HelpdeskText \ _es。</span><span class="sxs-lookup"><span data-stu-id="05f28-175">For example, to create a localized HelpdeskText statement in Spanish, you would name the parameter HelpdeskText\_es-es.</span></span> <span data-ttu-id="05f28-176">有关可使用的有效语言代码的列表，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="05f28-176">For a list of the valid language codes that you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="05f28-177">在 "**值**" 字段中，键入要向最终用户显示的本地化文本。</span><span class="sxs-lookup"><span data-stu-id="05f28-177">In the **Value** field, type the localized text that you want to display to end users.</span></span>

### <span data-ttu-id="05f28-178">能够本地化自助服务门户 HelpdeskURL</span><span class="sxs-lookup"><span data-stu-id="05f28-178">Ability to localize the Self-Service Portal HelpdeskURL</span></span>

<span data-ttu-id="05f28-179">你可以配置自服务门户 HelpdeskURL 的本地化版本，以便默认显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="05f28-179">You can configure a localized version of the Self-Service Portal HelpdeskURL to display to end users by default.</span></span> <span data-ttu-id="05f28-180">如果创建本地化版本（如以下说明所述），MBAM 将查找并显示本地化版本。</span><span class="sxs-lookup"><span data-stu-id="05f28-180">If you create a localized version, as described in the following instructions, MBAM finds and displays the localized version.</span></span> <span data-ttu-id="05f28-181">如果 MBAM 未找到本地化版本，它将显示为 HelpDeskURL 参数配置的 URL。</span><span class="sxs-lookup"><span data-stu-id="05f28-181">If MBAM does not find a localized version, it displays the URL that is configured for the HelpDeskURL parameter.</span></span>

**<span data-ttu-id="05f28-182">显示本地化的 HelpdeskURL</span><span class="sxs-lookup"><span data-stu-id="05f28-182">To display a localized HelpdeskURL</span></span>**

1.  <span data-ttu-id="05f28-183">在安装了自助服务门户的服务器上，打开 IIS 并浏览到 " \*\* &gt; Microsoft BitLocker 管理和监视网站" &gt; SelfService &gt; 应用程序设置\*\*。</span><span class="sxs-lookup"><span data-stu-id="05f28-183">On the server where you installed the Self-Service Portal, open IIS and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="05f28-184">在 "**操作**" 窗格中，单击 "**添加**" 以打开 "**添加应用程序设置**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="05f28-184">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="05f28-185">在 "**名称**" 字段中，键入**HelpdeskURL**\ _ &lt; *语言* &gt; ，其中 &lt; *language* &gt; "语言" 是 URL 的相应语言代码。</span><span class="sxs-lookup"><span data-stu-id="05f28-185">In the **Name** field, type **HelpdeskURL**\_&lt;*language*&gt;, where &lt;*language*&gt; is the appropriate language code for the URL.</span></span> <span data-ttu-id="05f28-186">例如，若要在西班牙语中创建本地化的 HelpdeskURL，请将参数命名为 HelpdeskURL \ _es。</span><span class="sxs-lookup"><span data-stu-id="05f28-186">For example, to create a localized HelpdeskURL in Spanish, you would name the parameter HelpdeskURL\_es-es.</span></span> <span data-ttu-id="05f28-187">有关可使用的有效语言代码的列表，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="05f28-187">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="05f28-188">在 "**值**" 字段中，键入要向最终用户显示的本地化 HelpdeskURL。</span><span class="sxs-lookup"><span data-stu-id="05f28-188">In the **Value** field, type the localized HelpdeskURL that you want to display to end users.</span></span>

### <span data-ttu-id="05f28-189">能够本地化自助服务门户通知文本</span><span class="sxs-lookup"><span data-stu-id="05f28-189">Ability to localize the Self-Service Portal notice text</span></span>

<span data-ttu-id="05f28-190">你可以将本地化声明文本配置为在自助服务门户中默认显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="05f28-190">You can configure localized notice text to display to end users by default in the Self-Service Portal.</span></span> <span data-ttu-id="05f28-191">显示声明文本的 notice.txt 文件位于以下根目录中：</span><span class="sxs-lookup"><span data-stu-id="05f28-191">The notice.txt file, which displays the notice text, is located in the following root directory:</span></span>

<span data-ttu-id="05f28-192">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="05f28-192">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="05f28-193">若要显示本地化声明文本，请创建一个已本地化的 notice.txt 文件，并将其保存在以下目录中的特定语言文件夹下：</span><span class="sxs-lookup"><span data-stu-id="05f28-193">To display localized notice text, you create a localized notice.txt file and save it under a specific language folder in the following directory:</span></span>

<span data-ttu-id="05f28-194">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="05f28-194">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="05f28-195">MBAM 根据以下规则显示声明文本：</span><span class="sxs-lookup"><span data-stu-id="05f28-195">MBAM displays the notice text, based on the following rules:</span></span>

-   <span data-ttu-id="05f28-196">如果在相应的语言文件夹中创建已本地化的 notice.txt 文件，MBAM 将显示本地化声明文本。</span><span class="sxs-lookup"><span data-stu-id="05f28-196">If you create a localized notice.txt file in the appropriate language folder, MBAM displays the localized notice text.</span></span>

-   <span data-ttu-id="05f28-197">如果 MBAM 没有找到 notice.txt 文件的本地化版本，它将在默认 notice.txt 文件中显示文本。</span><span class="sxs-lookup"><span data-stu-id="05f28-197">If MBAM does not find a localized version of the notice.txt file, it displays the text in the default notice.txt file.</span></span>

-   <span data-ttu-id="05f28-198">如果 MBAM 没有找到默认的 notice.txt 文件，它将在自助服务门户中显示默认文本。</span><span class="sxs-lookup"><span data-stu-id="05f28-198">If MBAM does not find a default notice.txt file, it displays the default text in the Self-Service Portal.</span></span>

**<span data-ttu-id="05f28-199">注意</span><span class="sxs-lookup"><span data-stu-id="05f28-199">Note</span></span>**  
<span data-ttu-id="05f28-200">如果最终用户的浏览器设置为不具有相应语言子文件夹或 notice.txt 的语言，则显示以下根目录中 notice.txt 文件中的文本：</span><span class="sxs-lookup"><span data-stu-id="05f28-200">If an end user’s browser is set to a language that does not have a corresponding language subfolder or notice.txt, the text that is in the notice.txt file in the following root directory is displayed:</span></span>

<span data-ttu-id="05f28-201">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="05f28-201">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\



**<span data-ttu-id="05f28-202">创建本地化的 notice.txt 文件</span><span class="sxs-lookup"><span data-stu-id="05f28-202">To create a localized notice.txt file</span></span>**

1.  <span data-ttu-id="05f28-203">在安装了自助服务门户的服务器上，在 &lt; *language* &gt; 以下目录中创建一个语言文件夹，其中的 &lt; *语言* &gt; 表示本地化语言的名称：</span><span class="sxs-lookup"><span data-stu-id="05f28-203">On the server where you installed the Self-Service Portal, create a &lt;*language*&gt; folder in the following directory, where &lt;*language*&gt; represents the name of the localized language:</span></span>

    <span data-ttu-id="05f28-204">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="05f28-204">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

    **<span data-ttu-id="05f28-205">注意</span><span class="sxs-lookup"><span data-stu-id="05f28-205">Note</span></span>**  
    <span data-ttu-id="05f28-206">某些语言文件夹已存在，因此你可能不需要创建一个。</span><span class="sxs-lookup"><span data-stu-id="05f28-206">Some language folders already exist, so you may not have to create one.</span></span> <span data-ttu-id="05f28-207">如果确实需要创建语言文件夹，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)，了解可用于 &lt; *语言*文件夹的有效名称的列表 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="05f28-207">If you do need to create a language folder, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947) for a list of the valid names that you can use for the &lt;*language*&gt; folder.</span></span>



2.  <span data-ttu-id="05f28-208">创建一个包含本地化声明文本的 notice.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="05f28-208">Create a notice.txt file that contains the localized notice text.</span></span>

3.  <span data-ttu-id="05f28-209">将 notice.txt 文件保存在 " &lt; *语言*" &gt; 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="05f28-209">Save the notice.txt file in the &lt;*language*&gt; folder.</span></span> <span data-ttu-id="05f28-210">例如，若要使用西班牙语创建本地化的 notice.txt 文件，请将本地化的 notice.txt 文件保存在以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="05f28-210">For example, to create a localized notice.txt file in Spanish, you would save the localized notice.txt file in the following folder:</span></span>

    <span data-ttu-id="05f28-211">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\es-es</span><span class="sxs-lookup"><span data-stu-id="05f28-211">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website\\es-es</span></span>

## <span data-ttu-id="05f28-212">升级到 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="05f28-212">Upgrading to MBAM 2.0 SP1</span></span>


<span data-ttu-id="05f28-213">你可以从 MBAM 的任何早期版本升级到 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="05f28-213">You can upgrade to MBAM 2.0 SP1 from any previous version of MBAM.</span></span>

### <span data-ttu-id="05f28-214">升级 MBAM 基础结构</span><span class="sxs-lookup"><span data-stu-id="05f28-214">Upgrading the MBAM infrastructure</span></span>

<span data-ttu-id="05f28-215">你可以将 MBAM Server 基础结构升级到 MBAM 2.0 SP1，如下所示：</span><span class="sxs-lookup"><span data-stu-id="05f28-215">You can upgrade the MBAM Server infrastructure to MBAM 2.0 SP1 as follows:</span></span>

<span data-ttu-id="05f28-216">**手动就地服务器更换**：必须手动卸载现有的 MBAM 服务器基础结构，然后安装 MBAM 2.0 SP1 服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="05f28-216">**Manual in-place server replacement**: You must manually uninstall the existing MBAM Server infrastructure, and then install the MBAM 2.0 SP1 Server infrastructure.</span></span> <span data-ttu-id="05f28-217">不必删除数据库即可进行升级。</span><span class="sxs-lookup"><span data-stu-id="05f28-217">You do not have to remove the databases to do the upgrade.</span></span> <span data-ttu-id="05f28-218">而是选择已创建 MBAM 早期版本的现有数据库。</span><span class="sxs-lookup"><span data-stu-id="05f28-218">Instead, you select the existing databases, which the previous version of MBAM created.</span></span> <span data-ttu-id="05f28-219">MBAM 2.0 SP1 升级安装然后将现有数据库迁移到 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="05f28-219">The MBAM 2.0 SP1 upgrade installation then migrates the existing databases to MBAM 2.0 SP1.</span></span>

<span data-ttu-id="05f28-220">**分布式客户端升级**：如果你使用的是独立的 MBAM 拓扑，则可以在安装 MBAM 2.0 SP1 服务器基础结构后逐步升级 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="05f28-220">**Distributed client upgrade**: If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 SP1 Server infrastructure.</span></span>

<span data-ttu-id="05f28-221">升级 MBAM 服务器基础结构后，MBAM 1.0 或2.0 客户端将成功向 MBAM 2.0 SP1 服务器报告，并将存储恢复数据，但合规性将基于当前已安装的 MBAM 客户端版本的可用策略。</span><span class="sxs-lookup"><span data-stu-id="05f28-221">After you upgrade the MBAM Server infrastructure, MBAM 1.0 or 2.0 Clients will report to the MBAM 2.0 SP1 Server successfully and will store the recovery data, but compliance will be based on the policies available for the MBAM Client version that is currently installed.</span></span> <span data-ttu-id="05f28-222">若要针对 MBAM 2.0 SP1 策略启用报告，必须将客户端计算机升级到 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="05f28-222">To enable reporting against MBAM 2.0 SP1 policies, you must upgrade client computers to MBAM 2.0 SP1.</span></span> <span data-ttu-id="05f28-223">你可以将客户端计算机升级到 MBAM 2.0 SP1 客户端，而不卸载以前的客户端，并且客户端将基于 MBAM 2.0 SP1 策略开始应用和报告。</span><span class="sxs-lookup"><span data-stu-id="05f28-223">You can upgrade the client computers to the MBAM 2.0 SP1 Client without uninstalling the previous Client, and the Client will start to apply and report, based on the MBAM 2.0 SP1 policies.</span></span>

<span data-ttu-id="05f28-224">有关升级 MBAM 服务器的详细信息，请参阅[从早期版本的 MBAM 升级](upgrading-from-previous-versions-of-mbam.md)。</span><span class="sxs-lookup"><span data-stu-id="05f28-224">For more information about upgrading the MBAM servers, see [Upgrading from Previous Versions of MBAM](upgrading-from-previous-versions-of-mbam.md).</span></span>

### <span data-ttu-id="05f28-225">将 MBAM 客户端升级到 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="05f28-225">Upgrading the MBAM Client to MBAM 2.0 SP1</span></span>

<span data-ttu-id="05f28-226">若要将最终用户计算机升级到 MBAM 2.0 SP1 客户端，请在每台客户端计算机上运行**MbamClientSetup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="05f28-226">To upgrade end-user computers to the MBAM 2.0 SP1 Client, run **MbamClientSetup.exe** on each client computer.</span></span> <span data-ttu-id="05f28-227">安装程序会自动将客户端更新到 MBAM 2.0 SP1 客户端。</span><span class="sxs-lookup"><span data-stu-id="05f28-227">The installer automatically updates the Client to the MBAM 2.0 SP1 Client.</span></span> <span data-ttu-id="05f28-228">安装完成后，客户端计算机无需重新启动，MBAM 2.0 SP1 客户端将开始应用并报告 MBAM 2.0 SP1 策略。</span><span class="sxs-lookup"><span data-stu-id="05f28-228">After the installation, client computers do not have to be rebooted, and the MBAM 2.0 SP1 Client starts to apply and report against MBAM 2.0 SP1 policies.</span></span>

<span data-ttu-id="05f28-229">如果你将 MBAM 与 Configuration Manager 配合使用，则必须将 MBAM 客户端计算机升级到 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="05f28-229">If you are using MBAM with Configuration Manager, you must upgrade the MBAM client computers to MBAM 2.0 SP1.</span></span>

<span data-ttu-id="05f28-230">有关升级 MBAM 客户端计算机的详细信息，请参阅[从早期版本的 MBAM 升级](upgrading-from-previous-versions-of-mbam.md)。</span><span class="sxs-lookup"><span data-stu-id="05f28-230">For more information about upgrading the MBAM client computers, see [Upgrading from Previous Versions of MBAM](upgrading-from-previous-versions-of-mbam.md).</span></span>

## <span data-ttu-id="05f28-231">通过 Configuration Manager 安装或升级到 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="05f28-231">Installing or upgrading to MBAM 2.0 SP1 with Configuration Manager</span></span>


<span data-ttu-id="05f28-232">本部分介绍将 MBAM 2.0 SP1 安装为新安装或升级到以前的 MBAM 2.0 SP1 安装时的要求。</span><span class="sxs-lookup"><span data-stu-id="05f28-232">This section describes the requirements when you are installing MBAM 2.0 SP1 as a new installation or as an upgrade to a previous MBAM 2.0 SP1 installation.</span></span>

### <span data-ttu-id="05f28-233">如果你将 MBAM 与 Configuration Manager 配合使用，则安装 MBAM 2.0 SP1 所需的文件</span><span class="sxs-lookup"><span data-stu-id="05f28-233">Required files for installing MBAM 2.0 SP1 if you are using MBAM with Configuration Manager</span></span>

<span data-ttu-id="05f28-234">如果你是第一次安装 MBAM，而你将 MBAM 2.0 SP1 与 System Center Configuration Manager 配合使用，则必须创建或编辑 mof 文件，以使 MBAM 能够使用 Configuration Manager 正常工作。</span><span class="sxs-lookup"><span data-stu-id="05f28-234">If you are installing MBAM for the first time and you are using MBAM 2.0 SP1 with System Center Configuration Manager, you must create or edit mof files to enable MBAM to work correctly with Configuration Manager.</span></span>

-   **<span data-ttu-id="05f28-235">配置 mof 文件</span><span class="sxs-lookup"><span data-stu-id="05f28-235">configuration.mof file</span></span>**

    -   <span data-ttu-id="05f28-236">如果你使用的是 Configuration Manager 2007，则必须编辑配置 mof 文件，方法是从项目中完成步骤 3**更新配置 mof 文件（如果升级到 MBAM 2.0 SP1，并将 MBAM 与 Configuration Manager 2007 一起使用**，这将在此项之后使用）。</span><span class="sxs-lookup"><span data-stu-id="05f28-236">If you are using Configuration Manager 2007, you must edit the configuration.mof file by completing step 3 from the item **Update the configuration.mof file if you upgrade to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007**, which follows this item.</span></span>

    -   <span data-ttu-id="05f28-237">如果您使用的是 System Center 2012 配置管理器，请按照[编辑配置 Mof 文件](edit-the-configurationmof-file.md)中的说明编辑配置 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="05f28-237">If you are using System Center 2012 Configuration Manager, edit the configuration.mof file by following the instructions in [Edit the Configuration.mof File](edit-the-configurationmof-file.md).</span></span>

-   <span data-ttu-id="05f28-238">**sms \ _def mof 文件**-按照[创建或编辑 sms \ _def mof 文件](create-or-edit-the-sms-defmof-file.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="05f28-238">**sms\_def.mof file** – follow the instructions in [Create or Edit the Sms\_def.mof File](create-or-edit-the-sms-defmof-file.md).</span></span>

### <span data-ttu-id="05f28-239">如果升级到 MBAM 2.0 SP1 并将 MBAM 与 Configuration Manager 2007 结合使用，请更新配置 mof 文件</span><span class="sxs-lookup"><span data-stu-id="05f28-239">Update the configuration.mof file if you upgrade to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007</span></span>

<span data-ttu-id="05f28-240">如果你要升级到 MBAM 2.0 SP1，而你将 MBAM 与 Configuration Manager 2007 结合使用，则必须更新配置 mof 文件，以确保 MBAM 2.0 SP1 正常工作。</span><span class="sxs-lookup"><span data-stu-id="05f28-240">If you are upgrading to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007, you must update the configuration.mof file to ensure that MBAM 2.0 SP1 works correctly.</span></span>

**<span data-ttu-id="05f28-241">若要更新 configuration mof 文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05f28-241">To update the configuration.mof file:</span></span>**

1.  <span data-ttu-id="05f28-242">在 Configuration Manager 服务器上，浏览到配置 mof 文件的位置：</span><span class="sxs-lookup"><span data-stu-id="05f28-242">On the Configuration Manager Server, browse to the location of the Configuration.mof file:</span></span>

    <span data-ttu-id="05f28-243">&lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv</span><span class="sxs-lookup"><span data-stu-id="05f28-243">&lt;CMInstallLocation&gt;\\Inboxes\\clifiles.src\\hinv</span></span>\\

    <span data-ttu-id="05f28-244">在默认安装中，安装位置是%systemdrive%\\Program Files （x86） \\Microsoft Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="05f28-244">On a default installation, the installation location is %systemdrive%\\Program Files (x86)\\Microsoft Configuration Manager.</span></span>

2.  <span data-ttu-id="05f28-245">查看追加到配置 mof 文件中的代码块，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="05f28-245">Review the block of code that you appended to the configuration.mof file, and delete it.</span></span> <span data-ttu-id="05f28-246">代码块将与以下步骤中所示类似。</span><span class="sxs-lookup"><span data-stu-id="05f28-246">The block of code will be similar to the one shown in the following step.</span></span>

3.  <span data-ttu-id="05f28-247">复制以下代码块，然后将其追加到配置 mof 文件，将以下必需的 MBAM 类添加到该文件：</span><span class="sxs-lookup"><span data-stu-id="05f28-247">Copy the following block of code, and then append it to the configuration.mof file to add the following required MBAM classes to the file:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL) 

    [Union, ViewSources{"select DeviceId, BitlockerPersistentVolumeId, BitLockerManagementPersistentVolumeId, BitLockerManagementVolumeType, DriveLetter, Compliant, ReasonsForNonCompliance, KeyProtectorTypes, EncryptionMethod, ConversionStatus, ProtectionStatus, IsAutoUnlockEnabled from Mbam_Volume"}, ViewSpaces{"\\\\.\\root\\microsoft\\mbam"}, dynamic, Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class Win32_BitLockerEncryptionDetails
    {
        [PropertySources{"DeviceId"},key]
        String     DeviceId;
        [PropertySources{"BitlockerPersistentVolumeId"}]
        String     BitlockerPersistentVolumeId;
        [PropertySources{"BitLockerManagementPersistentVolumeId"}]
        String     MbamPersistentVolumeId;
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        [PropertySources{"BitLockerManagementVolumeType"}]
        SInt32     MbamVolumeType;
        [PropertySources{"DriveLetter"}]
        String     DriveLetter;
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        [PropertySources{"Compliant"}]
        SInt32     Compliant;
        [PropertySources{"ReasonsForNonCompliance"}]
        SInt32     ReasonsForNonCompliance[];
        [PropertySources{"KeyProtectorTypes"}]
        SInt32     KeyProtectorTypes[];
        [PropertySources{"EncryptionMethod"}]
        SInt32     EncryptionMethod;
        [PropertySources{"ConversionStatus"}]
        SInt32     ConversionStatus;
        [PropertySources{"ProtectionStatus"}]
        SInt32     ProtectionStatus;
        [PropertySources{"IsAutoUnlockEnabled"}]
        Boolean     IsAutoUnlockEnabled;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
     [DYNPROPS]
    Class Win32Reg_MBAMPolicy
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate;
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

     [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy
    {
        KeyName="BitLocker policy";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [DYNPROPS]
    Class Win32Reg_MBAMPolicy_64
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

    [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy_64
    {
        KeyName="BitLocker policy 64";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
         [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,OperatingSystemSKU from Win32_OperatingSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_OperatingSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"OperatingSystemSKU"}]
        uint32     SKU;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,PCSystemType from Win32_ComputerSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_ComputerSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"PCSystemType"}]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================

    ```

### <span data-ttu-id="05f28-248">MBAM 2.0 SP1 的翻译</span><span class="sxs-lookup"><span data-stu-id="05f28-248">Translation of MBAM 2.0 SP1</span></span>

<span data-ttu-id="05f28-249">MBAM 2.0 SP1 现已提供以下语言版本：</span><span class="sxs-lookup"><span data-stu-id="05f28-249">MBAM 2.0 SP1 is now available in the following languages:</span></span>

-   <span data-ttu-id="05f28-250">英语（美国） en-us</span><span class="sxs-lookup"><span data-stu-id="05f28-250">English (United States) en-US</span></span>
-   <span data-ttu-id="05f28-251">法语（法国） fr-fr</span><span class="sxs-lookup"><span data-stu-id="05f28-251">French (France) fr-FR</span></span>
-   <span data-ttu-id="05f28-252">意大利语（意大利） it</span><span class="sxs-lookup"><span data-stu-id="05f28-252">Italian (Italy) it-IT</span></span>
-   <span data-ttu-id="05f28-253">德语（德国） de</span><span class="sxs-lookup"><span data-stu-id="05f28-253">German (Germany) de-DE</span></span>
-   <span data-ttu-id="05f28-254">西班牙语、国际排序（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="05f28-254">Spanish, International Sort (Spain) es-ES</span></span>
-   <span data-ttu-id="05f28-255">朝鲜语（韩国） ko-KR</span><span class="sxs-lookup"><span data-stu-id="05f28-255">Korean (Korea) ko-KR</span></span>
-   <span data-ttu-id="05f28-256">日语（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="05f28-256">Japanese (Japan) ja-JP</span></span>
-   <span data-ttu-id="05f28-257">葡萄牙语（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="05f28-257">Portuguese (Brazil) pt-BR</span></span>
-   <span data-ttu-id="05f28-258">俄语（俄罗斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="05f28-258">Russian (Russia) ru-RU</span></span>
-   <span data-ttu-id="05f28-259">繁体中文 zh-cn&platform-幼圆</span><span class="sxs-lookup"><span data-stu-id="05f28-259">Chinese Traditional zh-TW</span></span>
-   <span data-ttu-id="05f28-260">中文简体 zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="05f28-260">Chinese Simplified zh-CN</span></span>

## <span data-ttu-id="05f28-261">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="05f28-261">How to Get MDOP Technologies</span></span>

<span data-ttu-id="05f28-262">MBAM 2.0 SP1 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="05f28-262">MBAM 2.0 SP1 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="05f28-263">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="05f28-263">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="05f28-264">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="05f28-264">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="05f28-265">相关主题</span><span class="sxs-lookup"><span data-stu-id="05f28-265">Related topics</span></span>

[<span data-ttu-id="05f28-266">MBAM 2.0 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="05f28-266">Release Notes for MBAM 2.0 SP1</span></span>](release-notes-for-mbam-20-sp1.md)









