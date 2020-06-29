---
title: 配置 UE-V 2. x 的公司设置中心
description: 配置 UE-V 2. x 的公司设置中心
author: dansimp
ms.assetid: 48fadb0a-c0dc-4287-9474-f94ce1417003
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0226b3c156a6d6ca39b0214de8acf0c5990db349
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803339"
---
# <span data-ttu-id="d2212-103">配置 UE-V 2. x 的公司设置中心</span><span class="sxs-lookup"><span data-stu-id="d2212-103">Configuring the Company Settings Center for UE-V 2.x</span></span>


<span data-ttu-id="d2212-104">Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 包括新应用程序（公司设置中心），该应用程序可帮助用户管理要同步的设置。</span><span class="sxs-lookup"><span data-stu-id="d2212-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 include a new application, the Company Settings Center, which helps users manage settings to synchronize.</span></span> <span data-ttu-id="d2212-105">公司设置中心通过使用 UE-V Agent 进行安装。</span><span class="sxs-lookup"><span data-stu-id="d2212-105">The Company Settings Center is installed by using the UE-V Agent.</span></span> <span data-ttu-id="d2212-106">用户在 "控制面板" 的 "**开始**" 菜单或 "**开始**" 屏幕上，以及通过 ue-v 通知区域图标访问公司设置中心。</span><span class="sxs-lookup"><span data-stu-id="d2212-106">Users access the Company Settings Center in Control Panel, in the **Start** menu or on the **Start** screen, and via the UE-V notification area icon.</span></span> <span data-ttu-id="d2212-107">公司设置中心显示已同步的设置，并帮助用户查看 UE-V 的同步状态。</span><span class="sxs-lookup"><span data-stu-id="d2212-107">Company Settings Center displays which settings are synchronized and helps users see the synchronization status of UE-V.</span></span> <span data-ttu-id="d2212-108">用户可以使用公司设置中心来选择哪些应用程序或 Windows 功能在计算机之间同步其设置。</span><span class="sxs-lookup"><span data-stu-id="d2212-108">Users can use the Company Settings Center to select which applications or Windows features synchronize their settings between computers.</span></span> <span data-ttu-id="d2212-109">他们还可以单击 "**立即同步**" 按钮，立即同步所有设置。</span><span class="sxs-lookup"><span data-stu-id="d2212-109">They can also click the **Sync Now** button to synchronize all settings immediately.</span></span> <span data-ttu-id="d2212-110">管理员还可以在 "公司设置中心" 中包含支持链接。</span><span class="sxs-lookup"><span data-stu-id="d2212-110">The administrator can also include a link for support in the Company Settings Center.</span></span>

## <span data-ttu-id="d2212-111">关于公司设置中心</span><span class="sxs-lookup"><span data-stu-id="d2212-111">About the Company Settings Center</span></span>


<span data-ttu-id="d2212-112">公司设置中心桌面应用程序向用户提供有关 UE-V 设置同步的信息。</span><span class="sxs-lookup"><span data-stu-id="d2212-112">The Company Settings Center desktop application provides users with information about UE-V settings synchronization.</span></span> <span data-ttu-id="d2212-113">公司设置中心可通过多种不同的方式进行访问：</span><span class="sxs-lookup"><span data-stu-id="d2212-113">The Company Settings Center is accessible in several different ways:</span></span>

-   <span data-ttu-id="d2212-114">通知区域图标-启用**任务栏图标**组策略设置或 Windows PowerShell 配置后，将在通知区域中显示 ue-v 图标。</span><span class="sxs-lookup"><span data-stu-id="d2212-114">Notification area icon – With the **Tray Icon** Group Policy setting or Windows PowerShell configuration enabled, the UE-V icon appears in the notification area.</span></span> <span data-ttu-id="d2212-115">单击 "UE-V" 图标以打开 "公司设置中心"。</span><span class="sxs-lookup"><span data-stu-id="d2212-115">Click the UE-V icon to open the Company Settings Center.</span></span>

    <span data-ttu-id="d2212-116">**注意** 可通过使用以下设置禁用通知区域图标：</span><span class="sxs-lookup"><span data-stu-id="d2212-116">**Note** The notification area icon can be disabled by using the following settings:</span></span>

    -   <span data-ttu-id="d2212-117">组策略设置：</span><span class="sxs-lookup"><span data-stu-id="d2212-117">Group Policy setting:</span></span> `Policy Tray Icon`

    -   <span data-ttu-id="d2212-118">Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d2212-118">Windows PowerShell cmdlet:</span></span> `TrayIconEnabled`

    -   <span data-ttu-id="d2212-119">SystemCenter2012 ConfigurationManager 的 UE-V 配置包中的配置项目：</span><span class="sxs-lookup"><span data-stu-id="d2212-119">Configuration item in the UE-V Configuration Pack for SystemCenter2012 ConfigurationManager:</span></span> `Tray icon enabled`

     

-   <span data-ttu-id="d2212-120">控制面板应用程序-在 "控制面板" 中，通过浏览找到 "**外观和个性化**"，然后单击 "**公司设置中心**"。</span><span class="sxs-lookup"><span data-stu-id="d2212-120">Control Panel application – In Control Panel, browse to **Appearance and Personalization**, and then click **Company Settings Center**.</span></span>

-   <span data-ttu-id="d2212-121">第一次使用通知-除非 "已禁用"，UE-V Agent 将提醒用户在计算机上首次运行 UE-V 代理时，设置现在已同步。</span><span class="sxs-lookup"><span data-stu-id="d2212-121">First use notification – Unless disabled, the UE-V Agent alerts the user that settings are now synchronized when the UE-V agent runs for the first time on a computer.</span></span> <span data-ttu-id="d2212-122">单击 "通知" 对话框以打开 "公司设置中心"。</span><span class="sxs-lookup"><span data-stu-id="d2212-122">Click the notification dialog box to open the Company Settings Center.</span></span>

-   <span data-ttu-id="d2212-123">"**开始**" 屏幕或 "**开始**" 菜单包含指向公司设置中心的链接。</span><span class="sxs-lookup"><span data-stu-id="d2212-123">The **Start** screen or **Start** menu includes a link to the Company Settings Center.</span></span> <span data-ttu-id="d2212-124">"搜索公司设置中心" 将查找应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2212-124">A search for Company Settings Center finds the application.</span></span>

## <span data-ttu-id="d2212-125">在公司设置中心配置支持链接</span><span class="sxs-lookup"><span data-stu-id="d2212-125">Configuring the support link in the Company Settings Center</span></span>


<span data-ttu-id="d2212-126">公司设置中心可以包括超链接，用户可单击该超链接以获取 UE-V 设置同步问题的支持。</span><span class="sxs-lookup"><span data-stu-id="d2212-126">The Company Settings Center can include a hyperlink that users can click to get support with UE-V settings synchronization problems.</span></span> <span data-ttu-id="d2212-127">此链接可以打开任何有效的 URL 协议，例如用于网页的 http://或电子邮件的 mailto://。</span><span class="sxs-lookup"><span data-stu-id="d2212-127">This link can open any valid URL protocol, such as http:// for a webpage or mailto:// for an email.</span></span> <span data-ttu-id="d2212-128">支持链接可以使用组策略、Windows PowerShell 或 System Center 2012 Configuration Manager UE-V 配置包进行配置。</span><span class="sxs-lookup"><span data-stu-id="d2212-128">The support link can be configured by using Group Policy, Windows PowerShell, or the System Center 2012 Configuration Manager UE-V Configuration Pack.</span></span>

**<span data-ttu-id="d2212-129">如何配置公司设置中心支持链接</span><span class="sxs-lookup"><span data-stu-id="d2212-129">How to configure the Company Settings Center support link</span></span>**

1.  <span data-ttu-id="d2212-130">打开你的首选管理工具：</span><span class="sxs-lookup"><span data-stu-id="d2212-130">Open your preferred management tool:</span></span>

    -   <span data-ttu-id="d2212-131">**组策略**-如果尚未执行此操作，请从[MDOP 管理模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)中下载 ue-v 2 的 ADMX 模板。</span><span class="sxs-lookup"><span data-stu-id="d2212-131">**Group Policy** - If you have not already done so, download the ADMX template for UE-V 2 from [MDOP Administrative Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941).</span></span>

    -   <span data-ttu-id="d2212-132">**Windows powershell** -在安装了 ue-v Agent 的计算机上，打开**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="d2212-132">**Windows PowerShell** – On a computer with the UE-V Agent installed, open **Windows PowerShell**.</span></span> <span data-ttu-id="d2212-133">有关使用 Windows PowerShell 管理 UE-V 的详细信息，请参阅[使用 Windows powershell 和 WMI 管理 ue-v 2。](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="d2212-133">For more information about administering UE-V by using Windows PowerShell, see [Administering UE-V 2.x with Windows PowerShell and WMI](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md).</span></span>

    -   <span data-ttu-id="d2212-134">**适用于 Microsoft 用户体验虚拟化（ue-v）的 System Center 2012 配置包**-导入 Ue-v 配置包，然后按照配置包文档创建配置项。</span><span class="sxs-lookup"><span data-stu-id="d2212-134">**System Center 2012 Configuration Pack for Microsoft User Experience Virtualization (UE-V)** – Import the UE-V Configuration Pack and follow the Configuration Pack documentation to create configuration items.</span></span> <span data-ttu-id="d2212-135">有关 UE-V 配置包的详细信息，请参阅[通过 System Center Configuration Manager 2012 配置 ue-v 2。](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="d2212-135">For more information about the UE-V Configuration Pack, see [Configuring UE-V 2.x with System Center Configuration Manager 2012](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md).</span></span>

2.  <span data-ttu-id="d2212-136">编辑以下策略的设置：</span><span class="sxs-lookup"><span data-stu-id="d2212-136">Edit the settings for the following policies:</span></span>

    -   <span data-ttu-id="d2212-137">**联系 It 链接文本**-此设置在 "公司设置中心" 中指定 "联系 IT URL" 超链接的文本。</span><span class="sxs-lookup"><span data-stu-id="d2212-137">**Contact IT Link Text** - This setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span> <span data-ttu-id="d2212-138">如果启用此设置，公司设置中心将在指向联系人 IT URL 的链接中显示指定文本。</span><span class="sxs-lookup"><span data-stu-id="d2212-138">If you enable this setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span>

        -   <span data-ttu-id="d2212-139">组策略设置：</span><span class="sxs-lookup"><span data-stu-id="d2212-139">Group Policy settings:</span></span> `Contact IT Link Text`

        -   <span data-ttu-id="d2212-140">Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d2212-140">Windows PowerShell cmdlet:</span></span> `ContactITDescription`

        -   <span data-ttu-id="d2212-141">配置包配置项目：</span><span class="sxs-lookup"><span data-stu-id="d2212-141">Configuration Pack configuration item:</span></span> `IT contact descriptive text`

    -   <span data-ttu-id="d2212-142">**联系 IT URL** -此设置使用有效的 URL 协议（例如网页的 http://或电子邮件 mailto://）指定 "联系人 IT" 链接在 "公司设置中心" 中的 URL。</span><span class="sxs-lookup"><span data-stu-id="d2212-142">**Contact IT URL** - This setting specifies the URL for the Contact IT link in the Company Settings Center in a valid URL protocol, such as http:// for a webpage or mailto:// for an email.</span></span>

        -   <span data-ttu-id="d2212-143">组策略设置：</span><span class="sxs-lookup"><span data-stu-id="d2212-143">Group Policy settings:</span></span> `Contact IT URL`

        -   <span data-ttu-id="d2212-144">Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d2212-144">Windows PowerShell cmdlet:</span></span> `ContactITUrl`

        -   <span data-ttu-id="d2212-145">配置包配置项目：</span><span class="sxs-lookup"><span data-stu-id="d2212-145">Configuration Pack configuration item:</span></span> `IT contact URL`

3.  <span data-ttu-id="d2212-146">使用管理工具将设置部署到用户计算机。</span><span class="sxs-lookup"><span data-stu-id="d2212-146">Deploy settings to users’ computers by using the management tool.</span></span>






 

 





