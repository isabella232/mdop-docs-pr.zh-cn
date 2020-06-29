---
title: 关于连接组虚拟环境
description: 关于连接组虚拟环境
author: dansimp
ms.assetid: 535fa640-cbd9-425e-8437-94650a70c264
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bd93c9e7acbf7bbf3f9da506d5d95b8df09e1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798663"
---
# <span data-ttu-id="991c7-103">关于连接组虚拟环境</span><span class="sxs-lookup"><span data-stu-id="991c7-103">About the Connection Group Virtual Environment</span></span>


**<span data-ttu-id="991c7-104">本主题内容：</span><span class="sxs-lookup"><span data-stu-id="991c7-104">In this topic:</span></span>**

-   [<span data-ttu-id="991c7-105">如何确定程序包优先级</span><span class="sxs-lookup"><span data-stu-id="991c7-105">How package priority is determined</span></span>](#bkmk-pkg-priority-deter)

-   [<span data-ttu-id="991c7-106">将相同的包路径合并到连接组中的一个虚拟目录中</span><span class="sxs-lookup"><span data-stu-id="991c7-106">Merging identical package paths into one virtual directory in connection groups</span></span>](#bkmk-merged-root-ve-exp)

## <a href="" id="bkmk-pkg-priority-deter"></a><span data-ttu-id="991c7-107">如何确定程序包优先级</span><span class="sxs-lookup"><span data-stu-id="991c7-107">How package priority is determined</span></span>


<span data-ttu-id="991c7-108">虚拟环境及其当前状态与连接组关联，而不是与单个程序包关联。</span><span class="sxs-lookup"><span data-stu-id="991c7-108">The virtual environment and its current state are associated with the connection group, not with the individual packages.</span></span> <span data-ttu-id="991c7-109">如果从连接组中删除了 App-v 包，则作为连接组的一部分存在的状态将不会与程序包一起迁移。</span><span class="sxs-lookup"><span data-stu-id="991c7-109">If an App-V package is removed from the connection group, the state that existed as part of the connection group will not migrate with the package.</span></span>

<span data-ttu-id="991c7-110">如果同一程序包是两个不同连接组的一部分，则必须指明应使用的连接组 App-v。</span><span class="sxs-lookup"><span data-stu-id="991c7-110">If the same package is a part of two different connection groups, you have to indicate which connection group App-V should use.</span></span> <span data-ttu-id="991c7-111">例如，你可能在连接组中有两个程序包，每个程序包都定义相同的注册表 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="991c7-111">For example, you might have two packages in a connection group that each define the same registry DWORD value.</span></span>

<span data-ttu-id="991c7-112">所使用的连接组基于**AppConnectionGroup** XML 文档中程序包出现的顺序：</span><span class="sxs-lookup"><span data-stu-id="991c7-112">The connection group that is used is based on the order in which a package appears inside the **AppConnectionGroup** XML document:</span></span>

-   <span data-ttu-id="991c7-113">第一个程序包具有最高优先级。</span><span class="sxs-lookup"><span data-stu-id="991c7-113">The first package has the highest precedence.</span></span>

-   <span data-ttu-id="991c7-114">第二个程序包具有最高优先级。</span><span class="sxs-lookup"><span data-stu-id="991c7-114">The second package has the second highest precedence.</span></span>

<span data-ttu-id="991c7-115">请考虑以下示例部分：</span><span class="sxs-lookup"><span data-stu-id="991c7-115">Consider the following example section:</span></span>

```xml
<appv:Packages><appv:PackagePackageId="A8731008-4523-4713-83A4-CD1363907160"VersionId="E889951B-7F30-418B-A69C-B37283BC0DB9"/><appv:PackagePackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"VersionId="01F1943B-C778-40AD-BFAD-AC34A695DF3C"/><appv:PackagePackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"/></appv:Packages>
```

<span data-ttu-id="991c7-116">假设在第一个和第三个程序包中定义了相同的 DWORD 值 ABC （HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region），例如：</span><span class="sxs-lookup"><span data-stu-id="991c7-116">Assume that same DWORD value ABC (HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region) is defined in the first and third package, such as:</span></span>

-   <span data-ttu-id="991c7-117">程序包1（A8731008-4523-4713-83A4-CD1363907160）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5</span><span class="sxs-lookup"><span data-stu-id="991c7-117">Package 1 (A8731008-4523-4713-83A4-CD1363907160): HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=5</span></span>

-   <span data-ttu-id="991c7-118">程序包3（04220DCA-EE77-42BE-A9F5-96FD8E8593F2）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 10</span><span class="sxs-lookup"><span data-stu-id="991c7-118">Package 3 (04220DCA-EE77-42BE-A9F5-96FD8E8593F2): HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=10</span></span>

<span data-ttu-id="991c7-119">由于程序包1首先出现，AppConnectionGroup 的虚拟环境将具有单个 DWORD 值5（HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5）。</span><span class="sxs-lookup"><span data-stu-id="991c7-119">Since Package 1 appears first, the AppConnectionGroup's virtual environment will have the single DWORD value of 5 (HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=5).</span></span> <span data-ttu-id="991c7-120">这意味着在查询 HKEY \ _LOCAL \ _MACHINE 时，程序包1、程序包2和程序包3中的虚拟应用程序都将看到值 5 \ \\software\\contoso\\finapp\\region。</span><span class="sxs-lookup"><span data-stu-id="991c7-120">This means that the virtual applications in Package 1, Package 2, and Package 3 will all see the value 5 when they query for HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region.</span></span>

<span data-ttu-id="991c7-121">其他虚拟环境资源的解析方式类似，但通常情况下，注册表中发生冲突。</span><span class="sxs-lookup"><span data-stu-id="991c7-121">Other virtual environment resources are resolved similarly, but the usual case is that the collisions occur in the registry.</span></span>

## <a href="" id="bkmk-merged-root-ve-exp"></a><span data-ttu-id="991c7-122">将相同的包路径合并到连接组中的一个虚拟目录中</span><span class="sxs-lookup"><span data-stu-id="991c7-122">Merging identical package paths into one virtual directory in connection groups</span></span>


<span data-ttu-id="991c7-123">如果连接组中的两个或多个程序包包含相同的目录路径，则路径将合并到连接组虚拟环境内的单个虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="991c7-123">If two or more packages in a connection group contain identical directory paths, the paths are merged into a single virtual directory inside the connection group virtual environment.</span></span> <span data-ttu-id="991c7-124">这种路径合并允许一个程序包中的应用程序访问不同程序包中的文件。</span><span class="sxs-lookup"><span data-stu-id="991c7-124">This merging of paths allows an application in one package to access files that are in a different package.</span></span>

<span data-ttu-id="991c7-125">从连接组中删除程序包时，删除的程序包中的应用程序将无法再访问连接组中其余程序包中的文件。</span><span class="sxs-lookup"><span data-stu-id="991c7-125">When you remove a package from a connection group, the applications in that removed package are no longer able to access files in the remaining packages in the connection group.</span></span>

<span data-ttu-id="991c7-126">App-v 在 "连接" 组中查找文件名称的顺序由在连接组清单文件中列出 App-v 包的顺序指定。</span><span class="sxs-lookup"><span data-stu-id="991c7-126">The order in which App-V looks up a file’s name in the connection group is specified by the order in which the App-V packages are listed in the connection group manifest file.</span></span>

<span data-ttu-id="991c7-127">以下示例显示了**程序包 a**和**程序包 B**的连接组中的文件名查找的顺序和关系。</span><span class="sxs-lookup"><span data-stu-id="991c7-127">The following example shows the order and relationship of a file name lookup in a connection group for **Package A** and **Package B**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="991c7-128">程序包 A</span><span class="sxs-lookup"><span data-stu-id="991c7-128">Package A</span></span></th>
<th align="left"><span data-ttu-id="991c7-129">程序包 B</span><span class="sxs-lookup"><span data-stu-id="991c7-129">Package B</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="991c7-130">C：\Windows\System32</span><span class="sxs-lookup"><span data-stu-id="991c7-130">C:\Windows\System32</span></span></p></td>
<td align="left"><p><span data-ttu-id="991c7-131">C：\Windows\System32</span><span class="sxs-lookup"><span data-stu-id="991c7-131">C:\Windows\System32</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="991c7-132">C:\AppTest</span><span class="sxs-lookup"><span data-stu-id="991c7-132">C:\AppTest</span></span></p></td>
<td align="left"><p><span data-ttu-id="991c7-133">C:\AppTest</span><span class="sxs-lookup"><span data-stu-id="991c7-133">C:\AppTest</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="991c7-134">在上面的示例中，当虚拟化应用程序尝试查找特定文件时，将首先搜索程序包 A，查找匹配的文件路径。</span><span class="sxs-lookup"><span data-stu-id="991c7-134">In the example above, when a virtualized application tries to find a specific file, Package A is searched first for a matching file path.</span></span> <span data-ttu-id="991c7-135">如果找不到匹配路径，将使用以下映射规则搜索 Package B：</span><span class="sxs-lookup"><span data-stu-id="991c7-135">If a matching path is not found, Package B is searched, using the following mapping rules:</span></span>

-   <span data-ttu-id="991c7-136">如果在两个应用程序包的同一虚拟文件夹层次结构中存在名为**test.txt**的文件，则使用第一个匹配的文件。</span><span class="sxs-lookup"><span data-stu-id="991c7-136">If a file named **test.txt** exists in the same virtual folder hierarchy in both application packages, the first matching file is used.</span></span>

-   <span data-ttu-id="991c7-137">如果一个名为**bar.txt**的文件存在于一个应用程序包的虚拟文件夹层次结构中，但不在另一个应用程序包中，则使用第一个匹配的文件。</span><span class="sxs-lookup"><span data-stu-id="991c7-137">If a file named **bar.txt** exists in the virtual folder hierarchy of one application package, but not in the other, the first matching file is used.</span></span>






## <span data-ttu-id="991c7-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="991c7-138">Related topics</span></span>


[<span data-ttu-id="991c7-139">管理连接组</span><span class="sxs-lookup"><span data-stu-id="991c7-139">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





