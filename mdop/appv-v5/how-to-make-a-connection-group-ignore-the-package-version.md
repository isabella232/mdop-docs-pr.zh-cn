---
title: 如何使连接组忽略程序包版本
description: 如何使连接组忽略程序包版本
author: dansimp
ms.assetid: 6ebc1bff-d190-4f4c-a6da-e09a4cca7874
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b64d1938419aef184c5df667bf71b8157de0450a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798426"
---
# <span data-ttu-id="28e6f-103">如何使连接组忽略程序包版本</span><span class="sxs-lookup"><span data-stu-id="28e6f-103">How to Make a Connection Group Ignore the Package Version</span></span>


<span data-ttu-id="28e6f-104">Microsoft Application Virtualization （App-v） 5.0 SP3 使你能够将连接组配置为使用任何版本的程序包，从而简化程序包升级并减少你需要创建的连接组的数量。</span><span class="sxs-lookup"><span data-stu-id="28e6f-104">Microsoft Application Virtualization (App-V) 5.0 SP3 enables you to configure a connection group to use any version of a package, which simplifies package upgrades and reduces the number of connection groups you need to create.</span></span>

<span data-ttu-id="28e6f-105">若要升级早期版本的 app-v 中的程序包，必须执行几个步骤，包括禁用连接组和修改连接组的 XML 定义文件。</span><span class="sxs-lookup"><span data-stu-id="28e6f-105">To upgrade a package in earlier versions of App-V, you had to perform several steps, including disabling the connection group and modifying the connection group’s XML definition file.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="28e6f-106">带有 App-v 5.0 SP3 的任务说明</span><span class="sxs-lookup"><span data-stu-id="28e6f-106">Task description with App-V 5.0 SP3</span></span></th>
<th align="left"><span data-ttu-id="28e6f-107">如何通过 App-v 5.0 SP3 执行任务</span><span class="sxs-lookup"><span data-stu-id="28e6f-107">How to perform the task with App-V 5.0 SP3</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="28e6f-108">你可以将连接组配置为接受程序包的任何版本，这使你可以升级程序包，而无需禁用连接组。</span><span class="sxs-lookup"><span data-stu-id="28e6f-108">You can configure a connection group to accept any version of a package, which enables you to upgrade the package without having to disable the connection group.</span></span></p>
<p><strong><span data-ttu-id="28e6f-109">该功能的工作原理：</span><span class="sxs-lookup"><span data-stu-id="28e6f-109">How the feature works:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="28e6f-110">如果连接组具有对程序包的多个版本的访问权限，则使用最新版本。</span><span class="sxs-lookup"><span data-stu-id="28e6f-110">If the connection group has access to multiple versions of a package, the latest version is used.</span></span></p></li>
<li><p><span data-ttu-id="28e6f-111">如果连接组包含具有不正确版本的可选程序包，则会忽略该程序包，并且不会阻止创建连接组的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="28e6f-111">If the connection group contains an optional package that has an incorrect version, the package is ignored and won’t block the connection group’s virtual environment from being created.</span></span></p></li>
<li><p><span data-ttu-id="28e6f-112">如果连接组包含具有不正确版本的非可选程序包，则无法创建连接组的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="28e6f-112">If the connection group contains a non-optional package that has an incorrect version, the connection group’s virtual environment cannot be created.</span></span></p></li>
</ul></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="28e6f-113">方法</span><span class="sxs-lookup"><span data-stu-id="28e6f-113">Method</span></span></th>
<th align="left"><span data-ttu-id="28e6f-114">步骤</span><span class="sxs-lookup"><span data-stu-id="28e6f-114">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="28e6f-115">App-v Server-管理控制台</span><span class="sxs-lookup"><span data-stu-id="28e6f-115">App-V Server – Management Console</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="28e6f-116">在管理控制台中，选择 " <strong> 程序包 </strong> &gt; <strong> 连接组" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="28e6f-116">In the Management Console, select <strong>PACKAGES</strong> &gt; <strong>CONNECTION GROUPS</strong>.</span></span></p></li>
<li><p><span data-ttu-id="28e6f-117">从 "连接组" 库中选择正确的连接组。</span><span class="sxs-lookup"><span data-stu-id="28e6f-117">Select the correct connection group from the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="28e6f-118"><strong> </strong> 在 "已连接的程序包" 窗格中单击 "编辑"。</span><span class="sxs-lookup"><span data-stu-id="28e6f-118">Click <strong>EDIT</strong> in the CONNECTED PACKAGES pane.</span></span></p></li>
<li><p><span data-ttu-id="28e6f-119">选中 <strong> </strong> 程序包名称旁边的 "使用任意版本" 复选框，然后单击 " <strong> 应用" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="28e6f-119">Select <strong>Use Any Version</strong> check box next to the package name, and click <strong>Apply</strong>.</span></span></p></li>
</ol>
<p><span data-ttu-id="28e6f-120">有关添加或升级程序包的详细信息，请参阅 <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)"> 如何使用管理控制台添加或升级程序包 </a> 。</span><span class="sxs-lookup"><span data-stu-id="28e6f-120">For more about adding or upgrading packages, see <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)">How to Add or Upgrade Packages by Using the Management Console</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="28e6f-121">独立计算机上的 app-v 客户端</span><span class="sxs-lookup"><span data-stu-id="28e6f-121">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="28e6f-122">创建连接组 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="28e6f-122">Create the connection group XML document.</span></span></p></li>
<li><p><span data-ttu-id="28e6f-123">对于要升级的程序包，请将 " <strong> 程序包 </strong> 标签" 属性 "VersionID" 设置 <strong> </strong> 为星号（ <strong>\*</strong> ）。</span><span class="sxs-lookup"><span data-stu-id="28e6f-123">For the package to be upgraded, set the <strong>Package</strong> tag attribute <strong>VersionID</strong> to an asterisk (<strong>\*</strong>).</span></span></p></li>
<li><p><span data-ttu-id="28e6f-124">使用以下 cmdlet 添加连接组，并包含连接组 XML 文档的路径：</span><span class="sxs-lookup"><span data-stu-id="28e6f-124">Use the following cmdlet to add the connection group, and include the path to the connection group XML document:</span></span></p>
<p><strong><span data-ttu-id="28e6f-125">Add-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="28e6f-125">Add-AppvClientConnectionGroup</span></span></strong></p></li>
<li><p><span data-ttu-id="28e6f-126">升级程序包时，请使用以下 cmdlet 删除旧程序包、添加已升级的程序包并发布已升级的程序包：</span><span class="sxs-lookup"><span data-stu-id="28e6f-126">When you upgrade a package, use the following cmdlets to remove the old package, add the upgraded package, and publish the upgraded package:</span></span></p>
<ul>
<li><p><span data-ttu-id="28e6f-127">RemoveAppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="28e6f-127">RemoveAppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="28e6f-128">Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="28e6f-128">Add-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="28e6f-129">发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="28e6f-129">Publish-AppvClientPackage</span></span></p></li>
</ul></li>
</ol>
<p><span data-ttu-id="28e6f-130">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="28e6f-130">For more information, see:</span></span></p>
<ul>
<li><p><span data-ttu-id="28e6f-131"><strong>此部分中包含可选程序包的示例 XML 文件、连接组 XML 文件 </strong> ： <a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"> 如何在连接组中使用可选程序包</span><span class="sxs-lookup"><span data-stu-id="28e6f-131">The example XML file, <strong>Connection group XML file with optional packages</strong>, in this section: <a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">How to Use Optional Packages in Connection Groups</span></span></a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="28e6f-132">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="28e6f-132">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="28e6f-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="28e6f-133">Related topics</span></span>


[<span data-ttu-id="28e6f-134">管理连接组</span><span class="sxs-lookup"><span data-stu-id="28e6f-134">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





