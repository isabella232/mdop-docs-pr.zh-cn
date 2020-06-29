---
title: Microsoft 高级组策略管理 4.0 SP3 发行说明
description: Microsoft 高级组策略管理 4.0 SP3 发行说明
author: dansimp
ms.assetid: 955d7674-a8d9-4fc5-b18a-5a1639e38014
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 6e0da04d67b3d29135071e0bc82b8e01789e4e81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801851"
---
# <span data-ttu-id="9b5e7-103">Microsoft 高级组策略管理 4.0 SP3 发行说明</span><span class="sxs-lookup"><span data-stu-id="9b5e7-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>


<span data-ttu-id="9b5e7-104">若要搜索这些发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="9b5e7-105">安装 Microsoft 高级组策略管理（AGPM）4.0 服务 Pack3 （SP3）之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack3 (SP3).</span></span> <span data-ttu-id="9b5e7-106">这些发行说明包含成功安装 AGPM 4.0 SP3 所需的信息，其中包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-106">These release notes contain information that is required to successfully install AGPM4.0 SP3 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="9b5e7-107">如果这些发行说明和其他 AGPM 文档之间存在差异，请考虑最新的变更权威。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-107">If there is a difference between these release notes and other AGPM documentation, consider the latest change authoritative.</span></span> <span data-ttu-id="9b5e7-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="9b5e7-109">AGPM 4.0 SP3 的已知问题</span><span class="sxs-lookup"><span data-stu-id="9b5e7-109">AGPM4.0 SP3 known issues</span></span>


<span data-ttu-id="9b5e7-110">本部分介绍了 AGPM 4.0 SP3 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-110">This section describes the known issues for AGPM 4.0 SP3.</span></span>

### <span data-ttu-id="9b5e7-111">在 Windows 10 中安装的 AGPM 安装失败</span><span class="sxs-lookup"><span data-stu-id="9b5e7-111">AGPM installation fails in Windows 10</span></span>

<span data-ttu-id="9b5e7-112">AGPM 内部启用 Windows Communication Foundation （WCF）-安装期间的 NonHTTP-激活功能。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-112">AGPM internally enables the Windows Communication Foundation (WCF)-NonHTTP-Activation feature during installation.</span></span> <span data-ttu-id="9b5e7-113">在 Windows 10 中，WCF 现在包括在启用 WCF NonHTTP 激活功能后重新启动 Windows 的要求。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-113">In Windows 10, WCF now includes a requirement to restart Windows after enabling the WCF NonHTTP-Activation feature.</span></span> <span data-ttu-id="9b5e7-114">但是，当前的 AGPM 安装程序代码不会处理此重启要求，也不会在等待激活服务时停止响应。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-114">However, the current AGPM installer code does not handle this restart requirement and stops responding while it waits for the service to be activated.</span></span>

<span data-ttu-id="9b5e7-115">**解决方法：** 在运行 AGPM 安装程序之前，请启用 WCF 非 HTTP 激活功能，然后重新启动 Windows。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-115">**Workaround:** Before you run the AGPM installer, enable the WCF Non-HTTP Activation feature and then restart Windows.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="9b5e7-116">尝试更改 AGPM 服务器设置时，"控制面板" 的 "卸载" 工具可能不起作用</span><span class="sxs-lookup"><span data-stu-id="9b5e7-116">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="9b5e7-117">尝试更改 AGPM 服务器设置时，用于卸载或更改程序的 "控制面板" 中的工具可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-117">The tool in Control Panel that you use to uninstall or change a program may not work when you try to change AGPM Server settings.</span></span>

<span data-ttu-id="9b5e7-118">**解决方法：** 在尝试使用 "控制面板" 更改 AGPM 服务器设置之前，请创建 "AGPM 存档" 文件夹的副本。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-118">**Workaround:** Before you try to change AGPM Server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="9b5e7-119">然后，你可以使用 Setup.exe 重新安装 AGPM 服务器，并选择所需的配置参数。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-119">You can then use Setup.exe to reinstall the AGPM Server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="9b5e7-120">报表不显示已添加到组策略对象的链接</span><span class="sxs-lookup"><span data-stu-id="9b5e7-120">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="9b5e7-121">"AGPM 设置" 和 "差异" 报表不显示已添加到组策略对象（GPO）的链接。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-121">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="9b5e7-122">**解决方法：** 若要查看报表中的链接，请在组策略管理控制台（GPMC）中选择 GPO，然后单击右窗格中的 "**设置**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-122">**Workaround:** To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and then click the **Settings** tab in the right pane.</span></span>

### <span data-ttu-id="9b5e7-123">报表不显示所有选项属性设置</span><span class="sxs-lookup"><span data-stu-id="9b5e7-123">Reports do not display all Choice Options Properties settings</span></span>

<span data-ttu-id="9b5e7-124">"AGPM 设置" 和 "差异" 报表不会显示在 "组策略对象编辑器" 的 "**选项" 属性**窗口中选择的所有设置。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-124">The AGPM settings and difference reports do not display all of the settings that were selected in the **Choice Options Properties** window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="9b5e7-125">**解决方法：** 使用 GPMC 查看报表中所选的 "**选择选项" 属性**设置。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-125">**Workaround:** Use the GPMC to view the selected **Choice Options Properties** settings in the reports.</span></span>

### <span data-ttu-id="9b5e7-126">报表可能不会显示某些浏览器中的 "显示" 和 "隐藏" 选项卡</span><span class="sxs-lookup"><span data-stu-id="9b5e7-126">Reports may not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="9b5e7-127">在 Google Chrome 或 Mozilla Firefox 中查看报表时，无法显示 "AGPM 设置" 和 "差异" 报表右侧的 "**显示**" 和 "**隐藏**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-127">The **Show** and **Hide** tabs, on the right side of the AGPM settings and difference reports, may not appear when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="9b5e7-128">**解决方法：** 通过使用 Internet Explorer 浏览器查看报表。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-128">**Workaround:** View the reports by using the Internet Explorer browser.</span></span>

### <span data-ttu-id="9b5e7-129">AGPM 设置和差异报表可能显示 GPMC 报表中的不同内容</span><span class="sxs-lookup"><span data-stu-id="9b5e7-129">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="9b5e7-130">AGPM 设置和差异报表可能不会显示与 GPMC 中的报表相同的内容。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-130">The AGPM settings and difference reports may not show the same content as reports in the GPMC.</span></span>

<span data-ttu-id="9b5e7-131">**解决方法：** 使用 GPMC 查看 AGPM 报告。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-131">**Workaround:** Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="9b5e7-132">如果域控制器处于离线状态，则 AGPM 服务不会启动</span><span class="sxs-lookup"><span data-stu-id="9b5e7-132">AGPM Service does not start if the domain controller is offline</span></span>

<span data-ttu-id="9b5e7-133">在 Windows®8操作系统或更高版本操作系统上的域控制器上安装了 AGPM 服务时，如果域控制器脱机，则该服务不会启动。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-133">When the AGPM Service is installed on a domain controller on the Windows® 8 operating systems or later operating systems, the service does not start if the domain controller is offline.</span></span>

<span data-ttu-id="9b5e7-134">**解决方法：** 在域控制器联机后手动启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-134">**Workaround:** Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="9b5e7-135">从 AGPM 4.0 版本和 hotfix1 升级 AGPM 服务器时，将阻止将 AGPM 服务器升级到 AGPM 4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="9b5e7-135">Upgrade of AGPM Server to AGPM4.0 SP2 is blocked when you upgrade from the AGPM4.0 release plus hotfix1</span></span>

<span data-ttu-id="9b5e7-136">如果你尝试将 AGPM 服务器升级到 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-136">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="9b5e7-137">安装了 AGPM 4.0 Server 后安装了 agpm 服务器，然后安装了名为 AGPM 4.0 的 AGPM 修复程序报告 HTML 报表中不正确的差异（请参阅知识库文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升级失败，无法完成。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-137">SP2 after installing AGPM 4.0 Server and then installing the AGPM hotfix named AGPM 4.0 reports incorrect differences in the HTML report (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="9b5e7-138">**解决方法：** 卸载 AGPM 4.0 服务器，然后安装 AGPM 4.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-138">**Workaround:** Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="9b5e7-139">报表不显示组织单位链接</span><span class="sxs-lookup"><span data-stu-id="9b5e7-139">Reports do not display organizational unit links</span></span>

<span data-ttu-id="9b5e7-140">如果将不受管理的 GPO 链接到组织单元，然后使用 AGPM 控制该 GPO，则 AGPM 设置和差异报告不会显示组织单位链接。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-140">If you link an uncontrolled GPO to an organizational unit and then control that GPO by using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="9b5e7-141">**解决方法：** 在 "**更改设置**" 节点的 "**受控**" 选项卡上，右键单击该 GPO，单击 "**设置**"，然后单击 " **GPO 链接**" 以查看组织链接。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-141">**Workaround:** On the **Controlled** tab of the **Change Settings** node, right-click the GPO, click **Settings**, and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="9b5e7-142">或者，你可以使用 GPMC 从 "**范围**" 选项卡查看指向 GPO 的链接。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-142">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

### <span data-ttu-id="9b5e7-143">如果单击 "更改"、"修复" 或 "删除 AGPM 客户端" 对话框中的 "后退" 按钮，则 AGPM 将显示错误</span><span class="sxs-lookup"><span data-stu-id="9b5e7-143">AGPM displays an error if you click the Back button from the Change, Repair, or Remove AGPM Client dialog box</span></span>

<span data-ttu-id="9b5e7-144">如果在 "控制面板" 中浏览到 "**程序和功能**"，然后选择 " **Microsoft 高级组策略管理-客户端**"，则如果单击 "**修改**"，然后单击 "**更改、修复或删除 AGPM 客户端**" 对话框中的 "**返回**" 按钮，则 AGPM 会显示错误。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-144">If you browse to **Programs and Features** in Control Panel and then select **Microsoft Advanced Group Policy Management – Client**, AGPM displays an error if you click **Modify** and then click the **Back** button in the **Change, Repair, or Remove AGPM Client** dialog box.</span></span>

<span data-ttu-id="9b5e7-145">**解决方法：** 单击 "**取消**" 以清除错误，然后再次启动流程。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-145">**Workaround:** Click **Cancel** to clear the error, and then start the process again.</span></span> <span data-ttu-id="9b5e7-146">单击 "**修改**" 后，请不要单击 "**返回**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-146">Do not click the **Back** button after you click **Modify** .</span></span>

### <span data-ttu-id="9b5e7-147">当审批者部署 GPO 并输入注释时，批注不会显示在 "历史记录" 窗口中</span><span class="sxs-lookup"><span data-stu-id="9b5e7-147">Comment fails to appear in the History window when the Approver deploys a GPO and enters a comment</span></span>

<span data-ttu-id="9b5e7-148">如果具有编辑器角色的用户提交了一个部署 GPO 的请求，并且拥有审批者角色的用户随后部署该 GPO 并输入注释，则注释将无法在 "**历史记录**" 窗口中显示。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-148">If a user who has the Editor role submits a request to deploy a GPO, and the user who has the Approver role then deploys the GPO and enters a comment, the comment fails to appear in the **History** window.</span></span>

<span data-ttu-id="9b5e7-149">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-149">**Workaround:** None.</span></span>

### <span data-ttu-id="9b5e7-150">添加了替代删除 GPO 权限更改的 AGPM 默认行为的机制</span><span class="sxs-lookup"><span data-stu-id="9b5e7-150">Added mechanism to override AGPM default behavior of removing GPO permission changes</span></span>

<span data-ttu-id="9b5e7-151">从 HF02 起，AGPM 已添加了一个注册表项以启用替代默认的 AGPM GPO 权限行为。</span><span class="sxs-lookup"><span data-stu-id="9b5e7-151">As of HF02, AGPM has added a registry key to enable overriding the default AGPM GPO permission behavior.</span></span> <span data-ttu-id="9b5e7-152">有关详细信息，请参阅[通过 AGPM 忽略对组策略对象权限的更改](https://support.microsoft.com/kb/3174540)</span><span class="sxs-lookup"><span data-stu-id="9b5e7-152">For more information, please see [Changes to Group Policy object permissions through AGPM are ignored](https://support.microsoft.com/kb/3174540)</span></span>

## <span data-ttu-id="9b5e7-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="9b5e7-153">Related topics</span></span>


[<span data-ttu-id="9b5e7-154">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="9b5e7-154">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="9b5e7-155">AGPM 4.0 SP3 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="9b5e7-155">What's New in AGPM 4.0 SP3</span></span>](whats-new-in-agpm-40-sp3.md)

 

 





