---
title: 配置记录和跟踪
description: 配置记录和跟踪
author: dansimp
ms.assetid: 4f89552f-e949-48b0-9325-23746034eaa4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6edcb643dd34a20a845cb3d44a0fe8b353a6291
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802035"
---
# <span data-ttu-id="384c3-103">配置记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="384c3-103">Configure Logging and Tracing</span></span>


<span data-ttu-id="384c3-104">你可以使用 "管理模板" 集中配置可选日志记录和跟踪。</span><span class="sxs-lookup"><span data-stu-id="384c3-104">You can centrally configure optional logging and tracing using Administrative templates.</span></span> <span data-ttu-id="384c3-105">这可能有助于诊断与高级组策略管理（AGPM）相关的任何问题。</span><span class="sxs-lookup"><span data-stu-id="384c3-105">This may be helpful when diagnosing any problems related to Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="384c3-106">具有 AGPM 管理员（完全控制）角色的用户帐户、创建了在这些过程中使用组策略对象（GPO）的审批者的用户帐户，或者需要使用 AGPM 中的必要权限的用户帐户才能完成这些过程。</span><span class="sxs-lookup"><span data-stu-id="384c3-106">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the Group Policy Object (GPO) used in these procedures, or a user account with the necessary permissions in AGPM is required to complete these procedures.</span></span> <span data-ttu-id="384c3-107">此外，若要在 AGPM 服务器上启动日志记录，必须具有访问 AGPM 服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="384c3-107">Additionally, a user account with access to the AGPM Server is required to initiate logging on the AGPM Server.</span></span> <span data-ttu-id="384c3-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="384c3-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="384c3-109">为 AGPM 配置日志记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="384c3-109">To configure logging and tracing for AGPM</span></span>**

1.  <span data-ttu-id="384c3-110">在**组策略管理控制台**树中，编辑应用到要启用日志记录和跟踪的所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="384c3-110">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators for which you want to turn on logging and tracing.</span></span> <span data-ttu-id="384c3-111">（有关详细信息，请参阅[编辑 GPO](editing-a-gpo-agpm30ops.md)。）</span><span class="sxs-lookup"><span data-stu-id="384c3-111">(For more information, see [Editing a GPO](editing-a-gpo-agpm30ops.md).)</span></span>

2.  <span data-ttu-id="384c3-112">在**组策略管理编辑器**窗口中，单击 "**计算机配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="384c3-112">In the **Group Policy Management Editor** window, click **Computer Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

3.  <span data-ttu-id="384c3-113">在 "详细信息" 窗格中，双击 " **AGPM：配置日志记录**"。</span><span class="sxs-lookup"><span data-stu-id="384c3-113">In the details pane, double-click **AGPM: Configure logging**.</span></span>

4.  <span data-ttu-id="384c3-114">在 "**属性**" 窗口中，单击 "**已启用**"，并配置日志中记录的详细信息级别。</span><span class="sxs-lookup"><span data-stu-id="384c3-114">In the **Properties** window, click **Enabled**, and configure the level of detail to record in the logs.</span></span>

5.  <span data-ttu-id="384c3-115">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="384c3-115">Click **OK**.</span></span>

6.  <span data-ttu-id="384c3-116">关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="384c3-116">Close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="384c3-117">（有关详细信息，请参阅[部署 GPO](deploy-a-gpo-agpm30ops.md)。）更新组策略后，必须重新启动 AGPM 服务才能启动、修改或停止 AGPM 服务器上的日志记录。</span><span class="sxs-lookup"><span data-stu-id="384c3-117">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm30ops.md).) After Group Policy is updated, you must restart the AGPM Service to start, modify, or stop logging on the AGPM Server.</span></span> <span data-ttu-id="384c3-118">组策略管理员必须关闭并重新启动 GPMC，才能在其计算机上启动、修改或停止日志记录。</span><span class="sxs-lookup"><span data-stu-id="384c3-118">Group Policy administrators must close and restart the GPMC to start, modify, or stop logging on their computers.</span></span>

    <span data-ttu-id="384c3-119">**跟踪文件位置**：</span><span class="sxs-lookup"><span data-stu-id="384c3-119">**Trace file locations**:</span></span>

    -   <span data-ttu-id="384c3-120">客户端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="384c3-120">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

    -   <span data-ttu-id="384c3-121">服务器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="384c3-121">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

### <span data-ttu-id="384c3-122">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="384c3-122">Additional considerations</span></span>

-   <span data-ttu-id="384c3-123">你必须能够编辑和部署 GPO，才能配置 AGPM 日志记录和跟踪。</span><span class="sxs-lookup"><span data-stu-id="384c3-123">You must be able to edit and deploy a GPO to configure AGPM logging and tracing.</span></span> <span data-ttu-id="384c3-124">有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo-agpm30ops.md)和[部署 gpo](deploy-a-gpo-agpm30ops.md) 。</span><span class="sxs-lookup"><span data-stu-id="384c3-124">See [Editing a GPO](editing-a-gpo-agpm30ops.md) and [Deploy a GPO](deploy-a-gpo-agpm30ops.md) for additional detail.</span></span>

### <span data-ttu-id="384c3-125">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="384c3-125">Additional references</span></span>

-   [<span data-ttu-id="384c3-126">配置高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="384c3-126">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management.md)

 

 





