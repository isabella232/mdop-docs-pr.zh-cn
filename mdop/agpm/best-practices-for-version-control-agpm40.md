---
title: 版本控制最佳做法
description: 版本控制最佳做法
author: dansimp
ms.assetid: 4a2a1ac7-67f3-4ba3-ab07-860d33da0efe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d560913c4e0f49a2015f620564a9038677d65144
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802119"
---
# <span data-ttu-id="43d83-103">版本控制最佳做法</span><span class="sxs-lookup"><span data-stu-id="43d83-103">Best Practices for Version Control</span></span>


<span data-ttu-id="43d83-104">Microsoft 高级组策略管理（AGPM）为组策略对象（Gpo）提供版本控制，与 Microsoft Visual SourceSafe®提供源代码的版本控制。</span><span class="sxs-lookup"><span data-stu-id="43d83-104">Microsoft Advanced Group Policy Management (AGPM) provides version control for Group Policy Objects (GPOs) much like Microsoft Visual SourceSafe® provides version control for source code.</span></span> <span data-ttu-id="43d83-105">开发人员可以使用 Visual SourceSafe 管理每个源文件的多个版本。</span><span class="sxs-lookup"><span data-stu-id="43d83-105">Developers can use Visual SourceSafe to manage multiple versions of each source file.</span></span> <span data-ttu-id="43d83-106">组策略管理员可以使用 AGPM 对 Gpo 执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="43d83-106">Group Policy administrators can use AGPM to do the same for GPOs.</span></span> <span data-ttu-id="43d83-107">使用 AGPM 时，组策略管理员应注意适用于任何版本控制系统的最佳做法：</span><span class="sxs-lookup"><span data-stu-id="43d83-107">When you use AGPM, Group Policy administrators should be aware of best practices that apply to any version control system:</span></span>

-   <span data-ttu-id="43d83-108">**日期和时间：** AGPM 使用日期和时间标记 GPO 的每个版本。</span><span class="sxs-lookup"><span data-stu-id="43d83-108">**Date and time:** AGPM stamps each version of a GPO with the date and time.</span></span> <span data-ttu-id="43d83-109">为确保历史记录准确，尤其是在多台计算机上编辑 Gpo 时，请确保每台计算机都将其时钟与一个权威性的时间源同步。</span><span class="sxs-lookup"><span data-stu-id="43d83-109">To ensure that history is accurate, especially when you edit GPOs on more than one computer, make sure that each computer synchronizes its clock with one authoritative time source.</span></span>

-   <span data-ttu-id="43d83-110">**完成编辑 gpo 时，请签入这些 gpo：** 通常，编辑器签出 Gpo 并忘记将其签回存档中。</span><span class="sxs-lookup"><span data-stu-id="43d83-110">**Check in GPOs when you are finished editing them:** It is common for Editors to check out GPOs and forget to check them back into the archive.</span></span> <span data-ttu-id="43d83-111">但是，这可能会阻止其他组策略管理员更改 GPO。</span><span class="sxs-lookup"><span data-stu-id="43d83-111">However, this can prevent other Group Policy administrators from changing the GPO.</span></span> <span data-ttu-id="43d83-112">完成编辑后，始终将 Gpo 立即重新签入到 AGPM。</span><span class="sxs-lookup"><span data-stu-id="43d83-112">Always check GPOs back in to AGPM immediately when you are finished editing.</span></span>

-   <span data-ttu-id="43d83-113">**经常保存更改：** 编辑 GPO 时，请经常保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="43d83-113">**Save changes frequently:** When you edit a GPO, save changes frequently.</span></span> <span data-ttu-id="43d83-114">大多数编辑器签出 GPO，进行许多更改，然后将 GPO 签入存档。</span><span class="sxs-lookup"><span data-stu-id="43d83-114">Most Editors check out a GPO, make many changes, and then check the GPO into the archive.</span></span> <span data-ttu-id="43d83-115">而是定期将 GPO 检查到存档中，然后再次将其签出。</span><span class="sxs-lookup"><span data-stu-id="43d83-115">Instead, check the GPO into the archive regularly, and then check it out again.</span></span> <span data-ttu-id="43d83-116">在您更改每个设置（不推荐）或在您进行相关更改组之后检查 GPO 时，详细信息可以较小。</span><span class="sxs-lookup"><span data-stu-id="43d83-116">The detail can be as small as checking in the GPO after you change every setting (not recommended) or checking in the GPO after you make groups of related changes.</span></span> <span data-ttu-id="43d83-117">结果为每个 GPO 提供了一个更好记录的历史记录，可帮助解决问题。</span><span class="sxs-lookup"><span data-stu-id="43d83-117">The result is a better-documented history for each GPO that can help when troubleshooting issues.</span></span>

-   <span data-ttu-id="43d83-118">**经常部署 gpo：** 不要让尚未部署的新和编辑的 Gpo 累积在存档中的大量数字中。</span><span class="sxs-lookup"><span data-stu-id="43d83-118">**Deploy GPOs frequently:** Do not let new and edited GPOs that have not yet been deployed accumulate in large numbers in the archive.</span></span> <span data-ttu-id="43d83-119">而是尽快部署新的和编辑的 Gpo，以便它们对生产环境具有最小的影响。</span><span class="sxs-lookup"><span data-stu-id="43d83-119">Instead, deploy new and edited GPOs as soon as possible so that they have a minimum effect on the production environment.</span></span> <span data-ttu-id="43d83-120">一次部署许多新的和已编辑的 Gpo 可能会危害生产环境。</span><span class="sxs-lookup"><span data-stu-id="43d83-120">Deploying many new and edited GPOs at one time can jeopardize the production environment.</span></span>

-   <span data-ttu-id="43d83-121">在**签入 gpo 时记录更改的用途：** 任何审阅者都可以比较 GPO 的版本以查看二者之间的特定更改。</span><span class="sxs-lookup"><span data-stu-id="43d83-121">**Document the purpose of changes when you check in GPOs:** Any Reviewer can compare versions of a GPO to see specific changes between the two.</span></span> <span data-ttu-id="43d83-122">记录这些特定的更改不会增加任何价值。</span><span class="sxs-lookup"><span data-stu-id="43d83-122">Documenting those specific changes adds no value.</span></span> <span data-ttu-id="43d83-123">而是通过查看差异报告来记录更改的意图和用途，而不是记录审阅者可以查看哪些内容。</span><span class="sxs-lookup"><span data-stu-id="43d83-123">Instead, document the intent and purpose of a change instead of documenting what Reviewers can see by viewing difference reports.</span></span> <span data-ttu-id="43d83-124">版本注释应该为比较报告增加价值，并帮助审阅者了解编辑器更改 GPO 的原因。</span><span class="sxs-lookup"><span data-stu-id="43d83-124">Version comments should add value to the comparison report and help a Reviewer understand why the Editor changed the GPO.</span></span>

-   <span data-ttu-id="43d83-125">测试**环境中的测试 gpo：** 将 Gpo 部署到生产环境而不进行测试是危险的。</span><span class="sxs-lookup"><span data-stu-id="43d83-125">**Test GPOs in a test environment:** Deploying GPOs to the production environment without testing them is risky.</span></span> <span data-ttu-id="43d83-126">而是在测试林中的域中测试 Gpo，然后将 Gpo 导出到文件并将它们导入到生产林中的域。</span><span class="sxs-lookup"><span data-stu-id="43d83-126">Instead, test your GPOs in a domain in a test forest, and then export the GPOs to files and import them to a domain in a production forest.</span></span> <span data-ttu-id="43d83-127">此外，你还可以将 Gpo 链接到包含测试计算机和用户的组织单位。</span><span class="sxs-lookup"><span data-stu-id="43d83-127">Also, you can link GPOs to an organizational unit that contains test computers and users.</span></span> <span data-ttu-id="43d83-128">验证每个 GPO 在测试环境中正常工作，然后将 Gpo 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="43d83-128">Verify that each GPO functions correctly in the test environment and then deploy the GPOs to the production environment.</span></span>

### <span data-ttu-id="43d83-129">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="43d83-129">Additional references</span></span>

-   [<span data-ttu-id="43d83-130">高级组策略管理 4.0</span><span class="sxs-lookup"><span data-stu-id="43d83-130">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





