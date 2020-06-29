---
title: 创建模板
description: 创建模板
author: dansimp
ms.assetid: b38423af-7d24-437a-98bc-01f1ae891127
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd50dd41863e383b931b8563854a8bbd4ee196d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802871"
---
# <span data-ttu-id="58e50-103">创建模板</span><span class="sxs-lookup"><span data-stu-id="58e50-103">Create a Template</span></span>


<span data-ttu-id="58e50-104">通过创建模板，你可以保存特定版本的组策略对象（GPO）的所有设置，以便将其用作创建新 Gpo 的起始点。</span><span class="sxs-lookup"><span data-stu-id="58e50-104">Creating a template enables you to save all of the settings of a particular version of a Group Policy Object (GPO) to use as a starting point for creating new GPOs.</span></span>

<span data-ttu-id="58e50-105">**注意** 模板是 GPO 的不可编辑的静态版本，用作创建新的可编辑 Gpo 的起始点。</span><span class="sxs-lookup"><span data-stu-id="58e50-105">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="58e50-106">需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="58e50-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="58e50-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="58e50-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="58e50-108">基于现有 GPO 创建模板</span><span class="sxs-lookup"><span data-stu-id="58e50-108">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="58e50-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="58e50-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="58e50-110">在 "详细信息" 窗格的 "**目录**" 选项卡上，单击 "**受控**" 或 "未**控制**" 选项卡以显示可用 gpo</span><span class="sxs-lookup"><span data-stu-id="58e50-110">On the **Contents** tab in the details pane, click the **Controlled** or **Uncontrolled** tab to display available GPOs.</span></span>

3.  <span data-ttu-id="58e50-111">右键单击要从中创建模板的 GPO，然后单击 "**另存为模板**"。</span><span class="sxs-lookup"><span data-stu-id="58e50-111">Right-click the GPO from which you want to create a template, and then click **Save as Template**.</span></span>

4.  <span data-ttu-id="58e50-112">键入模板的名称和注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="58e50-112">Type a name for the template and a comment, and then click **OK**.</span></span>

5.  <span data-ttu-id="58e50-113">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="58e50-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="58e50-114">新模板将显示在 "**模板**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="58e50-114">The new template appears on the **Templates** tab.</span></span>

### <span data-ttu-id="58e50-115">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="58e50-115">Additional considerations</span></span>

-   <span data-ttu-id="58e50-116">默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="58e50-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="58e50-117">具体而言，您必须拥有**列表内容**并为域**创建模板**权限。</span><span class="sxs-lookup"><span data-stu-id="58e50-117">Specifically, you must have **List Contents** and **Create Template** permissions for the domain.</span></span>

-   <span data-ttu-id="58e50-118">重命名或删除模板不会影响从该模板创建的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="58e50-118">Renaming or deleting a template does not impact GPOs created from that template.</span></span>

-   <span data-ttu-id="58e50-119">由于不能对其进行更改，因此模板没有历史记录。</span><span class="sxs-lookup"><span data-stu-id="58e50-119">Because it cannot be altered, a template does not have a history.</span></span>

### <span data-ttu-id="58e50-120">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="58e50-120">Additional references</span></span>

-   [<span data-ttu-id="58e50-121">创建模板和设置默认模板</span><span class="sxs-lookup"><span data-stu-id="58e50-121">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [<span data-ttu-id="58e50-122">请求创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="58e50-122">Request the Creation of a New Controlled GPO</span></span>](request-the-creation-of-a-new-controlled-gpo-agpm40.md)

 

 





