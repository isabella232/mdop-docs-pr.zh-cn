---
title: 查看 GPO 设置
description: 查看 GPO 设置
author: dansimp
ms.assetid: bed956d0-082e-4fa9-bf1e-572d0d3d02ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 23d18eb5a41b4246964b79f687eb9fa44b98b730
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801776"
---
# <span data-ttu-id="9f487-103">查看 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="9f487-103">Review GPO Settings</span></span>


<span data-ttu-id="9f487-104">你可以生成基于 HTML 的报表和基于 XML 的报表，用于查看任何版本的组策略对象（GPO）内的设置。</span><span class="sxs-lookup"><span data-stu-id="9f487-104">You can generate HTML-based and XML-based reports for reviewing settings within any version of a Group Policy Object (GPO).</span></span>

<span data-ttu-id="9f487-105">需要具有 "审阅者"、"编辑"、"审批者" 或 "AGPM 管理员（完全控制）" 角色或 "高级组策略管理" （AGPM）中的必要权限才能完成此过程的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9f487-105">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="9f487-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9f487-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="9f487-107">查看 GPO 的任何版本中的设置</span><span class="sxs-lookup"><span data-stu-id="9f487-107">To review settings in any version of a GPO</span></span>**

1.  <span data-ttu-id="9f487-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="9f487-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="9f487-109">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo。</span><span class="sxs-lookup"><span data-stu-id="9f487-109">On the **Contents** tab in the details pane, click a tab to display GPOs.</span></span>

3.  <span data-ttu-id="9f487-110">双击该 GPO 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="9f487-110">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="9f487-111">右键单击要查看其设置的 GPO 版本，单击 "**设置**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示 GPO 设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="9f487-111">Right-click the GPO version for which to review the settings, click **Settings**, and then click **HTML Report** or **XML Report** to display a summary of the GPO's settings.</span></span>

### <span data-ttu-id="9f487-112">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="9f487-112">Additional considerations</span></span>

-   <span data-ttu-id="9f487-113">默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="9f487-113">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="9f487-114">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**读取设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="9f487-114">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="9f487-115">此外，若要显示 Gpo 的列表，您必须拥有该域的 "**列表内容**" 权限。</span><span class="sxs-lookup"><span data-stu-id="9f487-115">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="9f487-116">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="9f487-116">Additional references</span></span>

-   [<span data-ttu-id="9f487-117">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="9f487-117">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





