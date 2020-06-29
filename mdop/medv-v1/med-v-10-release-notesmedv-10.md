---
title: MED-V 1.0 发行说明
description: MED-V 1.0 发行说明
author: dansimp
ms.assetid: 006a3537-5c5b-43b5-8df8-4bf6ddd3cd2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 683056f768a3d547828996a9b191d58337c21ad6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803999"
---
# <span data-ttu-id="1742a-103">MED-V 1.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="1742a-103">MED-V 1.0 Release Notes</span></span>


## <span data-ttu-id="1742a-104">有关 MED-V 的已知问题</span><span class="sxs-lookup"><span data-stu-id="1742a-104">Known Issues with MED-V</span></span>


<span data-ttu-id="1742a-105">本部分提供有关 Microsoft 企业桌面虚拟化（MED-V）平台的一般问题的最新信息。</span><span class="sxs-lookup"><span data-stu-id="1742a-105">This section provides the most up-to-date information about general issues with the Microsoft Enterprise Desktop Virtualization (MED-V) platform.</span></span> <span data-ttu-id="1742a-106">这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。</span><span class="sxs-lookup"><span data-stu-id="1742a-106">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="1742a-107">只要有可能，这些问题将在以后的版本中解决。</span><span class="sxs-lookup"><span data-stu-id="1742a-107">Whenever possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="1742a-108">文件下载不遵循 Web 重定向规则</span><span class="sxs-lookup"><span data-stu-id="1742a-108">File downloads do not follow Web redirection rules</span></span>

<span data-ttu-id="1742a-109">文件下载不遵循 MED-V 工作区策略中设置的 Web 重定向规则。</span><span class="sxs-lookup"><span data-stu-id="1742a-109">File downloads do not follow Web redirection rules set in a MED-V workspace policy.</span></span>

### <span data-ttu-id="1742a-110">将控制台发布的应用程序窗口展开到全屏时，它将消失</span><span class="sxs-lookup"><span data-stu-id="1742a-110">When expanding a console-published application window to full screen, it disappears</span></span>

<span data-ttu-id="1742a-111">如果在无缝集成模式下配置的 MED-V 工作区中将控制台发布的应用程序（如 cmd.exe）窗口展开为全屏，则应用程序窗口可能会消失或不响应。</span><span class="sxs-lookup"><span data-stu-id="1742a-111">If you expand a console-published application (such as cmd.exe) window to full screen inside a MED-V workspace configured in seamless integration mode, the application window might disappear or not respond.</span></span>

### <span data-ttu-id="1742a-112">在完整桌面模式下工作时，桌面上的图标位置不会保存</span><span class="sxs-lookup"><span data-stu-id="1742a-112">When working in full desktop mode, icon locations on the desktop are not saved</span></span>

<span data-ttu-id="1742a-113">在完整桌面模式下工作时，桌面上的图标的手动位置更改不会保存在 MED-V 工作区会话中。</span><span class="sxs-lookup"><span data-stu-id="1742a-113">When working in full desktop mode, manual location changes of icons on the desktop are not saved between MED-V workspace sessions.</span></span>

### <span data-ttu-id="1742a-114">同一域中不能存在具有相同名称的本地映像和测试映像</span><span class="sxs-lookup"><span data-stu-id="1742a-114">A local image and a test image with the same name cannot exist in the same domain</span></span>

<span data-ttu-id="1742a-115">如果本地映像已加入域，并且管理员使用与测试映像相同的计算机名称创建新版本的同一映像，则当测试映像加入域时，加入域操作失败或成功，并且将从域中删除本地映像。</span><span class="sxs-lookup"><span data-stu-id="1742a-115">If a local image is joined to the domain and the administrator creates a new version of the same image with the same computer name as a test image, when the test image joins the domain, either the join domain action fails or it succeeds and the local image is removed from the domain.</span></span>

### <span data-ttu-id="1742a-116">MED-V 不支持 Windows Aero 功能</span><span class="sxs-lookup"><span data-stu-id="1742a-116">MED-V does not support Windows Aero features</span></span>

<span data-ttu-id="1742a-117">MED-V 不支持 Windows Aero 功能（如 Aero Flip 3D）。</span><span class="sxs-lookup"><span data-stu-id="1742a-117">MED-V does not support Windows Aero features (such as Aero Flip 3D).</span></span>

### <span data-ttu-id="1742a-118">每台计算机只能有一个 Windows 用户使用管理控制台</span><span class="sxs-lookup"><span data-stu-id="1742a-118">The management console can be used by only one Windows user per computer</span></span>

<span data-ttu-id="1742a-119">MED-V 管理控制台只能由管理员和安装了管理应用程序的 Windows 用户使用。</span><span class="sxs-lookup"><span data-stu-id="1742a-119">The MED-V management console can be used only by administrators and the Windows user who installed the management application.</span></span>

### <span data-ttu-id="1742a-120">MED-V 服务器配置实用工具在用户上下文中测试 Microsoft SQL Server 连接，而不是在 MED-V 服务器服务上下文中</span><span class="sxs-lookup"><span data-stu-id="1742a-120">The MED-V Server configuration utility tests Microsoft SQL Server connectivity under user context rather than under MED-V Server service context</span></span>

<span data-ttu-id="1742a-121">MED-V 使用 MED-V 服务器服务上下文收集 Microsoft SQL Server 报表数据库中的报表。</span><span class="sxs-lookup"><span data-stu-id="1742a-121">MED-V uses MED-V Server service context to collect reports from the Microsoft SQL Server reports database.</span></span> <span data-ttu-id="1742a-122">MED-V 服务器配置实用程序验证数据库并测试数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="1742a-122">The MED-V Server configuration utility verifies the database and tests the database connection string.</span></span> <span data-ttu-id="1742a-123">它不验证数据库的 MED-V 服务器服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1742a-123">It does not validate the access of MED-V Server service to the database.</span></span>

 

 





