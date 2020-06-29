---
title: 如何使用命令行删除所有的虚拟应用程序
description: 如何使用命令行删除所有的虚拟应用程序
author: dansimp
ms.assetid: bfe13b5c-825a-4eb1-a979-6c4b8d8b2a9c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 55c809df31fa5c19f2f1a56c143d492b092156c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801456"
---
# <span data-ttu-id="2bc45-103">如何使用命令行删除所有的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="2bc45-103">How to Delete All Virtual Applications by Using the Command Line</span></span>


<span data-ttu-id="2bc45-104">你可以使用以下过程从特定计算机中删除所有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc45-104">You can use the following procedure to delete all virtual applications from a specific computer.</span></span>

<span data-ttu-id="2bc45-105">**注意** 从程序包中删除所有应用程序时，应用程序虚拟化（app-v）客户端也会删除该程序包。</span><span class="sxs-lookup"><span data-stu-id="2bc45-105">**Note** When all applications are deleted from a package, the Application Virtualization (App-V) Client also deletes the package.</span></span>

 

**<span data-ttu-id="2bc45-106">删除所有应用程序</span><span class="sxs-lookup"><span data-stu-id="2bc45-106">To delete all applications</span></span>**

-   <span data-ttu-id="2bc45-107">运行以下命令以删除运行该命令的用户帐户的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc45-107">Run the following command to delete all applications for the user account under which the command is run.</span></span> <span data-ttu-id="2bc45-108">如果使用可选的/GLOBAL 开关运行命令，使用具有管理权限的帐户，将删除所有用户的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc45-108">If you run the command with the optional /GLOBAL switch, using an account with administrative rights, all applications are deleted for all users.</span></span>

    `SFTMIME DELETE OBJ:APP [/GLOBAL]`

    <span data-ttu-id="2bc45-109">**注意** 从程序包中删除所有应用程序时，应用程序虚拟化（app-v）客户端也会删除该程序包。</span><span class="sxs-lookup"><span data-stu-id="2bc45-109">**Note** When all applications are deleted from a package, the Application Virtualization (App-V) Client also deletes the package.</span></span>

     

## <span data-ttu-id="2bc45-110">相关主题</span><span class="sxs-lookup"><span data-stu-id="2bc45-110">Related topics</span></span>


[<span data-ttu-id="2bc45-111">如何使用命令行添加程序包</span><span class="sxs-lookup"><span data-stu-id="2bc45-111">How to Add a Package by Using the Command Line</span></span>](how-to-add-a-package-by-using-the-command-line.md)

[<span data-ttu-id="2bc45-112">如何使用命令行删除程序包</span><span class="sxs-lookup"><span data-stu-id="2bc45-112">How to Remove a Package by Using the Command Line</span></span>](how-to-remove-a-package-by-using-the-command-line.md)

 

 





