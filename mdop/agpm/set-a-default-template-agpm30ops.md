---
title: 设置默认模板
description: 设置默认模板
author: dansimp
ms.assetid: 84edbd69-451b-4c10-a898-781d4b75d09c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dec198126e98e1267589fdf252e158a0b1181b05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802544"
---
# <span data-ttu-id="d67fd-103">设置默认模板</span><span class="sxs-lookup"><span data-stu-id="d67fd-103">Set a Default Template</span></span>


<span data-ttu-id="d67fd-104">作为编辑器，你可以指定哪些可用模板将用作为所有组策略管理员创建新组策略对象（Gpo）推荐的默认模板。</span><span class="sxs-lookup"><span data-stu-id="d67fd-104">As an Editor, you can specify which of the available templates will be the default template suggested for all Group Policy administrators creating new Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="d67fd-105">**注意** 模板是 GPO 的不可编辑的静态版本，用作创建新的可编辑 Gpo 的起始点。</span><span class="sxs-lookup"><span data-stu-id="d67fd-105">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="d67fd-106">需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="d67fd-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="d67fd-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d67fd-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="d67fd-108">设置创建新 Gpo 时使用的默认模板</span><span class="sxs-lookup"><span data-stu-id="d67fd-108">To set the default template for use when creating new GPOs</span></span>**

1.  <span data-ttu-id="d67fd-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="d67fd-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d67fd-110">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**模板**" 选项卡以显示可用模板。</span><span class="sxs-lookup"><span data-stu-id="d67fd-110">On the **Contents** tab in the details pane, click the **Templates** tab to display available templates.</span></span>

3.  <span data-ttu-id="d67fd-111">右键单击要设置为默认模板的模板，然后单击 "**设为默认值**"。</span><span class="sxs-lookup"><span data-stu-id="d67fd-111">Right-click the template that you want to set as the default, and then click **Set as Default**.</span></span>

4.  <span data-ttu-id="d67fd-112">单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="d67fd-112">Click **Yes** to confirm.</span></span>

5.  <span data-ttu-id="d67fd-113">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="d67fd-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="d67fd-114">默认模板有一个蓝色图标，在 "**模板**" 选项卡上，其状态标识为 "**模板（默认）** "。</span><span class="sxs-lookup"><span data-stu-id="d67fd-114">The default template has a blue icon and the state is identified as **Template (default)** on the **Templates** tab.</span></span>

### <span data-ttu-id="d67fd-115">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="d67fd-115">Additional considerations</span></span>

-   <span data-ttu-id="d67fd-116">默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="d67fd-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="d67fd-117">具体而言，您必须拥有**列表内容**并为域**创建模板**权限。</span><span class="sxs-lookup"><span data-stu-id="d67fd-117">Specifically, you must have **List Contents** and **Create Template** permissions for the domain.</span></span>

-   <span data-ttu-id="d67fd-118">将模板设置为默认值后，该模板将是初始在组策略管理员创建新 Gpo 时的 "**新建受控 GPO** " 对话框中所选的模板。</span><span class="sxs-lookup"><span data-stu-id="d67fd-118">After you set a template as the default, that template will be the one initially selected in the **New Controlled GPO** dialog box when Group Policy administrators create new GPOs.</span></span> <span data-ttu-id="d67fd-119">但是，它们将具有选择任何其他 GPO 模板的选项，包括不包含任何设置的\*\* &lt; 空 gpo &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="d67fd-119">However, they will have the option to select any other GPO template, including **&lt;Empty GPO&gt;**, which does not include any settings.</span></span>

-   <span data-ttu-id="d67fd-120">重命名或删除模板不会影响从该模板创建的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="d67fd-120">Renaming or deleting a template does not impact GPOs created from that template.</span></span>

-   <span data-ttu-id="d67fd-121">由于不能对其进行更改，因此模板没有历史记录。</span><span class="sxs-lookup"><span data-stu-id="d67fd-121">Because it cannot be altered, a template does not have a history.</span></span>

### <span data-ttu-id="d67fd-122">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="d67fd-122">Additional references</span></span>

-   [<span data-ttu-id="d67fd-123">创建模板和设置默认模板</span><span class="sxs-lookup"><span data-stu-id="d67fd-123">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm30ops.md)

-   [<span data-ttu-id="d67fd-124">请求创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="d67fd-124">Request the Creation of a New Controlled GPO</span></span>](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)

 

 





