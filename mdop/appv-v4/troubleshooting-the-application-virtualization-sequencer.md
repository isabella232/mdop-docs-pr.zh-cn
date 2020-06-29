---
title: Application Virtualization Sequencer 故障排除
description: Application Virtualization Sequencer 故障排除
author: dansimp
ms.assetid: 12ea8367-0b84-44e1-a885-e0539486556b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60c47b853c74d90afc21e9ca172c0eec2a2c7a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798720"
---
# <span data-ttu-id="751ad-103">Application Virtualization Sequencer 故障排除</span><span class="sxs-lookup"><span data-stu-id="751ad-103">Troubleshooting the Application Virtualization Sequencer</span></span>


<span data-ttu-id="751ad-104">本主题包含可用于帮助解决应用程序虚拟化（app-v） Sequencer 上的一般问题的信息。</span><span class="sxs-lookup"><span data-stu-id="751ad-104">This topic includes information that you can use to help troubleshoot general issues on the Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="751ad-105">使用 App-v Sequencer 创建 SFTD 文件会意外地增加版本号</span><span class="sxs-lookup"><span data-stu-id="751ad-105">Creating an SFTD File by Using the App-V Sequencer Increases the Version Number Unexpectedly</span></span>


<span data-ttu-id="751ad-106">与 SFTD 文件关联的版本号会意外增加。</span><span class="sxs-lookup"><span data-stu-id="751ad-106">The version number associated with an SFTD file increases unexpectedly.</span></span>

**<span data-ttu-id="751ad-107">解决方案</span><span class="sxs-lookup"><span data-stu-id="751ad-107">Solution</span></span>**

<span data-ttu-id="751ad-108">使用命令行生成新的 sft 文件。</span><span class="sxs-lookup"><span data-stu-id="751ad-108">Use the command line to generate a new .sft file.</span></span> <span data-ttu-id="751ad-109">若要使用命令行创建 sft 文件，请在命令提示符处输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="751ad-109">To create the .sft file by using the command line, enter the following at a command prompt:</span></span>

**<span data-ttu-id="751ad-110">&lt;基本 sft 文件名称 &gt; &lt; 差异 mkdiffpkg.exe sft 文件名&gt;</span><span class="sxs-lookup"><span data-stu-id="751ad-110">mkdiffpkg.exe &lt;base SFT file name&gt; &lt;diff SFT file name&gt;</span></span>**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a><span data-ttu-id="751ad-111">软件包升级后，OSD 文件中的文件名不正确</span><span class="sxs-lookup"><span data-stu-id="751ad-111">File Name in OSD File Is Not Correct After Package Upgrade</span></span>


<span data-ttu-id="751ad-112">升级现有程序包后，文件名不正确。</span><span class="sxs-lookup"><span data-stu-id="751ad-112">After you upgrade an existing package, the file name is not correct.</span></span>

**<span data-ttu-id="751ad-113">解决方案</span><span class="sxs-lookup"><span data-stu-id="751ad-113">Solution</span></span>**

<span data-ttu-id="751ad-114">打开要升级的程序包时，应将根 Q:\\ 驱动器指定为程序包的输出位置。</span><span class="sxs-lookup"><span data-stu-id="751ad-114">When you open a package for upgrade, you should specify the root Q:\\ drive as the output location for the package.</span></span> <span data-ttu-id="751ad-115">不要使用输出位置指定关联的文件名。</span><span class="sxs-lookup"><span data-stu-id="751ad-115">Do not specify an associated file name with the output location.</span></span>

## <span data-ttu-id="751ad-116">当向客户端流处理时，Microsoft Word2003 默认安装导致错误</span><span class="sxs-lookup"><span data-stu-id="751ad-116">Microsoft Word2003 Default Install Results in an Error When Streamed to a Client</span></span>


<span data-ttu-id="751ad-117">将 Microsoft Word2003 流式传输到客户端时，将返回错误，但 Microsoft Word 将继续运行。</span><span class="sxs-lookup"><span data-stu-id="751ad-117">When you stream Microsoft Word2003 to a client, an error is returned but Microsoft Word continues to run.</span></span>

**<span data-ttu-id="751ad-118">解决方案</span><span class="sxs-lookup"><span data-stu-id="751ad-118">Solution</span></span>**

<span data-ttu-id="751ad-119">Resequence 虚拟应用程序包，然后选择 "**完全安装**"。</span><span class="sxs-lookup"><span data-stu-id="751ad-119">Resequence the virtual application package, and select **Full Install**.</span></span>

## <span data-ttu-id="751ad-120">创建依赖程序包时程序包升级不起作用</span><span class="sxs-lookup"><span data-stu-id="751ad-120">Package Upgrade Does Not Work When You Create a Dependent Package</span></span>


<span data-ttu-id="751ad-121">使用程序包升级创建依赖程序包并添加新的注册表项时，它似乎正常运行，但更新的注册表项不可用。</span><span class="sxs-lookup"><span data-stu-id="751ad-121">When you create a dependent package by using package upgrade and add new registry entries, it appears to function correctly but the updated registry entries are not available.</span></span>

**<span data-ttu-id="751ad-122">解决方案</span><span class="sxs-lookup"><span data-stu-id="751ad-122">Solution</span></span>**

<span data-ttu-id="751ad-123">注册表设置始终与程序包的原始版本一起存储，因此除非修复原始程序包，否则程序包的更新将不会显示为可用。</span><span class="sxs-lookup"><span data-stu-id="751ad-123">Registry settings are always stored with the original version of the package, so updates to the package will not appear to be available unless you repair the original package.</span></span>

## <span data-ttu-id="751ad-124">尝试序列时出错。NET 2。0</span><span class="sxs-lookup"><span data-stu-id="751ad-124">Error When Trying to Sequence .NET2.0</span></span>


<span data-ttu-id="751ad-125">对需要的程序包进行排序时。NET 2.0 后，您会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="751ad-125">When you sequence a package that requires .NET2.0, you get an error.</span></span>

**<span data-ttu-id="751ad-126">解决方案</span><span class="sxs-lookup"><span data-stu-id="751ad-126">Solution</span></span>**

<span data-ttu-id="751ad-127">需要的排序包。不支持 NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="751ad-127">Sequencing packages that require .NET2.0 is not supported.</span></span>

## <span data-ttu-id="751ad-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="751ad-128">Related topics</span></span>


[<span data-ttu-id="751ad-129">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="751ad-129">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





