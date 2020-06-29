---
title: 如何删除程序包版本
description: 如何删除程序包版本
author: dansimp
ms.assetid: a55adb9d-ffa6-4df3-a2d1-5e0c73c35e1b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc77e60ac9745033ae8f074ae71db0cb8517a202
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801467"
---
# <span data-ttu-id="db4bc-103">如何删除程序包版本</span><span class="sxs-lookup"><span data-stu-id="db4bc-103">How to Delete a Package Version</span></span>


<span data-ttu-id="db4bc-104">在应用程序虚拟化服务器管理控制台中，对于具有多个版本的程序包，你可以使用以下过程删除一个或多个版本，并继续流出其余版本的程序包。</span><span class="sxs-lookup"><span data-stu-id="db4bc-104">From the Application Virtualization Server Management Console, for a package that has multiple versions, you can use the following procedure to delete one or more versions and still stream the remaining versions of the package.</span></span> <span data-ttu-id="db4bc-105">你可能会执行此操作，以便更有效地管理服务器上的文件或删除过时的版本。</span><span class="sxs-lookup"><span data-stu-id="db4bc-105">You might do this to more effectively manage files on the server or to remove an obsolete version.</span></span>

<span data-ttu-id="db4bc-106">**注意** 当你选择删除一个版本时，将显示一个确认框，提醒你客户端计算机可能仍在使用它。</span><span class="sxs-lookup"><span data-stu-id="db4bc-106">**Note** When you choose to delete a version, a confirmation box reminds you that client computers might still be using it.</span></span> <span data-ttu-id="db4bc-107">在删除正在使用的版本之前，应建议用户退出并卸载任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="db4bc-107">You should advise users to exit and unload any applications before you remove a version that is in use.</span></span>

 

**<span data-ttu-id="db4bc-108">删除程序包版本</span><span class="sxs-lookup"><span data-stu-id="db4bc-108">To delete a package version</span></span>**

1.  <span data-ttu-id="db4bc-109">在应用程序虚拟化服务器管理控制台的左面板中，展开 "**程序包**"。</span><span class="sxs-lookup"><span data-stu-id="db4bc-109">In the left panel of the Application Virtualization Server Management Console, expand **Packages**.</span></span>

2.  <span data-ttu-id="db4bc-110">单击包含要删除的版本的程序包。</span><span class="sxs-lookup"><span data-stu-id="db4bc-110">Click the package that contains the version you want to delete.</span></span>

3.  <span data-ttu-id="db4bc-111">在中心窗格中，右键单击要删除的程序包版本，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="db4bc-111">In the center pane, right-click the version of the package you want to delete and choose **Delete**.</span></span>

4.  <span data-ttu-id="db4bc-112">阅读确认窗口，然后单击 **"是"** 完成操作。</span><span class="sxs-lookup"><span data-stu-id="db4bc-112">Read the confirmation window, and click **Yes** to complete the action.</span></span>

    <span data-ttu-id="db4bc-113">**注意** 如果你有用户处于断开连接的操作，则下次连接到服务器时，其应用程序将替换为新版本。</span><span class="sxs-lookup"><span data-stu-id="db4bc-113">**Note** If you have users in disconnected operation, their applications will be replaced with the new versions the next time they connect to the servers.</span></span> <span data-ttu-id="db4bc-114">在确保所有用户都已更新应用程序后，您可以删除旧版本。</span><span class="sxs-lookup"><span data-stu-id="db4bc-114">After you are sure all users have updated applications, you can delete old versions.</span></span>

     

## <span data-ttu-id="db4bc-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="db4bc-115">Related topics</span></span>


[<span data-ttu-id="db4bc-116">如何删除程序包</span><span class="sxs-lookup"><span data-stu-id="db4bc-116">How to Delete a Package</span></span>](how-to-delete-a-packageserver.md)

[<span data-ttu-id="db4bc-117">如何在 Server Management Console 中管理程序包</span><span class="sxs-lookup"><span data-stu-id="db4bc-117">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





