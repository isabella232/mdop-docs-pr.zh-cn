---
title: 如何配置 MBAM 2.5 Web 应用程序
description: 如何配置 MBAM 2.5 Web 应用程序
author: dansimp
ms.assetid: 909bf2d3-028c-4ac1-9247-171532a1eeae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0336d24f51167a00c8565ccd081f4bc5dfb2c4cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803580"
---
# <span data-ttu-id="e1e05-103">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="e1e05-103">How to Configure the MBAM 2.5 Web Applications</span></span>


<span data-ttu-id="e1e05-104">本主题介绍了如何使用以下方法之一为 MBAM 2.5 配置 Microsoft BitLocker 管理和监视（MBAM） 2.5 web 应用程序以获取推荐的[高级别体系结构](high-level-architecture-for-mbam-25.md)：</span><span class="sxs-lookup"><span data-stu-id="e1e05-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 web applications for the recommended [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md) by using one of the following methods:</span></span>

-   <span data-ttu-id="e1e05-105">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e1e05-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="e1e05-106">MBAM Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="e1e05-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="e1e05-107">Web 应用程序包含以下网站及其相应的 web 服务：</span><span class="sxs-lookup"><span data-stu-id="e1e05-107">The web applications comprise the following websites and their corresponding web services:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1e05-108">Website</span><span class="sxs-lookup"><span data-stu-id="e1e05-108">Website</span></span></th>
<th align="left"><span data-ttu-id="e1e05-109">描述</span><span class="sxs-lookup"><span data-stu-id="e1e05-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1e05-110">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="e1e05-110">Administration and Monitoring Website</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1e05-111">网站，其中指定用户可以查看报表，并帮助最终用户在忘记 PIN 或密码时恢复其计算机</span><span class="sxs-lookup"><span data-stu-id="e1e05-111">Website where specified users can view reports and help end users recover their computers when they forget their PIN or password</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1e05-112">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="e1e05-112">Self-Service Portal</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1e05-113">最终用户可以访问的网站，如果他们忘记了 PIN 或密码，可以独立地重新获得其计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="e1e05-113">Website that end users can access to independently regain access to their computers if they forget their PIN or password</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e1e05-114">开始配置之前：</span><span class="sxs-lookup"><span data-stu-id="e1e05-114">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1e05-115">步骤</span><span class="sxs-lookup"><span data-stu-id="e1e05-115">Step</span></span></th>
<th align="left"><span data-ttu-id="e1e05-116">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="e1e05-116">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1e05-117">查看建议的 MBAM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="e1e05-117">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="e1e05-118">MBAM 2.5 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="e1e05-118">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1e05-119">查看 MBAM 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="e1e05-119">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="e1e05-120">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="e1e05-120">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1e05-121">在每台服务器上完成所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1e05-121">Complete the required prerequisites on each server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e1e05-122">注意</span><span class="sxs-lookup"><span data-stu-id="e1e05-122">Note</span></span></strong><br/><p><span data-ttu-id="e1e05-123">在配置管理和监视网站之前，请确保将 SQL ServerReporting Services （SSRS）配置为使用安全套接字层（SSL）。</span><span class="sxs-lookup"><span data-stu-id="e1e05-123">Ensure that you configure SQL ServerReporting Services (SSRS) to use the Secure Sockets Layer (SSL) before you configure the Administration and Monitoring Website.</span></span> <span data-ttu-id="e1e05-124">否则，"报表" 功能将使用 HTTP 而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="e1e05-124">Otherwise, the Reports feature will use HTTP instead of HTTPS.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="e1e05-125">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="e1e05-125">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="e1e05-126">仅适用于 Configuration Manager 集成拓扑 </a> （如果适用）的 MBAM 2.5 服务器必备条件</span><span class="sxs-lookup"><span data-stu-id="e1e05-126">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1e05-127">注册网站的应用程序池帐户的服务主体名称（Spn）。</span><span class="sxs-lookup"><span data-stu-id="e1e05-127">Register service principal names (SPNs) for the application pool account for the websites.</span></span> <span data-ttu-id="e1e05-128">只有在 Active Directory 域服务（AD DS）中没有管理域权限的情况下，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="e1e05-128">You need to do this step only if you do not have administrative domain rights in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="e1e05-129">如果你在 AD DS 中拥有这些权限，MBAM 将为你创建 Spn。</span><span class="sxs-lookup"><span data-stu-id="e1e05-129">If you do have these rights in AD DS, MBAM will create the SPNs for you.</span></span></p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn)"><span data-ttu-id="e1e05-130">规划如何保护 MBAM 网站</span><span class="sxs-lookup"><span data-stu-id="e1e05-130">Planning How to Secure the MBAM Websites</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1e05-131">在将在其中配置 MBAM 服务器功能的每台服务器上安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="e1e05-131">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e1e05-132">注意</span><span class="sxs-lookup"><span data-stu-id="e1e05-132">Note</span></span></strong><br/><p><span data-ttu-id="e1e05-133">如果你计划在一台服务器上安装网站，并在另一台服务器上安装 web 服务，你将只能通过使用 <strong> Enable-MbamWebApplication </strong> Windows PowerShell cmdlet 来配置它们。</span><span class="sxs-lookup"><span data-stu-id="e1e05-133">If you plan to install the websites on one server and the web services on another, you will be able to configure them only by using the <strong>Enable-MbamWebApplication</strong> Windows PowerShell cmdlet.</span></span> <span data-ttu-id="e1e05-134">MBAM Server 配置向导不支持在单独的服务器上配置这些项目。</span><span class="sxs-lookup"><span data-stu-id="e1e05-134">The MBAM Server Configuration wizard does not support configuring these items on separate servers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="e1e05-135">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="e1e05-135">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1e05-136">如果计划使用 cmdlet 配置 MBAM Server 功能，请查看使用 Windows PowerShell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1e05-136">Review the prerequisites for using Windows PowerShell if you plan to use cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="e1e05-137">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="e1e05-137">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e1e05-138">使用 Windows PowerShell 配置 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="e1e05-138">To configure the web applications by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="e1e05-139">在开始配置之前，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1e05-139">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="e1e05-140">使用**MbamWebApplication** cmdlet 配置使用 Windows PowerShell 的 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e1e05-140">Use the **Enable-MbamWebApplication** cmdlet to configure the web applications using Windows PowerShell.</span></span> <span data-ttu-id="e1e05-141">若要获取有关此 cmdlet 的信息，请键入**Get-help Enable-MbamWebApplication**。</span><span class="sxs-lookup"><span data-stu-id="e1e05-141">To get information about this cmdlet, type **Get-Help Enable-MbamWebApplication**.</span></span>

**<span data-ttu-id="e1e05-142">使用向导配置所有 web 应用程序的设置</span><span class="sxs-lookup"><span data-stu-id="e1e05-142">To configure the settings for all web applications using the wizard</span></span>**

1. <span data-ttu-id="e1e05-143">在要配置 web 应用程序的服务器上，启动 "MBAM 服务器配置向导"。</span><span class="sxs-lookup"><span data-stu-id="e1e05-143">On the server where you want to configure the web applications, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="e1e05-144">可以从 "**开始**" 菜单中选择 " **MBAM 服务器配置**" 以打开该向导。</span><span class="sxs-lookup"><span data-stu-id="e1e05-144">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="e1e05-145">单击 "**添加新功能**"，选择 "**管理和监视网站**和**自助服务门户**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e1e05-145">Click **Add New Features**, select **Administration and Monitoring Website** and **Self-Service Portal**, and then click **Next**.</span></span> <span data-ttu-id="e1e05-146">向导检查是否满足 web 应用程序的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1e05-146">The wizard checks that all prerequisites for the web applications have been met.</span></span>

3. <span data-ttu-id="e1e05-147">如果先决条件检查成功，请单击 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="e1e05-147">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="e1e05-148">否则，请解决任何缺少的先决条件，然后**再次单击 "检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="e1e05-148">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4. <span data-ttu-id="e1e05-149">使用以下说明在向导中输入字段值。</span><span class="sxs-lookup"><span data-stu-id="e1e05-149">Use the following descriptions to enter the field values in the wizard.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><strong><span data-ttu-id="e1e05-150">字段</span><span class="sxs-lookup"><span data-stu-id="e1e05-150">Field</span></span></strong></th>
   <th align="left"><span data-ttu-id="e1e05-151">描述</span><span class="sxs-lookup"><span data-stu-id="e1e05-151">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-152">安全证书</span><span class="sxs-lookup"><span data-stu-id="e1e05-152">Security certificate</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-153">选择以前创建的证书，以选择性地加密 web 服务与正在配置网站的服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="e1e05-153">Select a previously created certificate to optionally encrypt the communication between the web services and the server on which you are configuring the websites.</span></span> <span data-ttu-id="e1e05-154">如果您选择 <strong> "不使用证书 </strong> "，则您的 web 通信可能不安全。</span><span class="sxs-lookup"><span data-stu-id="e1e05-154">If you choose <strong>Do not use a certificate</strong>, your web communication may not be secure.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e1e05-155">主机名</span><span class="sxs-lookup"><span data-stu-id="e1e05-155">Host name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-156">要在其中配置网站的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="e1e05-156">Name of the host computer where you are configuring the websites.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-157">安装路径</span><span class="sxs-lookup"><span data-stu-id="e1e05-157">Installation path</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-158">要在其中安装网站的路径。</span><span class="sxs-lookup"><span data-stu-id="e1e05-158">Path where you are installing the websites.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e1e05-159">端口</span><span class="sxs-lookup"><span data-stu-id="e1e05-159">Port</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-160">用于网站和服务通信的端口号。</span><span class="sxs-lookup"><span data-stu-id="e1e05-160">Port number to use for website and service communication.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e1e05-161">注意</span><span class="sxs-lookup"><span data-stu-id="e1e05-161">Note</span></span></strong><br/><p><span data-ttu-id="e1e05-162">必须设置防火墙例外以通过指定的端口启用通信。</span><span class="sxs-lookup"><span data-stu-id="e1e05-162">You must set a firewall exception to enable communication through the specified port.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-163">Web 服务应用程序池域帐户和密码</span><span class="sxs-lookup"><span data-stu-id="e1e05-163">Web service application pool domain account and password</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-164">Web 服务应用程序池的域用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="e1e05-164">Domain user account and password for the web service application pool.</span></span></p>
   <p><span data-ttu-id="e1e05-165">如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入用户名 </strong> <strong> </strong> ，则必须在此字段中输入相同的值。</span><span class="sxs-lookup"><span data-stu-id="e1e05-165">If you enter a user name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, you must enter that same value in this field.</span></span></p>
   <p><span data-ttu-id="e1e05-166">如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入组名称 </strong> <strong> </strong> ，则在此字段中输入的值必须是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="e1e05-166">If you enter a group name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, the value you enter in this field must be a member of that group.</span></span></p>
   <p><span data-ttu-id="e1e05-167">如果不指定凭据，将使用为以前启用的任何 web 应用程序指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="e1e05-167">If you do not specify credentials, the credentials that were specified for any previously enabled web application will be used.</span></span> <span data-ttu-id="e1e05-168">所有 web 应用程序都必须使用相同的应用程序池凭据。</span><span class="sxs-lookup"><span data-stu-id="e1e05-168">All web applications must use the same application pool credentials.</span></span> <span data-ttu-id="e1e05-169">如果为不同的 web 应用程序指定不同的凭据，将使用最近指定的值。</span><span class="sxs-lookup"><span data-stu-id="e1e05-169">If you specify different credentials for different web applications, the most recently specified value will be used.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e1e05-170">重要提示</span><span class="sxs-lookup"><span data-stu-id="e1e05-170">Important</span></span></strong><br/><p><span data-ttu-id="e1e05-171">为了提高安全性，请将凭据中指定的帐户设置为具有受限的用户权限。</span><span class="sxs-lookup"><span data-stu-id="e1e05-171">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span> <span data-ttu-id="e1e05-172">此外，将帐户的密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="e1e05-172">Also, set the password of the account to never expire.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="e1e05-173">验证内置 IIS \ _IUSRS 帐户或应用程序池帐户是否已添加到**身份验证后模拟客户端**，以及**作为批处理作业**的本地安全设置登录。</span><span class="sxs-lookup"><span data-stu-id="e1e05-173">Verify that the built-in IIS\_IUSRS account or the application pool account has been added to the **Impersonate a client after authentication** and the **Log on as a batch job** local security settings.</span></span>

   <span data-ttu-id="e1e05-174">若要检查是否已将其添加到本地安全设置，请打开 "**本地安全策略编辑器**"，展开 "**本地策略**" 节点，单击 "**用户权限分配**" 节点，然后双击 "在**身份验证后模拟客户端**" 和 "在右窗格中**作为批处理作业登录**" 策略。</span><span class="sxs-lookup"><span data-stu-id="e1e05-174">To check whether it has been added to the local security settings, open the **Local Security Policy editor**, expand the **Local Policies** node, click the **User Rights Assignment** node, and double-click **Impersonate a client after authentication** and **Log on as a batch job** policies in the right pane.</span></span>

**<span data-ttu-id="e1e05-175">使用向导配置数据库的连接信息</span><span class="sxs-lookup"><span data-stu-id="e1e05-175">To configure connection information for the databases by using the wizard</span></span>**

1.  <span data-ttu-id="e1e05-176">使用以下字段说明为合规性和审核数据库配置向导中的连接信息。</span><span class="sxs-lookup"><span data-stu-id="e1e05-176">Use the following field descriptions to configure the connection information in the wizard for the Compliance and Audit Database.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e1e05-177">字段</span><span class="sxs-lookup"><span data-stu-id="e1e05-177">Field</span></span></th>
    <th align="left"><span data-ttu-id="e1e05-178">描述</span><span class="sxs-lookup"><span data-stu-id="e1e05-178">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="e1e05-179">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="e1e05-179">SQL Server name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="e1e05-180">配置合规性和审核数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="e1e05-180">Name of the server where the Compliance and Audit Database is configured.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="e1e05-181">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="e1e05-181">SQL Server database instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="e1e05-182">配置合规性和审核数据库的 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="e1e05-182">SQL Server instance name where the Compliance and Audit Database is configured.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="e1e05-183">数据库名称</span><span class="sxs-lookup"><span data-stu-id="e1e05-183">Database name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="e1e05-184">合规性和审核数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e1e05-184">Name of the Compliance and Audit Database.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="e1e05-185">使用以下字段说明为恢复数据库配置向导中的连接信息。</span><span class="sxs-lookup"><span data-stu-id="e1e05-185">Use the following field descriptions to configure the connection information in the wizard for the Recovery Database.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e1e05-186">字段</span><span class="sxs-lookup"><span data-stu-id="e1e05-186">Field</span></span></th>
    <th align="left"><span data-ttu-id="e1e05-187">描述</span><span class="sxs-lookup"><span data-stu-id="e1e05-187">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="e1e05-188">SQL Server 名称</span><span class="sxs-lookup"><span data-stu-id="e1e05-188">SQL Server name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="e1e05-189">配置恢复数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="e1e05-189">Name of the server where the Recovery Database is configured.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="e1e05-190">SQL Server 数据库实例</span><span class="sxs-lookup"><span data-stu-id="e1e05-190">SQL Server database instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="e1e05-191">在其中配置了恢复数据库的 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="e1e05-191">SQL Server instance name where the Recovery Database is configured.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="e1e05-192">数据库名称</span><span class="sxs-lookup"><span data-stu-id="e1e05-192">Database name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="e1e05-193">恢复数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e1e05-193">Name of the Recovery Database.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="e1e05-194">使用向导配置 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="e1e05-194">To configure the web applications by using the wizard</span></span>**

1. <span data-ttu-id="e1e05-195">使用以下说明在向导中输入字段值以配置管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="e1e05-195">Use the following descriptions to enter the field values in the wizard to configure the Administration and Monitoring Website.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="e1e05-196">字段</span><span class="sxs-lookup"><span data-stu-id="e1e05-196">Field</span></span></th>
   <th align="left"><span data-ttu-id="e1e05-197">描述</span><span class="sxs-lookup"><span data-stu-id="e1e05-197">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-198">高级帮助台角色域组</span><span class="sxs-lookup"><span data-stu-id="e1e05-198">Advanced Helpdesk role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-199">其成员有权访问管理和监视网站的所有区域（"报表" 区域除外）的域用户组。</span><span class="sxs-lookup"><span data-stu-id="e1e05-199">Domain user group whose members have access to all areas of the Administration and Monitoring Website except the Reports area.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e1e05-200">帮助台角色域组</span><span class="sxs-lookup"><span data-stu-id="e1e05-200">Helpdesk role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-201">其成员有权访问 <strong> </strong> 管理和监视网站的 "管理 TPM" 和 " <strong> 驱动器恢复" 区域的域用户组 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e1e05-201">Domain user group whose members have access to the <strong>Manage TPM</strong> and <strong>Drive Recovery</strong> areas of the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-202">使用 System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="e1e05-202">Use System Center Configuration Manager Integration</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-203">如果你正在通过 Configuration Manager 集成拓扑配置 MBAM，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="e1e05-203">Select this check box if you are configuring MBAM with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="e1e05-204">选中此复选框将使除 "恢复审核报告" 之外的所有报告显示在 Configuration Manager 中，而不是在 "管理和监视" 网站中显示。</span><span class="sxs-lookup"><span data-stu-id="e1e05-204">Selecting this check box makes all reports, except the Recovery Audit report, appear in Configuration Manager instead of in the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e1e05-205">报告角色域组</span><span class="sxs-lookup"><span data-stu-id="e1e05-205">Reporting role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-206">其成员对管理和监视网站的 "报告" 区域具有只读访问权限的域用户组。</span><span class="sxs-lookup"><span data-stu-id="e1e05-206">Domain user group whose members have read-only access to the Reports area of the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-207">SQL Server Reporting Services URL</span><span class="sxs-lookup"><span data-stu-id="e1e05-207">SQL Server Reporting Services URL</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-208">配置了 MBAM 报表的 SSRS 服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="e1e05-208">URL for the SSRS server where the MBAM Reports are configured.</span></span></p>
   <p><span data-ttu-id="e1e05-209">报表 Url 的示例：</span><span class="sxs-lookup"><span data-stu-id="e1e05-209">Examples of report URLs:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="e1e05-210">主机名的类型</span><span class="sxs-lookup"><span data-stu-id="e1e05-210">Type of host name</span></span></th>
   <th align="left"><span data-ttu-id="e1e05-211">示例</span><span class="sxs-lookup"><span data-stu-id="e1e05-211">Example</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="e1e05-212">具有完全限定的域名的示例</span><span class="sxs-lookup"><span data-stu-id="e1e05-212">Example with a fully qualified domain name</span></span></p></td>
   <td align="left"><p><a href="https://MyReportServer.Contoso.com/ReportServer" data-raw-source="https://MyReportServer.Contoso.com/ReportServer">https://MyReportServer.Contoso.com/ReportServer</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="e1e05-213">带有自定义主机名的示例</span><span class="sxs-lookup"><span data-stu-id="e1e05-213">Example with a custom host name</span></span></p></td>
   <td align="left"><p><a href="https://MyReportServer/ReportServer" data-raw-source="https://MyReportServer/ReportServer">https://MyReportServer/ReportServer</a></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e1e05-214">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="e1e05-214">Virtual directory</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-215">管理和监视网站的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="e1e05-215">Virtual directory of the Administration and Monitoring Website.</span></span> <span data-ttu-id="e1e05-216">此名称对应于服务器上网站的物理目录，并附加到网站的主机名称，例如：</span><span class="sxs-lookup"><span data-stu-id="e1e05-216">This name corresponds to the website’s physical directory on the server and is appended to the website’s host name, for example:</span></span></p>
   <p><span data-ttu-id="e1e05-217">http （s）：// &lt; <em> 主机名 </em> &gt; ： &lt; <em> 端口 </em> &gt; /HelpDesk/</span><span class="sxs-lookup"><span data-stu-id="e1e05-217">http(s)://&lt;<em>hostname</em>&gt;:&lt;<em>port</em>&gt;/HelpDesk/</span></span></p>
   <p><span data-ttu-id="e1e05-218">如果不指定虚拟目录， <strong> 将使用值帮助台 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e1e05-218">If you do not specify a virtual directory, the value <strong>HelpDesk</strong> will be used.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-219">数据迁移角色域组 </strong> （可选）</span><span class="sxs-lookup"><span data-stu-id="e1e05-219">Data Migration role domain group</strong> (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-220">其成员有权使用 Write Mbam \* 信息 Cmdlet 来通过此终结点写入恢复信息的域用户组。</span><span class="sxs-lookup"><span data-stu-id="e1e05-220">Domain user group whose members have access to use the Write-Mbam\*Information Cmdlets to write recovery information via this endpoint.</span></span></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="e1e05-221">使用以下说明在向导中输入字段值以配置自助服务门户。</span><span class="sxs-lookup"><span data-stu-id="e1e05-221">Use the following description to enter the field values in the wizard to configure the Self-Service Portal.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="e1e05-222">字段</span><span class="sxs-lookup"><span data-stu-id="e1e05-222">Field</span></span></th>
   <th align="left"><span data-ttu-id="e1e05-223">描述</span><span class="sxs-lookup"><span data-stu-id="e1e05-223">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e1e05-224">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="e1e05-224">Virtual directory</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-225">Web 应用程序的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="e1e05-225">Virtual directory of the web application.</span></span> <span data-ttu-id="e1e05-226">此名称对应于服务器上网站的物理目录，并附加到网站的主机名称，例如：</span><span class="sxs-lookup"><span data-stu-id="e1e05-226">This name corresponds to the website’s physical directory on the server, and is appended to the website’s host name, for example:</span></span></p>
   <p><span data-ttu-id="e1e05-227">http （s）：// &lt; <em> 主机名 </em> &gt; ： &lt; <em> 端口 </em> &gt; /SelfService/</span><span class="sxs-lookup"><span data-stu-id="e1e05-227">http(s)://&lt;<em>hostname</em>&gt;:&lt;<em>port</em>&gt;/SelfService/</span></span></p>
   <p><span data-ttu-id="e1e05-228">如果不指定虚拟目录， <strong> </strong> 将使用值 SelfService。</span><span class="sxs-lookup"><span data-stu-id="e1e05-228">If you do not specify a virtual directory, the value <strong>SelfService</strong> will be used.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="e1e05-229">公司名称</span><span class="sxs-lookup"><span data-stu-id="e1e05-229">Company name</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-230">为自助服务门户指定公司名称，例如：</span><span class="sxs-lookup"><span data-stu-id="e1e05-230">Specify a company name for the Self-Service Portal, for example:</span></span></p>
   <p><span data-ttu-id="e1e05-231">Contoso IT</span><span class="sxs-lookup"><span data-stu-id="e1e05-231">Contoso IT</span></span></p>
   <p><span data-ttu-id="e1e05-232">此公司名称由所有自助门户用户查看。</span><span class="sxs-lookup"><span data-stu-id="e1e05-232">This company name is viewed by all Self-Service Portal users.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="e1e05-233">帮助台 URL 文本</span><span class="sxs-lookup"><span data-stu-id="e1e05-233">Helpdesk URL text</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-234">指定将用户定向到组织的帮助台网站的文本语句，例如：</span><span class="sxs-lookup"><span data-stu-id="e1e05-234">Specify a text statement that directs users to your organization's Helpdesk website, for example:</span></span></p>
   <p><span data-ttu-id="e1e05-235">联系支持人员或 IT 部门</span><span class="sxs-lookup"><span data-stu-id="e1e05-235">Contact Helpdesk or IT department</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="e1e05-236">帮助台 URL</span><span class="sxs-lookup"><span data-stu-id="e1e05-236">Helpdesk URL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-237">指定组织的帮助程序网站的 URL，例如：</span><span class="sxs-lookup"><span data-stu-id="e1e05-237">Specify the URL for your organization's Helpdesk website, for example:</span></span></p>
   <p><span data-ttu-id="e1e05-238">http （s）：// &lt; <em> companyHelpdeskURL</em>&gt;/</span><span class="sxs-lookup"><span data-stu-id="e1e05-238">http(s)://&lt;<em>companyHelpdeskURL</em>&gt;/</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="e1e05-239">通知文本文件</span><span class="sxs-lookup"><span data-stu-id="e1e05-239">Notice text file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-240">选择包含要在自助服务门户登录页面上向用户显示的通知的文件。</span><span class="sxs-lookup"><span data-stu-id="e1e05-240">Select a file that contains the notice you want displayed to users on the Self-Service Portal landing page.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="e1e05-241">不向用户显示通知文本</span><span class="sxs-lookup"><span data-stu-id="e1e05-241">Do not display notice text to users</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1e05-242">选中此复选框以指定不向用户显示声明文本。</span><span class="sxs-lookup"><span data-stu-id="e1e05-242">Select this check box to specify that the notice text is not displayed to users.</span></span></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="e1e05-243">完成输入后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e1e05-243">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="e1e05-244">向导检查是否满足 web 应用程序的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1e05-244">The wizard checks that all prerequisites for the web applications have been met.</span></span>

4. <span data-ttu-id="e1e05-245">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="e1e05-245">Click **Next** to continue.</span></span>

5. <span data-ttu-id="e1e05-246">在 "**摘要**" 页面上，查看将添加的功能。</span><span class="sxs-lookup"><span data-stu-id="e1e05-246">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="e1e05-247">注意</span><span class="sxs-lookup"><span data-stu-id="e1e05-247">Note</span></span>**  
   <span data-ttu-id="e1e05-248">若要为您所创建的条目创建 Windows PowerShell 脚本，请单击 "**导出 PowerShell 脚本**" 并保存脚本。</span><span class="sxs-lookup"><span data-stu-id="e1e05-248">To create a Windows PowerShell script for the entries you made, click **Export PowerShell Script** and save the script.</span></span>



6. <span data-ttu-id="e1e05-249">单击 "**添加**" 以将 web 应用程序添加到服务器，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e1e05-249">Click **Add** to add the web applications to the server, and then click **Close**.</span></span>

   <span data-ttu-id="e1e05-250">若要通过添加自定义声明文本、公司名称、指向详细信息的指针自定义自助服务门户，请参阅[自定义组织的自助服务门户](customizing-the-self-service-portal-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="e1e05-250">To customize the Self-Service Portal by adding custom notice text, your company name, pointers to more information, and so on, see [Customizing the Self-Service Portal for Your Organization](customizing-the-self-service-portal-for-your-organization.md).</span></span>

**<span data-ttu-id="e1e05-251">如果客户端计算机无法访问 CDN，则配置自助服务门户</span><span class="sxs-lookup"><span data-stu-id="e1e05-251">To configure the Self-Service Portal if client computers cannot access the CDN</span></span>**

1.  <span data-ttu-id="e1e05-252">确定你是否正在运行 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="e1e05-252">Determine whether you are running Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1.</span></span> <span data-ttu-id="e1e05-253">如果是，则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e1e05-253">If so, do nothing.</span></span> <span data-ttu-id="e1e05-254">您的自助服务门户配置已完成。</span><span class="sxs-lookup"><span data-stu-id="e1e05-254">Your Self-Service Portal configuration is complete.</span></span>

    **<span data-ttu-id="e1e05-255">注意</span><span class="sxs-lookup"><span data-stu-id="e1e05-255">Note</span></span>**  
    <span data-ttu-id="e1e05-256">Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 在安装程序中安装 JavaScript 文件，因此无需连接到 Microsoft Ajax 内容传递网络即可配置自助服务门户。</span><span class="sxs-lookup"><span data-stu-id="e1e05-256">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 installs the JavaScript files in setup, and so does not need to be connected to the Microsoft Ajax Content Delivery Network in order to configure the Self-Service Portal.</span></span> <span data-ttu-id="e1e05-257">只有在 SP1 之前使用版本的 Microsoft BitLocker 管理和监视（MBAM）2.5 时，才需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e1e05-257">The following steps are necessary only if you are using a version of Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 previous to SP1.</span></span>



2.  <span data-ttu-id="e1e05-258">确定客户端计算机是否有权访问 Microsoft Ajax 内容交付网络（CDN）。</span><span class="sxs-lookup"><span data-stu-id="e1e05-258">Determine if your client computers have access to the Microsoft Ajax Content Delivery Network (CDN).</span></span>

    <span data-ttu-id="e1e05-259">CDN 为自助服务门户提供对某些 JavaScript 文件所需的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e1e05-259">The CDN gives the Self-Service Portal the access it requires to certain JavaScript files.</span></span> <span data-ttu-id="e1e05-260">如果在客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和用于登录的最终用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e1e05-260">If you don’t configure the Self-Service Portal when client computers cannot access the CDN, only the company name and the account under which the end user signed in will be displayed.</span></span> <span data-ttu-id="e1e05-261">将不会显示任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="e1e05-261">No error message will be shown.</span></span>

3.  <span data-ttu-id="e1e05-262">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e1e05-262">Do one of the following:</span></span>

    -   <span data-ttu-id="e1e05-263">如果你的客户端计算机有权访问 CDN，请执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e1e05-263">If your client computers have access to the CDN, do nothing.</span></span> <span data-ttu-id="e1e05-264">您的自助服务门户配置已完成。</span><span class="sxs-lookup"><span data-stu-id="e1e05-264">Your Self-Service Portal configuration is complete.</span></span>

    -   <span data-ttu-id="e1e05-265">如果客户端计算机不具有 CDN 的访问权限，请完成在[客户端计算机无法访问 Microsoft 内容传递网络时如何配置自助服务门户](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)的步骤。</span><span class="sxs-lookup"><span data-stu-id="e1e05-265">If your client computers do not have access to the CDN, complete the steps in [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md).</span></span>


## <span data-ttu-id="e1e05-266">相关主题</span><span class="sxs-lookup"><span data-stu-id="e1e05-266">Related topics</span></span>


[<span data-ttu-id="e1e05-267">服务器事件日志</span><span class="sxs-lookup"><span data-stu-id="e1e05-267">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="e1e05-268">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="e1e05-268">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="e1e05-269">如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户</span><span class="sxs-lookup"><span data-stu-id="e1e05-269">How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network</span></span>](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)

[<span data-ttu-id="e1e05-270">为组织自定义自助服务门户</span><span class="sxs-lookup"><span data-stu-id="e1e05-270">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

[<span data-ttu-id="e1e05-271">验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="e1e05-271">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)



## <span data-ttu-id="e1e05-272">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="e1e05-272">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e1e05-273">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="e1e05-273">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e1e05-274">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e1e05-274">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





