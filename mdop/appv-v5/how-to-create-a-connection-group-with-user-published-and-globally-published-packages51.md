---
title: 如何创建与用户发布和全局发布的程序包的连接组
description: 如何创建与用户发布和全局发布的程序包的连接组
author: dansimp
ms.assetid: 851b8742-0283-4aa6-b3a3-f7f6289824c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 230e687360920c05a214624750eba54dc84b5731
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798527"
---
# <span data-ttu-id="0beff-103">如何创建与用户发布和全局发布的程序包的连接组</span><span class="sxs-lookup"><span data-stu-id="0beff-103">How to Create a Connection Group with User-Published and Globally Published Packages</span></span>


<span data-ttu-id="0beff-104">你可以使用以下两种方法之一创建包含用户发布和全局发布的程序包的用户具有标题的连接组：</span><span class="sxs-lookup"><span data-stu-id="0beff-104">You can create user-entitled connection groups that contain both user-published and globally published packages, using either of the following methods:</span></span>

-   [<span data-ttu-id="0beff-105">如何使用 PowerShell cmdlet 创建用户有资格的连接组</span><span class="sxs-lookup"><span data-stu-id="0beff-105">How to use PowerShell cmdlets to create the user-entitled connection groups</span></span>](#bkmk-posh-userentitled-cg)

-   [<span data-ttu-id="0beff-106">如何使用 App-v 服务器创建用户有资格的连接组</span><span class="sxs-lookup"><span data-stu-id="0beff-106">How to use the App-V Server to create the user-entitled connection groups</span></span>](#bkmk-appvserver-userentitled-cg)

**<span data-ttu-id="0beff-107">开始之前应了解的事项：</span><span class="sxs-lookup"><span data-stu-id="0beff-107">What to know before you start:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0beff-108">不受支持的方案和潜在问题</span><span class="sxs-lookup"><span data-stu-id="0beff-108">Unsupported scenarios and potential issues</span></span></th>
<th align="left"><span data-ttu-id="0beff-109">结果</span><span class="sxs-lookup"><span data-stu-id="0beff-109">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0beff-110">您不能在具有标题的连接组中包含用户发布的程序包。</span><span class="sxs-lookup"><span data-stu-id="0beff-110">You cannot include user-published packages in globally entitled connection groups.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0beff-111">连接组将失败。</span><span class="sxs-lookup"><span data-stu-id="0beff-111">The connection group will fail.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0beff-112">如果你在全局范围内发布程序包，然后创建用户发布的连接组（你已将该程序包设置为非可选），仍可以运行 <strong> 取消发布-AppvClientPackage &lt; 包 &gt; -全局 </strong> 来取消发布程序包，即使该程序包正在另一连接组中使用也是如此。</span><span class="sxs-lookup"><span data-stu-id="0beff-112">If you publish a package globally and then create a user-published connection group in which you’ve made that package non-optional, you can still run <strong>Unpublish-AppvClientPackage &lt;package&gt; -global</strong> to unpublish the package, even when that package is being used in another connection group.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0beff-113">如果任何其他连接组正在使用该程序包，则该程序包将在这些连接组中失败。</span><span class="sxs-lookup"><span data-stu-id="0beff-113">If any other connection groups are using that package, the package will fail in those connection groups.</span></span></p>
<p><span data-ttu-id="0beff-114">为了避免无意间取消发布在其他连接组中使用的非可选程序包，我们建议你跟踪已使用非可选程序包的连接组。</span><span class="sxs-lookup"><span data-stu-id="0beff-114">To avoid inadvertently unpublishing a non-optional package that is being used in another connection group, we recommend that you track the connection groups in which you’ve used a non-optional package.</span></span></p></td>
</tr>
</tbody>
</table>

<a href="" id="bkmk-posh-userentitled-cg"></a>**<span data-ttu-id="0beff-115">如何使用 PowerShell cmdlet 创建用户有资格的连接组</span><span class="sxs-lookup"><span data-stu-id="0beff-115">How to use PowerShell cmdlets to create user-entitled connection groups</span></span>**

1.  <span data-ttu-id="0beff-116">使用以下命令添加和发布程序包：</span><span class="sxs-lookup"><span data-stu-id="0beff-116">Add and publish packages by using the following commands:</span></span>

    **<span data-ttu-id="0beff-117">Add-AppvClientPackage Package1 \ _AppV \ _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="0beff-117">Add-AppvClientPackage Package1\_AppV\_file\_Path</span></span>**

    **<span data-ttu-id="0beff-118">Add-AppvClientPackage Package2 \ _AppV \ _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="0beff-118">Add-AppvClientPackage Package2\_AppV\_file\_Path</span></span>**

    **<span data-ttu-id="0beff-119">AppvClientPackage-PackageId ID-Global _Version _ID Package1</span><span class="sxs-lookup"><span data-stu-id="0beff-119">Publish-AppvClientPackage -PackageId Package1\_ID-VersionId Package1\_Version ID -Global</span></span>**

    **<span data-ttu-id="0beff-120">Publish-AppvClientPackage-PackageId Package2 \ _ID-VersionIdPackage2 \ _ID</span><span class="sxs-lookup"><span data-stu-id="0beff-120">Publish-AppvClientPackage -PackageId Package2\_ID -VersionIdPackage2\_ID</span></span>**

2.  <span data-ttu-id="0beff-121">创建连接组 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="0beff-121">Create the connection group XML file.</span></span> <span data-ttu-id="0beff-122">有关详细信息，请参阅[关于连接组文件](about-the-connection-group-file51.md)。</span><span class="sxs-lookup"><span data-stu-id="0beff-122">For more information, see [About the Connection Group File](about-the-connection-group-file51.md).</span></span>

3.  <span data-ttu-id="0beff-123">使用以下命令添加和发布连接组：</span><span class="sxs-lookup"><span data-stu-id="0beff-123">Add and publish the connection group by using the following commands:</span></span>

    **<span data-ttu-id="0beff-124">AppvClientConnectionGroup 连接 \ _Group \ _XML \ _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="0beff-124">Add-AppvClientConnectionGroup Connection\_Group\_XML\_file\_Path</span></span>**

    **<span data-ttu-id="0beff-125">Enable-AppvClientConnectionGroup-GroupId cg \ _Group \ _ID-VersionId CG \ _Version \ _ID</span><span class="sxs-lookup"><span data-stu-id="0beff-125">Enable-AppvClientConnectionGroup -GroupId CG\_Group\_ID-VersionId CG\_Version\_ID</span></span>**

<a href="" id="bkmk-appvserver-userentitled-cg"></a>**<span data-ttu-id="0beff-126">如何使用 App-v 服务器创建用户有资格的连接组</span><span class="sxs-lookup"><span data-stu-id="0beff-126">How to use the App-V Server to create user-entitled connection groups</span></span>**

1.  <span data-ttu-id="0beff-127">打开 app-v 5.1 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0beff-127">Open the App-V 5.1 Management Console.</span></span>

2.  <span data-ttu-id="0beff-128">按照[如何发布程序包的说明，使用管理控制台](how-to-publish-a-package-by-using-the-management-console-51.md)全局发布程序包和向用户发布程序包。</span><span class="sxs-lookup"><span data-stu-id="0beff-128">Follow the instructions in [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md) to publish packages globally and to the user.</span></span>

3.  <span data-ttu-id="0beff-129">按照[如何创建连接组](how-to-create-a-connection-group51.md)以创建连接组的说明进行操作，并添加用户发布和全局发布的程序包。</span><span class="sxs-lookup"><span data-stu-id="0beff-129">Follow the instructions in [How to Create a Connection Group](how-to-create-a-connection-group51.md) to create the connection group, and add the user-published and globally published packages.</span></span>

    <span data-ttu-id="0beff-130">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="0beff-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0beff-131">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="0beff-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0beff-132">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="0beff-132">Got an App-V issue?</span></span>** <span data-ttu-id="0beff-133">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="0beff-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0beff-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="0beff-134">Related topics</span></span>


[<span data-ttu-id="0beff-135">管理连接组</span><span class="sxs-lookup"><span data-stu-id="0beff-135">Managing Connection Groups</span></span>](managing-connection-groups51.md)

[<span data-ttu-id="0beff-136">如何使用连接组中的可选程序包</span><span class="sxs-lookup"><span data-stu-id="0beff-136">How to Use Optional Packages in Connection Groups</span></span>](how-to-use-optional-packages-in-connection-groups51.md)

 

 





