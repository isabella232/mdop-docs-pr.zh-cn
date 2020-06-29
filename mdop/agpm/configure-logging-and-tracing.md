---
title: 配置记录和跟踪
description: 配置记录和跟踪
author: dansimp
ms.assetid: 419231f9-e9db-4f91-a7cf-a0a73db25256
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa3dfa71edb25f6641ade595cd4469e846410ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802031"
---
# <span data-ttu-id="c44f7-103">配置记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="c44f7-103">Configure Logging and Tracing</span></span>


<span data-ttu-id="c44f7-104">你可以使用管理模板集中配置高级组策略管理（AGPM）的可选日志记录和跟踪。</span><span class="sxs-lookup"><span data-stu-id="c44f7-104">You can centrally configure optional logging and tracing for Advanced Group Policy Management (AGPM) using Administrative templates.</span></span>

<span data-ttu-id="c44f7-105">具有 AGPM 管理员（完全控制）角色的用户帐户、创建在这些过程中使用的 GPO 的审批者的用户帐户，或者需要高级组策略管理中具有必需权限的用户帐户才能完成这些过程。</span><span class="sxs-lookup"><span data-stu-id="c44f7-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete these procedures.</span></span> <span data-ttu-id="c44f7-106">此外，若要在 AGPM 服务器上启动日志记录，必须具有访问 AGPM 服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c44f7-106">Additionally, a user account with access to the AGPM Server is required to initiate logging on the AGPM Server.</span></span> <span data-ttu-id="c44f7-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c44f7-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="c44f7-108">为 AGPM 配置日志记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="c44f7-108">To configure logging and tracing for AGPM</span></span>**

1.  <span data-ttu-id="c44f7-109">在**组策略管理控制台**树中，编辑应用到要启用日志记录和跟踪的所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c44f7-109">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators for which you want to turn on logging and tracing.</span></span> <span data-ttu-id="c44f7-110">（有关详细信息，请参阅[编辑 GPO](editing-a-gpo.md)。）</span><span class="sxs-lookup"><span data-stu-id="c44f7-110">(For more information, see [Editing a GPO](editing-a-gpo.md).)</span></span>

2.  <span data-ttu-id="c44f7-111">在 "**组策略对象编辑器**" 中，单击 "**计算机配置**"、"**管理模板**" 和 " **Windows 组件**"。</span><span class="sxs-lookup"><span data-stu-id="c44f7-111">In the **Group Policy Object Editor**, click **Computer Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

3.  <span data-ttu-id="c44f7-112">如果 " **Windows 组件**" 下列出的是**AGPM**未列出：</span><span class="sxs-lookup"><span data-stu-id="c44f7-112">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="c44f7-113">右键单击 "**管理模板**"，然后单击 "**添加/删除模板**"。</span><span class="sxs-lookup"><span data-stu-id="c44f7-113">Right-click **Administrative Templates** and click **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="c44f7-114">单击 "**添加**"，选择 " **agpm** " 或 " **agpm .Adm**"，单击 "**打开**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="c44f7-114">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

4.  <span data-ttu-id="c44f7-115">在 " **Windows 组件**" 下，双击 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="c44f7-115">Under **Windows Components**, double-click **AGPM**.</span></span>

5.  <span data-ttu-id="c44f7-116">在 "详细信息" 窗格中，双击 " **AGPM 日志记录**"。</span><span class="sxs-lookup"><span data-stu-id="c44f7-116">In the details pane, double-click **AGPM Logging**.</span></span>

6.  <span data-ttu-id="c44f7-117">在 " **AGPM 日志记录属性**" 窗口中，单击 "**已启用**"，并配置日志中记录的详细信息级别。</span><span class="sxs-lookup"><span data-stu-id="c44f7-117">In the **AGPM Logging Properties** window, click **Enabled**, and configure the level of detail to record in the logs.</span></span>

7.  <span data-ttu-id="c44f7-118">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c44f7-118">Click **OK**.</span></span>

8.  <span data-ttu-id="c44f7-119">关闭 "**组策略对象编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="c44f7-119">Close the **Group Policy Object Editor**.</span></span> <span data-ttu-id="c44f7-120">（有关详细信息，请参阅[部署 GPO](deploy-a-gpo.md)。）更新组策略后，必须重新启动 AGPM 服务才能开始在 AGPM 服务器上登录。</span><span class="sxs-lookup"><span data-stu-id="c44f7-120">(For more information, see [Deploy a GPO](deploy-a-gpo.md).) After Group Policy is updated, you must restart the AGPM Service to begin logging on the AGPM Server.</span></span> <span data-ttu-id="c44f7-121">组策略管理员必须关闭并重新启动 GPMC，才能在其计算机上开始日志记录。</span><span class="sxs-lookup"><span data-stu-id="c44f7-121">Group Policy administrators must close and restart the GPMC to begin logging on their computers.</span></span>

    <span data-ttu-id="c44f7-122">**跟踪文件位置**：</span><span class="sxs-lookup"><span data-stu-id="c44f7-122">**Trace file locations**:</span></span>

    -   <span data-ttu-id="c44f7-123">客户端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="c44f7-123">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

    -   <span data-ttu-id="c44f7-124">服务器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="c44f7-124">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

### <span data-ttu-id="c44f7-125">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="c44f7-125">Additional considerations</span></span>

-   <span data-ttu-id="c44f7-126">你必须能够编辑和部署 GPO，才能配置 AGPM 日志记录和跟踪。</span><span class="sxs-lookup"><span data-stu-id="c44f7-126">You must be able to edit and deploy a GPO to configure AGPM logging and tracing.</span></span> <span data-ttu-id="c44f7-127">有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo.md)和[部署 gpo](deploy-a-gpo.md) 。</span><span class="sxs-lookup"><span data-stu-id="c44f7-127">See [Editing a GPO](editing-a-gpo.md) and [Deploy a GPO](deploy-a-gpo.md) for additional detail.</span></span>

### <span data-ttu-id="c44f7-128">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="c44f7-128">Additional references</span></span>

-   [<span data-ttu-id="c44f7-129">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="c44f7-129">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





