---
title: 如何在 Server Management Console 中管理报告
description: 如何在 Server Management Console 中管理报告
author: dansimp
ms.assetid: 28d99620-6339-43f6-9288-4aa958607c59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3d70734be04df380e6ce3f4ee8de126503e482e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801299"
---
# <span data-ttu-id="31b31-103">如何在 Server Management Console 中管理报告</span><span class="sxs-lookup"><span data-stu-id="31b31-103">How to Manage Reports in the Server Management Console</span></span>


<span data-ttu-id="31b31-104">若要有效管理应用程序虚拟化系统，可以使用应用程序虚拟化服务器管理控制台生成各种提供有关系统信息的报告。</span><span class="sxs-lookup"><span data-stu-id="31b31-104">To effectively manage the Application Virtualization System, you can use the Application Virtualization Server Management Console to generate a variety of reports that provide information about the system.</span></span> <span data-ttu-id="31b31-105">此信息包括特定应用程序或所有应用程序的每日使用信息，以及系统错误跟踪。</span><span class="sxs-lookup"><span data-stu-id="31b31-105">This information includes daily usage information for a specific application or all applications, and system error tracking.</span></span>

**<span data-ttu-id="31b31-106">注意</span><span class="sxs-lookup"><span data-stu-id="31b31-106">Note</span></span>**  
-   <span data-ttu-id="31b31-107">在安装期间，安装脚本仅安装英语版本的报表查看器。</span><span class="sxs-lookup"><span data-stu-id="31b31-107">During installation, the installation script installs only the English language version of report viewer.</span></span> <span data-ttu-id="31b31-108">为了让报表查看器以其他语言显示正确的信息，需要从以下位置安装语言包： <https://go.microsoft.com/fwlink/?LinkId=131645> 。</span><span class="sxs-lookup"><span data-stu-id="31b31-108">For the report viewer to display the correct information in other languages, it is necessary to install a language pack from the following location: <https://go.microsoft.com/fwlink/?LinkId=131645>.</span></span>

-   <span data-ttu-id="31b31-109">在服务器管理控制台中添加或编辑应用程序时，必须确保应用程序名称和版本与 OSD 文件中的应用名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="31b31-109">When you add or edit an application in the Server Management Console, you must make sure that the application names and versions exactly match those in the OSD files.</span></span> <span data-ttu-id="31b31-110">"报告" 功能在识别要报告的应用程序使用数据时使用 "应用程序名称" 和 "版本数据" 字段。</span><span class="sxs-lookup"><span data-stu-id="31b31-110">The reporting feature uses the application names and versions data fields when it identifies application usage data on which to report.</span></span> <span data-ttu-id="31b31-111">如果数据字段不匹配，将跳过使用记录。</span><span class="sxs-lookup"><span data-stu-id="31b31-111">If the data fields do not match, the usage records will be skipped.</span></span>

 

## <span data-ttu-id="31b31-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="31b31-112">In This Section</span></span>


<a href="" id="application-virtualization-report-types"></a>[<span data-ttu-id="31b31-113">Application Virtualization 报告类型</span><span class="sxs-lookup"><span data-stu-id="31b31-113">Application Virtualization Report Types</span></span>](application-virtualization-report-types.md)  
<span data-ttu-id="31b31-114">包含有关可用报告类型的信息。</span><span class="sxs-lookup"><span data-stu-id="31b31-114">Contains information about the available report types.</span></span>

<a href="" id="how-to-create-a-report"></a>[<span data-ttu-id="31b31-115">如何创建报告</span><span class="sxs-lookup"><span data-stu-id="31b31-115">How to Create a Report</span></span>](how-to-create-a-reportserver.md)  
<span data-ttu-id="31b31-116">提供创建报表的分步过程。</span><span class="sxs-lookup"><span data-stu-id="31b31-116">Provides a step-by-step process for creating a report.</span></span>

<a href="" id="how-to-run-a-report"></a>[<span data-ttu-id="31b31-117">如何运行报告</span><span class="sxs-lookup"><span data-stu-id="31b31-117">How to Run a Report</span></span>](how-to-run-a-reportserver.md)  
<span data-ttu-id="31b31-118">提供运行报表的分步过程。</span><span class="sxs-lookup"><span data-stu-id="31b31-118">Provides a step-by-step process for running a report.</span></span>

<a href="" id="how-to-print-a-report"></a>[<span data-ttu-id="31b31-119">如何打印报告</span><span class="sxs-lookup"><span data-stu-id="31b31-119">How to Print a Report</span></span>](how-to-print-a-reportserver.md)  
<span data-ttu-id="31b31-120">提供打印报表的分步过程。</span><span class="sxs-lookup"><span data-stu-id="31b31-120">Provides a step-by-step process for printing a report.</span></span>

<a href="" id="how-to-export-a-report"></a>[<span data-ttu-id="31b31-121">如何导出报告</span><span class="sxs-lookup"><span data-stu-id="31b31-121">How to Export a Report</span></span>](how-to-export-a-reportserver.md)  
<span data-ttu-id="31b31-122">提供导出报表的分步过程。</span><span class="sxs-lookup"><span data-stu-id="31b31-122">Provides a step-by-step process for exporting a report.</span></span>

<a href="" id="how-to-delete-a-report"></a>[<span data-ttu-id="31b31-123">如何删除报告</span><span class="sxs-lookup"><span data-stu-id="31b31-123">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)  
<span data-ttu-id="31b31-124">提供删除报表的分步过程。</span><span class="sxs-lookup"><span data-stu-id="31b31-124">Provides a step-by-step process for deleting a report.</span></span>

## <span data-ttu-id="31b31-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="31b31-125">Related topics</span></span>


[<span data-ttu-id="31b31-126">应用程序使用率报告</span><span class="sxs-lookup"><span data-stu-id="31b31-126">Application Utilization Report</span></span>](application-utilization-reportserver.md)

[<span data-ttu-id="31b31-127">如何在 Application Virtualization Server Management Console 中执行管理任务</span><span class="sxs-lookup"><span data-stu-id="31b31-127">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="31b31-128">软件审计报告</span><span class="sxs-lookup"><span data-stu-id="31b31-128">Software Audit Report</span></span>](software-audit-reportserver.md)

[<span data-ttu-id="31b31-129">系统错误报告</span><span class="sxs-lookup"><span data-stu-id="31b31-129">System Error Report</span></span>](system-error-reportserver.md)

[<span data-ttu-id="31b31-130">系统使用率报告</span><span class="sxs-lookup"><span data-stu-id="31b31-130">System Utilization Report</span></span>](system-utilization-reportserver.md)

 

 





