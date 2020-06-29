---
title: 如何使用命令行删除程序包
description: 如何使用命令行删除程序包
author: dansimp
ms.assetid: 47697ec7-20e5-4258-8865-a0a710d41d5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b282830802f34bfb0670ddfdb8e2852d3559e3f7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801171"
---
# <span data-ttu-id="2efde-103">如何使用命令行删除程序包</span><span class="sxs-lookup"><span data-stu-id="2efde-103">How to Remove a Package by Using the Command Line</span></span>


<span data-ttu-id="2efde-104">你可以使用以下命令行过程从特定计算机上的应用程序虚拟化（app-v）客户端中删除虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="2efde-104">You can use the following command-line procedures to delete a virtual application package from the Application Virtualization (App-V) Client on a specific computer.</span></span>

**<span data-ttu-id="2efde-105">删除所有用户的虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="2efde-105">To delete a virtual application package for all users</span></span>**

-   <span data-ttu-id="2efde-106">如果以前通过使用/GLOBAL 开关为所有用户添加了程序包，请使用以下命令删除程序包以及全局文件类型和快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2efde-106">If the package was previously added for all users by using the /GLOBAL switch, use the following command to delete the package and the global file types and shortcuts.</span></span> <span data-ttu-id="2efde-107">需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="2efde-107">Administrator rights are required.</span></span> <span data-ttu-id="2efde-108">在此情况下不需要/GLOBAL 开关，因为该命令始终执行程序包全局删除。</span><span class="sxs-lookup"><span data-stu-id="2efde-108">The /GLOBAL switch is not needed in this case because the command always performs a global deletion of the package.</span></span>

    `SFTMIME DELETE PACKAGE:”name”`

**<span data-ttu-id="2efde-109">删除之前为单个用户添加的程序包</span><span class="sxs-lookup"><span data-stu-id="2efde-109">To delete a package previously added for individual users</span></span>**

1.  <span data-ttu-id="2efde-110">如果以前为单个用户添加了该程序包，则有多个选项。</span><span class="sxs-lookup"><span data-stu-id="2efde-110">If the package was previously added for individual users, you have several options.</span></span>

    <span data-ttu-id="2efde-111">在发布程序包的每个人的用户帐户下运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2efde-111">Run the following command once under the user account of each person the package was published to.</span></span> <span data-ttu-id="2efde-112">这将在用户漫游到另一台计算机时拒绝用户访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="2efde-112">This denies the user access to the applications if they roam to another computer.</span></span> <span data-ttu-id="2efde-113">它将从配置文件中删除特定用户的设置、快捷方式和文件类型，并在用户的上下文中停止后台加载。</span><span class="sxs-lookup"><span data-stu-id="2efde-113">It deletes the specific user’s settings, shortcuts, and file types from the profile, and it stops background loads under the user’s context.</span></span>

    `SFTMIME UNPUBLISH PACKAGE:”name”`

2.  <span data-ttu-id="2efde-114">或者，在发布程序包的每个人的用户帐户下运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2efde-114">Alternatively, run the following command under the user account of each person the package was published to.</span></span>

    `SFTMIME UNPUBLISH PACKAGE:”name”`

    <span data-ttu-id="2efde-115">然后对程序包运行此命令。</span><span class="sxs-lookup"><span data-stu-id="2efde-115">Then run this command for the package.</span></span>

    `SFTMIME DELETE PACKAGE:”name”`

    <span data-ttu-id="2efde-116">这将完全删除程序包，并从其配置文件中删除所有用户设置、快捷方式和文件类型。</span><span class="sxs-lookup"><span data-stu-id="2efde-116">This completely removes the package, and it deletes all user settings, shortcuts, and file types from their profiles.</span></span> <span data-ttu-id="2efde-117">如果随后重新添加程序包，用户将必须再次指定其设置。</span><span class="sxs-lookup"><span data-stu-id="2efde-117">If the package is subsequently re-added, the users will have to specify their settings again.</span></span> <span data-ttu-id="2efde-118">若要运行此命令，只需 "删除应用程序" （**DeleteApp**）权限。</span><span class="sxs-lookup"><span data-stu-id="2efde-118">Only “Delete applications” (**DeleteApp**) permission is needed to run this command.</span></span>

3.  <span data-ttu-id="2efde-119">第三种方法是，无需使用**取消发布程序包**命令即可运行 "**删除包**" 命令。</span><span class="sxs-lookup"><span data-stu-id="2efde-119">As a third alternative, you can simply run the **DELETE PACKAGE** command without using the **UNPUBLISH PACKAGE** command.</span></span> <span data-ttu-id="2efde-120">在这种情况下，每个用户的文件类型和快捷方式均为隐藏而不是删除，并且用户设置已保留。</span><span class="sxs-lookup"><span data-stu-id="2efde-120">In this case, file types and shortcuts for each user are hidden rather than deleted, and the user settings are retained.</span></span> <span data-ttu-id="2efde-121">这意味着，如果随后为用户重新添加程序包，则会还原文件类型和快捷方式，并重新应用用户设置。</span><span class="sxs-lookup"><span data-stu-id="2efde-121">This means that if the package is subsequently re-added for the user, the file types and shortcuts are restored, and the user settings are reapplied.</span></span>

## <span data-ttu-id="2efde-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="2efde-122">Related topics</span></span>


[<span data-ttu-id="2efde-123">如何使用命令行添加程序包</span><span class="sxs-lookup"><span data-stu-id="2efde-123">How to Add a Package by Using the Command Line</span></span>](how-to-add-a-package-by-using-the-command-line.md)

[<span data-ttu-id="2efde-124">如何使用命令行删除所有的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="2efde-124">How to Delete All Virtual Applications by Using the Command Line</span></span>](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

 

 





