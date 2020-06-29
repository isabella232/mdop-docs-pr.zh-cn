---
title: 在单独的组织单位中测试 GPO
description: 在单独的组织单位中测试 GPO
author: dansimp
ms.assetid: 9a9e6d22-74e6-41d8-ac2f-12a1b76ad5a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 509721fdd775c8669399549f6dcc29cb9ebaea2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801744"
---
# <span data-ttu-id="140ad-103">在单独的组织单位中测试 GPO</span><span class="sxs-lookup"><span data-stu-id="140ad-103">Test a GPO in a Separate Organizational Unit</span></span>


<span data-ttu-id="140ad-104">如果在部署到生产环境之前使用测试组织单位（OU）测试同一域内的组策略对象（Gpo），则必须具有访问测试 OU 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="140ad-104">If you use a testing organizational unit (OU) to test Group Policy Objects (GPOs) within the same domain before deployment to the production environment, you must have the necessary permissions to access the test OU.</span></span> <span data-ttu-id="140ad-105">使用测试 OU 是可选的。</span><span class="sxs-lookup"><span data-stu-id="140ad-105">Using a test OU is optional.</span></span>

**<span data-ttu-id="140ad-106">使用测试 OU</span><span class="sxs-lookup"><span data-stu-id="140ad-106">To use a test OU</span></span>**

1.  <span data-ttu-id="140ad-107">虽然已签出 GPO 进行编辑，但在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略" 对象**。</span><span class="sxs-lookup"><span data-stu-id="140ad-107">Although you have the GPO checked out for editing, in the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you are managing GPOs.</span></span>

2.  <span data-ttu-id="140ad-108">单击要测试的 GPO 的签出副本。</span><span class="sxs-lookup"><span data-stu-id="140ad-108">Click the checked out copy of the GPO to be tested.</span></span> <span data-ttu-id="140ad-109">名称前面将显示**\ [AGPM \]**。</span><span class="sxs-lookup"><span data-stu-id="140ad-109">The name will be preceded by **\[AGPM\]**.</span></span> <span data-ttu-id="140ad-110">（如果未列出，请单击 "**操作**"，然后单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="140ad-110">(If it is not listed, click **Action**, then **Refresh**.</span></span> <span data-ttu-id="140ad-111">按字母顺序对名称进行排序， **\ [AGPM \]** gpo 通常会显示在列表顶部。）</span><span class="sxs-lookup"><span data-stu-id="140ad-111">Sort the names alphabetically, and **\[AGPM\]** GPOs will typically appear at the top of the list.)</span></span>

3.  <span data-ttu-id="140ad-112">将 GPO 拖动到测试 OU。</span><span class="sxs-lookup"><span data-stu-id="140ad-112">Drag the GPO to the test OU.</span></span>

4.  <span data-ttu-id="140ad-113">在询问是否在测试 OU 中创建 GPO 链接的对话框中单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="140ad-113">Click **OK** in the dialog box that asks whether to create a link to the GPO in the test OU.</span></span>

### <span data-ttu-id="140ad-114">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="140ad-114">Additional considerations</span></span>

-   <span data-ttu-id="140ad-115">测试完成后，在 GPO 中签入将自动删除指向已签出 GPO 的已签出副本的链接。</span><span class="sxs-lookup"><span data-stu-id="140ad-115">When testing is complete, checking in the GPO automatically deletes the link to the checked-out copy of the GPO.</span></span>

### <span data-ttu-id="140ad-116">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="140ad-116">Additional references</span></span>

-   [<span data-ttu-id="140ad-117">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="140ad-117">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





