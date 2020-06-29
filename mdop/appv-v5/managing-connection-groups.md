---
title: 管理连接组
description: 管理连接组
author: dansimp
ms.assetid: 1a9c8f26-f421-4b70-b7e2-da8118e8198c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2e57b9dbe56072e6049e8fabef5705c374d022c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798331"
---
# <span data-ttu-id="ba98e-103">管理连接组</span><span class="sxs-lookup"><span data-stu-id="ba98e-103">Managing Connection Groups</span></span>


<span data-ttu-id="ba98e-104">连接组使程序包中的应用程序可以在虚拟环境中相互交互，而不是与系统其余部分隔离。</span><span class="sxs-lookup"><span data-stu-id="ba98e-104">Connection groups enable the applications within a package to interact with each other in the virtual environment, while remaining isolated from the rest of the system.</span></span> <span data-ttu-id="ba98e-105">通过使用连接组，管理员可以独立管理程序包，并且可以避免将同一应用程序多次添加到客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="ba98e-105">By using connection groups, administrators can manage packages independently and can avoid having to add the same application multiple times to a client computer.</span></span>

<span data-ttu-id="ba98e-106">**注意** 在以前版本的 App-v 5.0 中，连接组被称为 "动态套件合成"。</span><span class="sxs-lookup"><span data-stu-id="ba98e-106">**Note** In previous versions of App-V 5.0, connection groups were referred to as Dynamic Suite Composition.</span></span>

 

**<span data-ttu-id="ba98e-107">本主题内容：</span><span class="sxs-lookup"><span data-stu-id="ba98e-107">In this topic:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md)"><span data-ttu-id="ba98e-108">关于连接组虚拟环境</span><span class="sxs-lookup"><span data-stu-id="ba98e-108">About the Connection Group Virtual Environment</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="ba98e-109">描述连接组虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="ba98e-109">Describes the connection group virtual environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="about-the-connection-group-file.md" data-raw-source="[About the Connection Group File](about-the-connection-group-file.md)"><span data-ttu-id="ba98e-110">关于连接组文件</span><span class="sxs-lookup"><span data-stu-id="ba98e-110">About the Connection Group File</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="ba98e-111">描述连接组文件。</span><span class="sxs-lookup"><span data-stu-id="ba98e-111">Describes the connection group file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-create-a-connection-group.md" data-raw-source="[How to Create a Connection Group](how-to-create-a-connection-group.md)"><span data-ttu-id="ba98e-112">如何创建连接组</span><span class="sxs-lookup"><span data-stu-id="ba98e-112">How to Create a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="ba98e-113">介绍如何创建新的连接组。</span><span class="sxs-lookup"><span data-stu-id="ba98e-113">Explains how to create a new connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)"><span data-ttu-id="ba98e-114">如何创建与用户发布和全局发布的程序包的连接组</span><span class="sxs-lookup"><span data-stu-id="ba98e-114">How to Create a Connection Group with User-Published and Globally Published Packages</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="ba98e-115">介绍如何创建新的连接组，其中包含发布给用户并全局发布的程序包的混合。</span><span class="sxs-lookup"><span data-stu-id="ba98e-115">Explains how to create a new connection group that contains a mix of packages that are published to the user and published globally.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-delete-a-connection-group.md" data-raw-source="[How to Delete a Connection Group](how-to-delete-a-connection-group.md)"><span data-ttu-id="ba98e-116">如何删除连接组</span><span class="sxs-lookup"><span data-stu-id="ba98e-116">How to Delete a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="ba98e-117">介绍如何删除连接组。</span><span class="sxs-lookup"><span data-stu-id="ba98e-117">Explains how to delete a connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-publish-a-connection-group.md" data-raw-source="[How to Publish a Connection Group](how-to-publish-a-connection-group.md)"><span data-ttu-id="ba98e-118">如何发布连接组</span><span class="sxs-lookup"><span data-stu-id="ba98e-118">How to Publish a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="ba98e-119">介绍如何发布连接组。</span><span class="sxs-lookup"><span data-stu-id="ba98e-119">Explains how to publish a connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="ba98e-120">App-v 5.0 连接组的其他资源</span><span class="sxs-lookup"><span data-stu-id="ba98e-120">Other resources for App-V 5.0 connection groups</span></span>


-   [<span data-ttu-id="ba98e-121">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="ba98e-121">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





