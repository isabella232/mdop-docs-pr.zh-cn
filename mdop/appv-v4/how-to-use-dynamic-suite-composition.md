---
title: 如何使用动态套件合成
description: 如何使用动态套件合成
author: dansimp
ms.assetid: 24147feb-a0a8-4791-a8e5-cbe5fe13c762
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bff4c9721352785cf6db5c497234ceaa3c5e448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798967"
---
# <span data-ttu-id="7b712-103">如何使用动态套件合成</span><span class="sxs-lookup"><span data-stu-id="7b712-103">How To Use Dynamic Suite Composition</span></span>


<span data-ttu-id="7b712-104">应用程序虚拟化中的动态套件合成使你能够将应用程序定义为依赖于另一个应用程序，如中间件或插件。</span><span class="sxs-lookup"><span data-stu-id="7b712-104">Dynamic Suite Composition in Application Virtualization enables you to define an application as being dependent on another application, such as middleware or a plug-in.</span></span> <span data-ttu-id="7b712-105">这使应用程序能够与虚拟环境中的中间件或插件交互，这通常会被阻止。</span><span class="sxs-lookup"><span data-stu-id="7b712-105">This enables the application to interact with the middleware or plug-in in the virtual environment, where typically this is prevented.</span></span> <span data-ttu-id="7b712-106">这很有用，因为辅助应用程序包可以与多个其他应用程序一起使用，这两个应用程序称为*主要应用*程序，这使每个主应用程序都可以引用同一辅助程序包。</span><span class="sxs-lookup"><span data-stu-id="7b712-106">This is useful because a secondary application package can be used with several other applications, referred to as the *primary applications*, which enables each primary application to reference the same secondary package.</span></span>

<span data-ttu-id="7b712-107">当序列应用程序依赖于插件（如 ActiveX 控件）或依赖中间件（如 OLE DB 或 Java 运行时环境（JRE））的应用程序时，可以使用动态套件合成。</span><span class="sxs-lookup"><span data-stu-id="7b712-107">You can use Dynamic Suite Composition when you sequence applications that depend on plug-ins such as ActiveX controls or for applications that depend on middleware such as OLE DB or the Java Runtime Environment (JRE).</span></span> <span data-ttu-id="7b712-108">如果使用这些依赖组件的每个应用程序都需要排序（包括组件），则对这些组件的更新需要重新对所有主应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="7b712-108">If each application that used these dependent components required sequencing, including the components, updates to those components would require re-sequencing all the primary applications.</span></span> <span data-ttu-id="7b712-109">如果对不带组件的主要应用程序进行排序，然后将中间件或插件序列化为辅助包，则只有辅助包必须更新。</span><span class="sxs-lookup"><span data-stu-id="7b712-109">If you sequence the primary applications without the components and then sequence the middleware or plug-in as a secondary package, then only the secondary package must be updated.</span></span>

<span data-ttu-id="7b712-110">此方法的一个优点是减小了主要程序包的大小。</span><span class="sxs-lookup"><span data-stu-id="7b712-110">One advantage of this approach is that it reduces the size of the primary packages.</span></span> <span data-ttu-id="7b712-111">另一个优点是，它使您能够更好地控制辅助应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7b712-111">Another advantage is that it provides you with better control of access permissions on the secondary applications.</span></span> <span data-ttu-id="7b712-112">请注意，辅助应用程序可以按常规方式进行流处理，无需完全缓存即可运行。</span><span class="sxs-lookup"><span data-stu-id="7b712-112">Note that the secondary application can be streamed in the regular way and does not have to be fully cached to run.</span></span>

<span data-ttu-id="7b712-113">主程序包可以有多个辅助程序包。</span><span class="sxs-lookup"><span data-stu-id="7b712-113">A primary package can have more than one secondary package.</span></span> <span data-ttu-id="7b712-114">但是，仅支持一个依赖级别，因此不能将辅助程序包定义为依赖于另一个辅助程序包。</span><span class="sxs-lookup"><span data-stu-id="7b712-114">However, only one level of dependency is supported, so you cannot define a secondary package as dependent on another secondary package.</span></span> <span data-ttu-id="7b712-115">辅助应用程序也只能是中间件或插件，不能是另一个完整软件产品。</span><span class="sxs-lookup"><span data-stu-id="7b712-115">Also the secondary application can only be middleware or a plug-in and cannot be another full software product.</span></span>

<span data-ttu-id="7b712-116">如果你计划使几个主要应用程序依赖于单个中间件产品，请确保在部署之前测试此配置以确定对系统性能的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="7b712-116">If you plan to make several primary applications dependent on a single middleware product, make sure that you test this configuration to determine the potential effect on system performance before you deploy it.</span></span>

<span data-ttu-id="7b712-117">**重要提示** 程序包依赖项可指定为主应用程序的强制。</span><span class="sxs-lookup"><span data-stu-id="7b712-117">**Important** Package dependencies can be specified as mandatory for a primary application.</span></span> <span data-ttu-id="7b712-118">如果辅助程序包已标记为必需，并且由于某些原因加载时无法访问它，则辅助程序包的加载将失败。</span><span class="sxs-lookup"><span data-stu-id="7b712-118">If a secondary package is flagged as mandatory and it cannot be accessed for some reason during loading, the load of the secondary package will fail.</span></span> <span data-ttu-id="7b712-119">此外，当用户尝试启动时，主应用程序将失败。</span><span class="sxs-lookup"><span data-stu-id="7b712-119">Also, the primary application will fail when the user tries to start it.</span></span>

 

<span data-ttu-id="7b712-120">你可以使用以下过程来创建辅助包（对于插件或中间件组件），然后可以使用最终过程来定义辅助程序包的 OSD 文件中的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="7b712-120">You can use the following procedures to create a secondary package, for either a plug-in or a middleware component, and then you can use the final procedure to define the dependency in the OSD file of the secondary package.</span></span>

**<span data-ttu-id="7b712-121">使用动态套件合成创建插件的辅助程序包</span><span class="sxs-lookup"><span data-stu-id="7b712-121">To create a secondary package for a plug-in by using Dynamic Suite Composition</span></span>**

1.  <span data-ttu-id="7b712-122">在使用干净映像设置的先后顺序计算机上，安装 Application Virtualization Sequencer 并保存计算机状态。</span><span class="sxs-lookup"><span data-stu-id="7b712-122">On a sequencing computer that is set up with a clean image, install Application Virtualization Sequencer and save the computer state.</span></span>

2.  <span data-ttu-id="7b712-123">序列化主应用程序，并将程序包保存到服务器上的内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="7b712-123">Sequence the primary application, and save the package to the Content folder on the server.</span></span>

3.  <span data-ttu-id="7b712-124">将顺序计算机从步骤1还原到其保存的状态。</span><span class="sxs-lookup"><span data-stu-id="7b712-124">Restore the sequencing computer to its saved state from step 1.</span></span>

4.  <span data-ttu-id="7b712-125">在排序计算机上本地安装和配置主应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b712-125">Install and configure the primary application locally on the sequencing computer.</span></span>

    <span data-ttu-id="7b712-126">**重要提示** 必须为辅助程序包指定新的程序包根。</span><span class="sxs-lookup"><span data-stu-id="7b712-126">**Important** You must specify a new package root for the secondary package.</span></span>

     

5.  <span data-ttu-id="7b712-127">启动 sequencer 监视阶段。</span><span class="sxs-lookup"><span data-stu-id="7b712-127">Start the sequencer monitoring phase.</span></span>

6.  <span data-ttu-id="7b712-128">在序列化计算机上安装插件，并根据需要进行配置。</span><span class="sxs-lookup"><span data-stu-id="7b712-128">Install the plug-in on the sequencing computer and configure it as needed.</span></span>

7.  <span data-ttu-id="7b712-129">打开主应用程序，并确认插件是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="7b712-129">Open the primary application, and confirm that the plug-in is working correctly.</span></span>

8.  <span data-ttu-id="7b712-130">在 sequencer 控制台中，创建一个虚拟应用程序来表示将包含该插件的辅助程序包，并选择一个图标。</span><span class="sxs-lookup"><span data-stu-id="7b712-130">In the sequencer console, create a dummy application to represent the secondary package that will contain the plug-in and select an icon.</span></span>

9.  <span data-ttu-id="7b712-131">将程序包保存到服务器上的内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="7b712-131">Save the package to the Content folder on the server.</span></span>

    <span data-ttu-id="7b712-132">**注意** 为了帮助管理辅助程序包，建议程序包名称包括术语 "辅助程序包"，以强调这是一个不充当独立应用程序的程序包，例如**\ [插入 name \] 辅助程序包**。</span><span class="sxs-lookup"><span data-stu-id="7b712-132">**Note** To assist with management of secondary packages, it is recommended that the package name include the term “Secondary package” to emphasize that this is a package that will not function as a stand-alone application—for example, **\[Plug In Name\] Secondary package**.</span></span>

     

**<span data-ttu-id="7b712-133">使用动态套件合成创建中间件的辅助程序包</span><span class="sxs-lookup"><span data-stu-id="7b712-133">To create a secondary package for middleware by using Dynamic Suite Composition</span></span>**

1.  <span data-ttu-id="7b712-134">在使用干净映像设置的先后顺序计算机上，安装 Application Virtualization Sequencer 并保存计算机状态。</span><span class="sxs-lookup"><span data-stu-id="7b712-134">On a sequencing computer that is set up with a clean image, install Application Virtualization Sequencer and save the computer state.</span></span>

2.  <span data-ttu-id="7b712-135">在排序计算机上本地安装中间件，并对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="7b712-135">Install the middleware locally on the sequencing computer, and configure it.</span></span>

3.  <span data-ttu-id="7b712-136">序列化主应用程序，并将程序包保存到服务器上的内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="7b712-136">Sequence the primary application, and save the package to the Content folder on the server.</span></span>

4.  <span data-ttu-id="7b712-137">将顺序计算机从步骤1还原到其保存的状态。</span><span class="sxs-lookup"><span data-stu-id="7b712-137">Restore the sequencing computer to its saved state from step 1.</span></span>

5.  <span data-ttu-id="7b712-138">启动 sequencer 以创建新的程序包。</span><span class="sxs-lookup"><span data-stu-id="7b712-138">Start the sequencer to create a new package.</span></span>

6.  <span data-ttu-id="7b712-139">启动 sequencer 监视阶段。</span><span class="sxs-lookup"><span data-stu-id="7b712-139">Start the sequencer monitoring phase.</span></span>

7.  <span data-ttu-id="7b712-140">在排序计算机上安装中间件应用程序，并将其配置为在典型安装中使用。</span><span class="sxs-lookup"><span data-stu-id="7b712-140">Install the middleware application on the sequencing computer, and configure it as in a typical installation.</span></span>

8.  <span data-ttu-id="7b712-141">完成排序过程。</span><span class="sxs-lookup"><span data-stu-id="7b712-141">Complete the sequencing process.</span></span>

9.  <span data-ttu-id="7b712-142">将程序包保存到服务器上的内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="7b712-142">Save the package to the Content folder on the server.</span></span>

    <span data-ttu-id="7b712-143">**注意** 为了帮助管理辅助程序包，建议程序包名称包括术语 "辅助程序包"，以强调这是一个不充当独立应用程序的程序包，例如**\ [中间件名称 \] 辅助包**。</span><span class="sxs-lookup"><span data-stu-id="7b712-143">**Note** To assist with management of secondary packages, it is recommended that the package name include the term “Secondary package” to emphasize that this is a package that will not function as a stand-alone application—for example, **\[Middleware Name\] Secondary package**.</span></span>

     

**<span data-ttu-id="7b712-144">在主程序包中定义相关性</span><span class="sxs-lookup"><span data-stu-id="7b712-144">To define the dependency in the primary package</span></span>**

1. <span data-ttu-id="7b712-145">在服务器上，打开辅助程序包的 OSD 文件进行编辑。</span><span class="sxs-lookup"><span data-stu-id="7b712-145">On the server, open the OSD file of the secondary package for editing.</span></span> <span data-ttu-id="7b712-146">（最好使用 XML 编辑器对 OSD 文件进行更改; 但是，你可以使用记事本作为替代项。）</span><span class="sxs-lookup"><span data-stu-id="7b712-146">(It is a good idea to use an XML editor to make changes to the OSD file; however, you can use Notepad as an alternative.)</span></span>

2. <span data-ttu-id="7b712-147">从该文件复制**基本代码 HREF**行。</span><span class="sxs-lookup"><span data-stu-id="7b712-147">Copy the **CODEBASE HREF** line from that file.</span></span>

3. <span data-ttu-id="7b712-148">打开主要程序包的 OSD 文件进行编辑。</span><span class="sxs-lookup"><span data-stu-id="7b712-148">Open the OSD file of the primary package for editing.</span></span>

4. <span data-ttu-id="7b712-149"><strong> &lt; &gt; </strong> 在\*\* &lt; VIRTUALENV &gt; **节末尾的** &lt; /ENVLIST &gt; \*\*标记后面的 " \*\* &lt; /VIRTUALENV &gt; \*\* " 标记前插入 "相关性" 标记。</span><span class="sxs-lookup"><span data-stu-id="7b712-149">Insert the <strong>&lt;DEPENDENCIES&gt;</strong>tag after the close of **&lt;/ENVLIST&gt;** tag at the end of the **&lt;VIRTUALENV&gt;** section just before the **&lt;/VIRTUALENV&gt;** tag.</span></span>

5. <span data-ttu-id="7b712-150">在刚刚创建的\*\* &lt; 依赖项 &gt; **标记之后，在辅助包中粘贴**基本代码 HREF\*\*行。</span><span class="sxs-lookup"><span data-stu-id="7b712-150">Paste the **CODEBASE HREF** line from the secondary package after the **&lt;DEPENDENCIES&gt;** tag you just created.</span></span>

6. <span data-ttu-id="7b712-151">如果辅助程序包是必需的程序包，这意味着必须在启动主程序包之前启动它，请在**CODEBASE**标记内添加**强制 = "TRUE"** 属性。</span><span class="sxs-lookup"><span data-stu-id="7b712-151">If the secondary package is a mandatory package, which means that it must be started before the primary package is started, add the **MANDATORY=”TRUE”** property inside the **CODEBASE** tag.</span></span> <span data-ttu-id="7b712-152">如果不是必需的，则可以省略该属性。</span><span class="sxs-lookup"><span data-stu-id="7b712-152">If it is not mandatory, the property can be omitted.</span></span>

7. <span data-ttu-id="7b712-153">插入以下内容以关闭 " \*\* &lt; 相关性 &gt; \*\* " 标记：</span><span class="sxs-lookup"><span data-stu-id="7b712-153">Close the **&lt;DEPENDENCIES&gt;** tag by inserting the following:</span></span>

   **<span data-ttu-id="7b712-154">&lt;/DEPENDENCIES&gt;</span><span class="sxs-lookup"><span data-stu-id="7b712-154">&lt;/DEPENDENCIES&gt;</span></span>**

8. <span data-ttu-id="7b712-155">查看你对 OSD 文件所做的更改，然后保存并关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="7b712-155">Review the changes that you made to the OSD file, and then save and close the file.</span></span> <span data-ttu-id="7b712-156">以下示例显示了添加的分区应如何显示。</span><span class="sxs-lookup"><span data-stu-id="7b712-156">The following example shows how the added section should appear.</span></span> <span data-ttu-id="7b712-157">此处显示的标记值仅适用于示例。</span><span class="sxs-lookup"><span data-stu-id="7b712-157">The tag values shown here are for example only.</span></span>

   **<span data-ttu-id="7b712-158">&lt;VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="7b712-158">&lt;VIRTUALENV&gt;</span></span>**

        **&lt;ENVLIST&gt;**

   **<span data-ttu-id="7b712-159">…</span><span class="sxs-lookup"><span data-stu-id="7b712-159">…</span></span>**

        **&lt;/ENVLIST&gt;**

        **&lt;DEPENDENCIES&gt;**

             **&lt;CODEBASE HREF="rtsp://virt\_apps/package.1/package.1.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.1\\osguard.cp"/&gt;**

             **&lt;CODEBASE HREF="rtsp://sample\_apps/package.2/sample.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.2\\osguard.cp" MANDATORY="TRUE" /&gt;**

        **&lt;/DEPENDENCIES&gt;**

   **<span data-ttu-id="7b712-160">&lt;/VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="7b712-160">&lt;/VIRTUALENV&gt;</span></span>**

9. <span data-ttu-id="7b712-161">如果辅助程序包在 OSD 文件的\*\* &lt; ENVLIST &gt; \*\*部分中有任何条目，则必须将这些条目复制到主程序包的同一节中。</span><span class="sxs-lookup"><span data-stu-id="7b712-161">If the secondary package has any entries in the **&lt;ENVLIST&gt;** section of the OSD file, you must copy those entries to the same section in the primary package.</span></span>

## <span data-ttu-id="7b712-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="7b712-162">Related topics</span></span>


[<span data-ttu-id="7b712-163">如何使用 App-v Sequencer 创建或升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="7b712-163">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





