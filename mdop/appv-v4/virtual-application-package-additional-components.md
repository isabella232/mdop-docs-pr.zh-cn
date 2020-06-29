---
title: 虚拟应用程序包附加组件
description: 虚拟应用程序包附加组件
author: dansimp
ms.assetid: 476b0f40-ebd6-4296-92fa-61fa9495c03c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d30c2c6561b0d2c08fd75e0c977bf4590d7e6688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798699"
---
# <span data-ttu-id="d86c9-103">虚拟应用程序包附加组件</span><span class="sxs-lookup"><span data-stu-id="d86c9-103">Virtual Application Package Additional Components</span></span>


<span data-ttu-id="d86c9-104">App-v Sequencer 检测到一个目录，其中包含依赖于相同并行程序集的64位和32位可执行文件和/或动态链接库（.dll）文件。</span><span class="sxs-lookup"><span data-stu-id="d86c9-104">The App-V Sequencer has detected a directory that contains 64-bit and 32-bit executables and/or dynamic-link library (.dll) files that depend on the same side-by-side assembly.</span></span> <span data-ttu-id="d86c9-105">通常，排序器为程序包使用的所有公共程序集创建专用的并行程序集;但是，不能在同一目录中创建私有程序集的32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="d86c9-105">Typically, the Sequencer creates private side-by-side assemblies for all public assemblies that are used by the package; however, it is not possible to create 32-bit and 64-bit versions of the private assemblies in the same directory.</span></span>

<span data-ttu-id="d86c9-106">如果 Sequencer 检测到单个冲突，则它将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d86c9-106">If the Sequencer detects a single conflict, it will perform the following actions:</span></span>

-   <span data-ttu-id="d86c9-107">删除整个程序包中的所有现有64位专用程序集，无论该目录是否有冲突。</span><span class="sxs-lookup"><span data-stu-id="d86c9-107">Remove all of the existing 64-bit private assemblies in the entire package, whether or not the directory has a conflict.</span></span>

-   <span data-ttu-id="d86c9-108">仅创建32位版本的私有并行程序集。</span><span class="sxs-lookup"><span data-stu-id="d86c9-108">Create only 32-bit versions of the private side-by-side assemblies.</span></span>

<span data-ttu-id="d86c9-109">你应该在运行 Sequencer 的计算机上和所有 App-v 客户端计算机上本机安装所有必需的64位程序集的公共版本。</span><span class="sxs-lookup"><span data-stu-id="d86c9-109">You should natively install public versions of all the required 64-bit assemblies on the computer running the Sequencer and on all App-V client computers.</span></span>

<span data-ttu-id="d86c9-110">若要查找所需的现有公共程序集，请打开保存程序包的目录，然后查看**VFS**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d86c9-110">To locate the required existing public assemblies, open the directory where the package is saved and look in the **VFS** folder.</span></span> <span data-ttu-id="d86c9-111">例如，如果程序包根为**Q:\\MyApp**，则当你对应用程序进行排序时，请在**Q:\\MyApp\\VFS\\CSIDL\ _Windows \\winsxs\\manifests**中查找所有现有公共程序集。</span><span class="sxs-lookup"><span data-stu-id="d86c9-111">For example, if the package root is **Q:\\MyApp**, when you sequence the application, look in **Q:\\MyApp\\VFS\\CSIDL\_Windows\\WinSxS\\Manifests** and locate all of the existing public assemblies.</span></span> <span data-ttu-id="d86c9-112">这些文件的64位版本将始终以以下文本开头，清单名称的开头： **amd64 ...**。</span><span class="sxs-lookup"><span data-stu-id="d86c9-112">The 64-bit versions of these files will always start with the following text at the beginning of the manifest name: **amd64…**.</span></span> <span data-ttu-id="d86c9-113">可以在关联的清单文件中找到该程序集的确切名称和版本。</span><span class="sxs-lookup"><span data-stu-id="d86c9-113">The exact name and version of the assembly can be found in the associated manifest file.</span></span>

<span data-ttu-id="d86c9-114">使用以下任一链接下载并安装所需先决条件的正确版本：</span><span class="sxs-lookup"><span data-stu-id="d86c9-114">Use any of the following links to download and install the correct version of the required prerequisites:</span></span>

-   [<span data-ttu-id="d86c9-115">Microsoft Visual c + + 2005 可再发行程序包（x64）</span><span class="sxs-lookup"><span data-stu-id="d86c9-115">Microsoft Visual C++ 2005 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152697)

-   [<span data-ttu-id="d86c9-116">Microsoft Visual c + + 2005 SP1 可再发行程序包（x64）</span><span class="sxs-lookup"><span data-stu-id="d86c9-116">Microsoft Visual C++ 2005 SP1 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152698)

-   [<span data-ttu-id="d86c9-117">Microsoft Visual c + + 2008 可再发行程序包（x64）</span><span class="sxs-lookup"><span data-stu-id="d86c9-117">Microsoft Visual C++ 2008 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152699)

-   [<span data-ttu-id="d86c9-118">Microsoft Visual c + + 2008 SP1 可再发行程序包（x64）</span><span class="sxs-lookup"><span data-stu-id="d86c9-118">Microsoft Visual C++ 2008 SP1 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152700)

 

 





