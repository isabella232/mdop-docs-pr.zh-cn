---
title: 从生产导入 GPO
description: 从生产导入 GPO
author: dansimp
ms.assetid: 35c2a682-ece8-4577-a083-7e3e9facfd13
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3d739a46d5ca078ec9d218c1cc1e5bd258c55601
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802727"
---
# <span data-ttu-id="f67d4-103">从生产导入 GPO</span><span class="sxs-lookup"><span data-stu-id="f67d4-103">Import a GPO from Production</span></span>


<span data-ttu-id="f67d4-104">如果在高级组策略管理（AGPM）之外对受控组策略对象（GPO）进行了更改，则可以从生产环境导入该 GPO 的副本并将其保存到存档中，以使存档和生产环境处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="f67d4-104">If changes are made to a controlled Group Policy Object (GPO) outside of Advanced Group Policy Management (AGPM), you can import a copy of the GPO from the production environment and save it to the archive to bring the archive and the production environment to a consistent state.</span></span> <span data-ttu-id="f67d4-105">（若要导入不受控制的 GPO，请控制该 GPO。</span><span class="sxs-lookup"><span data-stu-id="f67d4-105">(To import an uncontrolled GPO, control the GPO.</span></span> <span data-ttu-id="f67d4-106">请参阅[请求控制不受控制的 GPO](request-control-of-an-uncontrolled-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="f67d4-106">See [Request Control of an Uncontrolled GPO](request-control-of-an-uncontrolled-gpo-agpm30ops.md).)</span></span>

<span data-ttu-id="f67d4-107">具有 "编辑"、"审批者" 或 "AGPM 管理员（完全控制）" 角色或必需权限 inAGPM 的用户帐户需要完成此过程。</span><span class="sxs-lookup"><span data-stu-id="f67d4-107">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions inAGPM is required to complete this procedure.</span></span> <span data-ttu-id="f67d4-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f67d4-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="f67d4-109">从生产环境导入 GPO</span><span class="sxs-lookup"><span data-stu-id="f67d4-109">To import a GPO from the production environment</span></span>**

1.  <span data-ttu-id="f67d4-110">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="f67d4-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="f67d4-111">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="f67d4-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="f67d4-112">右键单击该 GPO，然后单击 "**从生产导入**"。</span><span class="sxs-lookup"><span data-stu-id="f67d4-112">Right-click the GPO, and then click **Import from Production**.</span></span>

4.  <span data-ttu-id="f67d4-113">为 GPO 的审核跟踪键入注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="f67d4-113">Type a comment for the audit trail of the GPO, and then click **OK**.</span></span>

### <span data-ttu-id="f67d4-114">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="f67d4-114">Additional considerations</span></span>

-   <span data-ttu-id="f67d4-115">默认情况下，你必须是编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="f67d4-115">By default, you must be an Editor, Approver, or AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="f67d4-116">具体而言，您必须具有**列表内容**，并且可以**编辑设置**、**部署 GPO**或删除 gpo 的**gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="f67d4-116">Specifically, you must have **List Contents** and either **Edit Settings**, **Deploy GPO**, or **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="f67d4-117">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="f67d4-117">Additional references</span></span>

-   [<span data-ttu-id="f67d4-118">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="f67d4-118">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-agpm30ops.md)

 

 





