---
title: 如何使用 PowerShell 管理独立计算机上的连接组
description: 如何使用 PowerShell 管理独立计算机上的连接组
author: dansimp
ms.assetid: e1589eff-d306-40fb-a0ae-727190dafe26
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: ab120f7089619fa01885d5182313dc33fc47f827
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798408"
---
# <span data-ttu-id="de786-103">如何使用 PowerShell 管理独立计算机上的连接组</span><span class="sxs-lookup"><span data-stu-id="de786-103">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span>


<span data-ttu-id="de786-104">App-v 连接组允许你将所有虚拟应用程序作为单个虚拟环境中定义的程序包集运行。</span><span class="sxs-lookup"><span data-stu-id="de786-104">An App-V connection group allows you to run all the virtual applications as a defined set of packages in a single virtual environment.</span></span> <span data-ttu-id="de786-105">例如，你可以使用单独的程序包虚拟化应用程序及其插件，但将它们一起运行在单个连接组中。</span><span class="sxs-lookup"><span data-stu-id="de786-105">For example, you can virtualize an application and its plug-ins by using separate packages, but run them together in a single connection group.</span></span>

<span data-ttu-id="de786-106">连接组 XML 文件定义在安装了 App-v 客户端的计算机上运行的连接组。</span><span class="sxs-lookup"><span data-stu-id="de786-106">A connection group XML file defines the connection group that runs on the computer where you’ve installed the App-V client.</span></span> <span data-ttu-id="de786-107">有关连接组 XML 文件以及如何配置它的信息，请参阅[关于连接组文件](about-the-connection-group-file51.md)。</span><span class="sxs-lookup"><span data-stu-id="de786-107">For information about the connection group XML file and how to configure it, see [About the Connection Group File](about-the-connection-group-file51.md).</span></span>

<span data-ttu-id="de786-108">本主题介绍下列过程：</span><span class="sxs-lookup"><span data-stu-id="de786-108">This topic explains the following procedures:</span></span>

-   [<span data-ttu-id="de786-109">在连接组中添加和发布 app-v 程序包</span><span class="sxs-lookup"><span data-stu-id="de786-109">To add and publish the App-V packages in the connection group</span></span>](#bkmk-add-pub-pkgs-in-cg)

-   [<span data-ttu-id="de786-110">在 App-v 客户端上添加和启用连接组</span><span class="sxs-lookup"><span data-stu-id="de786-110">To add and enable the connection group on the App-V client</span></span>](#bkmk-add-enable-cg-on-clt)

-   [<span data-ttu-id="de786-111">为特定用户启用或禁用连接组</span><span class="sxs-lookup"><span data-stu-id="de786-111">To enable or disable a connection group for a specific user</span></span>](#bkmk-enable-cg-for-user-poshtopic)

-   [<span data-ttu-id="de786-112">仅允许管理员启用连接组</span><span class="sxs-lookup"><span data-stu-id="de786-112">To allow only administrators to enable connection groups</span></span>](#bkmk-admin-only-posh-topic-cg)

<a href="" id="bkmk-add-pub-pkgs-in-cg"></a><span data-ttu-id="de786-113">*在连接组中添加和发布 app-v 程序包*\*</span><span class="sxs-lookup"><span data-stu-id="de786-113">*To add and publish the App-V packages in the connection group*\*</span></span>

1.  <span data-ttu-id="de786-114">若要将 app-v 5.1 程序包添加并发布到运行 App-v 客户端的计算机，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="de786-114">To add and publish the App-V 5.1 packages to the computer running the App-V client, type the following command:</span></span>

    <span data-ttu-id="de786-115">AppvClientPackage – path c:\\tmpstore\\quartfin.appv |发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="de786-115">Add-AppvClientPackage –path c:\\tmpstore\\quartfin.appv | Publish-AppvClientPackage</span></span>

2.  <span data-ttu-id="de786-116">对 "连接" 组中的每个程序包重复此过程的**步骤 1** 。</span><span class="sxs-lookup"><span data-stu-id="de786-116">Repeat **step 1** of this procedure for each package in the connection group.</span></span>

<a href="" id="bkmk-add-enable-cg-on-clt"></a>**<span data-ttu-id="de786-117">在 App-v 客户端上添加和启用连接组</span><span class="sxs-lookup"><span data-stu-id="de786-117">To add and enable the connection group on the App-V client</span></span>**

1.  <span data-ttu-id="de786-118">通过键入以下命令来添加连接组：</span><span class="sxs-lookup"><span data-stu-id="de786-118">Add the connection group by typing the following command:</span></span>

    <span data-ttu-id="de786-119">AppvClientConnectionGroup-路径 c:\\tmpstore\\financ.xml</span><span class="sxs-lookup"><span data-stu-id="de786-119">Add-AppvClientConnectionGroup –path c:\\tmpstore\\financ.xml</span></span>

2.  <span data-ttu-id="de786-120">通过键入以下命令启用连接组：</span><span class="sxs-lookup"><span data-stu-id="de786-120">Enable the connection group by typing the following command:</span></span>

    <span data-ttu-id="de786-121">Enable-AppvClientConnectionGroup-名称 "财务应用程序"</span><span class="sxs-lookup"><span data-stu-id="de786-121">Enable-AppvClientConnectionGroup –name “Financial Applications”</span></span>

    <span data-ttu-id="de786-122">当成员程序包中的任何虚拟应用程序在目标计算机上运行时，它们将在连接组的虚拟环境内运行，并且将在连接组中的其他程序包内的所有虚拟应用程序中可用。</span><span class="sxs-lookup"><span data-stu-id="de786-122">When any virtual applications that are in the member packages are run on the target computer, they will run inside the connection group’s virtual environment and will be available to all the virtual applications in the other packages in the connection group.</span></span>

<a href="" id="bkmk-enable-cg-for-user-poshtopic"></a>**<span data-ttu-id="de786-123">为特定用户启用或禁用连接组</span><span class="sxs-lookup"><span data-stu-id="de786-123">To enable or disable a connection group for a specific user</span></span>**

1.  <span data-ttu-id="de786-124">查看参数说明和要求：</span><span class="sxs-lookup"><span data-stu-id="de786-124">Review the parameter description and requirements:</span></span>

    -   <span data-ttu-id="de786-125">该参数使管理员能够为特定用户启用或禁用连接组。</span><span class="sxs-lookup"><span data-stu-id="de786-125">The parameter enables an administrator to enable or disable a connection group for a specific user.</span></span>

    -   <span data-ttu-id="de786-126">必须使用 App-v 5.0 SP2 修补程序包5或更高版本才能使用此参数。</span><span class="sxs-lookup"><span data-stu-id="de786-126">You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

    -   <span data-ttu-id="de786-127">你可以从用户或管理员会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de786-127">You can run this cmdlet from the user or administrator session.</span></span>

    -   <span data-ttu-id="de786-128">必须使用管理凭据登录才能使用该参数。</span><span class="sxs-lookup"><span data-stu-id="de786-128">You must be logged in with administrative credentials to use the parameter.</span></span>

    -   <span data-ttu-id="de786-129">最终用户必须登录。</span><span class="sxs-lookup"><span data-stu-id="de786-129">The end user must be logged in.</span></span>

    -   <span data-ttu-id="de786-130">您必须提供最终用户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="de786-130">You must provide the end user’s security identifier (SID).</span></span>

2.  <span data-ttu-id="de786-131">使用以下 cmdlet，并添加可选的 **-UserSID**参数，其中 **-UserSID**表示最终用户的安全标识符（SID）：</span><span class="sxs-lookup"><span data-stu-id="de786-131">Use the following cmdlets, and add the optional **–UserSID** parameter, where **-UserSID** represents the end user’s security identifier (SID):</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="de786-132">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="de786-132">Cmdlet</span></span></th>
    <th align="left"><span data-ttu-id="de786-133">示例</span><span class="sxs-lookup"><span data-stu-id="de786-133">Examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="de786-134">Enable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="de786-134">Enable-AppVClientConnectionGroup</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de786-135">Enable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="de786-135">Enable-AppVClientConnectionGroup “ConnectionGroupA” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="de786-136">Disable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="de786-136">Disable -AppVClientConnectionGroup</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de786-137">Disable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="de786-137">Disable -AppVClientConnectionGroup “ConnectionGroupA” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
    </tr>
    </tbody>
    </table>

<a href="" id="bkmk-admin-only-posh-topic-cg"></a>**<span data-ttu-id="de786-138">仅允许管理员启用连接组</span><span class="sxs-lookup"><span data-stu-id="de786-138">To allow only administrators to enable connection groups</span></span>**

1.  <span data-ttu-id="de786-139">查看使用此 cmdlet 的说明和要求：</span><span class="sxs-lookup"><span data-stu-id="de786-139">Review the description and requirement for using this cmdlet:</span></span>

    -   <span data-ttu-id="de786-140">使用此 cmdlet 和参数将 App-v 客户端配置为仅允许管理员（而非最终用户）启用或禁用连接组。</span><span class="sxs-lookup"><span data-stu-id="de786-140">Use this cmdlet and parameter to configure the App-V client to allow only administrators (not end users) to enable or disable connection groups.</span></span>

    -   <span data-ttu-id="de786-141">必须至少使用 app-v 5.0 SP3 才能使用此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de786-141">You must be using at least App-V 5.0 SP3 to use this cmdlet.</span></span>

2.  <span data-ttu-id="de786-142">运行以下 cmdlet 和参数：</span><span class="sxs-lookup"><span data-stu-id="de786-142">Run the following cmdlet and parameter:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="de786-143">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="de786-143">Cmdlet</span></span></th>
    <th align="left"><span data-ttu-id="de786-144">参数和值</span><span class="sxs-lookup"><span data-stu-id="de786-144">Parameter and values</span></span></th>
    <th align="left"><span data-ttu-id="de786-145">示例</span><span class="sxs-lookup"><span data-stu-id="de786-145">Example</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="de786-146">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="de786-146">Set-AppvClientConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de786-147">–RequirePublishAsAdmin</span><span class="sxs-lookup"><span data-stu-id="de786-147">–RequirePublishAsAdmin</span></span></p>
    <ul>
    <li><p><span data-ttu-id="de786-148">0-假</span><span class="sxs-lookup"><span data-stu-id="de786-148">0 - False</span></span></p></li>
    <li><p><span data-ttu-id="de786-149">1-True</span><span class="sxs-lookup"><span data-stu-id="de786-149">1 - True</span></span></p></li>
    </ul></td>
    <td align="left"><p><span data-ttu-id="de786-150">Set-AppvClientConfiguration-RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="de786-150">Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="de786-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="de786-151">Related topics</span></span>


[<span data-ttu-id="de786-152">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="de786-152">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="de786-153">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="de786-153">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)









