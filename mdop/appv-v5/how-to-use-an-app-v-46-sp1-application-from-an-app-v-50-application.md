---
ms.reviewer: ''
title: 如何从 app-v 5.0 应用程序使用 app-v 4.6 应用程序
description: 如何从 app-v 5.0 应用程序使用 app-v 4.6 应用程序
ms.assetid: 4e78cb32-9c8b-478e-ae8b-c474a7e42487
author: msfttracyp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 8b29e861b97d18e427f6a8247a1f731be2dc0889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798347"
---
# <span data-ttu-id="0ec03-103">如何从 app-v 5.0 应用程序使用 app-v 4.6 应用程序</span><span class="sxs-lookup"><span data-stu-id="0ec03-103">How to Use an App-V 4.6 Application From an App-V 5.0 Application</span></span>

<span data-ttu-id="0ec03-104">*注意：*\* App-V 4.6 已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="0ec03-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="0ec03-105">以下情况适用于 App-v 4.6 SP3 程序包。</span><span class="sxs-lookup"><span data-stu-id="0ec03-105">The following applies to an App-V 4.6 SP3 package.</span></span>

<span data-ttu-id="0ec03-106">使用以下过程，在独立客户端上运行 app-v 4.6 应用程序和 app-v 5.0 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec03-106">Use the following procedure to run an App-V4.6 application with App-V 5.0 applications on a standalone client.</span></span>

**<span data-ttu-id="0ec03-107">在独立客户端上运行应用程序</span><span class="sxs-lookup"><span data-stu-id="0ec03-107">To run applications on a standalone client</span></span>**

1.  <span data-ttu-id="0ec03-108">选择你的环境中可彼此打开的两个应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec03-108">Select two applications in your environment that can be opened from one another.</span></span> <span data-ttu-id="0ec03-109">例如，Microsoft Outlook 和 Adobe Acrobat Reader。</span><span class="sxs-lookup"><span data-stu-id="0ec03-109">For example, Microsoft Outlook and Adobe Acrobat Reader.</span></span> <span data-ttu-id="0ec03-110">您可以访问使用 Adobe Acrobat 创建的电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="0ec03-110">You can access an email attachment created using Adobe Acrobat.</span></span>

2.  <span data-ttu-id="0ec03-111">转换程序包，或使用 App-v 5.0 格式为任何一个应用程序创建新的程序包。</span><span class="sxs-lookup"><span data-stu-id="0ec03-111">Convert the packages, or create a new package for either of the applications using the App-V 5.0 format.</span></span> <span data-ttu-id="0ec03-112">有关转换程序包的详细信息，请参阅[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定计算机上所有用户](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)的已转换的 App-v 5.0 程序包，或者[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定用户](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)的 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="0ec03-112">For more information about converting packages see, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md) or [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md).</span></span>

3.  <span data-ttu-id="0ec03-113">使用 App-v 5.0 管理控制台添加和预配程序包。</span><span class="sxs-lookup"><span data-stu-id="0ec03-113">Add and provision the package using the App-V 5.0 management console.</span></span> <span data-ttu-id="0ec03-114">有关添加和预配程序包的详细信息，请参阅[如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)以及[如何使用管理控制台配置对程序包的访问](how-to-configure-access-to-packages-by-using-the-management-console-50.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec03-114">For more information adding and provisioning packages see, [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md) and [How to Configure Access to Packages by Using the Management Console](how-to-configure-access-to-packages-by-using-the-management-console-50.md).</span></span>

4.  <span data-ttu-id="0ec03-115">转换后的应用程序现在使用 App-v 5.0 运行，您可以从另一个应用程序中打开一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec03-115">The converted application now runs using App-V 5.0 and you can open one application from the other.</span></span> <span data-ttu-id="0ec03-116">例如，如果将 Microsoft Office 程序包转换为 app-v 5.0 程序包，并且 Adobe Acrobat 仍以 App-v 4.6 程序包的形式运行，则可以使用 Microsoft Outlook 打开 Adobe Acrobat 阅读器附件。</span><span class="sxs-lookup"><span data-stu-id="0ec03-116">For example, if you converted a Microsoft Office package to an App-V 5.0 package and Adobe Acrobat is still running as an App-V4.6 package, you can open an Adobe Acrobat Reader attachment using Microsoft Outlook.</span></span>

    <span data-ttu-id="0ec03-117">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="0ec03-117">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0ec03-118">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="0ec03-118">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0ec03-119">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="0ec03-119">Got an App-V issue?</span></span>** <span data-ttu-id="0ec03-120">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="0ec03-120">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0ec03-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="0ec03-121">Related topics</span></span>


[<span data-ttu-id="0ec03-122">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="0ec03-122">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 








