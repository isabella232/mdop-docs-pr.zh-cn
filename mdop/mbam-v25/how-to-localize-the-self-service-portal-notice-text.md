---
title: 如何本地化自助服务门户通知文本
description: 如何本地化自助服务门户通知文本
author: dansimp
ms.assetid: a4c878b7-e5c8-45af-a537-761bb2991659
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a2385f6b00713e7373bd1707b02324b80f300c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804023"
---
# <span data-ttu-id="4fd68-103">如何本地化自助服务门户通知文本</span><span class="sxs-lookup"><span data-stu-id="4fd68-103">How to Localize the Self-Service Portal Notice Text</span></span>


<span data-ttu-id="4fd68-104">你可以将本地化声明文本配置为在自助服务门户中默认显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="4fd68-104">You can configure localized notice text to display to end users by default in the Self-Service Portal.</span></span> <span data-ttu-id="4fd68-105">显示声明文本的 Notice.txt 文件位于以下根目录中：</span><span class="sxs-lookup"><span data-stu-id="4fd68-105">The Notice.txt file that displays the notice text is in the following root directory:</span></span>

<span data-ttu-id="4fd68-106">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="4fd68-106">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="4fd68-107">若要显示本地化声明文本，请创建一个已本地化的 Notice.txt 文件，然后将其保存在以下示例目录中的特定语言文件夹下：</span><span class="sxs-lookup"><span data-stu-id="4fd68-107">To display localized notice text, you create a localized Notice.txt file, and then save it under a specific language folder in the following example directory:</span></span>

<span data-ttu-id="4fd68-108">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="4fd68-108">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="4fd68-109">**注意** 你可以使用**应用程序设置**中的**NoticeTextPath**项配置路径。</span><span class="sxs-lookup"><span data-stu-id="4fd68-109">**Note** You can configure the path by using the **NoticeTextPath** item in **Application Settings**.</span></span>

 

<span data-ttu-id="4fd68-110">MBAM 根据以下规则显示声明文本：</span><span class="sxs-lookup"><span data-stu-id="4fd68-110">MBAM displays the notice text, based on the following rules:</span></span>

-   <span data-ttu-id="4fd68-111">如果在相应的语言文件夹中创建已本地化的**Notice.txt**文件，MBAM 将显示本地化声明文本（如果默认**Notice.txt**文件存在）。</span><span class="sxs-lookup"><span data-stu-id="4fd68-111">If you create a localized **Notice.txt** file in the appropriate language folder, MBAM displays the localized notice text if the default **Notice.txt** file exists.</span></span> <span data-ttu-id="4fd68-112">如果缺少默认**Notice.txt**文件，则会显示一条消息，指示缺少默认文件。</span><span class="sxs-lookup"><span data-stu-id="4fd68-112">If the default **Notice.txt** file is missing, a message displays indicating that the default file is missing.</span></span>

-   <span data-ttu-id="4fd68-113">如果 MBAM 没有找到 Notice.txt 文件的本地化版本，它将在默认 Notice.txt 文件中显示文本。</span><span class="sxs-lookup"><span data-stu-id="4fd68-113">If MBAM does not find a localized version of the Notice.txt file, it displays the text in the default Notice.txt file.</span></span>

-   <span data-ttu-id="4fd68-114">如果 MBAM 没有找到默认的 Notice.txt 文件，它将在自助服务门户中显示默认文本。</span><span class="sxs-lookup"><span data-stu-id="4fd68-114">If MBAM does not find a default Notice.txt file, it displays the default text in the Self-Service Portal.</span></span>

<span data-ttu-id="4fd68-115">**注意** 如果最终用户的浏览器设置为不具有相应语言子文件夹或 Notice.txt 的语言，则显示以下根目录中 Notice.txt 文件中的文本：</span><span class="sxs-lookup"><span data-stu-id="4fd68-115">**Note** If an end user’s browser is set to a language that does not have a corresponding language subfolder or Notice.txt, the text in the Notice.txt file in the following root directory is displayed:</span></span>

<span data-ttu-id="4fd68-116">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="4fd68-116">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

 

**<span data-ttu-id="4fd68-117">创建本地化的 Notice.txt 文件</span><span class="sxs-lookup"><span data-stu-id="4fd68-117">To create a localized Notice.txt file</span></span>**

1.  <span data-ttu-id="4fd68-118">在配置了自助服务门户的服务器上，在 &lt; *Language* &gt; 以下示例目录中创建一个语言文件夹，其中的 &lt; *语言* &gt; 表示本地化语言的名称：</span><span class="sxs-lookup"><span data-stu-id="4fd68-118">On the server where you configured the Self-Service Portal, create a &lt;*Language*&gt; folder in the following example directory, where &lt;*Language*&gt; represents the name of the localized language:</span></span>

    <span data-ttu-id="4fd68-119">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website</span><span class="sxs-lookup"><span data-stu-id="4fd68-119">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

    <span data-ttu-id="4fd68-120">**注意** 某些语言文件夹已存在，因此你可能不需要创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="4fd68-120">**Note** Some language folders already exist, so you might not have to create a folder.</span></span> <span data-ttu-id="4fd68-121">如果必须创建语言文件夹，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)，了解可用于 &lt; *语言*文件夹的有效名称的列表 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="4fd68-121">If you do have to create a language folder, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947) for a list of the valid names that you can use for the &lt;*Language*&gt; folder.</span></span>

     

2.  <span data-ttu-id="4fd68-122">创建一个包含本地化声明文本的 Notice.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="4fd68-122">Create a Notice.txt file that contains the localized notice text.</span></span>

3.  <span data-ttu-id="4fd68-123">将 Notice.txt 文件保存在 " &lt; *语言*" &gt; 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4fd68-123">Save the Notice.txt file in the &lt;*Language*&gt; folder.</span></span> <span data-ttu-id="4fd68-124">例如，若要使用西班牙语创建本地化的 Notice.txt 文件，请在以下示例目录中保存本地化的 Notice.txt 文件：</span><span class="sxs-lookup"><span data-stu-id="4fd68-124">For example, to create a localized Notice.txt file in Spanish, save the localized Notice.txt file in the following example directory:</span></span>

    <span data-ttu-id="4fd68-125">&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\Es-es</span><span class="sxs-lookup"><span data-stu-id="4fd68-125">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website\\Es-es</span></span>

    <span data-ttu-id="4fd68-126">语言文件夹的名称也可以是语言中性名称**es** ，而不是**es**。</span><span class="sxs-lookup"><span data-stu-id="4fd68-126">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="4fd68-127">如果最终用户的浏览器设置为**es** ，并且该文件夹不存在，则会以递归方式检索和检查父区域设置（在 .net 中定义），并在 &lt; &gt; 最终成为默认 Notice.txt 文件之前解析到 MBAM 自助服务安装目录\\SelfServiceWebsite\\es\\Notice.txt。</span><span class="sxs-lookup"><span data-stu-id="4fd68-127">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="4fd68-128">此递归回退模拟 .NET 资源加载规则。</span><span class="sxs-lookup"><span data-stu-id="4fd68-128">This recursive fallback mimics the .NET resource loading rules.</span></span>



## <span data-ttu-id="4fd68-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="4fd68-129">Related topics</span></span>


[<span data-ttu-id="4fd68-130">为组织自定义自助服务门户</span><span class="sxs-lookup"><span data-stu-id="4fd68-130">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

## <span data-ttu-id="4fd68-131">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="4fd68-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4fd68-132">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="4fd68-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4fd68-133">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4fd68-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





