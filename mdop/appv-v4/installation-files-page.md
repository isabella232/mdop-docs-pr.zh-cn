---
title: “安装文件”页
description: “安装文件”页
author: dansimp
ms.assetid: b0aad26f-b143-4f09-87a1-9f016a23cb62
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 08a2e7318271503f072298ca137a1e65e16c0178
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798952"
---
# <span data-ttu-id="4ad77-103">“安装文件”页</span><span class="sxs-lookup"><span data-stu-id="4ad77-103">Installation Files Page</span></span>


<span data-ttu-id="4ad77-104">使用 "**安装文件**" 页面指定用于创建在此向导的 "**选择程序包**" 页面上指定的虚拟应用程序包的安装文件。</span><span class="sxs-lookup"><span data-stu-id="4ad77-104">Use the **Installation Files** page to specify the installation files that were used to create the virtual application package specified on the **Select Package** page of this wizard.</span></span> <span data-ttu-id="4ad77-105">如果你创建了一个包含多个应用程序的虚拟应用程序包，则应将所有所需的安装文件复制到运行 Microsoft Application Virtualization Sequencer 的计算机上的单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ad77-105">If you created a virtual application package that contains multiple applications, you should copy all required installation files to a single folder on the computer running the Microsoft Application Virtualization Sequencer.</span></span>

<span data-ttu-id="4ad77-106">此页面包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="4ad77-106">This page contains the following elements:</span></span>

<a href="" id="original-installation-files"></a>**<span data-ttu-id="4ad77-107">原始安装文件</span><span class="sxs-lookup"><span data-stu-id="4ad77-107">Original Installation Files</span></span>**  
<span data-ttu-id="4ad77-108">单击 "**浏览**" 以指定最初用于创建虚拟应用程序包的安装文件。</span><span class="sxs-lookup"><span data-stu-id="4ad77-108">Click **Browse** to specify the installation files that were originally used to create the virtual application package.</span></span> <span data-ttu-id="4ad77-109">你指定的父目录应保存到运行 Sequencer 的计算机，并且必须包含所有必需的安装文件或包含安装文件的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ad77-109">The parent directory you specify should be saved locally to the computer running the Sequencer and must contain all required installation files or subfolders that contain the installation files.</span></span> <span data-ttu-id="4ad77-110">安装文件可以包含在父文件夹中，也可以包含在指定父文件夹的任何子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4ad77-110">The installation files can be contained in the parent folder or in any of the subfolders of the specified parent folder.</span></span>

<a href="" id="files-installed-on-local-system"></a>**<span data-ttu-id="4ad77-111">本地系统上安装的文件</span><span class="sxs-lookup"><span data-stu-id="4ad77-111">Files installed on local system</span></span>**  
<span data-ttu-id="4ad77-112">单击 "**浏览**" 以指定运行 Sequencer 的计算机上本地安装的安装文件。</span><span class="sxs-lookup"><span data-stu-id="4ad77-112">Click **Browse** to specify the installation files that have been installed locally on the computer running the Sequencer.</span></span> <span data-ttu-id="4ad77-113">仅当已将应用程序安装文件安装到应用程序的默认位置时，才能选择此选项。</span><span class="sxs-lookup"><span data-stu-id="4ad77-113">You can only select this option if the application installation files have been installed to the application’s default location.</span></span>

<span data-ttu-id="4ad77-114">**注意** 你提供的默认安装位置取决于以下条件：</span><span class="sxs-lookup"><span data-stu-id="4ad77-114">**Note** The default installation location you provide depends on the following conditions:</span></span>

 

-   <span data-ttu-id="4ad77-115">最初创建程序包时指定的程序包根目录。</span><span class="sxs-lookup"><span data-stu-id="4ad77-115">The package root specified when the package was originally created.</span></span>

-   <span data-ttu-id="4ad77-116">最初创建程序包时在 Windows Installer 中指定的安装位置。</span><span class="sxs-lookup"><span data-stu-id="4ad77-116">The installation location specified in the Windows Installer when the package was originally created.</span></span>

-   <span data-ttu-id="4ad77-117">默认应用程序安装路径。</span><span class="sxs-lookup"><span data-stu-id="4ad77-117">The default application installation path.</span></span>

<span data-ttu-id="4ad77-118">例如，如果指定的程序包根是**Q:\\Office12** ，并且在安装期间，默认安装位置从**c:\\program files Files\\Office12**更改为**Q:\\Office12**，则冻结期间指定的路径必须是**c:\\program files Files\\Office 12**。</span><span class="sxs-lookup"><span data-stu-id="4ad77-118">For example, if the package root specified is **Q:\\Office12** and during installation, the default installation location is changed from **C:\\Program Files\\Office12** to **Q:\\Office12**, then the path specified during dehydration must be **C:\\Program Files\\Office 12**.</span></span>

<span data-ttu-id="4ad77-119">如果指定的程序包根是**Q:\\Microsoft** ，并且在安装期间，默认安装位置从**c:\\program files Files\\Office12**更改为**Q:\\Microsoft\\Office12**，则冻结期间指定的路径必须是**c:\\program files 文件**。</span><span class="sxs-lookup"><span data-stu-id="4ad77-119">If the package root specified is **Q:\\Microsoft** and during installation, the default installation location is changed from **C:\\Program Files\\Office12** to **Q:\\Microsoft\\Office12**, then the path specified during dehydration must be **C:\\Program Files**.</span></span>

<span data-ttu-id="4ad77-120">使用程序包加速器创建程序包时，程序包中的每个文件（例如**Q:\\Office12\\file.txt**在本地计算机上）通过将程序包根**Q:\\Office12**替换为创建程序包加速器时指定的默认位置，例如**c:\\program files Files\\Office12**。</span><span class="sxs-lookup"><span data-stu-id="4ad77-120">When you create a package using a package accelerator, each file in the package, for example **Q:\\Office12\\file.txt** is found on the local computer by replacing the package root **Q:\\Office12** with the default location specified when the Package Accelerator was created, for example, **C:\\Program Files\\Office12**.</span></span> <span data-ttu-id="4ad77-121">在前面的示例中，该文件应位于**c:\\program files Files\\Office12\\file.txt**中。</span><span class="sxs-lookup"><span data-stu-id="4ad77-121">In the previous example, the file should be located in **C:\\Program Files\\Office12\\file.txt**.</span></span>

## <span data-ttu-id="4ad77-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="4ad77-122">Related topics</span></span>


[<span data-ttu-id="4ad77-123">“创建包加速器”向导 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="4ad77-123">Create Package Accelerator Wizard (AppV 4.6 SP1)</span></span>](create-package-accelerator-wizard--appv-46-sp1-.md)

 

 





