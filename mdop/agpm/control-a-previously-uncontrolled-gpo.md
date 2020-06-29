---
title: 控制以前不受控的 GPO
description: 控制以前不受控的 GPO
author: dansimp
ms.assetid: 452689a9-4e32-4e3b-8208-56353a82bf36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d7349b16b326a49b701efae5379c313bde0964f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801996"
---
# <span data-ttu-id="94f7d-103">控制以前不受控的 GPO</span><span class="sxs-lookup"><span data-stu-id="94f7d-103">Control a Previously Uncontrolled GPO</span></span>


<span data-ttu-id="94f7d-104">若要使用高级组策略管理（AGPM）为组策略对象（GPO）提供更改控制，必须首先使用 AGPM 控制 GPO。</span><span class="sxs-lookup"><span data-stu-id="94f7d-104">To use Advanced Group Policy Management (AGPM) to provide change control for a Group Policy object (GPO), you must first control the GPO with AGPM.</span></span>

<span data-ttu-id="94f7d-105">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="94f7d-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="94f7d-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="94f7d-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="94f7d-107">控制以前的不受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="94f7d-107">To control a previously uncontrolled GPO</span></span>**

1.  <span data-ttu-id="94f7d-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="94f7d-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="94f7d-109">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "未**控制**" 选项卡以显示非受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="94f7d-109">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="94f7d-110">右键单击要通过 AGPM 控制的 GPO，然后单击 "**控制**"。</span><span class="sxs-lookup"><span data-stu-id="94f7d-110">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="94f7d-111">键入要在 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="94f7d-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="94f7d-112">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="94f7d-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94f7d-113">GPO 将从 "不可**控制**" 选项卡上的列表中删除，并添加到 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="94f7d-113">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Controlled** tab.</span></span>

### <span data-ttu-id="94f7d-114">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="94f7d-114">Additional considerations</span></span>

-   <span data-ttu-id="94f7d-115">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="94f7d-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="94f7d-116">具体而言，您必须拥有**列表内容**并为域**创建 GPO**权限。</span><span class="sxs-lookup"><span data-stu-id="94f7d-116">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="94f7d-117">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="94f7d-117">Additional references</span></span>

-   [<span data-ttu-id="94f7d-118">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="94f7d-118">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

 

 





