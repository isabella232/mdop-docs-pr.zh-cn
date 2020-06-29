---
title: 限制存储的 GPO 版本
description: 限制存储的 GPO 版本
author: dansimp
ms.assetid: da14edc5-0c36-4c54-b122-861c86b99eb1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20a3ae60cc330c27cbd19e943ba7f071d4ec60b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802691"
---
# <span data-ttu-id="a4f75-103">限制存储的 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="a4f75-103">Limit the GPO Versions Stored</span></span>


<span data-ttu-id="a4f75-104">默认情况下，每个受控制的组策略对象（GPO）的所有版本均保留在 AGPM 服务器上的存档中。</span><span class="sxs-lookup"><span data-stu-id="a4f75-104">By default, all versions of every controlled Group Policy Object (GPO) are retained in the archive on the AGPM Server.</span></span> <span data-ttu-id="a4f75-105">但是，你可以限制每个 GPO 的保留版本数，并在超过该限制时删除较早的版本。</span><span class="sxs-lookup"><span data-stu-id="a4f75-105">However, you can limit the number of versions retained for each GPO and delete older versions when that limit is exceeded.</span></span> <span data-ttu-id="a4f75-106">删除 GPO 版本后，该版本的记录将保留在 GPO 的历史记录中，但 GPO 版本本身将从存档中删除。</span><span class="sxs-lookup"><span data-stu-id="a4f75-106">When GPO versions are deleted, a record of the version remains in the history of the GPO, but the GPO version itself is deleted from the archive.</span></span>

<span data-ttu-id="a4f75-107">需要具有 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必需权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="a4f75-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="a4f75-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4f75-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="a4f75-109">限制存储的 GPO 版本数</span><span class="sxs-lookup"><span data-stu-id="a4f75-109">To limit the number of GPO versions stored</span></span>**

1.  <span data-ttu-id="a4f75-110">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="a4f75-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="a4f75-111">在 "详细信息" 窗格中，单击 " **AGPM 服务器**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a4f75-111">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="a4f75-112">从 "存档" 复选框中选择 "**删除每个 gpo 的旧版本**" 复选框，然后键入要为每个 gpo 存储的最大 gpo 版本数，不包括当前版本。</span><span class="sxs-lookup"><span data-stu-id="a4f75-112">Select the **Delete old versions of each GPO from the archive** check box, and type the maximum number of GPO versions to store for each GPO, not including the current version.</span></span> <span data-ttu-id="a4f75-113">若要仅保留当前版本，请输入0。</span><span class="sxs-lookup"><span data-stu-id="a4f75-113">To retain only the current version, enter 0.</span></span> <span data-ttu-id="a4f75-114">最大值不得大于999。</span><span class="sxs-lookup"><span data-stu-id="a4f75-114">The maximum must be no greater than 999.</span></span>

    <span data-ttu-id="a4f75-115">**重要提示** 仅在 "**历史记录**" 窗口的 "**唯一版本**" 选项卡上显示的 GPO 版本将计为 "限制"。</span><span class="sxs-lookup"><span data-stu-id="a4f75-115">**Important** Only GPO versions displayed on the **Unique Versions** tab of the **History** window count toward the limit.</span></span>

     

4.  <span data-ttu-id="a4f75-116">单击 "**应用**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a4f75-116">Click the **Apply** button.</span></span>

### <span data-ttu-id="a4f75-117">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="a4f75-117">Additional considerations</span></span>

-   <span data-ttu-id="a4f75-118">默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="a4f75-118">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="a4f75-119">具体而言，您必须具有域的 "**列表内容**" 和 "**修改选项**" 权限。</span><span class="sxs-lookup"><span data-stu-id="a4f75-119">Specifically, you must have **List Contents** and **Modify Options** permissions for the domain.</span></span>

-   <span data-ttu-id="a4f75-120">你可以通过将 GPO 版本标记在历史记录中，将其标记为不符合删除条件，从而阻止删除 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="a4f75-120">You can prevent a GPO version from being deleted by marking it in the history as ineligible for deletion.</span></span> <span data-ttu-id="a4f75-121">若要执行此操作，请右键单击 GPO 历史记录中的版本，然后单击 "不**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a4f75-121">To do so, right-click the version in the history of the GPO and click **Do Not Delete**.</span></span>

### <span data-ttu-id="a4f75-122">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="a4f75-122">Additional references</span></span>

-   [<span data-ttu-id="a4f75-123">管理存档</span><span class="sxs-lookup"><span data-stu-id="a4f75-123">Managing the Archive</span></span>](managing-the-archive.md)

 

 





