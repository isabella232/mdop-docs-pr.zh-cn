---
title: 如何使用管理控制台添加或删除管理员
description: 如何使用管理控制台添加或删除管理员
author: dansimp
ms.assetid: 7ff8c436-9d2e-446a-9ea2-bbab7e25bf21
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8fbc1a532a39c8688b99c28a2e23b713b348967c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798559"
---
# <span data-ttu-id="a3c7d-103">如何使用管理控制台添加或删除管理员</span><span class="sxs-lookup"><span data-stu-id="a3c7d-103">How to Add or Remove an Administrator by Using the Management Console</span></span>


<span data-ttu-id="a3c7d-104">使用以下过程在 Microsoft Application Virtualization （App-v）5.1 服务器上添加或删除管理员。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-104">Use the following procedures to add or remove an administrator on the Microsoft Application Virtualization (App-V) 5.1 server.</span></span>

**<span data-ttu-id="a3c7d-105">使用管理控制台添加管理员</span><span class="sxs-lookup"><span data-stu-id="a3c7d-105">To add an administrator using the Management Console</span></span>**

1.  <span data-ttu-id="a3c7d-106">打开 Microsoft Application Virtualization （App-v）5.1 管理控制台，然后在导航窗格中单击 "**管理员**"。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-106">Open the Microsoft Application Virtualization (App-V) 5.1 Management Console and click **Administrators** in the navigation pane.</span></span> <span data-ttu-id="a3c7d-107">导航窗格显示访问目录（AD）用户和组的列表，这些用户和组当前具有对 Microsoft Application Virtualization （App-v）5.1 服务器的管理访问权限。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-107">The navigation pane displays a list of Access Directory (AD) users and groups that currently have administrative access to the Microsoft Application Virtualization (App-V) 5.1 server.</span></span>

2.  <span data-ttu-id="a3c7d-108">若要添加新的管理员，请单击 "**添加管理员**" 在 " **Active Directory 名称**" 字段中键入要添加的管理员的名称。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-108">To add a new administrator, click **Add Administrator** Type the name of the administrator that you want to add in the **Active Directory Name** field.</span></span> <span data-ttu-id="a3c7d-109">确保提供相关联的用户帐户域名。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-109">Ensure you provide the associated user account domain name.</span></span> <span data-ttu-id="a3c7d-110">例如，**域**  \\  **用户名**。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-110">For example, **Domain** \\ **UserName**.</span></span>

3.  <span data-ttu-id="a3c7d-111">选择要添加的帐户，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-111">Select the account that you want to add and click **Add**.</span></span> <span data-ttu-id="a3c7d-112">新帐户将显示在服务器管理员列表中。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-112">The new account is displayed in the list of server administrators.</span></span>

**<span data-ttu-id="a3c7d-113">使用管理控制台删除管理员</span><span class="sxs-lookup"><span data-stu-id="a3c7d-113">To remove an administrator using the Management Console</span></span>**

1.  <span data-ttu-id="a3c7d-114">打开 Microsoft Application Virtualization （App-v）5.1 管理控制台，然后在导航窗格中单击 "**管理员**"。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-114">Open the Microsoft Application Virtualization (App-V) 5.1 Management Console and click **Administrators** in the navigation pane.</span></span> <span data-ttu-id="a3c7d-115">导航窗格显示了当前对 Microsoft Application Virtualization （App-v）5.1 服务器具有管理访问权限的 AD 用户和组的列表。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-115">The navigation pane displays a list of AD users and groups that currently have administrative access to the Microsoft Application Virtualization (App-V) 5.1 server.</span></span>

2.  <span data-ttu-id="a3c7d-116">右键单击要从管理员列表中删除的帐户，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-116">Right-click the account to be removed from the list of administrators and select **Remove**.</span></span>

    <span data-ttu-id="a3c7d-117">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="a3c7d-117">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a3c7d-118">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-118">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a3c7d-119">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="a3c7d-119">Got an App-V issue?</span></span>** <span data-ttu-id="a3c7d-120">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="a3c7d-120">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a3c7d-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="a3c7d-121">Related topics</span></span>


[<span data-ttu-id="a3c7d-122">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="a3c7d-122">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





