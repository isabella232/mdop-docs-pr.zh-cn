---
title: 从文件导入 GPO
description: 从文件导入 GPO
author: dansimp
ms.assetid: 6e901a52-1101-4fed-9f90-3819b573b378
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15704806f089bb0d8530cd84df64b0889413426
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802731"
---
# <span data-ttu-id="83516-103">从文件导入 GPO</span><span class="sxs-lookup"><span data-stu-id="83516-103">Import a GPO from a File</span></span>


<span data-ttu-id="83516-104">在高级组策略管理（AGPM）中，如果已将组策略对象（GPO）导出到 CAB 文件，则可以将该 GPO 中的策略设置导入另一个林中的域中的现有 GPO。</span><span class="sxs-lookup"><span data-stu-id="83516-104">In Advanced Group Policy Management (AGPM), if you have exported a Group Policy Object (GPO) to a CAB file, you can import the policy settings from that GPO into an existing GPO in a domain in another forest.</span></span> <span data-ttu-id="83516-105">将策略设置导入现有 GPO 将替换该 GPO 中的所有策略设置。</span><span class="sxs-lookup"><span data-stu-id="83516-105">Importing policy settings into an existing GPO replaces all policy settings within that GPO.</span></span> <span data-ttu-id="83516-106">有关将 GPO 设置导出到 CAB 文件的信息，请参阅[将 Gpo 导出到文件](export-a-gpo-to-a-file.md)。</span><span class="sxs-lookup"><span data-stu-id="83516-106">For information about exporting GPO settings to a CAB file, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

<span data-ttu-id="83516-107">需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="83516-107">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span><span data-ttu-id="83516-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83516-108">Review the details in "Additional considerations" in this topic.</span></span>

## <a href="" id="bkmk-existing"></a>


**<span data-ttu-id="83516-109">将策略设置导入到现有 GPO 中</span><span class="sxs-lookup"><span data-stu-id="83516-109">To import policy settings into an existing GPO</span></span>**

1.  <span data-ttu-id="83516-110">在 "**组策略管理" 控制台**树中，单击要将策略设置导入到的域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="83516-110">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="83516-111">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="83516-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="83516-112">查看要将策略设置导入到的目标 GPO。</span><span class="sxs-lookup"><span data-stu-id="83516-112">Check out the destination GPO to which you want to import policy settings.</span></span>

4.  <span data-ttu-id="83516-113">右键单击目标 GPO，指向 "**导入**"，然后单击 "**文件**"。</span><span class="sxs-lookup"><span data-stu-id="83516-113">Right-click the destination GPO, point to **Import from**, and then click **File**.</span></span>

5.  <span data-ttu-id="83516-114">按照**导入设置向导**中的说明选择 GPO 备份，导入其策略设置以替换目标 gpo 中的这些设置，并输入目标 gpo 审核跟踪的注释。</span><span class="sxs-lookup"><span data-stu-id="83516-114">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import its policy settings to replace those in the destination GPO, and enter a comment for the audit trail of the destination GPO.</span></span> <span data-ttu-id="83516-115">默认情况下，向导完成时将签入目标 GPO。</span><span class="sxs-lookup"><span data-stu-id="83516-115">By default, the destination GPO is checked in when the wizard is finished.</span></span>

### <span data-ttu-id="83516-116">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="83516-116">Additional considerations</span></span>

-   <span data-ttu-id="83516-117">默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="83516-117">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="83516-118">具体而言，您必须具有 "**列表内容**"、"**编辑设置**" 和 "**导入**域的 gpo" 权限，并且 GPO 必须由您签出。</span><span class="sxs-lookup"><span data-stu-id="83516-118">Specifically, you must have **List Contents**, **Edit Settings**, and **Import GPO** permissions for the domain, and the GPO must be checked out by you.</span></span>

-   <span data-ttu-id="83516-119">尽管编辑器在创建新 GPO 期间无法将策略设置导入到新 GPO 中，但编辑器可请求创建新 GPO，然后在创建新 GPO 后将策略设置导入该 GPO。</span><span class="sxs-lookup"><span data-stu-id="83516-119">Although an Editor cannot import policy settings into a new GPO during its creation, an Editor can request the creation of a new GPO and then import policy settings into it after it is created.</span></span>

### <span data-ttu-id="83516-120">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="83516-120">Additional references</span></span>

-   [<span data-ttu-id="83516-121">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="83516-121">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





