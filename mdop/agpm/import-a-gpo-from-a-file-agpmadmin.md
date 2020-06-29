---
title: 从文件导入 GPO
description: 从文件导入 GPO
author: dansimp
ms.assetid: 2cbcda72-4de3-47ad-aaf8-4fc7341d5a00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 04819dacac8df73f0a61cace0dab8b9fa79b7307
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802743"
---
# <span data-ttu-id="aaa65-103">从文件导入 GPO</span><span class="sxs-lookup"><span data-stu-id="aaa65-103">Import a GPO from a File</span></span>


<span data-ttu-id="aaa65-104">在高级组策略管理（AGPM）中，如果你是 AGPM 管理员（完全控制），并且已将组策略对象（GPO）导出到 CAB 文件，则可以将该 GPO 中的策略设置导入新 GPO 或另一个林中的域中的现有 GPO。</span><span class="sxs-lookup"><span data-stu-id="aaa65-104">In Advanced Group Policy Management (AGPM), if you are an AGPM Administrator (Full Control) and you have exported a Group Policy Object (GPO) to a CAB file, you can import the policy settings from that GPO into a new GPO or an existing GPO in a domain in another forest.</span></span> <span data-ttu-id="aaa65-105">有关将 GPO 设置导出到 CAB 文件的信息，请参阅[将 Gpo 导出到文件](export-a-gpo-to-a-file.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa65-105">For information about exporting GPO settings to a CAB file, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

<span data-ttu-id="aaa65-106">需要使用 AGPM 管理员角色的用户帐户或 AGPM 中的必要权限才能将策略设置导入到新的受控 GPO 中。</span><span class="sxs-lookup"><span data-stu-id="aaa65-106">A user account with the AGPM Administrator role or the necessary permissions in AGPM is required to import policy settings into a new controlled GPO.</span></span> <span data-ttu-id="aaa65-107">需要具有编辑者或 AGPM 管理员角色的用户帐户或 AGPM 中的必需权限才能将策略设置导入到现有 GPO 中。</span><span class="sxs-lookup"><span data-stu-id="aaa65-107">A user account with the Editor or AGPM Administrator role or necessary permissions in AGPM is required to import policy settings into an existing GPO.</span></span> <span data-ttu-id="aaa65-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aaa65-108">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="aaa65-109">从文件导入策略设置</span><span class="sxs-lookup"><span data-stu-id="aaa65-109">Importing policy settings from a file</span></span>


<span data-ttu-id="aaa65-110">从文件导入策略设置时，可以将其导入到新的 GPO 或现有 GPO 中。</span><span class="sxs-lookup"><span data-stu-id="aaa65-110">When you import policy settings from a file, you can import them into a new GPO or an existing GPO.</span></span> <span data-ttu-id="aaa65-111">但是，如果将策略设置导入到现有 GPO 中，则会替换其中的所有策略设置。</span><span class="sxs-lookup"><span data-stu-id="aaa65-111">However, if you import policy settings into an existing GPO, all policy settings within it are replaced.</span></span>

-   [<span data-ttu-id="aaa65-112">将策略设置导入到新的受控 GPO 中</span><span class="sxs-lookup"><span data-stu-id="aaa65-112">Import policy settings into a new controlled GPO</span></span>](#bkmk-new)

-   [<span data-ttu-id="aaa65-113">将策略设置导入到现有 GPO 中</span><span class="sxs-lookup"><span data-stu-id="aaa65-113">Import policy settings into an existing GPO</span></span>](#bkmk-existing)

### <a href="" id="bkmk-new"></a>

**<span data-ttu-id="aaa65-114">将策略设置导入新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="aaa65-114">To import policy settings into a new controlled GPO</span></span>**

1.  <span data-ttu-id="aaa65-115">在 "**组策略管理" 控制台**树中，单击要将策略设置导入到的域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aaa65-115">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="aaa65-116">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="aaa65-116">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="aaa65-117">创建一个新的受控 GPO。</span><span class="sxs-lookup"><span data-stu-id="aaa65-117">Create a new controlled GPO.</span></span> <span data-ttu-id="aaa65-118">在 "**新建受控制的 GPO** " 对话框中，单击 "**导入**"，然后单击 "**启动向导**"。</span><span class="sxs-lookup"><span data-stu-id="aaa65-118">In the **New Controlled GPO** dialog box, click **Import** and then click **Launch Wizard**.</span></span> <span data-ttu-id="aaa65-119">有关如何创建 GPO 的详细信息，请参阅[创建新的受控 GPO](create-a-new-controlled-gpo-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa65-119">For more information about how to create a GPO, see [Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md).</span></span>

4.  <span data-ttu-id="aaa65-120">按照**导入设置向导**中的说明选择 GPO 备份，从其导入新 gpo 的策略设置，并为新 gpo 的审核跟踪输入注释。</span><span class="sxs-lookup"><span data-stu-id="aaa65-120">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import policy settings from it for the new GPO, and enter a comment for the audit trail of the new GPO.</span></span>

### <a href="" id="bkmk-existing"></a>

**<span data-ttu-id="aaa65-121">将策略设置导入到现有 GPO 中</span><span class="sxs-lookup"><span data-stu-id="aaa65-121">To import policy settings into an existing GPO</span></span>**

1.  <span data-ttu-id="aaa65-122">在 "**组策略管理" 控制台**树中，单击要将策略设置导入到的域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aaa65-122">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="aaa65-123">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="aaa65-123">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="aaa65-124">查看要将策略设置导入到的目标 GPO。</span><span class="sxs-lookup"><span data-stu-id="aaa65-124">Check out the destination GPO to which you want to import policy settings.</span></span>

4.  <span data-ttu-id="aaa65-125">右键单击目标 GPO，指向 "**导入**"，然后单击 "**文件**"。</span><span class="sxs-lookup"><span data-stu-id="aaa65-125">Right-click the destination GPO, point to **Import from**, and then click **File**.</span></span>

5.  <span data-ttu-id="aaa65-126">按照**导入设置向导**中的说明选择 GPO 备份，导入其策略设置以替换目标 gpo 中的这些设置，并输入目标 gpo 审核跟踪的注释。</span><span class="sxs-lookup"><span data-stu-id="aaa65-126">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import its policy settings to replace those in the destination GPO, and enter a comment for the audit trail of the destination GPO.</span></span> <span data-ttu-id="aaa65-127">默认情况下，向导完成时将签入目标 GPO。</span><span class="sxs-lookup"><span data-stu-id="aaa65-127">By default, the destination GPO is checked in when the wizard is finished.</span></span>

### <span data-ttu-id="aaa65-128">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="aaa65-128">Additional considerations</span></span>

-   <span data-ttu-id="aaa65-129">若要将策略设置导入到新的受控制的 GPO，必须具有**列表内容**、**导入 GPO**和为域**创建 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="aaa65-129">To import policy settings to a new controlled GPO, you must have **List Contents**, **Import GPO**, and **Create GPO** permissions for the domain.</span></span> <span data-ttu-id="aaa65-130">默认情况下，您必须是 AGPM 管理员才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="aaa65-130">By default, you must be an AGPM Administrator to perform this procedure.</span></span>

-   <span data-ttu-id="aaa65-131">若要将策略设置导入到现有 GPO，必须具有**列表内容**、**编辑设置**和为域**导入 gpo**权限，并且 GPO 必须由你签出。</span><span class="sxs-lookup"><span data-stu-id="aaa65-131">To import policy settings to an existing GPO, you must have **List Contents**, **Edit Settings**, and **Import GPO** permissions for the domain, and the GPO must be checked out by you.</span></span> <span data-ttu-id="aaa65-132">默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="aaa65-132">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span>

### <span data-ttu-id="aaa65-133">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="aaa65-133">Additional references</span></span>

-   [<span data-ttu-id="aaa65-134">管理存档</span><span class="sxs-lookup"><span data-stu-id="aaa65-134">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





