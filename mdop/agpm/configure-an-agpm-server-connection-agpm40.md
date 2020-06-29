---
title: 配置 AGPM 服务器连接
description: 配置 AGPM 服务器连接
author: dansimp
ms.assetid: 409cbbcf-3b0e-459d-9bd2-75cb7b9430b0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7fdc26045b478da14957cdfe6000d58ab72a064
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802075"
---
# <span data-ttu-id="f926c-103">配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="f926c-103">Configure an AGPM Server Connection</span></span>


<span data-ttu-id="f926c-104">若要确保已连接到正确的中心存档，请查看 AGPM 服务器连接的配置。</span><span class="sxs-lookup"><span data-stu-id="f926c-104">To ensure that you are connected to the correct central archive, review the configuration of the AGPM Server connection.</span></span> <span data-ttu-id="f926c-105">如果 AGPM 管理员（完全控制）尚未为你配置 AGPM 服务器连接，则必须手动配置它。</span><span class="sxs-lookup"><span data-stu-id="f926c-105">If an AGPM Administrator (Full Control) has not configured an AGPM Server connection for you, then you must manually configure it.</span></span>

**<span data-ttu-id="f926c-106">选择 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="f926c-106">To select an AGPM Server</span></span>**

1.  <span data-ttu-id="f926c-107">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="f926c-107">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="f926c-108">在 "详细信息" 窗格中，单击 " **AGPM 服务器**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="f926c-108">In the details pane, click the **AGPM Server** tab:</span></span>

    -   <span data-ttu-id="f926c-109">如果 " **Agpm 服务器**" 选项卡上的选项不可用，则是由 AGPM 管理员集中配置的。</span><span class="sxs-lookup"><span data-stu-id="f926c-109">If the options on the **AGPM Server** tab are unavailable, they have been centrally configured by an AGPM Administrator.</span></span>

    -   <span data-ttu-id="f926c-110">如果 " **Agpm server** " 选项卡上的选项可用，请键入 agpm 服务器的完全限定的计算机名称（例如，server.contoso.com）和 agpm 服务侦听的端口（默认情况下为端口4600）。</span><span class="sxs-lookup"><span data-stu-id="f926c-110">If the options on the **AGPM Server** tab are available, type the fully-qualified computer name for the AGPM Server (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span> <span data-ttu-id="f926c-111">单击 "**应用**"，然后单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="f926c-111">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="f926c-112">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="f926c-112">Additional considerations</span></span>

-   <span data-ttu-id="f926c-113">所选的 AGPM 服务器确定在 "**目录**" 选项卡上显示哪些 gpo 以及应用 "**域委派**" 选项卡设置的位置。</span><span class="sxs-lookup"><span data-stu-id="f926c-113">The AGPM Servers selected determine which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="f926c-114">如果不是通过管理模板进行集中管理，则每个组策略管理员必须将此设置配置为指向域的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="f926c-114">If not centrally managed through the Administrative template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

### <span data-ttu-id="f926c-115">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="f926c-115">Additional references</span></span>

-   [<span data-ttu-id="f926c-116">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="f926c-116">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





