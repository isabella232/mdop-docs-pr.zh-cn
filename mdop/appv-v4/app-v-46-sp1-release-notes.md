---
title: App-V 4.6 SP1 发行说明
description: App-V 4.6 SP1 发行说明
author: dansimp
ms.assetid: aeb6784a-864a-4f4e-976b-40c34dcfd8d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7081aaf4a04d52bf288d7a76b4a488e2b200c3d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802376"
---
# <span data-ttu-id="13fc4-103">App-V 4.6 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="13fc4-103">App-V 4.6 SP1 Release Notes</span></span>


<span data-ttu-id="13fc4-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="13fc4-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="13fc4-105">**重要提示** 在安装 Microsoft Application Virtualization （app-v）管理系统之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="13fc4-105">**Important** Read these Release Notes thoroughly before you install the Microsoft Application Virtualization (App-V) Management System.</span></span> <span data-ttu-id="13fc4-106">这些发行说明包含的信息可帮助你成功安装应用程序虚拟化（app-v） 4.6 SP1。</span><span class="sxs-lookup"><span data-stu-id="13fc4-106">These Release Notes contain information that helps you successfully install Application Virtualization (App-V)4.6 SP1.</span></span> <span data-ttu-id="13fc4-107">本文档包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="13fc4-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="13fc4-108">如果这些发行说明和其他 App-v 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="13fc4-108">If there is a difference between these Release Notes and other App-V documentation, the latest change should be considered authoritative.</span></span>

 

## <span data-ttu-id="13fc4-109">防范安全漏洞和病毒</span><span class="sxs-lookup"><span data-stu-id="13fc4-109">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="13fc4-110">若要帮助防范安全漏洞和病毒，请务必为正在安装的任何新软件安装最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="13fc4-110">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="13fc4-111">有关详细信息，请参阅[Microsoft 安全网站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="13fc4-111">For more information, see the [Microsoft Security website](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="13fc4-112">应用程序虚拟化 4.6 SP1 的已知问题</span><span class="sxs-lookup"><span data-stu-id="13fc4-112">Known Issues with Application Virtualization4.6 SP1</span></span>


<span data-ttu-id="13fc4-113">本部分提供有关 Microsoft Application Virtualization （app-v） 4.6 SP1 问题的最新信息。</span><span class="sxs-lookup"><span data-stu-id="13fc4-113">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.6 SP1.</span></span> <span data-ttu-id="13fc4-114">这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。</span><span class="sxs-lookup"><span data-stu-id="13fc4-114">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="13fc4-115">如果可能，这些问题将在以后的版本中解决。</span><span class="sxs-lookup"><span data-stu-id="13fc4-115">When it is possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="13fc4-116">如果从 SPRT 的路径不以正斜杠（/）结尾，则该路径将丢失</span><span class="sxs-lookup"><span data-stu-id="13fc4-116">Path from SPRT is lost if it does not end in forward slash ( / )</span></span>

<span data-ttu-id="13fc4-117">当项目模板中的 HREF 中的路径不以正斜杠（）结尾时 **/** ，生成的 HREF 不包含该路径。</span><span class="sxs-lookup"><span data-stu-id="13fc4-117">When the path in an HREF in a project template does not end with a forward slash (**/**), the generated HREF does not include the path.</span></span> <span data-ttu-id="13fc4-118">当用户手动处理**sprt**文件时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="13fc4-118">This occurs when the user manually manipulates the **.sprt** file.</span></span> <span data-ttu-id="13fc4-119">如果使用 sequencer，它总是在路径后添加斜杠（ **/** ）。</span><span class="sxs-lookup"><span data-stu-id="13fc4-119">If you use the sequencer it always adds the forward slash (**/**) after the path.</span></span>

<span data-ttu-id="13fc4-120">解决方法确保 HREF 具有结尾的正斜杠（ **/** ）。</span><span class="sxs-lookup"><span data-stu-id="13fc4-120">WORKAROUND Make sure that the HREF has a trailing forward slash (**/**).</span></span>

### <span data-ttu-id="13fc4-121">用户文件夹名称与程序包名称不对应</span><span class="sxs-lookup"><span data-stu-id="13fc4-121">User folder name do not correspond to the package name</span></span>

<span data-ttu-id="13fc4-122">包含用户和 installer.pkg 文件的文件夹不再包含程序包名称。</span><span class="sxs-lookup"><span data-stu-id="13fc4-122">Folders that contain user and global .pkg files no longer include the package name.</span></span> <span data-ttu-id="13fc4-123">以前，App-v 客户端用于将程序包根文件夹8.3 短名称用作文件夹名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="13fc4-123">Previously, the App-V client used to use the package root folder 8.3 short name as part of the folder name.</span></span> <span data-ttu-id="13fc4-124">这使你可以轻松地识别它。</span><span class="sxs-lookup"><span data-stu-id="13fc4-124">This lets you easily identify it.</span></span> <span data-ttu-id="13fc4-125">使用 app-v 4.6 SP1 排序器时，程序包根文件夹8.3 短名称现在是随机字符串。</span><span class="sxs-lookup"><span data-stu-id="13fc4-125">When you use the App-V 4.6 SP1 sequencer, the package root folder 8.3 short names are now random strings.</span></span> <span data-ttu-id="13fc4-126">这使得很难在运行 App-v client 的计算机上标识包含程序包的**installer.pkg**文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="13fc4-126">This makes it difficult to identify the folders that contain the package’s **.pkg** files on the computer that is running the App-V client.</span></span>

<span data-ttu-id="13fc4-127">解决方法使用下列方法之一更轻松地识别这些包文件夹：</span><span class="sxs-lookup"><span data-stu-id="13fc4-127">WORKAROUND Use one of the following methods to more easily identify these package folders:</span></span>

1.  <span data-ttu-id="13fc4-128">使用排序器创建程序包时，请为主应用程序文件夹指定8.3 命名约定遵循的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="13fc4-128">When you create the package by using the Sequencer, specify a folder name that follows the 8.3 naming convention for the primary application folder.</span></span> <span data-ttu-id="13fc4-129">然后，此名称将用作用户文件夹名称的一部分，就像 App-v 4.6 中的情况一样。</span><span class="sxs-lookup"><span data-stu-id="13fc4-129">This name will then be used as part of the user folder name as was the case in App-V 4.6.</span></span>

2.  <span data-ttu-id="13fc4-130">Sprj 文件现在包含一个标记，该标记显示用作用户文件夹名称的开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="13fc4-130">The .sprj file now contains a tag that displays the string that is used as the beginning of the user folder name.</span></span> <span data-ttu-id="13fc4-131">你可以使用**PACKAGEROOTFOLDER**元素的**SHORTNAME**元素来确定名称。</span><span class="sxs-lookup"><span data-stu-id="13fc4-131">You can use the **SHORTNAME** element of the **PACKAGEROOTFOLDER** element to determine the name.</span></span>

### <span data-ttu-id="13fc4-132">在超过64个处理器的计算机上运行 app-v 4.6 SP1</span><span class="sxs-lookup"><span data-stu-id="13fc4-132">Running App-V 4.6 SP1 on computers that have more than 64 processors</span></span>

<span data-ttu-id="13fc4-133">在安装了超过64个处理器的计算机上运行 app-v 4.6 SP1 时，App-v 客户端将失败。</span><span class="sxs-lookup"><span data-stu-id="13fc4-133">When you run App-V 4.6 SP1 on computers that have more than 64 processors installed, the App-V client fails.</span></span>

<span data-ttu-id="13fc4-134">解决方法无。</span><span class="sxs-lookup"><span data-stu-id="13fc4-134">WORKAROUND None.</span></span> <span data-ttu-id="13fc4-135">不支持此配置。</span><span class="sxs-lookup"><span data-stu-id="13fc4-135">This configuration is not supported.</span></span> <span data-ttu-id="13fc4-136">您必须运行 SP1on 个处理器小于64的 app-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="13fc4-136">You must run App-V 4.6 SP1on computers that have fewer than 64 processors.</span></span>

### <span data-ttu-id="13fc4-137">未在使用 Microsoft Update 的所有区域设置中提供 Application Virtualization 4.6 SP1 更新</span><span class="sxs-lookup"><span data-stu-id="13fc4-137">Application Virtualization 4.6 SP1 update is not offered on all locales that use Microsoft Update</span></span>

<span data-ttu-id="13fc4-138">使用 Microsoft Update 时，对于以下语言区域设置，app-v 4.6 SP1 的更新不可用：</span><span class="sxs-lookup"><span data-stu-id="13fc4-138">When you use Microsoft Update, the update for App-V 4.6 SP1 is not available for the following language locales:</span></span>

-   <span data-ttu-id="13fc4-139">哈萨克语</span><span class="sxs-lookup"><span data-stu-id="13fc4-139">Kazakh</span></span>

-   <span data-ttu-id="13fc4-140">印地语</span><span class="sxs-lookup"><span data-stu-id="13fc4-140">Hindi</span></span>

-   <span data-ttu-id="13fc4-141">塞尔维亚语-西里尔文</span><span class="sxs-lookup"><span data-stu-id="13fc4-141">Serbian-Cyrillic</span></span>

<span data-ttu-id="13fc4-142">解决方法如果您使用的是 Microsoft Windows Server 更新服务（WSUS），请使用英文版更新或从 Microsoft Update 目录下载更新。</span><span class="sxs-lookup"><span data-stu-id="13fc4-142">WORKAROUND If you are using Microsoft Windows Server Update Services (WSUS) use the English version of the update or download the update from the Microsoft Update Catalog.</span></span>

### <span data-ttu-id="13fc4-143">展开父程序包后，你无法使用并排组件序列化插件</span><span class="sxs-lookup"><span data-stu-id="13fc4-143">After expanding the parent package, you cannot sequence a plug-in with side by side components</span></span>

<span data-ttu-id="13fc4-144">当使用工具展开父包时， **Tools**  /  在 app-v Sequencer 控制台中将 "**包扩展到本地系统**" 并将插件序列化到 "并行" 组件，则会返回安装错误。</span><span class="sxs-lookup"><span data-stu-id="13fc4-144">When you expand a parent package by using **Tools** / **Expand Package to Local System** in the App-V Sequencer console and you sequence a plug-in with side by side components, an installation error is returned.</span></span> <span data-ttu-id="13fc4-145">例如：</span><span class="sxs-lookup"><span data-stu-id="13fc4-145">For example:</span></span>

-   **<span data-ttu-id="13fc4-146">HRESULT 0x80073712</span><span class="sxs-lookup"><span data-stu-id="13fc4-146">HRESULT 0x80073712</span></span>**

<span data-ttu-id="13fc4-147">当 sequencer 将并行组件写入注册表但不清除以下注册表项的值时，会导致此情况：</span><span class="sxs-lookup"><span data-stu-id="13fc4-147">This is caused when the sequencer writes the side-by-side component to the registry but does not clear the value for the following registry key:</span></span>

<span data-ttu-id="13fc4-148">HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty</span><span class="sxs-lookup"><span data-stu-id="13fc4-148">HKEY\_LOCAL\_MACHINE\\COMPONENTS\\StoreDirty</span></span>

<span data-ttu-id="13fc4-149">解决方法在运行 sequencer 的计算机上展开父程序包后，必须删除以下注册表项的值：</span><span class="sxs-lookup"><span data-stu-id="13fc4-149">WORKAROUND After expanding the parent package on the computer that is running the sequencer, you have to delete the value for the following registry key:</span></span>

<span data-ttu-id="13fc4-150">HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty</span><span class="sxs-lookup"><span data-stu-id="13fc4-150">HKEY\_LOCAL\_MACHINE\\COMPONENTS\\StoreDirty</span></span>

<span data-ttu-id="13fc4-151">删除值后，将插件序列化。</span><span class="sxs-lookup"><span data-stu-id="13fc4-151">After you have deleted the value, sequence the plug-in.</span></span>

### <span data-ttu-id="13fc4-152">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="13fc4-152">Release Notes Copyright Information</span></span>

<span data-ttu-id="13fc4-153">本文档 "按现状" 提供。</span><span class="sxs-lookup"><span data-stu-id="13fc4-153">This document is provided “as-is”.</span></span> <span data-ttu-id="13fc4-154">本文档中表示的信息和视图（如 URL 和其他 Internet 网站参考）可能会更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="13fc4-154">Information and views expressed in this document, such as URL and other Internet website references, may change without notice.</span></span> <span data-ttu-id="13fc4-155">使用本文档的风险由你自己承担。</span><span class="sxs-lookup"><span data-stu-id="13fc4-155">You bear the risk of using it.</span></span>

<span data-ttu-id="13fc4-156">此处描述的一些示例仅供说明，并且是虚构的。</span><span class="sxs-lookup"><span data-stu-id="13fc4-156">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="13fc4-157">不打算或应该推断出真正的关联或连接。</span><span class="sxs-lookup"><span data-stu-id="13fc4-157">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="13fc4-158">本文档未向你提供针对任何 Microsoft 产品的任何知识产权的任何法律权限。</span><span class="sxs-lookup"><span data-stu-id="13fc4-158">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="13fc4-159">可以复制本文档并将其用于进行内部参考。</span><span class="sxs-lookup"><span data-stu-id="13fc4-159">You may copy and use this document for your internal, reference purposes.</span></span> <span data-ttu-id="13fc4-160">你可以出于内部参考目的修改此文档。</span><span class="sxs-lookup"><span data-stu-id="13fc4-160">You may modify this document for your internal, reference purposes.</span></span>



<span data-ttu-id="13fc4-161">Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、Windows、Windows PowerShell、Windows Server 和 Windows Vista 是 Microsoft 组公司的商标。</span><span class="sxs-lookup"><span data-stu-id="13fc4-161">Microsoft, Active Directory, ActiveSync, ActiveX, Excel, SQL Server, Windows, Windows PowerShell, Windows Server, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="13fc4-162">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="13fc4-162">All other trademarks are property of their respective owners.</span></span>

 

 





