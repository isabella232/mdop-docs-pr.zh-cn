---
title: 使用测试环境
description: 使用测试环境
author: dansimp
ms.assetid: 86295084-b39e-4040-bb3f-15c3c1e99b1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1264d9fe6f922a7e61bcd069581c7bd5e39b7787
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801736"
---
# <span data-ttu-id="5f26c-103">使用测试环境</span><span class="sxs-lookup"><span data-stu-id="5f26c-103">Use a Test Environment</span></span>


<span data-ttu-id="5f26c-104">如果在部署到生产环境之前使用测试组织单位（OU）测试组策略对象（Gpo），则必须具有访问测试 OU 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="5f26c-104">If you use a testing organizational unit (OU) to test Group Policy Objects (GPOs) before deployment to the production environment, you must have the necessary permissions to access the test OU.</span></span> <span data-ttu-id="5f26c-105">测试 OU 的使用是可选的。</span><span class="sxs-lookup"><span data-stu-id="5f26c-105">The use of a test OU is optional.</span></span>

**<span data-ttu-id="5f26c-106">使用测试 OU</span><span class="sxs-lookup"><span data-stu-id="5f26c-106">To use a test OU</span></span>**

1.  <span data-ttu-id="5f26c-107">当已签出 GPO 进行编辑时，请在**组策略管理控制台**中单击要在其中管理 gpo 的林和域中的 "**组策略" 对象**。</span><span class="sxs-lookup"><span data-stu-id="5f26c-107">While you have the GPO checked out for editing, in the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you are managing GPOs.</span></span>

2.  <span data-ttu-id="5f26c-108">单击要测试的 GPO 的签出副本。</span><span class="sxs-lookup"><span data-stu-id="5f26c-108">Click the checked out copy of the GPO to be tested.</span></span> <span data-ttu-id="5f26c-109">名称前面将显示**\ [已签出 \]**。</span><span class="sxs-lookup"><span data-stu-id="5f26c-109">The name will be preceded with **\[Checked Out\]**.</span></span> <span data-ttu-id="5f26c-110">（如果未列出，请单击 "**操作**"，然后单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="5f26c-110">(If it is not listed, click **Action**, then **Refresh**.</span></span> <span data-ttu-id="5f26c-111">按字母顺序对名称进行排序， **\ [签出的 \]** gpo 通常会显示在列表顶部。）</span><span class="sxs-lookup"><span data-stu-id="5f26c-111">Sort the names alphabetically, and **\[Checked Out\]** GPOs will typically appear at the top of the list.)</span></span>

3.  <span data-ttu-id="5f26c-112">将 GPO 拖放到测试 OU。</span><span class="sxs-lookup"><span data-stu-id="5f26c-112">Drag and drop the GPO to the test OU.</span></span>

4.  <span data-ttu-id="5f26c-113">在对话框中单击 **"确定"** ，询问是否在测试 OU 中创建指向 GPO 的链接。</span><span class="sxs-lookup"><span data-stu-id="5f26c-113">Click **OK** in the dialog box asking whether to create a link to the GPO in the test OU.</span></span>

### <span data-ttu-id="5f26c-114">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="5f26c-114">Additional considerations</span></span>

-   <span data-ttu-id="5f26c-115">测试完成后，在 GPO 中签入将自动删除指向已签出 GPO 的已签出副本的链接。</span><span class="sxs-lookup"><span data-stu-id="5f26c-115">When testing is complete, checking in the GPO automatically deletes the link to the checked-out copy of the GPO.</span></span>

### <span data-ttu-id="5f26c-116">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="5f26c-116">Additional references</span></span>

-   [<span data-ttu-id="5f26c-117">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="5f26c-117">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

 

 





