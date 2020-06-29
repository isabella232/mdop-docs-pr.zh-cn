---
title: 如何使用命令行添加程序包
description: 如何使用命令行添加程序包
author: dansimp
ms.assetid: e75af49e-811a-407a-a7f0-6de8562b9188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab418017a075300f308d4ef4c6eceb4f623a05c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802962"
---
# <span data-ttu-id="335a0-103">如何使用命令行添加程序包</span><span class="sxs-lookup"><span data-stu-id="335a0-103">How to Add a Package by Using the Command Line</span></span>


<span data-ttu-id="335a0-104">以下过程列出了将虚拟应用程序包添加到特定计算机上的应用程序虚拟化（app-v）客户端所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="335a0-104">The following procedures list the steps that are necessary to add a virtual application package to the Application Virtualization (App-V) Client on a specific computer.</span></span>

**<span data-ttu-id="335a0-105">为特定用户添加虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="335a0-105">To add a virtual application package for a specific user</span></span>**

-   <span data-ttu-id="335a0-106">在要获取程序包的人员的用户帐户下运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="335a0-106">Run the following command under the user account of the person who is to get the package.</span></span> <span data-ttu-id="335a0-107">该命令为该用户添加和发布程序包。</span><span class="sxs-lookup"><span data-stu-id="335a0-107">The command adds and publishes the package for that user.</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

**<span data-ttu-id="335a0-108">为所有用户添加虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="335a0-108">To add a virtual application package for all users</span></span>**

-   <span data-ttu-id="335a0-109">在具有管理员权限的帐户下运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="335a0-109">Run the following command under an account that has administrator rights.</span></span> <span data-ttu-id="335a0-110">将为计算机上的所有用户添加和发布程序包。</span><span class="sxs-lookup"><span data-stu-id="335a0-110">The package is added and published for all users on the computer.</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

**<span data-ttu-id="335a0-111">使用电子软件分发系统添加程序包</span><span class="sxs-lookup"><span data-stu-id="335a0-111">To add a package using an electronic software distribution system</span></span>**

1.  <span data-ttu-id="335a0-112">如果您使用的电子软件分发系统在计算机的**系统**帐户下运行命令，则仅为该帐户发布程序包，除非您使用/GLOBAL 开关。</span><span class="sxs-lookup"><span data-stu-id="335a0-112">If you are using an electronic software distribution system that runs the commands under the computer’s **SYSTEM** account, the package is published for that account only, unless you use the /GLOBAL switch.</span></span> <span data-ttu-id="335a0-113">运行以下命令为计算机上的所有用户添加和发布程序包：</span><span class="sxs-lookup"><span data-stu-id="335a0-113">Run the following command to add and publish the package for all users on the computer:</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

2.  

    <span data-ttu-id="335a0-114">如果只想为特定用户添加程序包，请运行 "**添加程序包**" 命令，然后通过在每个人员的用户帐户下运行以下 "**发布包**" 命令，为每个用户显式发布程序包：</span><span class="sxs-lookup"><span data-stu-id="335a0-114">If you want to add the package for specific users only, run the **ADD PACKAGE** command, and then explicitly publish the package for each user by running the following **PUBLISH PACKAGE** command under each person’s user account:</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

    `SFTMIME PUBLISH PACKAGE:”name” /MANIFEST <manifest-path>`

    <span data-ttu-id="335a0-115">发布没有全局参数的程序包会授予用户对程序包中的应用程序的访问权限，并将清单中列出的文件类型和快捷方式发布到用户的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="335a0-115">Publishing the package without the GLOBAL parameter grants the user access to the applications in the package and publishes the file types and shortcuts that are listed in the manifest to the user’s profile.</span></span> <span data-ttu-id="335a0-116">所需权限包括 "管理文件类型关联" （**ManageTypes**）和 "发布快捷方式" （**PublishShortcut**）。</span><span class="sxs-lookup"><span data-stu-id="335a0-116">Permissions required are “Manage file type associations” (**ManageTypes**) and “Publish shortcuts” (**PublishShortcut**).</span></span>

## <span data-ttu-id="335a0-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="335a0-117">Related topics</span></span>


[<span data-ttu-id="335a0-118">如何使用命令行删除所有的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="335a0-118">How to Delete All Virtual Applications by Using the Command Line</span></span>](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

[<span data-ttu-id="335a0-119">如何使用命令行删除程序包</span><span class="sxs-lookup"><span data-stu-id="335a0-119">How to Remove a Package by Using the Command Line</span></span>](how-to-remove-a-package-by-using-the-command-line.md)

 

 





