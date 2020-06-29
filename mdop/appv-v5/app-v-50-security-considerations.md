---
title: App-V 5.0 安全注意事项
description: App-V 5.0 安全注意事项
author: dansimp
ms.assetid: 1e7292a0-7972-4b4f-85a9-eaf33f6c563a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fcd740345be7f532502b8996d8d2b1f4437ed6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798638"
---
# <span data-ttu-id="56c15-103">App-V 5.0 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="56c15-103">App-V 5.0 Security Considerations</span></span>


<span data-ttu-id="56c15-104">本主题包含有关 app-v 5.0 的帐户和组、日志文件以及其他安全相关注意事项的简要概述。</span><span class="sxs-lookup"><span data-stu-id="56c15-104">This topic contains a brief overview of the accounts and groups, log files, and other security-related considerations for App-V 5.0.</span></span>

**<span data-ttu-id="56c15-105">重要提示</span><span class="sxs-lookup"><span data-stu-id="56c15-105">Important</span></span>**  
<span data-ttu-id="56c15-106">App-v 5.0 不是一种安全产品，并且不提供对安全环境的任何保证。</span><span class="sxs-lookup"><span data-stu-id="56c15-106">App-V 5.0 is not a security product and does not provide any guarantees for a secure environment.</span></span>



## <span data-ttu-id="56c15-107">PackageStoreAccessControl （PSAC）功能已弃用</span><span class="sxs-lookup"><span data-stu-id="56c15-107">PackageStoreAccessControl (PSAC) feature has been deprecated</span></span>


<span data-ttu-id="56c15-108">从2014年6月起生效，在单用户和多用户环境中，在 Microsoft Application Virtualization （App-v） 5.0 Service Pack 2 （SP2）中引入的 PackageStoreAccessControl （PSAC）功能已被弃用。</span><span class="sxs-lookup"><span data-stu-id="56c15-108">Effective as of June, 2014, the PackageStoreAccessControl (PSAC) feature that was introduced in Microsoft Application Virtualization (App-V) 5.0 Service Pack 2 (SP2) has been deprecated in both single-user and multi-user environments.</span></span>

## <span data-ttu-id="56c15-109">常规安全注意事项</span><span class="sxs-lookup"><span data-stu-id="56c15-109">General security considerations</span></span>


**<span data-ttu-id="56c15-110">了解安全风险。</span><span class="sxs-lookup"><span data-stu-id="56c15-110">Understand the security risks.</span></span>** <span data-ttu-id="56c15-111">App-v 5.0 的最严重的风险是它的功能可能会被未经授权的用户劫持，这样就可以在 app-v 5.0 客户端上重新配置密钥数据。</span><span class="sxs-lookup"><span data-stu-id="56c15-111">The most serious risk to App-V 5.0 is that its functionality could be hijacked by an unauthorized user who could then reconfigure key data on App-V 5.0 clients.</span></span> <span data-ttu-id="56c15-112">由于拒绝服务攻击，较短时间内的 app-v 5.0 功能丢失通常不会产生灾难性影响。</span><span class="sxs-lookup"><span data-stu-id="56c15-112">The loss of App-V 5.0 functionality for a short period of time due to a denial-of-service attack would not generally have a catastrophic impact.</span></span>

<span data-ttu-id="56c15-113">**确保计算机的物理安全**。</span><span class="sxs-lookup"><span data-stu-id="56c15-113">**Physically secure your computers**.</span></span> <span data-ttu-id="56c15-114">安全性不完整，没有物理安全。</span><span class="sxs-lookup"><span data-stu-id="56c15-114">Security is incomplete without physical security.</span></span> <span data-ttu-id="56c15-115">对 app-v 5.0 服务器具有物理访问权限的任何人都可能会攻击整个客户端基。</span><span class="sxs-lookup"><span data-stu-id="56c15-115">Anyone with physical access to an App-V 5.0 server could potentially attack the entire client base.</span></span> <span data-ttu-id="56c15-116">任何潜在的物理攻击都必须被视为高风险并相应地缓解。</span><span class="sxs-lookup"><span data-stu-id="56c15-116">Any potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="56c15-117">App-v 5.0 服务器应存储在具有可控访问权限的物理安全的服务器机房中。</span><span class="sxs-lookup"><span data-stu-id="56c15-117">App-V 5.0 servers should be stored in a physically secure server room with controlled access.</span></span> <span data-ttu-id="56c15-118">通过让操作系统锁定计算机，或使用安全的屏幕保护程序，确保管理员不在物理上显示这些计算机。</span><span class="sxs-lookup"><span data-stu-id="56c15-118">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="56c15-119">**对所有计算机应用最新的安全更新**。</span><span class="sxs-lookup"><span data-stu-id="56c15-119">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="56c15-120">若要随时了解操作系统、Microsoft SQL Server 和 App-v 5.0 的最新更新，请订阅安全通知服务（ <https://go.microsoft.com/fwlink/p/?LinkId=28819> ）。</span><span class="sxs-lookup"><span data-stu-id="56c15-120">To stay informed about the latest updates for operating systems, Microsoft SQL Server, and App-V 5.0, subscribe to the Security Notification service (<https://go.microsoft.com/fwlink/p/?LinkId=28819>).</span></span>

<span data-ttu-id="56c15-121">**使用强密码或密码短语**。</span><span class="sxs-lookup"><span data-stu-id="56c15-121">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="56c15-122">对于所有 App-v 5.0 和 App-v 5.0 管理员帐户，请始终使用具有15个或更多字符的强密码。</span><span class="sxs-lookup"><span data-stu-id="56c15-122">Always use strong passwords with 15 or more characters for all App-V 5.0 and App-V 5.0 administrator accounts.</span></span> <span data-ttu-id="56c15-123">千万不要使用空白密码。</span><span class="sxs-lookup"><span data-stu-id="56c15-123">Never use blank passwords.</span></span> <span data-ttu-id="56c15-124">有关密码概念的详细信息，请参阅 TechNet 上的 "帐户密码和策略" 白皮书（ <https://go.microsoft.com/fwlink/p/?LinkId=30009> ）。</span><span class="sxs-lookup"><span data-stu-id="56c15-124">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/p/?LinkId=30009>).</span></span>

## <span data-ttu-id="56c15-125">App-v 5.0 中的帐户和组</span><span class="sxs-lookup"><span data-stu-id="56c15-125">Accounts and groups in App-V 5.0</span></span>


<span data-ttu-id="56c15-126">用户帐户管理的最佳做法是创建域全局组并向其添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="56c15-126">A best practice for user account management is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="56c15-127">然后，将域全局帐户添加到 App-v 5.0 服务器上必需的 App-v 5.0 本地组。</span><span class="sxs-lookup"><span data-stu-id="56c15-127">Then, add the domain global accounts to the necessary App-V 5.0 local groups on the App-V 5.0 servers.</span></span>

**<span data-ttu-id="56c15-128">注意</span><span class="sxs-lookup"><span data-stu-id="56c15-128">Note</span></span>**  
<span data-ttu-id="56c15-129">需要连接到发布服务器的 app-v 客户端计算机帐户必须是发布服务器**用户**本地组的一部分。</span><span class="sxs-lookup"><span data-stu-id="56c15-129">App-V client computer accounts that need to connect to the publishing server must be part of the publishing server’s **Users** local group.</span></span> <span data-ttu-id="56c15-130">默认情况下，域中的所有计算机都是 "**授权用户**" 组的一部分，该用户组是 "**用户**本地组" 的一部分。</span><span class="sxs-lookup"><span data-stu-id="56c15-130">By default, all computers in the domain are part of the **Authorized Users** group, which is part of the **Users** local group.</span></span>



### <a href="" id="-------------app-v-5-0-server-security"></a> <span data-ttu-id="56c15-131">App-v 5.0 服务器安全</span><span class="sxs-lookup"><span data-stu-id="56c15-131">App-V 5.0 server security</span></span>

<span data-ttu-id="56c15-132">在 App-v 5.0 安装过程中不会自动创建任何组。</span><span class="sxs-lookup"><span data-stu-id="56c15-132">No groups are created automatically during App-V 5.0 Setup.</span></span> <span data-ttu-id="56c15-133">应创建以下 Active Directory 域服务全局组以管理 App-v 5.0 服务器操作。</span><span class="sxs-lookup"><span data-stu-id="56c15-133">You should create the following Active Directory Domain Services global groups to manage App-V 5.0 server operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="56c15-134">组名称</span><span class="sxs-lookup"><span data-stu-id="56c15-134">Group name</span></span></th>
<th align="left"><span data-ttu-id="56c15-135">详细信息</span><span class="sxs-lookup"><span data-stu-id="56c15-135">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="56c15-136">App-v 管理管理员组</span><span class="sxs-lookup"><span data-stu-id="56c15-136">App-V Management Admin group</span></span></p></td>
<td align="left"><p><span data-ttu-id="56c15-137">用于管理 app-v 5.0 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="56c15-137">Used to manage the App-V 5.0 management server.</span></span> <span data-ttu-id="56c15-138">此组在 App-v 5.0 管理服务器安装期间创建。</span><span class="sxs-lookup"><span data-stu-id="56c15-138">This group is created during the App-V 5.0 Management Server installation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="56c15-139">重要提示</span><span class="sxs-lookup"><span data-stu-id="56c15-139">Important</span></span></strong><br/><p><span data-ttu-id="56c15-140">在完成安装后，没有使用管理控制台创建组的方法。</span><span class="sxs-lookup"><span data-stu-id="56c15-140">There is no method to create the group using the management console after you have completed the installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="56c15-141">管理服务帐户的数据库读/写</span><span class="sxs-lookup"><span data-stu-id="56c15-141">Database read/write for Management Service account</span></span></p></td>
<td align="left"><p><span data-ttu-id="56c15-142">提供对管理数据库的读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="56c15-142">Provides read/write access to the management database.</span></span> <span data-ttu-id="56c15-143">应在安装 app-v 5.0 管理数据库期间创建此帐户。</span><span class="sxs-lookup"><span data-stu-id="56c15-143">This account should be created during the App-V 5.0 management database installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="56c15-144">App-v 管理服务安装管理员帐户</span><span class="sxs-lookup"><span data-stu-id="56c15-144">App-V Management Service install admin account</span></span></p>
<div class="alert">
<strong><span data-ttu-id="56c15-145">注意</span><span class="sxs-lookup"><span data-stu-id="56c15-145">Note</span></span></strong><br/><p><span data-ttu-id="56c15-146">仅当管理数据库与服务分开安装时，才需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="56c15-146">This is only required if management database is being installed separately from the service.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="56c15-147">提供对管理数据库中的架构版本表的公共访问权限。</span><span class="sxs-lookup"><span data-stu-id="56c15-147">Provides public access to schema-version table in management database.</span></span> <span data-ttu-id="56c15-148">应在安装 app-v 5.0 管理数据库期间创建此帐户。</span><span class="sxs-lookup"><span data-stu-id="56c15-148">This account should be created during the App-V 5.0 management database installation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="56c15-149">App-v Reporting Service 安装管理员帐户</span><span class="sxs-lookup"><span data-stu-id="56c15-149">App-V Reporting Service install admin account</span></span></p>
<div class="alert">
<strong><span data-ttu-id="56c15-150">注意</span><span class="sxs-lookup"><span data-stu-id="56c15-150">Note</span></span></strong><br/><p><span data-ttu-id="56c15-151">仅当报告数据库与服务分开安装时，才需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="56c15-151">This is only required if reporting database is being installed separately from the service.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="56c15-152">对报告数据库中的架构版本表的公共访问。</span><span class="sxs-lookup"><span data-stu-id="56c15-152">Public access to schema-version table in reporting database.</span></span> <span data-ttu-id="56c15-153">此帐户应在 App-v 5.0 reporting 数据库安装期间创建。</span><span class="sxs-lookup"><span data-stu-id="56c15-153">This account should be created during the App-V 5.0 reporting database installation.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="56c15-154">请考虑以下其他信息：</span><span class="sxs-lookup"><span data-stu-id="56c15-154">Consider the following additional information:</span></span>

-   <span data-ttu-id="56c15-155">访问软件包共享-如果与管理服务器位于同一台计算机上的共享位于同一台计算机上，则**网络**服务需要对该共享的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="56c15-155">Access to the package shares - If a share exists on the same computer as the management Server, the **Network** service requires read access to the share.</span></span> <span data-ttu-id="56c15-156">此外，每个 App-v 客户端计算机必须具有程序包共享的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="56c15-156">In addition, each App-V client computer must have read access to the package share.</span></span>

    **<span data-ttu-id="56c15-157">注意</span><span class="sxs-lookup"><span data-stu-id="56c15-157">Note</span></span>**  
    <span data-ttu-id="56c15-158">在早期版本的 App-v 中，程序包共享称为内容共享。</span><span class="sxs-lookup"><span data-stu-id="56c15-158">In previous versions of App-V, package share was referred to as content share.</span></span>



-   <span data-ttu-id="56c15-159">向管理服务器注册发布服务器-发布服务器必须在管理服务器上注册。</span><span class="sxs-lookup"><span data-stu-id="56c15-159">Registering publishing servers with Management Server - A publishing server must be registered with the Management server.</span></span> <span data-ttu-id="56c15-160">例如，必须将其添加到数据库，以便发布服务器计算机帐户能够调用管理服务 API。</span><span class="sxs-lookup"><span data-stu-id="56c15-160">For example, it must be added to the database, so that the Publishing server machine accounts are able to call into the Management service API.</span></span>

### <a href="" id="-------------app-v-5-0-package-security"></a> <span data-ttu-id="56c15-161">App-v 5.0 程序包安全性</span><span class="sxs-lookup"><span data-stu-id="56c15-161">App-V 5.0 package security</span></span>

<span data-ttu-id="56c15-162">以下将帮助你规划如何确保虚拟化程序包的安全。</span><span class="sxs-lookup"><span data-stu-id="56c15-162">The following will help you plan how to ensure that virtualized packages are secure.</span></span>

-   <span data-ttu-id="56c15-163">如果应用程序安装程序将访问控制列表（ACL）应用到文件或目录，则该 ACL 不会保留在程序包中。</span><span class="sxs-lookup"><span data-stu-id="56c15-163">If an application installer applies an access control list (ACL) to a file or directory, then that ACL is not persisted in the package.</span></span> <span data-ttu-id="56c15-164">当部署程序包时，如果文件或目录由用户修改，它将在 **% userprofile%** 中继承 acl 或继承目标计算机目录的 acl。</span><span class="sxs-lookup"><span data-stu-id="56c15-164">When the package is deployed, if the file or directory is modified by a user it will either inherit the ACL in the **%userprofile%** or inherit the ACL of the target computer’s directory.</span></span> <span data-ttu-id="56c15-165">如果文件或目录在虚拟文件系统位置中不存在，则会出现前一种情况;如果文件或目录存在于虚拟文件系统位置（例如 **% windir%**）中，则会出现后一种情况。</span><span class="sxs-lookup"><span data-stu-id="56c15-165">The former case occurs if the file or directory does not exist in a virtual file system location; the latter case occurs if the file or directory exists in a virtual file system location, for example **%windir%**.</span></span>

## <a href="" id="---------app-v-5-0-log-files"></a> <span data-ttu-id="56c15-166">App-v 5.0 日志文件</span><span class="sxs-lookup"><span data-stu-id="56c15-166">App-V 5.0 log files</span></span>


<span data-ttu-id="56c15-167">在 App-v 5.0 设置期间，安装日志文件在安装用户的 **% temp%** 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="56c15-167">During App-V 5.0 Setup, setup log files are created in the **%temp%** folder of the installing user.</span></span>
