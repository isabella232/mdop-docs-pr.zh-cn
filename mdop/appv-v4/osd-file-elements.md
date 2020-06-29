---
title: OSD 文件元素
description: OSD 文件元素
author: dansimp
ms.assetid: 8211b562-7549-4331-8321-144f52574e99
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8e3ebcf53ff39ecd2ef7ad0feec0bbbcae199db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798905"
---
# <span data-ttu-id="8e63f-103">OSD 文件元素</span><span class="sxs-lookup"><span data-stu-id="8e63f-103">OSD File Elements</span></span>


<span data-ttu-id="8e63f-104">Sequencer 安装目录包含 XML 架构文件**Softricity**，该文件定义了开放软件描述符（OSD）文件的有效结构。</span><span class="sxs-lookup"><span data-stu-id="8e63f-104">The Sequencer installation directory contains an XML schema file, **Softricity.xsd**, which defines the valid structure of an Open Software Descriptor (OSD) file.</span></span> <span data-ttu-id="8e63f-105">下面是一些使用较频繁的 OSD 元素。</span><span class="sxs-lookup"><span data-stu-id="8e63f-105">Following are some of the more frequently used OSD elements.</span></span>

<a href="" id="softpkg"></a><span data-ttu-id="8e63f-106">SOFTPKG</span><span class="sxs-lookup"><span data-stu-id="8e63f-106">SOFTPKG</span></span>  
<span data-ttu-id="8e63f-107">包含定义软件包的所有元素的 OSD 文件的根元素。</span><span class="sxs-lookup"><span data-stu-id="8e63f-107">The root element of the OSD file containing all elements defining the software package.</span></span>

<a href="" id="codebase"></a><span data-ttu-id="8e63f-108">CODEBASE</span><span class="sxs-lookup"><span data-stu-id="8e63f-108">CODEBASE</span></span>  
<span data-ttu-id="8e63f-109">有关此程序包的 sft 文件的信息，包括 HREF、文件名和 GUID 属性。</span><span class="sxs-lookup"><span data-stu-id="8e63f-109">Information about the .sft file for this package, including the HREF, FILENAME, and GUID attributes.</span></span> <span data-ttu-id="8e63f-110">如果更改此特定程序包的分发点，则可以编辑 HREF 属性。</span><span class="sxs-lookup"><span data-stu-id="8e63f-110">You can edit the HREF attribute if you change the distribution point of this particular package.</span></span>

<a href="" id="os"></a><span data-ttu-id="8e63f-111">操作系统</span><span class="sxs-lookup"><span data-stu-id="8e63f-111">OS</span></span>  
<span data-ttu-id="8e63f-112">根据最初在排序向导中设置的值，定义此应用程序可以运行的操作系统。</span><span class="sxs-lookup"><span data-stu-id="8e63f-112">Defines on what operating systems this application can run based on values that are initially set in the Sequencing Wizard.</span></span> <span data-ttu-id="8e63f-113">此值只能包含**Softricity**中定义的值。</span><span class="sxs-lookup"><span data-stu-id="8e63f-113">This value can contain only the values defined in **Softricity.xsd**.</span></span>

<a href="" id="local-interaction-allowed"></a><span data-ttu-id="8e63f-114">本地 \ _INTERACTION \ _ALLOWED</span><span class="sxs-lookup"><span data-stu-id="8e63f-114">LOCAL\_INTERACTION\_ALLOWED</span></span>  
<span data-ttu-id="8e63f-115">设置为 TRUE，这将允许在全局命名空间中创建命名对象（事件、mutex、信号、文件映射和 mailslots）和 COM 对象，而不是在特定虚拟环境内隔离，从而允许虚拟应用程序与主机操作系统的应用程序交互。</span><span class="sxs-lookup"><span data-stu-id="8e63f-115">Set to TRUE, this enables creation of named objects (events, mutexes, semaphores, file mappings, and mailslots) and COM objects in the global namespace rather than isolated inside a particular virtual environment, which allows virtual applications to interact with the host operating system's applications.</span></span>

<span data-ttu-id="8e63f-116">示例： &lt; SOFTPKG &gt; &lt; 实现&gt;</span><span class="sxs-lookup"><span data-stu-id="8e63f-116">Example:&lt;SOFTPKG&gt;&lt;IMPLEMENTATION&gt;</span></span>

<span data-ttu-id="8e63f-117">&lt;VIRTUALENV &gt; &lt; 策略&gt;</span><span class="sxs-lookup"><span data-stu-id="8e63f-117">&lt;VIRTUALENV&gt;&lt;POLICIES&gt;</span></span>

<span data-ttu-id="8e63f-118">&lt;本地 \ _INTERACTION \ _ALLOWED &gt; TRUE</span><span class="sxs-lookup"><span data-stu-id="8e63f-118">&lt;LOCAL\_INTERACTION\_ALLOWED&gt;TRUE</span></span>

<span data-ttu-id="8e63f-119">&lt;/LOCAL\ _INTERACTION \ _ALLOWED&gt;</span><span class="sxs-lookup"><span data-stu-id="8e63f-119">&lt;/LOCAL\_INTERACTION\_ALLOWED&gt;</span></span>

<span data-ttu-id="8e63f-120">&lt;/POLICIES &gt; &lt; /VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="8e63f-120">&lt;/POLICIES&gt;&lt;/VIRTUALENV&gt;</span></span>

<span data-ttu-id="8e63f-121">&lt;/IMPLEMENTATION &gt; &lt; /SOFTPKG&gt;</span><span class="sxs-lookup"><span data-stu-id="8e63f-121">&lt;/IMPLEMENTATION&gt;&lt;/SOFTPKG&gt;</span></span>

<a href="" id="dependencies"></a><span data-ttu-id="8e63f-122">相关</span><span class="sxs-lookup"><span data-stu-id="8e63f-122">DEPENDENCIES</span></span>  
<span data-ttu-id="8e63f-123">使用另一个程序包中的 CODEBASE 标记定义动态套件合成（其他程序包上的依赖项）。</span><span class="sxs-lookup"><span data-stu-id="8e63f-123">Defines Dynamic Suite Composition (dependencies on other packages) by using a CODEBASE tag from another package.</span></span>

<span data-ttu-id="8e63f-124">示例： &lt; 依赖项 &gt; &lt; 基本代码 HREF = "rtsps：//server/package.sft" GUID = "7579F4DF-2461-4219-494E1FDC69E3" SYSGUARDFILE = "installer.pkg =" osguard = "6572748" SIZE = "/DEPENDENCIES" 必需 = "FALSE"/ &gt; &lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="8e63f-124">Example:&lt;DEPENDENCIES&gt;&lt;CODEBASE HREF="rtsps://server/package.sft" GUID="7579F4DF-2461-4219-BD43-494E1FDC69E3" SYSGUARDFILE="pkg.1\\osguard.cp" SIZE="6572748" MANDATORY="FALSE"/&gt;&lt;/DEPENDENCIES&gt;</span></span>

<a href="" id="package-name"></a><span data-ttu-id="8e63f-125">程序包名称</span><span class="sxs-lookup"><span data-stu-id="8e63f-125">PACKAGE NAME</span></span>  
<span data-ttu-id="8e63f-126">在 "排序向导"**包信息**页面中输入的程序包的公用名，使你能够指定用于包含多个应用程序的序列化应用程序的单个名称。</span><span class="sxs-lookup"><span data-stu-id="8e63f-126">A common name for the package entered into the Sequencing Wizard **Package Information** page, which enables you to specify a single name used for a sequenced application containing multiple applications.</span></span>

<a href="" id="title"></a><span data-ttu-id="8e63f-127">标题</span><span class="sxs-lookup"><span data-stu-id="8e63f-127">TITLE</span></span>  
<span data-ttu-id="8e63f-128">要对其进行排序的应用程序的可选描述性名称。</span><span class="sxs-lookup"><span data-stu-id="8e63f-128">Optional descriptive name of the application you are sequencing.</span></span>

<a href="" id="abstract"></a><span data-ttu-id="8e63f-129">抽象化</span><span class="sxs-lookup"><span data-stu-id="8e63f-129">ABSTRACT</span></span>  
<span data-ttu-id="8e63f-130">在排序向导**包信息**页面的 "**注释**" 字段中输入的软件包的简短说明。</span><span class="sxs-lookup"><span data-stu-id="8e63f-130">Short description of the software package entered in the **Comments** field in the Sequencing Wizard **Package Information** page.</span></span> <span data-ttu-id="8e63f-131">最佳做法是指定诸如 Sequencer 工作站、Sequencer 版本的操作系统和服务包级别以及排序工程师的名称等信息。</span><span class="sxs-lookup"><span data-stu-id="8e63f-131">A best practice is to specify information such as the operating system and service-pack level of the Sequencer workstation, Sequencer version, and the sequencing engineer’s name.</span></span>

<a href="" id="script"></a><span data-ttu-id="8e63f-132">书写</span><span class="sxs-lookup"><span data-stu-id="8e63f-132">SCRIPT</span></span>  
<span data-ttu-id="8e63f-133">定义要在启动、关闭或流式处理期间发生的特定脚本事件。</span><span class="sxs-lookup"><span data-stu-id="8e63f-133">Defines specific scripted events to occur during startup, shutdown, or streaming.</span></span>

<a href="" id="mgmt-shortcutlist"></a><span data-ttu-id="8e63f-134">管理 \ _SHORTCUTLIST</span><span class="sxs-lookup"><span data-stu-id="8e63f-134">MGMT\_SHORTCUTLIST</span></span>  
<span data-ttu-id="8e63f-135">向导中定义的所有快捷方式的列表。</span><span class="sxs-lookup"><span data-stu-id="8e63f-135">List of all shortcuts defined in the wizard.</span></span>

<a href="" id="mgmt-fileassociations"></a><span data-ttu-id="8e63f-136">管理 \ _FILEASSOCIATIONS</span><span class="sxs-lookup"><span data-stu-id="8e63f-136">MGMT\_FILEASSOCIATIONS</span></span>  
<span data-ttu-id="8e63f-137">在向导中指定的文件类型的列表。</span><span class="sxs-lookup"><span data-stu-id="8e63f-137">List of the file types specified in the wizard.</span></span>

## <span data-ttu-id="8e63f-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="8e63f-138">Related topics</span></span>


[<span data-ttu-id="8e63f-139">关于“OSD”选项卡</span><span class="sxs-lookup"><span data-stu-id="8e63f-139">About the OSD Tab</span></span>](about-the-osd-tab.md)

 

 





