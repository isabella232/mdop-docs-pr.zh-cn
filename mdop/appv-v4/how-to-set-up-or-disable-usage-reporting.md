---
title: 如何设置或禁用使用情况报告
description: 如何设置或禁用使用情况报告
author: dansimp
ms.assetid: 8587003a-128d-4b5d-ac70-5b9eddddd3dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f8f6c44d4060581f1ebe435875bc2f105cb93d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801060"
---
# <span data-ttu-id="8652b-103">如何设置或禁用使用情况报告</span><span class="sxs-lookup"><span data-stu-id="8652b-103">How to Set Up or Disable Usage Reporting</span></span>


<span data-ttu-id="8652b-104">你可以使用应用程序虚拟化服务器管理控制台中的以下过程来指定要存储在数据库中的应用程序虚拟化系统使用信息的持续时间（以月为单位）。</span><span class="sxs-lookup"><span data-stu-id="8652b-104">You can use the following procedures in the Application Virtualization Server Management Console to specify the duration (in months) of Application Virtualization System usage information you want to store in the database.</span></span>

<span data-ttu-id="8652b-105">**注意** 若要存储使用信息，必须选中 "**提供程序管道**" 选项卡上的 "**日志使用信息**" 复选框。若要显示此选项卡，请右键单击 "**提供程序策略结果**" 窗格中的提供程序策略，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="8652b-105">**Note** To store usage information, you must select the **Log Usage Information** check box on the **Provider Pipeline** tab. To display this tab, right-click the provider policy in the **Provider Policies Results** pane and select **Properties**.</span></span>

 

**<span data-ttu-id="8652b-106">设置使用率报告</span><span class="sxs-lookup"><span data-stu-id="8652b-106">To set up usage reporting</span></span>**

1.  <span data-ttu-id="8652b-107">右键单击左窗格中的 "应用程序虚拟化系统" 节点，然后选择 "**系统选项**"。</span><span class="sxs-lookup"><span data-stu-id="8652b-107">Right-click the Application Virtualization System node in the left pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="8652b-108">选择 "**数据库**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8652b-108">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="8652b-109">选择 "**保留使用情况（月）** " 或 "**保留所有使用情况**" 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="8652b-109">Select the **Keep Usage For (Months)** or **Keep All Usage** radio button.</span></span>

4.  <span data-ttu-id="8652b-110">如果您选择以月为单位指定使用持续时间，请输入从1到120的数字（默认值为6个月）。</span><span class="sxs-lookup"><span data-stu-id="8652b-110">If you choose to specify usage duration in months, enter a number from 1 to 120 (default value is 6 months).</span></span> <span data-ttu-id="8652b-111">如果选择 "**保留所有用法**"，数据库将增长，直至达到指定的大小限制。</span><span class="sxs-lookup"><span data-stu-id="8652b-111">If you select **Keep All Usage**, the database will grow until it reaches the specified size limit.</span></span>

5.  <span data-ttu-id="8652b-112">单击**Apply** "应用 **" 或 "确定"**。</span><span class="sxs-lookup"><span data-stu-id="8652b-112">Click **Apply** or **OK**.</span></span>

**<span data-ttu-id="8652b-113">禁用使用率报告</span><span class="sxs-lookup"><span data-stu-id="8652b-113">To disable usage reporting</span></span>**

1.  <span data-ttu-id="8652b-114">单击 "**提供商策略**" 节点。</span><span class="sxs-lookup"><span data-stu-id="8652b-114">Click the **Provider Policies** node.</span></span>

2.  <span data-ttu-id="8652b-115">右键单击 "**提供程序策略**"，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="8652b-115">Right-click **Provider Policy** and select **Properties**.</span></span>

3.  <span data-ttu-id="8652b-116">选择 "**提供商管道**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8652b-116">Select the **Provider Pipeline** tab.</span></span>

4.  <span data-ttu-id="8652b-117">清除 "**日志使用情况信息**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="8652b-117">Clear the **Log Usage Information** check box.</span></span>

5.  <span data-ttu-id="8652b-118">单击**Apply** "应用 **" 或 "确定"**。</span><span class="sxs-lookup"><span data-stu-id="8652b-118">Click **Apply** or **OK**.</span></span>

## <span data-ttu-id="8652b-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="8652b-119">Related topics</span></span>


[<span data-ttu-id="8652b-120">如何在 Server Management Console 中自定义 Application Virtualization System</span><span class="sxs-lookup"><span data-stu-id="8652b-120">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[<span data-ttu-id="8652b-121">如何设置或禁用数据库大小</span><span class="sxs-lookup"><span data-stu-id="8652b-121">How to Set Up or Disable Database Size</span></span>](how-to-set-up-or-disable-database-size.md)

 

 





