---
title: SFTMIME 命令引用
description: SFTMIME 命令引用
author: dansimp
ms.assetid: a4a69228-9dd3-4623-b773-899d03c0cf10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 47aac9110febaf3f349461d74fef840326b1c6e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798753"
---
# <span data-ttu-id="b280a-103">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="b280a-103">SFTMIME Command Reference</span></span>


<span data-ttu-id="b280a-104">SFTMIME 是应用程序虚拟化（app-v）使用的命令行界面，可让你管理许多客户端配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="b280a-104">SFTMIME is a command-line interface used by Application Virtualization (App-V) that enables you to manage many client configuration details.</span></span> <span data-ttu-id="b280a-105">本部分包含所有命令及其参数，以及每个命令的简短说明。</span><span class="sxs-lookup"><span data-stu-id="b280a-105">This section contains all the commands and their parameters, with a brief description of each.</span></span>

**<span data-ttu-id="b280a-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="b280a-106">Important</span></span>**  
-   <span data-ttu-id="b280a-107">所有反斜杠字符都必须使用前面的反斜杠进行转义，否则将无法正确分析路径。</span><span class="sxs-lookup"><span data-stu-id="b280a-107">All backslash characters must be escaped using a preceding backslash, or the path will not be parsed correctly.</span></span>

-   <span data-ttu-id="b280a-108">如果使用调用程序通过**CreateProcess**调用 SFTMIME，则必须确保第一个参数是 sftmime.exe 的路径。</span><span class="sxs-lookup"><span data-stu-id="b280a-108">If you are using a calling program to invoke SFTMIME with **CreateProcess**, you must ensure that the first parameter is the path to sftmime.exe.</span></span>

-   <span data-ttu-id="b280a-109">SFTMIME**查询 OBJ**命令的输出无法输送到**findstr**命令以搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="b280a-109">The output of the SFTMIME **QUERY OBJ** command cannot be piped to the **findstr** command to search for a string.</span></span>

-   <span data-ttu-id="b280a-110">使用**全局**开关需要本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="b280a-110">Use of the **GLOBAL** switch requires local administrator rights.</span></span>

-   <span data-ttu-id="b280a-111">使用短路径和相对路径可能导致意外结果，应避免使用。</span><span class="sxs-lookup"><span data-stu-id="b280a-111">Use of short paths and relative paths can lead to unexpected results and should be avoided.</span></span> <span data-ttu-id="b280a-112">始终使用完整路径。</span><span class="sxs-lookup"><span data-stu-id="b280a-112">Always use full paths.</span></span>

 

## <span data-ttu-id="b280a-113">本部分内容</span><span class="sxs-lookup"><span data-stu-id="b280a-113">In This Section</span></span>


[<span data-ttu-id="b280a-114">ADD APP</span><span class="sxs-lookup"><span data-stu-id="b280a-114">ADD APP</span></span>](add-app.md)

[<span data-ttu-id="b280a-115">ADD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b280a-115">ADD PACKAGE</span></span>](add-package.md)

[<span data-ttu-id="b280a-116">ADD SERVER</span><span class="sxs-lookup"><span data-stu-id="b280a-116">ADD SERVER</span></span>](add-server.md)

[<span data-ttu-id="b280a-117">ADD TYPE</span><span class="sxs-lookup"><span data-stu-id="b280a-117">ADD TYPE</span></span>](add-type.md)

[<span data-ttu-id="b280a-118">CLEAR APP</span><span class="sxs-lookup"><span data-stu-id="b280a-118">CLEAR APP</span></span>](clear-app.md)

[<span data-ttu-id="b280a-119">CLEAR OBJ</span><span class="sxs-lookup"><span data-stu-id="b280a-119">CLEAR OBJ</span></span>](clear-obj.md)

[<span data-ttu-id="b280a-120">CONFIGURE APP</span><span class="sxs-lookup"><span data-stu-id="b280a-120">CONFIGURE APP</span></span>](configure-app.md)

[<span data-ttu-id="b280a-121">CONFIGURE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b280a-121">CONFIGURE PACKAGE</span></span>](configure-package.md)

[<span data-ttu-id="b280a-122">CONFIGURE SERVER</span><span class="sxs-lookup"><span data-stu-id="b280a-122">CONFIGURE SERVER</span></span>](configure-server.md)

[<span data-ttu-id="b280a-123">CONFIGURE TYPE</span><span class="sxs-lookup"><span data-stu-id="b280a-123">CONFIGURE TYPE</span></span>](configure-type.md)

[<span data-ttu-id="b280a-124">DELETE APP</span><span class="sxs-lookup"><span data-stu-id="b280a-124">DELETE APP</span></span>](delete-app.md)

[<span data-ttu-id="b280a-125">DELETE OBJ</span><span class="sxs-lookup"><span data-stu-id="b280a-125">DELETE OBJ</span></span>](delete-obj.md)

[<span data-ttu-id="b280a-126">DELETE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b280a-126">DELETE PACKAGE</span></span>](delete-package.md)

[<span data-ttu-id="b280a-127">DELETE SERVER</span><span class="sxs-lookup"><span data-stu-id="b280a-127">DELETE SERVER</span></span>](delete-server.md)

[<span data-ttu-id="b280a-128">DELETE TYPE</span><span class="sxs-lookup"><span data-stu-id="b280a-128">DELETE TYPE</span></span>](delete-type.md)

[<span data-ttu-id="b280a-129">HELP</span><span class="sxs-lookup"><span data-stu-id="b280a-129">HELP</span></span>](help.md)

[<span data-ttu-id="b280a-130">LOAD APP</span><span class="sxs-lookup"><span data-stu-id="b280a-130">LOAD APP</span></span>](load-app.md)

[<span data-ttu-id="b280a-131">LOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b280a-131">LOAD PACKAGE</span></span>](load-package.md)

[<span data-ttu-id="b280a-132">LOCK APP</span><span class="sxs-lookup"><span data-stu-id="b280a-132">LOCK APP</span></span>](lock-app.md)

[<span data-ttu-id="b280a-133">PUBLISH APP</span><span class="sxs-lookup"><span data-stu-id="b280a-133">PUBLISH APP</span></span>](publish-app.md)

[<span data-ttu-id="b280a-134">PUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b280a-134">PUBLISH PACKAGE</span></span>](publish-package.md)

[<span data-ttu-id="b280a-135">QUERY OBJ</span><span class="sxs-lookup"><span data-stu-id="b280a-135">QUERY OBJ</span></span>](query-obj.md)

[<span data-ttu-id="b280a-136">REFRESH SERVER</span><span class="sxs-lookup"><span data-stu-id="b280a-136">REFRESH SERVER</span></span>](refresh-server.md)

[<span data-ttu-id="b280a-137">REPAIR APP</span><span class="sxs-lookup"><span data-stu-id="b280a-137">REPAIR APP</span></span>](repair-app.md)

[<span data-ttu-id="b280a-138">UNLOAD APP</span><span class="sxs-lookup"><span data-stu-id="b280a-138">UNLOAD APP</span></span>](unload-app.md)

[<span data-ttu-id="b280a-139">UNLOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b280a-139">UNLOAD PACKAGE</span></span>](unload-package.md)

[<span data-ttu-id="b280a-140">UNLOCK APP</span><span class="sxs-lookup"><span data-stu-id="b280a-140">UNLOCK APP</span></span>](unlock-app.md)

[<span data-ttu-id="b280a-141">UNPUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b280a-141">UNPUBLISH PACKAGE</span></span>](unpublish-package.md)

 

 





