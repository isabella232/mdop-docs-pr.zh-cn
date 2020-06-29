---
title: 解决 Application Virtualization Sequencer 问题
description: 解决 Application Virtualization Sequencer 问题
author: dansimp
ms.assetid: 2712094b-a0bc-4643-aced-5415535f3fec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8b84f37217f29ff2c08a2254d7f54ce74348d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798732"
---
# <span data-ttu-id="eea4c-103">解决 Application Virtualization Sequencer 问题</span><span class="sxs-lookup"><span data-stu-id="eea4c-103">Troubleshooting Application Virtualization Sequencer Issues</span></span>


<span data-ttu-id="eea4c-104">本主题包含可用于帮助解决应用程序虚拟化（app-v） Sequencer 上的一般问题的信息。</span><span class="sxs-lookup"><span data-stu-id="eea4c-104">This topic includes information that you can use to help troubleshoot general issues on the Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="eea4c-105">使用 App-v Sequencer 创建 SFTD 文件会意外地增加版本号</span><span class="sxs-lookup"><span data-stu-id="eea4c-105">Creating an SFTD File by Using the App-V Sequencer Increases the Version Number Unexpectedly</span></span>


<span data-ttu-id="eea4c-106">使用命令行生成新的 sft 文件。</span><span class="sxs-lookup"><span data-stu-id="eea4c-106">Use the command line to generate a new .sft file.</span></span> <span data-ttu-id="eea4c-107">若要使用命令行创建 sft 文件，请在命令提示符处输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="eea4c-107">To create the .sft file by using the command line, enter the following at a command prompt:</span></span>

**<span data-ttu-id="eea4c-108">&lt;基本 sft 文件名称 &gt; &lt; 差异 mkdiffpkg.exe sft 文件名&gt;</span><span class="sxs-lookup"><span data-stu-id="eea4c-108">mkdiffpkg.exe &lt;base SFT file name&gt; &lt;diff SFT file name&gt;</span></span>**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a><span data-ttu-id="eea4c-109">软件包升级后，OSD 文件中的文件名不正确</span><span class="sxs-lookup"><span data-stu-id="eea4c-109">File Name in OSD File Is Not Correct After Package Upgrade</span></span>


<span data-ttu-id="eea4c-110">打开要升级的程序包时，应将根 Q:\\ 驱动器指定为程序包的输出位置。</span><span class="sxs-lookup"><span data-stu-id="eea4c-110">When you open a package for upgrade, you should specify the root Q:\\ drive as the output location for the package.</span></span> <span data-ttu-id="eea4c-111">不要使用输出位置指定关联的文件名。</span><span class="sxs-lookup"><span data-stu-id="eea4c-111">Do not specify an associated file name with the output location.</span></span>

## <span data-ttu-id="eea4c-112">当向客户端流处理时，Microsoft Word2003 默认安装导致错误</span><span class="sxs-lookup"><span data-stu-id="eea4c-112">Microsoft Word2003 Default Install Results in an Error When Streamed to a Client</span></span>


<span data-ttu-id="eea4c-113">将 Microsoft Word2003 流式传输到客户端时，将返回错误，但 Microsoft Word 将继续运行。</span><span class="sxs-lookup"><span data-stu-id="eea4c-113">When you stream Microsoft Word2003 to a client, an error is returned, but Microsoft Word continues to run.</span></span>

**<span data-ttu-id="eea4c-114">解决方案</span><span class="sxs-lookup"><span data-stu-id="eea4c-114">Solution</span></span>**

<span data-ttu-id="eea4c-115">Resequence 虚拟应用程序包，然后选择 "**完全安装**"。</span><span class="sxs-lookup"><span data-stu-id="eea4c-115">Resequence the virtual application package and select **Full Install**.</span></span>

## <span data-ttu-id="eea4c-116">创建依赖程序包时，活动升级不起作用</span><span class="sxs-lookup"><span data-stu-id="eea4c-116">Active Upgrade Does Not Work When You Create a Dependent Package</span></span>


<span data-ttu-id="eea4c-117">通过使用 "活动升级" 并添加新的注册表项创建依赖程序包时，它似乎正常运行，但更新的注册表项不可用。</span><span class="sxs-lookup"><span data-stu-id="eea4c-117">When you create a dependent package by using active upgrade and add new registry entries, it appears to function correctly, but the updated registry entries are not available.</span></span>

**<span data-ttu-id="eea4c-118">解决方案</span><span class="sxs-lookup"><span data-stu-id="eea4c-118">Solution</span></span>**

<span data-ttu-id="eea4c-119">注册表设置始终与程序包的原始版本一起存储，因此除非修复原始程序包，否则程序包的更新将不会显示为可用。</span><span class="sxs-lookup"><span data-stu-id="eea4c-119">Registry settings are always stored with the original version of the package, so updates to the package will not appear to be available unless you repair the original package.</span></span>

## <span data-ttu-id="eea4c-120">通过使用 "属性" 页面不显示 Microsoft Office2007 文档的详细信息</span><span class="sxs-lookup"><span data-stu-id="eea4c-120">Detailed information is not visible for Microsoft Office2007 documents by using the properties page</span></span>


<span data-ttu-id="eea4c-121">当您尝试使用 "属性" 页面查看与 Microsoft Office2007 文档相关联的详细信息时，详细信息不可见。</span><span class="sxs-lookup"><span data-stu-id="eea4c-121">When you try to view detailed information associated with a Microsoft Office2007 document by using the properties page, the detailed information is not visible.</span></span>

**<span data-ttu-id="eea4c-122">解决方案</span><span class="sxs-lookup"><span data-stu-id="eea4c-122">Solution</span></span>**

<span data-ttu-id="eea4c-123">App-v 不支持这些属性页所需的 shell 扩展。</span><span class="sxs-lookup"><span data-stu-id="eea4c-123">App-V does not support the required shell extensions for these property pages.</span></span>

## <span data-ttu-id="eea4c-124">序列16位应用程序时，某些注册表项不会捕获</span><span class="sxs-lookup"><span data-stu-id="eea4c-124">Some registry keys are not captured when you sequence 16-bit applications</span></span>


<span data-ttu-id="eea4c-125">在 App-v 4.5 中，注册表挂钩已从内核模式移动到用户模式。</span><span class="sxs-lookup"><span data-stu-id="eea4c-125">In App-V 4.5, registry hooking has been moved from kernel mode to user mode.</span></span> <span data-ttu-id="eea4c-126">如果想要对使用16位安装程序的16位应用程序或应用程序进行排序，必须首先配置 sequencer 计算机，以便该进程在其自己的 Windows NT 虚拟 DOS 计算机（NTVDM）副本中运行。</span><span class="sxs-lookup"><span data-stu-id="eea4c-126">If you want to sequence a 16-bit application or an application that uses a 16-bit installer, you must first configure the sequencer computer so that the process runs in its own copy of the Windows NT Virtual DOS Machine (NTVDM).</span></span>

**<span data-ttu-id="eea4c-127">解决方案</span><span class="sxs-lookup"><span data-stu-id="eea4c-127">Solution</span></span>**

<span data-ttu-id="eea4c-128">在对应用程序进行排序之前，在排序计算机上将以下全局 REGSZ 注册表项值设置为 "yes"：</span><span class="sxs-lookup"><span data-stu-id="eea4c-128">Before you sequence the application, set the following global REGSZ registry key value to "yes" on the sequencing computer:</span></span>

<span data-ttu-id="eea4c-129">HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM</span><span class="sxs-lookup"><span data-stu-id="eea4c-129">HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM</span></span>

<span data-ttu-id="eea4c-130">您必须重新启动计算机才能使此操作生效。</span><span class="sxs-lookup"><span data-stu-id="eea4c-130">You must restart the computer before this takes effect.</span></span>

## <span data-ttu-id="eea4c-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="eea4c-131">Related topics</span></span>


[<span data-ttu-id="eea4c-132">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="eea4c-132">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





