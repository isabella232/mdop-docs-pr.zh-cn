---
title: 如何设置并发许可证组
description: 如何设置并发许可证组
author: dansimp
ms.assetid: 031abcf6-d8ed-49be-bddb-91b2c695d411
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e3035362cd645b6488b07408d6a9444f632fc88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801092"
---
# <span data-ttu-id="da683-103">如何设置并发许可证组</span><span class="sxs-lookup"><span data-stu-id="da683-103">How to Set Up a Concurrent License Group</span></span>


<span data-ttu-id="da683-104">你可以使用应用程序虚拟化服务器管理控制台中的以下过程设置并发许可证组。</span><span class="sxs-lookup"><span data-stu-id="da683-104">You can use the following procedure in the Application Virtualization Server Management Console to set up a concurrent license group.</span></span> <span data-ttu-id="da683-105">设置并发许可证组时，你可以将应用程序的访问限制为特定数量的并发用户。</span><span class="sxs-lookup"><span data-stu-id="da683-105">When you set up a concurrent license group, you can limit access to applications to a specific number of concurrent users.</span></span>

**<span data-ttu-id="da683-106">设置并发许可证组</span><span class="sxs-lookup"><span data-stu-id="da683-106">To set up a concurrent license group</span></span>**

1.  <span data-ttu-id="da683-107">在应用程序虚拟化服务器管理控制台的左窗格中，右键单击 "**应用程序许可证**" 节点。</span><span class="sxs-lookup"><span data-stu-id="da683-107">In the left pane of the Application Virtualization Server Management Console, right-click the **Application Licenses** node.</span></span>

2.  <span data-ttu-id="da683-108">选择 "**新的并发许可证**"。</span><span class="sxs-lookup"><span data-stu-id="da683-108">Select **New Concurrent License**.</span></span>

3.  <span data-ttu-id="da683-109">在 "**应用程序许可证组名称**" 字段中输入一个名称。</span><span class="sxs-lookup"><span data-stu-id="da683-109">Enter a name in the **Application License Group Name** field.</span></span>

4.  <span data-ttu-id="da683-110">在 "**许可证过期警告**" 字段中输入一个值（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="da683-110">Enter a value (in minutes) in the **License Expiration Warning** field.</span></span>

5.  <span data-ttu-id="da683-111">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da683-111">Click **Next**.</span></span>

6.  <span data-ttu-id="da683-112">在 "**许可证说明**" 字段中输入描述性文本。</span><span class="sxs-lookup"><span data-stu-id="da683-112">Enter descriptive text in the **License Description** field.</span></span>

7.  <span data-ttu-id="da683-113">在 "**并发许可证数量**" 字段中输入值。</span><span class="sxs-lookup"><span data-stu-id="da683-113">Enter a value in the **Concurrent License Quantity** field.</span></span>

8.  <span data-ttu-id="da683-114">选中 "**已启用**" 复选框以启用许可证。</span><span class="sxs-lookup"><span data-stu-id="da683-114">Select the **Enabled** check box to enable the license.</span></span>

9.  <span data-ttu-id="da683-115">选中 "**到期日期**" 复选框（如果要设置过期日期），请输入到期日期或使用日历实用工具选择日期。</span><span class="sxs-lookup"><span data-stu-id="da683-115">Select the **Expiration Date** check box (if you want to set an expiration date), and enter the expiration date or use the calendar utility to select a date.</span></span>

10. <span data-ttu-id="da683-116">如果需要将某个密钥与许可证相关联，请在 "**许可证密钥**" 字段中输入许可证密钥信息。</span><span class="sxs-lookup"><span data-stu-id="da683-116">If you need to associate a key with the license, enter the license key information in the **License Key** field.</span></span>

11. <span data-ttu-id="da683-117">单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="da683-117">Click **Finish**.</span></span>

## <span data-ttu-id="da683-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="da683-118">Related topics</span></span>


[<span data-ttu-id="da683-119">如何将应用程序与许可证组关联</span><span class="sxs-lookup"><span data-stu-id="da683-119">How to Associate an Application with a License Group</span></span>](how-to-associate-an-application-with-a-license-group.md)

[<span data-ttu-id="da683-120">如何创建应用程序许可证组</span><span class="sxs-lookup"><span data-stu-id="da683-120">How to Create an Application License Group</span></span>](how-to-create-an-application-license-group.md)

[<span data-ttu-id="da683-121">如何从许可证组中删除应用程序</span><span class="sxs-lookup"><span data-stu-id="da683-121">How to Remove an Application from a License Group</span></span>](how-to-remove-an-application-from-a-license-group.md)

[<span data-ttu-id="da683-122">如何设置命名的许可证组</span><span class="sxs-lookup"><span data-stu-id="da683-122">How to Set Up a Named License Group</span></span>](how-to-set-up-a-named-license-group.md)

[<span data-ttu-id="da683-123">如何设置无限制的许可证组</span><span class="sxs-lookup"><span data-stu-id="da683-123">How to Set Up an Unlimited License Group</span></span>](how-to-set-up-an-unlimited-license-group.md)

 

 





