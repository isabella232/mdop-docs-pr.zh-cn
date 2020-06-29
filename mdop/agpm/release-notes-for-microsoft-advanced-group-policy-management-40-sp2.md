---
title: Microsoft 高级组策略管理 4.0 SP2 发行说明
description: Microsoft 高级组策略管理 4.0 SP2 发行说明
author: dansimp
ms.assetid: 0593cd11-3308-4942-bf19-8a7bb9447f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 736eb8d41cbb72b274a2941c60b0357bbc948c9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802596"
---
# <span data-ttu-id="61a42-103">Microsoft 高级组策略管理 4.0 SP2 发行说明</span><span class="sxs-lookup"><span data-stu-id="61a42-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP2</span></span>


<span data-ttu-id="61a42-104">若要搜索这些发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="61a42-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="61a42-105">安装 Microsoft 高级组策略管理（AGPM）4.0 服务 Pack2 （SP2）之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="61a42-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack2 (SP2).</span></span> <span data-ttu-id="61a42-106">这些发行说明包含成功安装 AGPM 4.0 SP2 所需的信息，其中包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="61a42-106">These release notes contain information that is required to successfully install AGPM4.0 SP2 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="61a42-107">如果这些发行说明和其他 AGPM 文档之间存在差异，请考虑最新的变更权威。</span><span class="sxs-lookup"><span data-stu-id="61a42-107">If there is a difference between these release notes and other AGPM documentation, consider the latest change authoritative.</span></span> <span data-ttu-id="61a42-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="61a42-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="61a42-109">AGPM 4.0 SP2 的已知问题</span><span class="sxs-lookup"><span data-stu-id="61a42-109">AGPM4.0 SP2 known issues</span></span>


<span data-ttu-id="61a42-110">本部分介绍了 AGPM 4.0 SP2 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="61a42-110">This section describes the known issues for AGPM 4.0 SP2.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="61a42-111">尝试更改 AGPM 服务器设置时，"控制面板" 的 "卸载" 工具可能不起作用</span><span class="sxs-lookup"><span data-stu-id="61a42-111">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="61a42-112">尝试更改 AGPM 服务器设置时，用于卸载或更改程序的 "控制面板" 中的工具可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="61a42-112">The tool in Control Panel that you use to uninstall or change a program may not work when you try to change AGPM Server settings.</span></span>

<span data-ttu-id="61a42-113">**解决方法：** 在尝试使用 "控制面板" 更改 AGPM 服务器设置之前，请创建 "AGPM 存档" 文件夹的副本。</span><span class="sxs-lookup"><span data-stu-id="61a42-113">**Workaround:** Before you try to change AGPM Server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="61a42-114">然后，你可以使用 Setup.exe 重新安装 AGPM 服务器，并选择所需的配置参数。</span><span class="sxs-lookup"><span data-stu-id="61a42-114">You can then use Setup.exe to reinstall the AGPM Server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="61a42-115">报表不显示已添加到组策略对象的链接</span><span class="sxs-lookup"><span data-stu-id="61a42-115">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="61a42-116">"AGPM 设置" 和 "差异" 报表不显示已添加到组策略对象（GPO）的链接。</span><span class="sxs-lookup"><span data-stu-id="61a42-116">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="61a42-117">**解决方法：** 若要查看报表中的链接，请在组策略管理控制台（GPMC）中选择 GPO，然后单击右窗格中的 "**设置**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="61a42-117">**Workaround:** To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and then click the **Settings** tab in the right pane.</span></span>

### <span data-ttu-id="61a42-118">报表不显示所有选项属性设置</span><span class="sxs-lookup"><span data-stu-id="61a42-118">Reports do not display all Choice Options Properties settings</span></span>

<span data-ttu-id="61a42-119">"AGPM 设置" 和 "差异" 报表不会显示在 "组策略对象编辑器" 的 "**选项" 属性**窗口中选择的所有设置。</span><span class="sxs-lookup"><span data-stu-id="61a42-119">The AGPM settings and difference reports do not display all of the settings that were selected in the **Choice Options Properties** window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="61a42-120">**解决方法：** 使用 GPMC 查看报表中所选的 "**选择选项" 属性**设置。</span><span class="sxs-lookup"><span data-stu-id="61a42-120">**Workaround:** Use the GPMC to view the selected **Choice Options Properties** settings in the reports.</span></span>

### <span data-ttu-id="61a42-121">报表可能不会显示某些浏览器中的 "显示" 和 "隐藏" 选项卡</span><span class="sxs-lookup"><span data-stu-id="61a42-121">Reports may not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="61a42-122">在 Google Chrome 或 Mozilla Firefox 中查看报表时，无法显示 "AGPM 设置" 和 "差异" 报表右侧的 "**显示**" 和 "**隐藏**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="61a42-122">The **Show** and **Hide** tabs, on the right side of the AGPM settings and difference reports, may not appear when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="61a42-123">**解决方法：** 通过使用 Internet Explorer 浏览器查看报表。</span><span class="sxs-lookup"><span data-stu-id="61a42-123">**Workaround:** View the reports by using the Internet Explorer browser.</span></span>

### <span data-ttu-id="61a42-124">AGPM 设置和差异报表可能显示 GPMC 报表中的不同内容</span><span class="sxs-lookup"><span data-stu-id="61a42-124">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="61a42-125">AGPM 设置和差异报表可能不会显示与 GPMC 中的报表相同的内容。</span><span class="sxs-lookup"><span data-stu-id="61a42-125">The AGPM settings and difference reports may not show the same content as reports in the GPMC.</span></span>

<span data-ttu-id="61a42-126">**解决方法：** 使用 GPMC 查看 AGPM 报告。</span><span class="sxs-lookup"><span data-stu-id="61a42-126">**Workaround:** Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="61a42-127">如果域控制器处于离线状态，则 AGPM 服务不会启动</span><span class="sxs-lookup"><span data-stu-id="61a42-127">AGPM Service does not start if the domain controller is offline</span></span>

<span data-ttu-id="61a42-128">在 Windows®8操作系统或更高版本操作系统上的域控制器上安装了 AGPM 服务时，如果域控制器脱机，则该服务不会启动。</span><span class="sxs-lookup"><span data-stu-id="61a42-128">When the AGPM Service is installed on a domain controller on the Windows® 8 operating systems or later operating systems, the service does not start if the domain controller is offline.</span></span>

<span data-ttu-id="61a42-129">**解决方法：** 在域控制器联机后手动启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="61a42-129">**Workaround:** Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="61a42-130">从 AGPM 4.0 版本和 hotfix1 升级 AGPM 服务器时，将阻止将 AGPM 服务器升级到 AGPM 4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="61a42-130">Upgrade of AGPM Server to AGPM4.0 SP2 is blocked when you upgrade from the AGPM4.0 release plus hotfix1</span></span>

<span data-ttu-id="61a42-131">如果你尝试将 AGPM 服务器升级到 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="61a42-131">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="61a42-132">安装了 AGPM 4.0 Server 后安装了 agpm 服务器，然后安装了名为 AGPM 4.0 的 AGPM 修复程序报告 HTML 报表中不正确的差异（请参阅知识库文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升级失败，无法完成。</span><span class="sxs-lookup"><span data-stu-id="61a42-132">SP2 after installing AGPM 4.0 Server and then installing the AGPM hotfix named AGPM 4.0 reports incorrect differences in the HTML report (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="61a42-133">**解决方法：** 卸载 AGPM 4.0 服务器，然后安装 AGPM 4.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="61a42-133">**Workaround:** Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="61a42-134">报表不显示组织单位链接</span><span class="sxs-lookup"><span data-stu-id="61a42-134">Reports do not display organizational unit links</span></span>

<span data-ttu-id="61a42-135">如果将不受管理的 GPO 链接到组织单元，然后使用 AGPM 控制该 GPO，则 AGPM 设置和差异报告不会显示组织单位链接。</span><span class="sxs-lookup"><span data-stu-id="61a42-135">If you link an uncontrolled GPO to an organizational unit and then control that GPO by using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="61a42-136">**解决方法：** 在 "**更改设置**" 节点的 "**受控**" 选项卡上，右键单击该 GPO，单击 "**设置**"，然后单击 " **GPO 链接**" 以查看组织链接。</span><span class="sxs-lookup"><span data-stu-id="61a42-136">**Workaround:** On the **Controlled** tab of the **Change Settings** node, right-click the GPO, click **Settings**, and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="61a42-137">或者，你可以使用 GPMC 从 "**范围**" 选项卡查看指向 GPO 的链接。</span><span class="sxs-lookup"><span data-stu-id="61a42-137">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

### <span data-ttu-id="61a42-138">如果单击 "更改"、"修复" 或 "删除 AGPM 客户端" 对话框中的 "后退" 按钮，则 AGPM 将显示错误</span><span class="sxs-lookup"><span data-stu-id="61a42-138">AGPM displays an error if you click the Back button from the Change, Repair, or Remove AGPM Client dialog box</span></span>

<span data-ttu-id="61a42-139">如果在 "控制面板" 中浏览到 "**程序和功能**"，然后选择 " **Microsoft 高级组策略管理-客户端**"，则如果单击 "**修改**"，然后单击 "**更改、修复或删除 AGPM 客户端**" 对话框中的 "**返回**" 按钮，则 AGPM 会显示错误。</span><span class="sxs-lookup"><span data-stu-id="61a42-139">If you browse to **Programs and Features** in Control Panel and then select **Microsoft Advanced Group Policy Management – Client**, AGPM displays an error if you click **Modify** and then click the **Back** button in the **Change, Repair, or Remove AGPM Client** dialog box.</span></span>

<span data-ttu-id="61a42-140">**解决方法：** 单击 "**取消**" 以清除错误，然后再次启动流程。</span><span class="sxs-lookup"><span data-stu-id="61a42-140">**Workaround:** Click **Cancel** to clear the error, and then start the process again.</span></span> <span data-ttu-id="61a42-141">单击 "**修改**" 后，请不要单击 "**返回**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="61a42-141">Do not click the **Back** button after you click **Modify** .</span></span>

### <span data-ttu-id="61a42-142">当审批者部署 GPO 并输入注释时，批注不会显示在 "历史记录" 窗口中</span><span class="sxs-lookup"><span data-stu-id="61a42-142">Comment fails to appear in the History window when the Approver deploys a GPO and enters a comment</span></span>

<span data-ttu-id="61a42-143">如果具有编辑器角色的用户提交了一个部署 GPO 的请求，并且拥有审批者角色的用户随后部署该 GPO 并输入注释，则注释将无法在 "**历史记录**" 窗口中显示。</span><span class="sxs-lookup"><span data-stu-id="61a42-143">If a user who has the Editor role submits a request to deploy a GPO, and the user who has the Approver role then deploys the GPO and enters a comment, the comment fails to appear in the **History** window.</span></span>

<span data-ttu-id="61a42-144">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="61a42-144">**Workaround:** None.</span></span>

## <span data-ttu-id="61a42-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="61a42-145">Related topics</span></span>


[<span data-ttu-id="61a42-146">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="61a42-146">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="61a42-147">AGPM 4.0 SP2 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="61a42-147">What's New in AGPM 4.0 SP2</span></span>](whats-new-in-agpm-40-sp2.md)

 

 





