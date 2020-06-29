---
title: 如果对程序包进行分支
description: 如果对程序包进行分支
author: dansimp
ms.assetid: bfe46a8a-f0ee-4a71-9e9c-64ac08aac9c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2de36fae1a09aeae4d1b7b21ebe00f683e3b3693
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801692"
---
# <span data-ttu-id="8dd25-103">如果对程序包进行分支</span><span class="sxs-lookup"><span data-stu-id="8dd25-103">How to Branch a Package</span></span>


<span data-ttu-id="8dd25-104">使用此过程修改现有的顺序应用程序包，以便可以与原始顺序的应用程序包并行运行。</span><span class="sxs-lookup"><span data-stu-id="8dd25-104">Use this procedure to modify an existing sequenced application package so you can run it side-by-side with the original sequenced application package.</span></span> <span data-ttu-id="8dd25-105">此过程称为分支。</span><span class="sxs-lookup"><span data-stu-id="8dd25-105">This process is called branching.</span></span> <span data-ttu-id="8dd25-106">当你对虚拟应用程序包进行分支时，你可以运行两个版本的同一程序包。</span><span class="sxs-lookup"><span data-stu-id="8dd25-106">When you branch a virtual application package you are able to run two versions of the same package.</span></span> <span data-ttu-id="8dd25-107">例如，你可以将 service pack 应用于现有程序包，并与原始已排序虚拟应用程序包并行运行。</span><span class="sxs-lookup"><span data-stu-id="8dd25-107">For example, you can apply a service pack to an existing package, and run it side-by-side with the original sequenced virtual application package.</span></span>

<span data-ttu-id="8dd25-108">使用以下过程对已排序的虚拟应用程序包进行分支。</span><span class="sxs-lookup"><span data-stu-id="8dd25-108">Use the following procedure to branch a sequenced virtual application package.</span></span>

**<span data-ttu-id="8dd25-109">对已排序的虚拟应用程序包进行分支</span><span class="sxs-lookup"><span data-stu-id="8dd25-109">To branch a sequenced virtual application package</span></span>**

1.  <span data-ttu-id="8dd25-110">打开 Microsoft Application Virtualization （App-v） Sequencer。</span><span class="sxs-lookup"><span data-stu-id="8dd25-110">Open the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="8dd25-111">若要指定包含要分支的程序包（sprj）的目标目录，请选择 "**文件**"，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="8dd25-111">To specify the destination directory that contains the package (.sprj) you want to branch select **File**, **Open**.</span></span>

2.  <span data-ttu-id="8dd25-112">导航到包含计划要分支的序列化应用程序的目录，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="8dd25-112">Navigate to the directory that contains the sequenced application you plan to branch and click **Open**.</span></span>

3.  <span data-ttu-id="8dd25-113">若要保存程序包的副本，请在 app-v 排序器中选择 "**文件**"，然后选择 "**另存为**"。</span><span class="sxs-lookup"><span data-stu-id="8dd25-113">To save a copy of the package, in the App-V Sequencer, select **File**, **Save As**.</span></span> <span data-ttu-id="8dd25-114">指定新的唯一名称，并为程序包副本指定新的唯一程序包根目录。</span><span class="sxs-lookup"><span data-stu-id="8dd25-114">Specify a new, unique name, and specify a new unique package root directory for the copy of the package.</span></span> <span data-ttu-id="8dd25-115">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="8dd25-115">Click **Save**.</span></span>

    **<span data-ttu-id="8dd25-116">重要提示</span><span class="sxs-lookup"><span data-stu-id="8dd25-116">Important</span></span>**  
    <span data-ttu-id="8dd25-117">必须指定新的程序包名称，否则将覆盖程序包的现有版本。</span><span class="sxs-lookup"><span data-stu-id="8dd25-117">You must specify a new package name or you will overwrite the existing version of the package.</span></span>



~~~
The sequencer will automatically generate new GUID files for the new package. The version number associated with the package will also be automatically appended to the OSD file name.
~~~

4. <span data-ttu-id="8dd25-118">保存新版本后，你可以应用所需的配置更改，并将关联的 .ICO、OSD、SFT 和 SPRJ 文件保存到应用程序虚拟化（app-v）服务器上的正确位置。</span><span class="sxs-lookup"><span data-stu-id="8dd25-118">After you save the new version you can apply the required configuration changes and save the associated ICO, OSD, SFT, and SPRJ files to correct location on the Application Virtualization (App-V) server.</span></span>

## <span data-ttu-id="8dd25-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="8dd25-119">Related topics</span></span>


[<span data-ttu-id="8dd25-120">Application Virtualization Sequencer 的任务</span><span class="sxs-lookup"><span data-stu-id="8dd25-120">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)









