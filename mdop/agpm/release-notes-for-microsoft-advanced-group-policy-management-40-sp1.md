---
title: Microsoft 高级组策略管理 4.0 SP1 发行说明
description: Microsoft 高级组策略管理 4.0 SP1 发行说明
author: dansimp
ms.assetid: 91835bf8-e53c-4202-986e-8d37050d1267
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff9ce0405df766aef9b30e67d07ceb579c4fa89f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801855"
---
# <span data-ttu-id="98c47-103">Microsoft 高级组策略管理 4.0 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="98c47-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP1</span></span>


<span data-ttu-id="98c47-104">若要搜索这些发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="98c47-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="98c47-105">在安装 Microsoft 高级组策略管理（AGPM） 4.0 SP1 之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="98c47-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1.</span></span> <span data-ttu-id="98c47-106">这些发行说明包含成功安装 AGPM 4.0 SP1 所需的信息，其中包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="98c47-106">These release notes contain information that is required to successfully install AGPM 4.0 SP1 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="98c47-107">如果这些发行说明和其他 AGPM 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="98c47-107">If there is a difference between these release notes and other AGPM documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="98c47-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="98c47-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="98c47-109">AGPM 4.0 SP1 已知问题</span><span class="sxs-lookup"><span data-stu-id="98c47-109">AGPM 4.0 SP1 known issues</span></span>


<span data-ttu-id="98c47-110">本部分包含针对 AGPM 4.0 SP1 的发行说明。</span><span class="sxs-lookup"><span data-stu-id="98c47-110">This section contains release notes for AGPM 4.0 SP1.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="98c47-111">尝试更改 AGPM 服务器设置时，"控制面板" 的 "卸载" 工具可能不起作用</span><span class="sxs-lookup"><span data-stu-id="98c47-111">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="98c47-112">当您尝试更改 AGPM 服务器设置时，"控制面板" 中允许卸载或更改程序的工具可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="98c47-112">The tool in Control Panel that lets you uninstall or change a program may not work when you try to change AGPM server settings.</span></span>

<span data-ttu-id="98c47-113">解决方法：在尝试使用 "控制面板" 更改 AGPM 服务器设置之前，请创建 "AGPM 存档" 文件夹的副本。</span><span class="sxs-lookup"><span data-stu-id="98c47-113">WORKAROUND: Before you try to change AGPM server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="98c47-114">然后，你可以使用 Setup.exe 重新安装 AGPM 服务器，并选择所需的配置参数。</span><span class="sxs-lookup"><span data-stu-id="98c47-114">You can then use Setup.exe to reinstall the AGPM server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="98c47-115">报表不显示已添加到组策略对象的链接</span><span class="sxs-lookup"><span data-stu-id="98c47-115">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="98c47-116">"AGPM 设置" 和 "差异" 报表不显示已添加到组策略对象（GPO）的链接。</span><span class="sxs-lookup"><span data-stu-id="98c47-116">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="98c47-117">解决方法：若要查看报表中的链接，请在组策略管理控制台（GPMC）中选择 GPO，然后单击右窗格中的 "**设置**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="98c47-117">WORKAROUND: To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and click the **Settings** tab in the right pane.</span></span>

### <a href="" id="reports-do-not-display-all--choice-options-properties--settings"></a><span data-ttu-id="98c47-118">报表不显示所有 "选择选项属性" 设置</span><span class="sxs-lookup"><span data-stu-id="98c47-118">Reports do not display all “Choice Options Properties” settings</span></span>

<span data-ttu-id="98c47-119">"AGPM 设置" 和 "差异" 报表不会显示在 "组策略对象编辑器" 的 "选项" 属性窗口中选择的所有设置。</span><span class="sxs-lookup"><span data-stu-id="98c47-119">The AGPM settings and difference reports do not display all of the settings that were selected on the Choice Options Properties window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="98c47-120">解决方法：使用 GPMC 查看报表中所选的 "选择选项" 属性设置。</span><span class="sxs-lookup"><span data-stu-id="98c47-120">WORKAROUND: Use the GPMC to view the selected Choice Options Properties settings in the reports.</span></span>

### <span data-ttu-id="98c47-121">报表在某些浏览器中不显示 "显示" 和 "隐藏" 选项卡</span><span class="sxs-lookup"><span data-stu-id="98c47-121">Reports do not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="98c47-122">查看 Google Chrome 或 Mozilla Firefox 中的报表时，不会显示在 "AGPM 设置" 和 "差异" 报表右侧显示的 "显示" 和 "隐藏" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="98c47-122">The Show and Hide tabs, shown on the right side of the AGPM settings and difference reports, are not displayed when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="98c47-123">解决方法：使用 Internet Explorer 查看报表。</span><span class="sxs-lookup"><span data-stu-id="98c47-123">WORKAROUND: View the reports by using Internet Explorer.</span></span>

### <span data-ttu-id="98c47-124">AGPM 设置和差异报表可能显示 GPMC 报表中的不同内容</span><span class="sxs-lookup"><span data-stu-id="98c47-124">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="98c47-125">"AGPM 设置" 和 "差异" 报表可能不会显示与组策略管理控制台（GPMC）中的报表相同的内容。</span><span class="sxs-lookup"><span data-stu-id="98c47-125">The AGPM settings and difference reports may not show the same content as reports in the Group Policy Management Console (GPMC).</span></span>

<span data-ttu-id="98c47-126">解决方法：使用 GPMC 查看 AGPM 报表。</span><span class="sxs-lookup"><span data-stu-id="98c47-126">WORKAROUND: Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="98c47-127">如果域控制器未联机，则 AGPM 服务不会启动</span><span class="sxs-lookup"><span data-stu-id="98c47-127">AGPM Service does not start if the domain controller is not online</span></span>

<span data-ttu-id="98c47-128">当 AGPM 服务安装在 Windows 8 上的域控制器上时，如果域控制器未联机，则该服务不会启动。</span><span class="sxs-lookup"><span data-stu-id="98c47-128">When the AGPM Service is installed on a domain controller on Windows 8, the Service does not start if the domain controller is not online.</span></span>

<span data-ttu-id="98c47-129">解决方法：在域控制器联机后手动启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="98c47-129">WORKAROUND: Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="98c47-130">从 AGPM 4.0 发布和修补程序升级到 AGPM 4.0 SP1 时，将阻止升级到 AGPM SP1</span><span class="sxs-lookup"><span data-stu-id="98c47-130">Upgrade of AGPM Server to AGPM 4.0 SP1 is blocked when you upgrade from the AGPM 4.0 release plus the hotfix</span></span>

<span data-ttu-id="98c47-131">如果你尝试将 AGPM 服务器升级到 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="98c47-131">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="98c47-132">SP1 安装了 AGPM 4.0，然后安装 AGPM 修复程序（请参阅知识库文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)）后，升级失败，无法完成。</span><span class="sxs-lookup"><span data-stu-id="98c47-132">SP1 after installing AGPM 4.0 and then installing the AGPM hotfix (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="98c47-133">解决方法：卸载 AGPM 4.0 服务器，然后安装 AGPM 4.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="98c47-133">WORKAROUND: Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP1.</span></span>

### <span data-ttu-id="98c47-134">报表不显示组织单位链接</span><span class="sxs-lookup"><span data-stu-id="98c47-134">Reports do not display organizational unit links</span></span>

<span data-ttu-id="98c47-135">如果将不受控制的 GPO 链接到组织单元，然后使用 AGPM 控制该 GPO，则 AGPM 设置和差异报告不会显示组织单位链接。</span><span class="sxs-lookup"><span data-stu-id="98c47-135">If you link an uncontrolled GPO to an organizational unit and then control that GPO using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="98c47-136">解决方法：在 "**更改设置**" 节点的 "**受控**" 选项卡上，右键单击该 GPO，然后单击 "**设置**"，然后单击 " **GPO 链接**" 以查看组织链接。</span><span class="sxs-lookup"><span data-stu-id="98c47-136">WORKAROUND: From the **Controlled** tab of the **Change Settings** node, right-click the GPO and click **Settings** and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="98c47-137">或者，你可以使用 GPMC 从 "**范围**" 选项卡查看指向 GPO 的链接。</span><span class="sxs-lookup"><span data-stu-id="98c47-137">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

## <span data-ttu-id="98c47-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="98c47-138">Related topics</span></span>


[<span data-ttu-id="98c47-139">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="98c47-139">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="98c47-140">AGPM 4.0 SP1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="98c47-140">What's New in AGPM 4.0 SP1</span></span>](whats-new-in-agpm-40-sp1.md)

 

 





