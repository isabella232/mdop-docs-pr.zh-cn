---
title: 如何拒绝对应用程序的访问
description: 如何拒绝对应用程序的访问
author: dansimp
ms.assetid: 14f5e201-7265-462c-b738-57938dc3fc30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a89669ea8c6323023b585d6d58620cd203fc00
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801448"
---
# <span data-ttu-id="46f4e-103">如何拒绝对应用程序的访问</span><span class="sxs-lookup"><span data-stu-id="46f4e-103">How to Deny Access to an Application</span></span>


<span data-ttu-id="46f4e-104">用户必须位于应用程序的**访问权限**列表中才能加载和使用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="46f4e-104">Users must be in an application's **Access Permissions** list to load and use the application.</span></span> <span data-ttu-id="46f4e-105">尽管应用程序虚拟化服务器管理控制台不支持显式拒绝用户组对应用程序的访问，但你可以从应用程序的属性中删除用户组来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="46f4e-105">Although the Application Virtualization Server Management Console does not support explicitly denying a user group access to an application, you can remove the user groups from an application’s properties to achieve this.</span></span>

**<span data-ttu-id="46f4e-106">拒绝访问应用程序</span><span class="sxs-lookup"><span data-stu-id="46f4e-106">To deny access to an application</span></span>**

1.  <span data-ttu-id="46f4e-107">对于现有应用程序，请单击左窗格中的 "**应用程序**" 节点。</span><span class="sxs-lookup"><span data-stu-id="46f4e-107">For an existing application, click the **Applications** node in the left pane.</span></span>

2.  <span data-ttu-id="46f4e-108">右键单击右窗格中的应用程序，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="46f4e-108">Right-click an application in the right pane, and choose **Properties**.</span></span> <span data-ttu-id="46f4e-109">然后选择 "**访问权限**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="46f4e-109">Then select the **Access Permissions** tab.</span></span>

3.  <span data-ttu-id="46f4e-110">若要删除用户组的访问权限，请突出显示 "用户" 组，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="46f4e-110">To remove access for a user group, highlight the user group and click **Remove**.</span></span>

4.  <span data-ttu-id="46f4e-111">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46f4e-111">Click **OK**.</span></span>

    <span data-ttu-id="46f4e-112">**注意** 若要控制对应用程序的访问，您还可以限制应用程序许可证。</span><span class="sxs-lookup"><span data-stu-id="46f4e-112">**Note** To control access to applications, you can also limit the application licenses.</span></span> <span data-ttu-id="46f4e-113">在 Active Directory 域服务中设置适当的用户组可提供授予和拒绝特定用户集访问权限的最简单方式。</span><span class="sxs-lookup"><span data-stu-id="46f4e-113">Setting up the proper user groups in Active Directory Domain Services provides the easiest way to grant and deny access to specific sets of users.</span></span>

     

## <span data-ttu-id="46f4e-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="46f4e-114">Related topics</span></span>


[<span data-ttu-id="46f4e-115">如何授予对应用程序的访问权限</span><span class="sxs-lookup"><span data-stu-id="46f4e-115">How to Grant Access to an Application</span></span>](how-to-grant-access-to-an-application.md)

[<span data-ttu-id="46f4e-116">如何在 Server Management Console 中管理应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="46f4e-116">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="46f4e-117">如何在 Server Management Console 中管理应用程序</span><span class="sxs-lookup"><span data-stu-id="46f4e-117">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





