---
title: 将 GPO 导出到文件
description: 将 GPO 导出到文件
author: dansimp
ms.assetid: 0d01b1f7-a6a4-4d0d-9aa7-2d6f1ae93d9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4622930cb0e5b439649cc0445ae2b3d02d7d3224
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802783"
---
# <span data-ttu-id="5a64a-103">将 GPO 导出到文件</span><span class="sxs-lookup"><span data-stu-id="5a64a-103">Export a GPO to a File</span></span>


<span data-ttu-id="5a64a-104">你可以将受控制的组策略对象（GPO）导出到 CAB 文件，以便你可以将其复制到另一个林中的域，并将 GPO 导入到该域中的高级组策略管理（AGPM）中。</span><span class="sxs-lookup"><span data-stu-id="5a64a-104">You can export a controlled Group Policy Object (GPO) to a CAB file so that you can copy it to a domain in another forest and import the GPO into Advanced Group Policy Management (AGPM) in that domain.</span></span> <span data-ttu-id="5a64a-105">有关如何将 GPO 设置导入新的或现有 GPO 的信息，请参阅[从文件导入 gpo](import-a-gpo-from-a-file-ed.md)。</span><span class="sxs-lookup"><span data-stu-id="5a64a-105">For information about how to import GPO settings into a new or existing GPO, see [Import a GPO from a File](import-a-gpo-from-a-file-ed.md).</span></span>

<span data-ttu-id="5a64a-106">需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="5a64a-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span><span data-ttu-id="5a64a-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a64a-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="5a64a-108">将 GPO 导出到文件</span><span class="sxs-lookup"><span data-stu-id="5a64a-108">To export a GPO to a file</span></span>**

1.  <span data-ttu-id="5a64a-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="5a64a-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="5a64a-110">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="5a64a-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="5a64a-111">右键单击该 GPO，然后单击 "**导出到**"。</span><span class="sxs-lookup"><span data-stu-id="5a64a-111">Right-click the GPO, and then click **Export to**.</span></span>

4.  <span data-ttu-id="5a64a-112">输入要将 GPO 导出到的文件的文件名，然后单击 "**导出**"。</span><span class="sxs-lookup"><span data-stu-id="5a64a-112">Enter a file name for the file to which you want to export the GPO, and then click **Export**.</span></span> <span data-ttu-id="5a64a-113">如果文件不存在，则会创建该文件。</span><span class="sxs-lookup"><span data-stu-id="5a64a-113">If the file does not exist, it is created.</span></span> <span data-ttu-id="5a64a-114">如果已存在，将替换它。</span><span class="sxs-lookup"><span data-stu-id="5a64a-114">If it already exists, it is replaced.</span></span>

### <span data-ttu-id="5a64a-115">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="5a64a-115">Additional considerations</span></span>

-   <span data-ttu-id="5a64a-116">默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="5a64a-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="5a64a-117">具体而言，您必须具有**列表内容**、**阅读设置**和 gpo 的**导出 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="5a64a-117">Specifically, you must have **List Contents**, **Read Settings**, and **Export GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="5a64a-118">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="5a64a-118">Additional references</span></span>

-   [<span data-ttu-id="5a64a-119">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="5a64a-119">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





