---
title: 关于 Client 配置设置
description: 关于 Client 配置设置
author: dansimp
ms.assetid: cc7ae28c-b2ac-4f68-b992-5ccdbd5316a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 289f5b35ac223d488152ff7ee1f42b1cf50341df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798671"
---
# <span data-ttu-id="ee854-103">关于 Client 配置设置</span><span class="sxs-lookup"><span data-stu-id="ee854-103">About Client Configuration Settings</span></span>


<span data-ttu-id="ee854-104">Microsoft Application Virtualization （App-v）5.0 客户端将其配置存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="ee854-104">The Microsoft Application Virtualization (App-V) 5.0 client stores its configuration in the registry.</span></span> <span data-ttu-id="ee854-105">如果你了解注册表中的数据的格式，则可以收集有关客户端的一些有用信息。</span><span class="sxs-lookup"><span data-stu-id="ee854-105">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="ee854-106">您也可以通过更改注册表项来配置多个客户端操作。</span><span class="sxs-lookup"><span data-stu-id="ee854-106">You can also configure many client actions by changing registry entries.</span></span> <span data-ttu-id="ee854-107">本主题列出了 app-v 5.0 客户端配置设置并解释其用法。</span><span class="sxs-lookup"><span data-stu-id="ee854-107">This topic lists the App-V 5.0 Client configuration settings and explains their uses.</span></span> <span data-ttu-id="ee854-108">你可以使用 PowerShell 修改客户端配置设置。</span><span class="sxs-lookup"><span data-stu-id="ee854-108">You can use PowerShell to modify the client configuration settings.</span></span> <span data-ttu-id="ee854-109">有关使用 PowerShell 和 App-v 5.0 的详细信息，请参阅[使用 Powershell 管理 app-v](administering-app-v-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="ee854-109">For more information about using PowerShell and App-V 5.0 see [Administering App-V by Using PowerShell](administering-app-v-by-using-powershell.md).</span></span>

## <a href="" id="---------app-v-5-0-client-configuration-settings"></a> <span data-ttu-id="ee854-110">App-v 5.0 客户端配置设置</span><span class="sxs-lookup"><span data-stu-id="ee854-110">App-V 5.0 Client Configuration Settings</span></span>


<span data-ttu-id="ee854-111">下表显示了有关 App-v 5.0 客户端配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="ee854-111">The following table displays information about the App-V 5.0 client configuration settings:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ee854-112">设置名称</span><span class="sxs-lookup"><span data-stu-id="ee854-112">Setting Name</span></span></th>
<th align="left"><span data-ttu-id="ee854-113">设置标志</span><span class="sxs-lookup"><span data-stu-id="ee854-113">Setup Flag</span></span></th>
<th align="left"><span data-ttu-id="ee854-114">描述</span><span class="sxs-lookup"><span data-stu-id="ee854-114">Description</span></span></th>
<th align="left"><span data-ttu-id="ee854-115">设置选项</span><span class="sxs-lookup"><span data-stu-id="ee854-115">Setting Options</span></span></th>
<th align="left"><span data-ttu-id="ee854-116">注册表项值</span><span class="sxs-lookup"><span data-stu-id="ee854-116">Registry Key Value</span></span></th>
<th align="left"><span data-ttu-id="ee854-117">已禁用策略状态键和值</span><span class="sxs-lookup"><span data-stu-id="ee854-117">Disabled Policy State Keys and Values</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-118">PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="ee854-118">PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-119">PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="ee854-119">PACKAGEINSTALLATIONROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-120">指定将安装所有新应用程序和更新的目录。</span><span class="sxs-lookup"><span data-stu-id="ee854-120">Specifies directory where all new applications and updates will be installed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-121">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-121">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-122">Streaming\PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="ee854-122">Streaming\PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-123">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-123">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-124">PackageSourceRoot</span><span class="sxs-lookup"><span data-stu-id="ee854-124">PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-125">PACKAGESOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="ee854-125">PACKAGESOURCEROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-126">替代用于下载软件包内容的源位置。</span><span class="sxs-lookup"><span data-stu-id="ee854-126">Overrides source location for downloading package content.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-127">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-127">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-128">Streaming\PackageSourceRoot</span><span class="sxs-lookup"><span data-stu-id="ee854-128">Streaming\PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-129">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-129">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-130">AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="ee854-130">AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-131">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-131">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-132">此设置控制是否在通过按流量计费的网络连接（例如，4G）连接的 Windows 8 计算机上启动虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee854-132">This setting controls whether virtualized applications are launched on Windows 8 machines connected via a metered network connection (For example, 4G).</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-133">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-133">True (enabled); False (Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-134">Streaming\AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="ee854-134">Streaming\AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-135">0</span><span class="sxs-lookup"><span data-stu-id="ee854-135">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-136">ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="ee854-136">ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-137">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-137">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-138">指定重试已删除的会话的次数。</span><span class="sxs-lookup"><span data-stu-id="ee854-138">Specifies the number of times to retry a dropped session.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-139">整数（0-99）</span><span class="sxs-lookup"><span data-stu-id="ee854-139">Integer (0-99)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-140">Streaming\ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="ee854-140">Streaming\ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-141">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-141">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-142">ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-142">ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-143">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-143">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-144">指定尝试重新建立已删除会话之间的秒数。</span><span class="sxs-lookup"><span data-stu-id="ee854-144">Specifies the number of seconds between attempts to reestablish a dropped session.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-145">整数（0-3600）</span><span class="sxs-lookup"><span data-stu-id="ee854-145">Integer (0-3600)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-146">Streaming\ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-146">Streaming\ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-147">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-147">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-148">AutoLoad</span><span class="sxs-lookup"><span data-stu-id="ee854-148">AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-149">AUTOLOAD</span><span class="sxs-lookup"><span data-stu-id="ee854-149">AUTOLOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-150">指定如何在特定计算机上使用 app-v 自动加载新程序包。</span><span class="sxs-lookup"><span data-stu-id="ee854-150">Specifies how new packages should be loaded automatically by App-V on a specific computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-151">（0x0）无;（0x1）以前使用过的;（0x2） All</span><span class="sxs-lookup"><span data-stu-id="ee854-151">(0x0) None; (0x1) Previously used; (0x2) All</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-152">Streaming\AutoLoad</span><span class="sxs-lookup"><span data-stu-id="ee854-152">Streaming\AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-153">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-153">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-154">LocationProvider</span><span class="sxs-lookup"><span data-stu-id="ee854-154">LocationProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-155">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-155">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-156">指定 IAppvPackageLocationProvider 接口的兼容实现的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="ee854-156">Specifies the CLSID for a compatible implementation of the IAppvPackageLocationProvider interface.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-157">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-157">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-158">Streaming\LocationProvider</span><span class="sxs-lookup"><span data-stu-id="ee854-158">Streaming\LocationProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-159">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-159">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-160">CertFilterForClientSsl</span><span class="sxs-lookup"><span data-stu-id="ee854-160">CertFilterForClientSsl</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-161">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-161">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-162">指定证书存储中的有效证书的路径。</span><span class="sxs-lookup"><span data-stu-id="ee854-162">Specifies the path to a valid certificate in the certificate store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-163">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-163">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-164">Streaming\CertFilterForClientSsl</span><span class="sxs-lookup"><span data-stu-id="ee854-164">Streaming\CertFilterForClientSsl</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-165">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-165">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-166">VerifyCertificateRevocationList</span><span class="sxs-lookup"><span data-stu-id="ee854-166">VerifyCertificateRevocationList</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-167">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-167">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-168">在 steaming 使用 HTTPS 之前验证服务器证书吊销状态。</span><span class="sxs-lookup"><span data-stu-id="ee854-168">Verifies Server certificate revocation status before steaming using HTTPS.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-169">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-169">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-170">Streaming\VerifyCertificateRevocationList</span><span class="sxs-lookup"><span data-stu-id="ee854-170">Streaming\VerifyCertificateRevocationList</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-171">0</span><span class="sxs-lookup"><span data-stu-id="ee854-171">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-172">SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="ee854-172">SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-173">SHAREDCONTENTSTOREMODE</span><span class="sxs-lookup"><span data-stu-id="ee854-173">SHAREDCONTENTSTOREMODE</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-174">指定流式处理的程序包内容将不会保存到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="ee854-174">Specifies that streamed package contents will be not be saved to the local hard disk.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-175">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-175">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-176">Streaming\SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="ee854-176">Streaming\SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-177">0</span><span class="sxs-lookup"><span data-stu-id="ee854-177">0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-178">名称</span><span class="sxs-lookup"><span data-stu-id="ee854-178">Name</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-179">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-179">Note</span></span></strong><br/><p><span data-ttu-id="ee854-180">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-180">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-181">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-181">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-182">PUBLISHINGSERVERNAME</span><span class="sxs-lookup"><span data-stu-id="ee854-182">PUBLISHINGSERVERNAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-183">显示发布服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ee854-183">Displays the name of publishing server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-184">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-184">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-185">Publishing\Servers {serverId} \ FriendlyName</span><span class="sxs-lookup"><span data-stu-id="ee854-185">Publishing\Servers{serverId}\FriendlyName</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-186">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-186">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-187">URL</span><span class="sxs-lookup"><span data-stu-id="ee854-187">URL</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-188">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-188">Note</span></span></strong><br/><p><span data-ttu-id="ee854-189">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-189">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-190">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-190">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-191">PUBLISHINGSERVERURL</span><span class="sxs-lookup"><span data-stu-id="ee854-191">PUBLISHINGSERVERURL</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-192">显示发布服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="ee854-192">Displays the URL of publishing server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-193">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-193">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-194">Publishing\Servers {serverId} \ URL</span><span class="sxs-lookup"><span data-stu-id="ee854-194">Publishing\Servers{serverId}\URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-195">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-195">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-196">GlobalRefreshEnabled</span><span class="sxs-lookup"><span data-stu-id="ee854-196">GlobalRefreshEnabled</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-197">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-197">Note</span></span></strong><br/><p><span data-ttu-id="ee854-198">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-198">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-199">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-199">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-200">GLOBALREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="ee854-200">GLOBALREFRESHENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-201">启用全局发布刷新（布尔值）</span><span class="sxs-lookup"><span data-stu-id="ee854-201">Enables global publishing refresh (Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-202">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-202">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-203">Publishing\Servers{serverId}\GlobalEnabled</span><span class="sxs-lookup"><span data-stu-id="ee854-203">Publishing\Servers{serverId}\GlobalEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-204">False</span><span class="sxs-lookup"><span data-stu-id="ee854-204">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-205">GlobalRefreshOnLogon</span><span class="sxs-lookup"><span data-stu-id="ee854-205">GlobalRefreshOnLogon</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-206">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-206">Note</span></span></strong><br/><p><span data-ttu-id="ee854-207">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-207">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-208">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-208">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-209">GLOBALREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="ee854-209">GLOBALREFRESHONLOGON</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-210">在登录时触发全局发布刷新。</span><span class="sxs-lookup"><span data-stu-id="ee854-210">Triggers a global publishing refresh on logon.</span></span> <span data-ttu-id="ee854-211">布尔</span><span class="sxs-lookup"><span data-stu-id="ee854-211">( Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-212">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-212">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-213">Publishing\Servers{serverId}\GlobalLogonRefresh</span><span class="sxs-lookup"><span data-stu-id="ee854-213">Publishing\Servers{serverId}\GlobalLogonRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-214">False</span><span class="sxs-lookup"><span data-stu-id="ee854-214">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-215">GlobalRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-215">GlobalRefreshInterval</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-216">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-216">Note</span></span></strong><br/><p><span data-ttu-id="ee854-217">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-217">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-218">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-218">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-219">GLOBALREFRESHINTERVAL</span><span class="sxs-lookup"><span data-stu-id="ee854-219">GLOBALREFRESHINTERVAL</span></span>  </p></td>
<td align="left"><p><span data-ttu-id="ee854-220">使用 GlobalRefreshIntervalUnit 指定发布刷新间隔。</span><span class="sxs-lookup"><span data-stu-id="ee854-220">Specifies the publishing refresh interval using the GlobalRefreshIntervalUnit.</span></span> <span data-ttu-id="ee854-221">若要禁用程序包刷新，请选择 "0"。</span><span class="sxs-lookup"><span data-stu-id="ee854-221">To disable package refresh, select 0.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-222">整数（0-744</span><span class="sxs-lookup"><span data-stu-id="ee854-222">Integer (0-744</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-223">Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-223">Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-224">0</span><span class="sxs-lookup"><span data-stu-id="ee854-224">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-225">GlobalRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="ee854-225">GlobalRefreshIntervalUnit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-226">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-226">Note</span></span></strong><br/><p><span data-ttu-id="ee854-227">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-227">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-228">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-228">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-229">GLOBALREFRESHINTERVALUNI</span><span class="sxs-lookup"><span data-stu-id="ee854-229">GLOBALREFRESHINTERVALUNI</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-230">指定间隔单位（小时0-23，第0-31 天）。</span><span class="sxs-lookup"><span data-stu-id="ee854-230">Specifies the interval unit (Hour 0-23, Day 0-31).</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ee854-231">0表示小时，1表示天</span><span class="sxs-lookup"><span data-stu-id="ee854-231">0 for hour, 1 for day</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-232">Publishing\Servers{serverId}\GlobalPeriodicRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="ee854-232">Publishing\Servers{serverId}\GlobalPeriodicRefreshIntervalUnit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-233">raid-1</span><span class="sxs-lookup"><span data-stu-id="ee854-233">1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-234">UserRefreshEnabled</span><span class="sxs-lookup"><span data-stu-id="ee854-234">UserRefreshEnabled</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-235">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-235">Note</span></span></strong><br/><p><span data-ttu-id="ee854-236">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-236">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-237">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-237">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-238">USERREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="ee854-238">USERREFRESHENABLED</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ee854-239">启用用户发布刷新（布尔值）</span><span class="sxs-lookup"><span data-stu-id="ee854-239">Enables user publishing refresh (Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-240">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-240">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-241">Publishing\Servers{serverId}\UserEnabled</span><span class="sxs-lookup"><span data-stu-id="ee854-241">Publishing\Servers{serverId}\UserEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-242">False</span><span class="sxs-lookup"><span data-stu-id="ee854-242">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-243">UserRefreshOnLogon</span><span class="sxs-lookup"><span data-stu-id="ee854-243">UserRefreshOnLogon</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-244">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-244">Note</span></span></strong><br/><p><span data-ttu-id="ee854-245">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-245">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-246">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-246">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-247">USERREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="ee854-247">USERREFRESHONLOGON</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-248">触发用户发布刷新 onlogon。</span><span class="sxs-lookup"><span data-stu-id="ee854-248">Triggers a user publishing refresh onlogon.</span></span> <span data-ttu-id="ee854-249">布尔</span><span class="sxs-lookup"><span data-stu-id="ee854-249">( Boolean)</span></span></p>
<p><span data-ttu-id="ee854-250">字数统计（带空格）：60</span><span class="sxs-lookup"><span data-stu-id="ee854-250">Word count (with spaces): 60</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-251">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-251">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-252">Publishing\Servers{serverId}\UserLogonRefresh</span><span class="sxs-lookup"><span data-stu-id="ee854-252">Publishing\Servers{serverId}\UserLogonRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-253">False</span><span class="sxs-lookup"><span data-stu-id="ee854-253">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-254">UserRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-254">UserRefreshInterval</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-255">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-255">Note</span></span></strong><br/><p><span data-ttu-id="ee854-256">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-256">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-257">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-257">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-258">USERREFRESHINTERVAL</span><span class="sxs-lookup"><span data-stu-id="ee854-258">USERREFRESHINTERVAL</span></span>     </p></td>
<td align="left"><p><span data-ttu-id="ee854-259">使用 UserRefreshIntervalUnit 指定发布刷新间隔。</span><span class="sxs-lookup"><span data-stu-id="ee854-259">Specifies the publishing refresh interval using the UserRefreshIntervalUnit.</span></span> <span data-ttu-id="ee854-260">若要禁用程序包刷新，请选择 "0"。</span><span class="sxs-lookup"><span data-stu-id="ee854-260">To disable package refresh, select 0.</span></span></p>
<p><span data-ttu-id="ee854-261">字数统计（带空格）：85</span><span class="sxs-lookup"><span data-stu-id="ee854-261">Word count (with spaces): 85</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-262">整数（0-744 小时）</span><span class="sxs-lookup"><span data-stu-id="ee854-262">Integer (0-744 Hours)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-263">Publishing\Servers{serverId}\UserPeriodicRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-263">Publishing\Servers{serverId}\UserPeriodicRefreshInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-264">0</span><span class="sxs-lookup"><span data-stu-id="ee854-264">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-265">UserRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="ee854-265">UserRefreshIntervalUnit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-266">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-266">Note</span></span></strong><br/><p><span data-ttu-id="ee854-267">无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-267">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="ee854-268">你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee854-268">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-269">USERREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="ee854-269">USERREFRESHINTERVALUNIT</span></span>  </p></td>
<td align="left"><p><span data-ttu-id="ee854-270">指定间隔单位（小时0-23，第0-31 天）。</span><span class="sxs-lookup"><span data-stu-id="ee854-270">Specifies the interval unit (Hour 0-23, Day 0-31).</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ee854-271">0表示小时，1表示天</span><span class="sxs-lookup"><span data-stu-id="ee854-271">0 for hour, 1 for day</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-272">Publishing\Servers{serverId}\UserPeriodicRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="ee854-272">Publishing\Servers{serverId}\UserPeriodicRefreshIntervalUnit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-273">raid-1</span><span class="sxs-lookup"><span data-stu-id="ee854-273">1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-274">MigrationMode</span><span class="sxs-lookup"><span data-stu-id="ee854-274">MigrationMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-275">MIGRATIONMODE</span><span class="sxs-lookup"><span data-stu-id="ee854-275">MIGRATIONMODE</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-276">迁移模式允许 App-v 客户端修改使用早期版本的 App-v 创建的程序包的快捷方式和 FTA。</span><span class="sxs-lookup"><span data-stu-id="ee854-276">Migration mode allows the App-V client to modify shortcuts and FTA’s for packages created using a previous version of App-V.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-277">True （已启用状态）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-277">True(enabled state); False (disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-278">Coexistence\MigrationMode</span><span class="sxs-lookup"><span data-stu-id="ee854-278">Coexistence\MigrationMode</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-279">CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="ee854-279">CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-280">CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="ee854-280">CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-281">允许运行 app-v 5.0 客户端的计算机收集并返回某些使用信息，以帮助我们进一步改进应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee854-281">Allows the computer running the App-V 5.0 Client to collect and return certain usage information to help allow us to further improve the application.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-282">0表示已禁用;1表示已启用</span><span class="sxs-lookup"><span data-stu-id="ee854-282">0 for disabled; 1 for enabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-283">软件/Microsoft/AppV/CEIP/CEIPEnable</span><span class="sxs-lookup"><span data-stu-id="ee854-283">SOFTWARE/Microsoft/AppV/CEIP/CEIPEnable</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-284">0</span><span class="sxs-lookup"><span data-stu-id="ee854-284">0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-285">EnablePackageScripts</span><span class="sxs-lookup"><span data-stu-id="ee854-285">EnablePackageScripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-286">ENABLEPACKAGESCRIPTS</span><span class="sxs-lookup"><span data-stu-id="ee854-286">ENABLEPACKAGESCRIPTS</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-287">支持在应运行的配置文件的程序包清单中定义的脚本。</span><span class="sxs-lookup"><span data-stu-id="ee854-287">Enables scripts defined in the package manifest of configuration files that should run.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-288">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-288">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-289">\Scripting\EnablePackageScripts</span><span class="sxs-lookup"><span data-stu-id="ee854-289">\Scripting\EnablePackageScripts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-290">RoamingFileExclusions</span><span class="sxs-lookup"><span data-stu-id="ee854-290">RoamingFileExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-291">ROAMINGFILEEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="ee854-291">ROAMINGFILEEXCLUSIONS</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-292">指定相对于% userprofile% 的文件路径，不要与用户&#39;s 配置文件一起漫游。</span><span class="sxs-lookup"><span data-stu-id="ee854-292">Specifies the file paths relative to %userprofile% that do not roam with a user&#39;s profile.</span></span> <span data-ttu-id="ee854-293">示例用法：/ROAMINGFILEEXCLUSIONS =&#39;桌面; 我的图片&#39;</span><span class="sxs-lookup"><span data-stu-id="ee854-293">Example usage:  /ROAMINGFILEEXCLUSIONS=&#39;desktop;my pictures&#39;</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-294">RoamingRegistryExclusions</span><span class="sxs-lookup"><span data-stu-id="ee854-294">RoamingRegistryExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-295">ROAMINGREGISTRYEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="ee854-295">ROAMINGREGISTRYEXCLUSIONS</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-296">指定不与用户配置文件一起漫游的注册表路径。</span><span class="sxs-lookup"><span data-stu-id="ee854-296">Specifies the registry paths that do not roam with a user profile.</span></span> <span data-ttu-id="ee854-297">示例用法：/ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</span><span class="sxs-lookup"><span data-stu-id="ee854-297">Example usage: /ROAMINGREGISTRYEXCLUSIONS=software\classes;software\clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-298">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-298">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-299">Integration\RoamingRegistryExclusions</span><span class="sxs-lookup"><span data-stu-id="ee854-299">Integration\RoamingRegistryExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-300">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-300">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-301">IntegrationRootUser</span><span class="sxs-lookup"><span data-stu-id="ee854-301">IntegrationRootUser</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-302">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-302">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-303">指定创建与每用户已发布程序包的当前版本相关联的符号链接的位置。</span><span class="sxs-lookup"><span data-stu-id="ee854-303">Specifies the location to create symbolic links associated with the current version of a per-user published package.</span></span> <span data-ttu-id="ee854-304">所有虚拟应用程序扩展（例如快捷方式和文件类型关联）都将指向此路径。</span><span class="sxs-lookup"><span data-stu-id="ee854-304">all virtual application extensions, for example shortcuts and file type associations, will point to this path.</span></span> <span data-ttu-id="ee854-305">如果不指定路径，则在发布包时不会使用符号链接。</span><span class="sxs-lookup"><span data-stu-id="ee854-305">If you do not specify a path, symbolic links will not be used when you publish the package.</span></span> <span data-ttu-id="ee854-306">例如：%localappdata%\Microsoft\AppV\Client\Integration。</span><span class="sxs-lookup"><span data-stu-id="ee854-306">For example: %localappdata%\Microsoft\AppV\Client\Integration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-307">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-307">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-308">Integration\IntegrationRootUser</span><span class="sxs-lookup"><span data-stu-id="ee854-308">Integration\IntegrationRootUser</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-309">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-309">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-310">IntegrationRootGlobal</span><span class="sxs-lookup"><span data-stu-id="ee854-310">IntegrationRootGlobal</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-311">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-311">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-312">指定创建与全局发布的程序包的当前版本相关联的符号链接的位置。</span><span class="sxs-lookup"><span data-stu-id="ee854-312">Specifies the location to create symbolic links associated with the current version of a globally published package.</span></span> <span data-ttu-id="ee854-313">所有虚拟应用程序扩展（例如快捷方式和文件类型关联）都将指向此路径。</span><span class="sxs-lookup"><span data-stu-id="ee854-313">all virtual application extensions, for example shortcuts and file type associations, will point to this path.</span></span> <span data-ttu-id="ee854-314">如果不指定路径，则在发布包时不会使用符号链接。</span><span class="sxs-lookup"><span data-stu-id="ee854-314">If you do not specify a path, symbolic links will not be used when you publish the package.</span></span> <span data-ttu-id="ee854-315">例如：%allusersprofile%\Microsoft\AppV\Client\Integration</span><span class="sxs-lookup"><span data-stu-id="ee854-315">For example: %allusersprofile%\Microsoft\AppV\Client\Integration</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-316">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-316">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-317">Integration\IntegrationRootGlobal</span><span class="sxs-lookup"><span data-stu-id="ee854-317">Integration\IntegrationRootGlobal</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-318">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-318">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-319">VirtualizableExtensions</span><span class="sxs-lookup"><span data-stu-id="ee854-319">VirtualizableExtensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-320">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-320">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-321">可用于确定本地安装的应用程序是否可以在虚拟环境中运行的文件扩展名的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ee854-321">A comma -delineated list of file name extensions that can be used to determine if a locally installed application can be run in the virtual environment.</span></span></p>
<p><span data-ttu-id="ee854-322">在发布期间创建快捷方式、FTAs 和其他扩展点时，如果与扩展点关联的应用程序在本地安装，则 App-v 会将文件扩展名与列表进行比较。</span><span class="sxs-lookup"><span data-stu-id="ee854-322">When shortcuts, FTAs, and other extension points are created during publishing, App-V will compare the file name extension to the list if the application that is associated with the extension point is locally installed.</span></span> <span data-ttu-id="ee854-323">如果扩展已找到，则 <strong> </strong> 将添加 RunVirtual 命令行参数，并且应用程序将完全运行。</span><span class="sxs-lookup"><span data-stu-id="ee854-323">If the extension is located, the <strong>RunVirtual</strong> command line parameter will be added, and the application will run virtually.</span></span></p>
<p><span data-ttu-id="ee854-324">有关 RunVirtual 参数的详细 <strong> 信息 </strong> ，请参阅 <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)"> 在虚拟环境中使用虚拟化的应用程序运行本地安装的应用程序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ee854-324">For more information about the <strong>RunVirtual</strong> parameter, see <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)">Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications</a>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-325">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-325">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-326">Integration\VirtualizableExtensions</span><span class="sxs-lookup"><span data-stu-id="ee854-326">Integration\VirtualizableExtensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-327">策略值未写入</span><span class="sxs-lookup"><span data-stu-id="ee854-327">Policy value not written</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-328">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="ee854-328">ReportingEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-329">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-329">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-330">使客户端能够将信息返回到报表服务器。</span><span class="sxs-lookup"><span data-stu-id="ee854-330">Enables the client to return information to a reporting server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-331">True （已启用）;False （已禁用状态）</span><span class="sxs-lookup"><span data-stu-id="ee854-331">True (enabled); False (Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-332">Reporting\EnableReporting</span><span class="sxs-lookup"><span data-stu-id="ee854-332">Reporting\EnableReporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-333">False</span><span class="sxs-lookup"><span data-stu-id="ee854-333">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-334">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="ee854-334">ReportingServerURL</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-335">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-335">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-336">指定报表服务器上保存客户端信息的位置。</span><span class="sxs-lookup"><span data-stu-id="ee854-336">Specifies the location on the reporting server where client information is saved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-337">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-337">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-338">Reporting\ReportingServer</span><span class="sxs-lookup"><span data-stu-id="ee854-338">Reporting\ReportingServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-339">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-339">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-340">ReportingDataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="ee854-340">ReportingDataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-341">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-341">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-342">指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。</span><span class="sxs-lookup"><span data-stu-id="ee854-342">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="ee854-343">大小应用于内存中的缓存。</span><span class="sxs-lookup"><span data-stu-id="ee854-343">The size applies to the cache in memory.</span></span> <span data-ttu-id="ee854-344">达到限制时，日志文件将翻转。</span><span class="sxs-lookup"><span data-stu-id="ee854-344">When the limit is reached, the log file will roll over.</span></span> <span data-ttu-id="ee854-345">在0和1024之间设置。</span><span class="sxs-lookup"><span data-stu-id="ee854-345">Set between 0 and 1024.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-346">Integer [0-1024]</span><span class="sxs-lookup"><span data-stu-id="ee854-346">Integer [0-1024]</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-347">Reporting\DataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="ee854-347">Reporting\DataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-348">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-348">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-349">ReportingDataBlockSize</span><span class="sxs-lookup"><span data-stu-id="ee854-349">ReportingDataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-350">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-350">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-351">指定用于报告上载请求的服务器传输到服务器的最大大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ee854-351">Specifies the maximum size in bytes to transmit to the server for reporting upload requests.</span></span> <span data-ttu-id="ee854-352">这有助于避免在日志达到较大大小时出现永久性传输故障。</span><span class="sxs-lookup"><span data-stu-id="ee854-352">This can help avoid permanent transmission failures when the log has reached a significant size.</span></span> <span data-ttu-id="ee854-353">设置为1024和无限制。</span><span class="sxs-lookup"><span data-stu-id="ee854-353">Set between 1024 and unlimited.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-354">Integer [1024-无限]</span><span class="sxs-lookup"><span data-stu-id="ee854-354">Integer [1024 - Unlimited]</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-355">Reporting\DataBlockSize</span><span class="sxs-lookup"><span data-stu-id="ee854-355">Reporting\DataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-356">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-356">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-357">ReportingStartTime</span><span class="sxs-lookup"><span data-stu-id="ee854-357">ReportingStartTime</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-358">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-358">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-359">指定启动客户端以将数据发送到报告服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="ee854-359">Specifies the time to initiate the client to send data to the reporting server.</span></span> <span data-ttu-id="ee854-360">你必须在0-23 之间指定一个有效的整数，对应于一天中的小时。</span><span class="sxs-lookup"><span data-stu-id="ee854-360">You must specify a valid integer between 0-23 corresponding to the hour of the day.</span></span> <span data-ttu-id="ee854-361">默认情况下， <strong> ReportingStartTime </strong> 将在当前日期的10个第 M 个、第 M 个或第22天开始。</span><span class="sxs-lookup"><span data-stu-id="ee854-361">By default the <strong>ReportingStartTime</strong> will start on the current day at 10 P.M.or 22.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-362">注意</span><span class="sxs-lookup"><span data-stu-id="ee854-362">Note</span></span></strong><br/><p><span data-ttu-id="ee854-363">当运行 App-v 5.0 客户端的计算机最有可能处于离线状态时，应将此设置配置为一个时间。</span><span class="sxs-lookup"><span data-stu-id="ee854-363">You should configure this setting to a time when computers running the App-V 5.0 client are least likely to be offline.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-364">整数（0–23）</span><span class="sxs-lookup"><span data-stu-id="ee854-364">Integer (0 – 23)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-365">报告 \ 开始</span><span class="sxs-lookup"><span data-stu-id="ee854-365">Reporting\ StartTime</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-366">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-366">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-367">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-367">ReportingInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-368">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-368">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-369">指定客户端将用于向报告服务器重新发送数据的重试间隔。</span><span class="sxs-lookup"><span data-stu-id="ee854-369">Specifies the retry interval that the client will use to resend data to the reporting server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-370">整型</span><span class="sxs-lookup"><span data-stu-id="ee854-370">Integer</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-371">Reporting\RetryInterval</span><span class="sxs-lookup"><span data-stu-id="ee854-371">Reporting\RetryInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-372">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-372">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-373">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="ee854-373">ReportingRandomDelay</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-374">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-374">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-375">指定发送到报告服务器的数据的最大延迟（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="ee854-375">Specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="ee854-376">当计划任务启动时，客户端会在0和 ReportingRandomDelay 之间生成一个随机延迟， <strong> </strong> 并在发送数据之前等待指定的持续时间。</span><span class="sxs-lookup"><span data-stu-id="ee854-376">When the scheduled task is started, the client generates a random delay between 0 and <strong>ReportingRandomDelay</strong> and will wait the specified duration before sending data.</span></span> <span data-ttu-id="ee854-377">这有助于防止服务器冲突。</span><span class="sxs-lookup"><span data-stu-id="ee854-377">This can help to prevent collisions on the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-378">Integer [0-ReportingRandomDelay]</span><span class="sxs-lookup"><span data-stu-id="ee854-378">Integer [0 - ReportingRandomDelay]</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-379">Reporting\RandomDelay</span><span class="sxs-lookup"><span data-stu-id="ee854-379">Reporting\RandomDelay</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-380">未写入策略值（与 "未配置" 相同）</span><span class="sxs-lookup"><span data-stu-id="ee854-380">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-381">EnableDynamicVirtualization</span><span class="sxs-lookup"><span data-stu-id="ee854-381">EnableDynamicVirtualization</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-382">重要提示</span><span class="sxs-lookup"><span data-stu-id="ee854-382">Important</span></span></strong><br/><p><span data-ttu-id="ee854-383">此设置仅适用于 app-v 5.0 SP2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ee854-383">This setting is available only with App-V 5.0 SP2 or later.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-384">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-384">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-385">启用要虚拟化并与虚拟应用程序一起运行的受支持的 Shell 扩展、浏览器帮助程序对象和 Active X 控件。</span><span class="sxs-lookup"><span data-stu-id="ee854-385">Enables supported Shell Extensions, Browser Helper Objects, and Active X controls to be virtualized and run with virtual applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-386">1（已启用），0（已禁用）</span><span class="sxs-lookup"><span data-stu-id="ee854-386">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-387">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization</span><span class="sxs-lookup"><span data-stu-id="ee854-387">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\Virtualization</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-388">EnablePublishingRefreshUI</span><span class="sxs-lookup"><span data-stu-id="ee854-388">EnablePublishingRefreshUI</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-389">重要提示</span><span class="sxs-lookup"><span data-stu-id="ee854-389">Important</span></span></strong><br/><p><span data-ttu-id="ee854-390">此设置仅适用于 app-v 5.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="ee854-390">This setting is available only with App-V 5.0 SP2.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-391">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-391">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-392">为运行 app-v 5.0 客户端的计算机启用发布刷新进度栏。</span><span class="sxs-lookup"><span data-stu-id="ee854-392">Enables the publishing refresh progress bar for the computer running the App-V 5.0 Client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-393">1（已启用），0（已禁用）</span><span class="sxs-lookup"><span data-stu-id="ee854-393">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-394">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing</span><span class="sxs-lookup"><span data-stu-id="ee854-394">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\Publishing</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee854-395">HideUI</span><span class="sxs-lookup"><span data-stu-id="ee854-395">HideUI</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ee854-396">重要提示</span><span class="sxs-lookup"><span data-stu-id="ee854-396">Important</span></span></strong><br/><p><span data-ttu-id="ee854-397">此设置仅适用于 app-v 5.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="ee854-397">This setting is available only with App-V 5.0 SP2.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="ee854-398">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-398">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-399">隐藏发布刷新进度栏。</span><span class="sxs-lookup"><span data-stu-id="ee854-399">Hides the publishing refresh progress bar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-400">1（已启用），0（已禁用）</span><span class="sxs-lookup"><span data-stu-id="ee854-400">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee854-401">ProcessesUsingVirtualComponents</span><span class="sxs-lookup"><span data-stu-id="ee854-401">ProcessesUsingVirtualComponents</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-402">不可用。</span><span class="sxs-lookup"><span data-stu-id="ee854-402">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-403">指定处理路径（可能包含通配符）的列表，这些路径是使用动态虚拟化（支持的 shell 扩展、浏览器帮助程序对象和 ActiveX 控件）的候选对象。</span><span class="sxs-lookup"><span data-stu-id="ee854-403">Specifies a list of process paths (that may contain wildcards), which are candidates for using dynamic virtualization (supported shell extensions, browser helper objects, and ActiveX controls).</span></span> <span data-ttu-id="ee854-404">只有其完整路径与其中一个项目相匹配的进程才能使用动态虚拟化。</span><span class="sxs-lookup"><span data-stu-id="ee854-404">Only processes whose full path matches one of these items can use dynamic virtualization.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-405">字符串</span><span class="sxs-lookup"><span data-stu-id="ee854-405">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-406">Virtualization\ProcessesUsingVirtualComponents</span><span class="sxs-lookup"><span data-stu-id="ee854-406">Virtualization\ProcessesUsingVirtualComponents</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee854-407">空字符串。</span><span class="sxs-lookup"><span data-stu-id="ee854-407">Empty string.</span></span></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="ee854-408">相关主题</span><span class="sxs-lookup"><span data-stu-id="ee854-408">Related topics</span></span>


[<span data-ttu-id="ee854-409">部署 App-V 5.0 Sequencer 和 Client</span><span class="sxs-lookup"><span data-stu-id="ee854-409">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

[<span data-ttu-id="ee854-410">如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置</span><span class="sxs-lookup"><span data-stu-id="ee854-410">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span>](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)

[<span data-ttu-id="ee854-411">如何部署 App-V Client</span><span class="sxs-lookup"><span data-stu-id="ee854-411">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-gb18030.md)









