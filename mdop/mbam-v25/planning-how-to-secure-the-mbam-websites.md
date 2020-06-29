---
title: 规划如何保护 MBAM 网站
description: 规划如何保护 MBAM 网站
author: dansimp
ms.assetid: aea1d137-62cf-4da4-9989-541e0b5ad8d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 223c9397ad7933e11051c289c3dbcab63940fbc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803685"
---
# <span data-ttu-id="cba0d-103">规划如何保护 MBAM 网站</span><span class="sxs-lookup"><span data-stu-id="cba0d-103">Planning How to Secure the MBAM Websites</span></span>


<span data-ttu-id="cba0d-104">本主题介绍以下用于保护 Microsoft BitLocker 管理和监视（MBAM）2.5 管理和监控网站和自助服务门户的方法：</span><span class="sxs-lookup"><span data-stu-id="cba0d-104">This topic describes the following methods for securing the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Administration and Monitoring Website and Self-Service Portal:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cba0d-105">方法</span><span class="sxs-lookup"><span data-stu-id="cba0d-105">Method</span></span></th>
<th align="left"><span data-ttu-id="cba0d-106">必需还是可选的？</span><span class="sxs-lookup"><span data-stu-id="cba0d-106">Required or optional?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-107">使用证书保护 MBAM 网站</span><span class="sxs-lookup"><span data-stu-id="cba0d-107">Using certificates to secure MBAM websites</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-108">可选，但强烈建议</span><span class="sxs-lookup"><span data-stu-id="cba0d-108">Optional, but highly recommended</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-109">注册应用程序池帐户的服务主体名称（SPN）</span><span class="sxs-lookup"><span data-stu-id="cba0d-109">Registering Service Principal Names (SPN) for the application pool account</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-110">必需</span><span class="sxs-lookup"><span data-stu-id="cba0d-110">Required</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="cba0d-111">有关如何保护 MBAM 部署的详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="cba0d-111">For more information about how to secure your MBAM deployment, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md).</span></span>

## <span data-ttu-id="cba0d-112">使用证书保护 MBAM 网站</span><span class="sxs-lookup"><span data-stu-id="cba0d-112">Using certificates to secure MBAM websites</span></span>


<span data-ttu-id="cba0d-113">我们建议你使用证书来保护以下各内容之间的通信：</span><span class="sxs-lookup"><span data-stu-id="cba0d-113">We recommend that you use a certificate to secure the communication between the:</span></span>

-   <span data-ttu-id="cba0d-114">MBAM 客户端和 web 服务</span><span class="sxs-lookup"><span data-stu-id="cba0d-114">MBAM Client and the web services</span></span>

-   <span data-ttu-id="cba0d-115">浏览器和管理和监控网站以及自助服务门户网站</span><span class="sxs-lookup"><span data-stu-id="cba0d-115">Browser and the Administration and Monitoring Website and the Self-Service Portal websites</span></span>

<span data-ttu-id="cba0d-116">有关请求和安装证书的信息，请参阅[配置 Internet 服务器证书](https://technet.microsoft.com/library/cc731977.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cba0d-116">For information about requesting and installing a certificate, see [Configuring Internet Server Certificates](https://technet.microsoft.com/library/cc731977.aspx).</span></span>

**<span data-ttu-id="cba0d-117">注意</span><span class="sxs-lookup"><span data-stu-id="cba0d-117">Note</span></span>**  
<span data-ttu-id="cba0d-118">只有在使用 Windows PowerShell 时，才能在不同服务器上配置网站和 web 服务。</span><span class="sxs-lookup"><span data-stu-id="cba0d-118">You can configure the websites and web services on different servers only if you are using Windows PowerShell.</span></span> <span data-ttu-id="cba0d-119">如果使用 MBAM 服务器配置向导配置网站，则必须在同一台服务器上配置网站和 web 服务。</span><span class="sxs-lookup"><span data-stu-id="cba0d-119">If you use the MBAM Server Configuration wizard to configure the websites, you must configure the websites and the web services on the same server.</span></span>



<span data-ttu-id="cba0d-120">为了保护 web 服务和数据库之间的通信，我们还建议你在 SQL Server 中强制执行加密。</span><span class="sxs-lookup"><span data-stu-id="cba0d-120">To secure the communication between the web services and the databases, we also recommend that you force encryption in SQL Server.</span></span> <span data-ttu-id="cba0d-121">有关保护 SQL Server 的所有连接（包括 web 服务和 SQL Server 之间的通信）的详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-secure-databases)。</span><span class="sxs-lookup"><span data-stu-id="cba0d-121">For information about securing all connections to SQL Server, including communication between the web services and SQL Server, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-secure-databases).</span></span>

## <span data-ttu-id="cba0d-122">注册应用程序池帐户的 Spn</span><span class="sxs-lookup"><span data-stu-id="cba0d-122">Registering SPNs for the application pool account</span></span>


<span data-ttu-id="cba0d-123">若要使 MBAM 服务器能够对来自管理和监视网站和自助服务门户的通信进行身份验证，你必须在用于 web 应用程序池的域帐户下注册主机名的服务主体名称（SPN）。</span><span class="sxs-lookup"><span data-stu-id="cba0d-123">To enable the MBAM Servers to authenticate communication from the Administration and Monitoring Website and the Self-Service Portal, you must register a Service Principal Name (SPN) for the host name under the domain account that you are using for the web application pool.</span></span>

<span data-ttu-id="cba0d-124">本主题包含有关如何为以下类型的主机名称注册 Spn 的说明：</span><span class="sxs-lookup"><span data-stu-id="cba0d-124">This topic contains instructions on how to register SPNs for the following types of host names:</span></span>

-   <span data-ttu-id="cba0d-125">完全限定的域名</span><span class="sxs-lookup"><span data-stu-id="cba0d-125">Fully qualified domain name</span></span>

-   <span data-ttu-id="cba0d-126">NetBIOS 名称</span><span class="sxs-lookup"><span data-stu-id="cba0d-126">NetBIOS name</span></span>

-   <span data-ttu-id="cba0d-127">虚拟名称</span><span class="sxs-lookup"><span data-stu-id="cba0d-127">Virtual name</span></span>

### <span data-ttu-id="cba0d-128">在为初始 MBAM 安装创建 Spn 之前</span><span class="sxs-lookup"><span data-stu-id="cba0d-128">Before you create SPNs for an initial MBAM installation</span></span>

<span data-ttu-id="cba0d-129">开始创建 Spn 之前，请查看下表中的信息。</span><span class="sxs-lookup"><span data-stu-id="cba0d-129">Review the information in the following table before you start creating SPNs.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cba0d-130">任务或项目</span><span class="sxs-lookup"><span data-stu-id="cba0d-130">Task or item</span></span></th>
<th align="left"><span data-ttu-id="cba0d-131">详细信息</span><span class="sxs-lookup"><span data-stu-id="cba0d-131">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-132">在 Active Directory 域服务（AD DS）中创建服务帐户。</span><span class="sxs-lookup"><span data-stu-id="cba0d-132">Create a service account in Active Directory Domain Services (AD DS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-133">服务帐户是在 AD DS 中创建的用于为 MBAM 网站提供安全性的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cba0d-133">The service account is a user account that you create in AD DS to provide security for the MBAM websites.</span></span> <span data-ttu-id="cba0d-134">MBAM 网站在应用程序池下运行，其标识是服务帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="cba0d-134">The MBAM websites run under an application pool, whose identity is the name of the service account.</span></span> <span data-ttu-id="cba0d-135">然后，在应用程序池帐户中注册 Spn。</span><span class="sxs-lookup"><span data-stu-id="cba0d-135">The SPNs are then registered in the application pool account.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="cba0d-136">注意</span><span class="sxs-lookup"><span data-stu-id="cba0d-136">Note</span></span></strong><br/><p><span data-ttu-id="cba0d-137">你必须对所有 web 服务器使用相同的应用程序池帐户。</span><span class="sxs-lookup"><span data-stu-id="cba0d-137">You must use the same application pool account for all web servers.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-138">验证 IIS IUSRS 组帐户或应用程序池帐户是否已被授予必要的权限。</span><span class="sxs-lookup"><span data-stu-id="cba0d-138">Verify that either the IIS-IUSRS group account or the application pool account has been granted the necessary rights.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-139">若要检查此内容，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cba0d-139">To check this, follow these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="cba0d-140">打开 " <strong> 本地安全策略编辑器" </strong> ，然后展开 " <strong> 本地策略" </strong> 节点。</span><span class="sxs-lookup"><span data-stu-id="cba0d-140">Open the <strong>Local Security Policy editor</strong> and expand the <strong>Local Policies</strong> node.</span></span></p></li>
<li><p><span data-ttu-id="cba0d-141">选择 " <strong> 用户权限分配" </strong> 节点，然后双击 " <strong> 身份验证后模拟客户端" 和 "在 </strong> <strong> </strong> 右窗格中作为批处理作业组策略设置登录"。</span><span class="sxs-lookup"><span data-stu-id="cba0d-141">Select the <strong>User Rights Assignment</strong> node, and double-click the <strong>Impersonate a client after authentication</strong> and <strong>Log on as a batch job</strong> Group Policy settings in the right pane.</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-142">如果您使用域管理帐户配置 MBAM 网站，MBAM 将为您创建 Spn。</span><span class="sxs-lookup"><span data-stu-id="cba0d-142">If you configure the MBAM websites by using a domain administrative account, MBAM will create the SPNs for you.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-143">如果你使用域管理帐户配置 MBAM 网站，请按照本主题中的步骤为你使用的主机名类型手动注册 Spn。</span><span class="sxs-lookup"><span data-stu-id="cba0d-143">If you configure the MBAM websites by using a domain administrative account, follow the steps in this topic to register SPNs manually for the type of host name that you are using.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="cba0d-144">使用完全限定的域主机名时注册 Spn</span><span class="sxs-lookup"><span data-stu-id="cba0d-144">Registering SPNs when you use a fully qualified domain host name</span></span>

<span data-ttu-id="cba0d-145">如果在配置 MBAM 时使用完全限定的域名主机名，则只需注册一个 SPN，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="cba0d-145">If you use a fully qualified domain host name when you configure MBAM, you have to register only one SPN, as shown in the following example.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cba0d-146">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="cba0d-146">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="cba0d-147">示例和详细信息</span><span class="sxs-lookup"><span data-stu-id="cba0d-147">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-148">为完全限定的域名注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="cba0d-148">Register an SPN for the fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mybitlockerrecovery.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="cba0d-149">完全限定的主机名为 <strong> mybitlockerrecovery.contoso.com </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-149">The fully qualified host name is <strong>mybitlockerrecovery.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-150">为你为应用程序池帐户注册的 SPN 配置受限委派。</span><span class="sxs-lookup"><span data-stu-id="cba0d-150">Configure constrained delegation for the SPN that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="cba0d-151">配置受限委派</span><span class="sxs-lookup"><span data-stu-id="cba0d-151">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="cba0d-152">此要求仅适用于 MBAM 2.5;MBAM 2.5 SP1 中不需要此功能。</span><span class="sxs-lookup"><span data-stu-id="cba0d-152">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="cba0d-153">使用 NetBIOS 主机名注册 Spn</span><span class="sxs-lookup"><span data-stu-id="cba0d-153">Registering SPNs when you use a NetBIOS host name</span></span>

<span data-ttu-id="cba0d-154">如果在配置 MBAM 时使用 NetBIOS 主机名，请为 NetBIOS 名称注册一个 SPN，为完全限定的域名注册另一个 SPN，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="cba0d-154">If you use a NetBIOS host name when you configure MBAM, register one SPN for the NetBIOS name, and another SPN for the fully qualified domain name, as shown in the following examples.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cba0d-155">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="cba0d-155">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="cba0d-156">示例和详细信息</span><span class="sxs-lookup"><span data-stu-id="cba0d-156">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-157">为 NetBIOS 主机名注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="cba0d-157">Register an SPN for the NetBIOS host name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/nbname01 contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="cba0d-158">NetBIOS 主机名为 <strong> nbname01 </strong> ，用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-158">The NetBIOS host name is <strong>nbname01</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-159">为完全限定的域名注册 SPN。</span><span class="sxs-lookup"><span data-stu-id="cba0d-159">Register an SPN for the fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn –s http/nbname01.corp.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="cba0d-160">完全限定的域名是 <strong> nbname01.contoso.com </strong> ，而用于 web 应用程序池的域帐户是 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-160">The fully qualified domain name is <strong>nbname01.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-161">针对为应用程序池帐户注册的 Spn 配置受约束的委派。</span><span class="sxs-lookup"><span data-stu-id="cba0d-161">Configure constrained delegation for the SPNs that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="cba0d-162">配置受限委派</span><span class="sxs-lookup"><span data-stu-id="cba0d-162">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="cba0d-163">此要求仅适用于 MBAM 2.5;MBAM 2.5 SP1 中不需要此功能。</span><span class="sxs-lookup"><span data-stu-id="cba0d-163">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-regvirtualspn"></a><span data-ttu-id="cba0d-164">使用虚拟主机名时注册 Spn</span><span class="sxs-lookup"><span data-stu-id="cba0d-164">Registering SPNs when you use a virtual host name</span></span>

<span data-ttu-id="cba0d-165">如果将 MBAM 配置为具有完全限定域名的虚拟主机名，请仅为虚拟主机名注册一个 SPN。</span><span class="sxs-lookup"><span data-stu-id="cba0d-165">If you configure MBAM with a virtual host name that is a fully qualified domain name, register only one SPN for the virtual host name.</span></span> <span data-ttu-id="cba0d-166">如果你配置的虚拟主机名不是完全限定的域名，则必须创建第二个 SPN 来指定完全限定的域名，如以下示例中所述。</span><span class="sxs-lookup"><span data-stu-id="cba0d-166">If the virtual host name that you configure is not a fully qualified domain name, you must create a second SPN that specifies the fully qualified domain name, as described in the following examples.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cba0d-167">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="cba0d-167">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="cba0d-168">示例和详细信息</span><span class="sxs-lookup"><span data-stu-id="cba0d-168">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-169">如果你的虚拟主机名是完全限定的域名，如本示例中所示，仅注册一个 SPN。</span><span class="sxs-lookup"><span data-stu-id="cba0d-169">If your virtual host name is a fully qualified domain name, as in this example, register only one SPN.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="cba0d-170">在此示例中，虚拟主机名为 <strong> mbamvirtual.contoso.com </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-170">In the example, the virtual host name is <strong>mbamvirtual.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-171">如果你的虚拟主机名不是完全限定的域名，请注册此额外的 SPN。</span><span class="sxs-lookup"><span data-stu-id="cba0d-171">Register this additional SPN if your virtual host name is not a fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="cba0d-172">在此示例中，虚拟主机名为 <strong> mbamvirtual </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-172">In the example, the virtual host name is <strong>mbamvirtual</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-173">如果你的虚拟主机名不是完全限定的域名，请注册此额外的 SPN。</span><span class="sxs-lookup"><span data-stu-id="cba0d-173">Register this additional SPN if your virtual host name is not a fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="cba0d-174">在此示例中，虚拟主机名为 <strong> mbamvirtual.contoso.com </strong> ，而用于 web 应用程序池的域帐户为 <strong> contoso\mbamapppooluser </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-174">In the example, the virtual host name is <strong>mbamvirtual.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-175">在 "域名服务器（DNS）" 服务器上，为自定义主机名创建一个 "A 记录"，并将其指向 web 服务器或负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="cba0d-175">On the Domain Name Server (DNS) server, create an “A record” for the custom host name and point it to a web server or a load balancer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-176">请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)"> 配置 Dns 主机记录中的 "配置 Dns 主机 A 记录" 部分 </a> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-176">See the “To configure DNS Host A Records” section in <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)">Configure DNS Host Records</a>.</span></span></p>
<p><span data-ttu-id="cba0d-177">我们建议您使用记录，而不是 CNAMES。</span><span class="sxs-lookup"><span data-stu-id="cba0d-177">We recommend that you use A records instead of CNAMES.</span></span> <span data-ttu-id="cba0d-178">如果使用 CNAMES 指向域地址，还必须在应用程序池帐户中注册 web 服务器名称的 Spn。</span><span class="sxs-lookup"><span data-stu-id="cba0d-178">If you use CNAMES to point to the domain address, you must also register SPNs for the web server name in the application pool account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-179">针对为应用程序池帐户注册的 Spn 配置受约束的委派。</span><span class="sxs-lookup"><span data-stu-id="cba0d-179">Configure constrained delegation for the SPNs that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="cba0d-180">配置受限委派</span><span class="sxs-lookup"><span data-stu-id="cba0d-180">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="cba0d-181">此要求仅适用于 MBAM 2.5;MBAM 2.5 SP1 中不需要此功能。</span><span class="sxs-lookup"><span data-stu-id="cba0d-181">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-registerspn"></a><span data-ttu-id="cba0d-182">从早期版本的 MBAM 升级时注册 SPN</span><span class="sxs-lookup"><span data-stu-id="cba0d-182">Registering an SPN when you upgrade from previous versions of MBAM</span></span>

<span data-ttu-id="cba0d-183">仅当需要执行以下操作时才完成本部分中的步骤：</span><span class="sxs-lookup"><span data-stu-id="cba0d-183">Complete the steps in this section only if you want to:</span></span>

-   <span data-ttu-id="cba0d-184">从早期版本的 MBAM 升级。</span><span class="sxs-lookup"><span data-stu-id="cba0d-184">Upgrade from a previous version of MBAM.</span></span>

-   <span data-ttu-id="cba0d-185">在负载平衡或分布式配置中运行 MBAM 2.5 中的网站，并且当前在未进行负载平衡的配置中运行。</span><span class="sxs-lookup"><span data-stu-id="cba0d-185">Run the websites in MBAM 2.5 in a load-balanced or distributed configuration, and you are currently running in a configuration that is not load balanced.</span></span>

<span data-ttu-id="cba0d-186">如果你已在计算机帐户（而不是应用程序池帐户）中注册了 Spn，MBAM 将使用现有的 Spn，并且你无法在负载平衡或分布式配置中配置网站。</span><span class="sxs-lookup"><span data-stu-id="cba0d-186">If you already registered SPNs on the machine account rather than in an application pool account, MBAM uses the existing SPNs, and you cannot configure the websites in a load-balanced or distributed configuration.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cba0d-187">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="cba0d-187">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="cba0d-188">示例和详细信息</span><span class="sxs-lookup"><span data-stu-id="cba0d-188">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-189">在 Active Directory 域服务（AD DS）中创建应用程序池帐户。</span><span class="sxs-lookup"><span data-stu-id="cba0d-189">Create an application pool account in Active Directory Domain Services (AD DS).</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-190">删除当前已安装的网站和 web 服务。</span><span class="sxs-lookup"><span data-stu-id="cba0d-190">Remove the currently installed websites and web services.</span></span></p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)"><span data-ttu-id="cba0d-191">删除 MBAM 服务器功能或软件</span><span class="sxs-lookup"><span data-stu-id="cba0d-191">Removing MBAM Server Features or Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-192">从计算机帐户中删除 Spn。</span><span class="sxs-lookup"><span data-stu-id="cba0d-192">Remove SPNs from the machine account.</span></span></p></td>
<td align="left"><p><code>Setspn –d http/mbamwebserver mbamwebserver</code></p>
<p><code>Setspn –d http/mbamwebserver.contoso.com mbamwebserver</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-193">在应用程序池帐户中注册 Spn。</span><span class="sxs-lookup"><span data-stu-id="cba0d-193">Register SPNs in the application pool account.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-194"><a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">使用虚拟主机名时，请按照注册 spn 的步骤进行操作 </a> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-194">Follow the steps for <a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">Registering SPNs when you use a virtual host name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cba0d-195">重新配置 web 应用程序和 web 服务。</span><span class="sxs-lookup"><span data-stu-id="cba0d-195">Reconfigure the web applications and web services.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="cba0d-196">如何配置 MBAM 2.5 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="cba0d-196">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cba0d-197">根据用于配置的方法，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="cba0d-197">Do one of the following, depending on the method you use for the configuration:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cba0d-198">方法</span><span class="sxs-lookup"><span data-stu-id="cba0d-198">Method</span></span></th>
<th align="left"><span data-ttu-id="cba0d-199">详细信息</span><span class="sxs-lookup"><span data-stu-id="cba0d-199">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="cba0d-200">MBAM Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="cba0d-200">MBAM Server Configuration wizard</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="cba0d-201">在 " <strong> Web 服务应用程序池域帐户" 字段中输入应用程序池帐户 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-201">Enter the application pool account in the <strong>Web service application pool domain account</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><code>Enable-MbamWebApplication</code> <span data-ttu-id="cba0d-202">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="cba0d-202">Windows PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="cba0d-203">在参数中输入帐户 <code>WebServiceApplicationPoolCredential</code> 。</span><span class="sxs-lookup"><span data-stu-id="cba0d-203">Enter the account in the <code>WebServiceApplicationPoolCredential</code> parameter.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="cba0d-204">重要提示</span><span class="sxs-lookup"><span data-stu-id="cba0d-204">Important</span></span></strong><br/><p><span data-ttu-id="cba0d-205">输入的主机名必须与要为其创建 Spn 的虚拟主机名同名。</span><span class="sxs-lookup"><span data-stu-id="cba0d-205">The host name that you enter must be the same name as the virtual host name for which you are creating the SPNs.</span></span> <span data-ttu-id="cba0d-206">此外，在您的 web 场中，主机名和应用程序池凭据在您要配置的每台服务器上必须是相同的。</span><span class="sxs-lookup"><span data-stu-id="cba0d-206">Also, in your web farm, the host names and the application pool credentials must be the same on every server that you are configuring.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="cba0d-207">当 MBAM 配置 web 应用程序时，它将尝试为你注册 Spn，但只有当你在其上安装 MBAM 的服务器上有域管理员权限时，才可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cba0d-207">When MBAM configures the web applications, it will try to register the SPNs for you, but it can do so only if you have Domain Admin rights on the server on which you are installing MBAM.</span></span> <span data-ttu-id="cba0d-208">如果你不具有这些权限，则可以完成配置，但你必须在配置 MBAM 之前或之后设置 Spn。</span><span class="sxs-lookup"><span data-stu-id="cba0d-208">If you do not have these rights, you can complete the configuration, but you will have to set the SPNs before or after you configure MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="cba0d-209">所需的请求筛选设置</span><span class="sxs-lookup"><span data-stu-id="cba0d-209">Required Request Filtering Settings</span></span>

 <span data-ttu-id="cba0d-210">应用程序按预期操作时需要 "允许未列出的文件扩展名"。</span><span class="sxs-lookup"><span data-stu-id="cba0d-210">'Allow unlisted file name extensions' is required for the application to operate as expected.</span></span>  <span data-ttu-id="cba0d-211">可通过导航到 "Microsoft BitLocker 管理和监视"-> 请求筛选-> "编辑" 功能设置找到此项。</span><span class="sxs-lookup"><span data-stu-id="cba0d-211">This can be found by navigating to the 'Microsoft BitLocker Administration and Monitoring' -> Request Filtering -> Edit Feature Settings.</span></span>


## <span data-ttu-id="cba0d-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="cba0d-212">Related topics</span></span>


[<span data-ttu-id="cba0d-213">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="cba0d-213">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="cba0d-214">MBAM 2.5 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="cba0d-214">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)





## <span data-ttu-id="cba0d-215">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="cba0d-215">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="cba0d-216">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="cba0d-216">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="cba0d-217">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="cba0d-217">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



