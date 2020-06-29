---
title: 如何本地化自助服务门户“HelpdeskURL”
description: 如何本地化自助服务门户“HelpdeskURL”
author: dansimp
ms.assetid: 86798460-077b-459b-8d54-4b605e07d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0d7ec4ce87bbe5aab56e9fa877ced5f51625a5dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804022"
---
# <span data-ttu-id="d082f-103">如何本地化自助服务门户“HelpdeskURL”</span><span class="sxs-lookup"><span data-stu-id="d082f-103">How to Localize the Self-Service Portal “HelpdeskURL”</span></span>


<span data-ttu-id="d082f-104">你可以配置自服务门户 URL 的本地化版本，以便默认显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="d082f-104">You can configure a localized version of the Self-Service Portal URL to display to end users by default.</span></span> <span data-ttu-id="d082f-105">自助服务门户 URL 由参数**HelpdeskURL**表示。</span><span class="sxs-lookup"><span data-stu-id="d082f-105">The Self-Service Portal URL is represented by the parameter **HelpdeskURL**.</span></span>

<span data-ttu-id="d082f-106">如果你创建本地化版本（如以下说明中所述），Microsoft BitLocker 管理和监视（MBAM）将查找并显示本地化版本。</span><span class="sxs-lookup"><span data-stu-id="d082f-106">If you create a localized version, as described in the following instructions, Microsoft BitLocker Administration and Monitoring (MBAM) finds and displays the localized version.</span></span> <span data-ttu-id="d082f-107">如果 MBAM 未找到本地化版本，它将显示为参数**HelpDeskURL**配置的 URL。</span><span class="sxs-lookup"><span data-stu-id="d082f-107">If MBAM does not find a localized version, it displays the URL that is configured for the parameter **HelpDeskURL**.</span></span>

<span data-ttu-id="d082f-108">**注意** 在以下说明中， *SelfService*是自助服务门户的默认虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="d082f-108">**Note** In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="d082f-109">当您配置了自助服务门户时，您可能使用了其他名称。</span><span class="sxs-lookup"><span data-stu-id="d082f-109">You might have used a different name when you configured the Self-Service Portal.</span></span>

 

**<span data-ttu-id="d082f-110">本地化自助服务门户 URL</span><span class="sxs-lookup"><span data-stu-id="d082f-110">To localize the Self-Service Portal URL</span></span>**

1.  <span data-ttu-id="d082f-111">在配置了自助服务门户的服务器上，浏览到 " **Sites** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **应用程序设置**" 网站。</span><span class="sxs-lookup"><span data-stu-id="d082f-111">On the server where you configured the Self-Service Portal, browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

2.  <span data-ttu-id="d082f-112">在 "**操作**" 窗格中，单击 "**添加**" 以打开 "**添加应用程序设置**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="d082f-112">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="d082f-113">在 "**名称**" 字段中，键入**HelpdeskURL**\ _ &lt; *语言* &gt; ，其中 &lt; *Language* &gt; "语言" 是 URL 的相应语言代码。</span><span class="sxs-lookup"><span data-stu-id="d082f-113">In the **Name** field, type **HelpdeskURL**\_&lt;*Language*&gt;, where &lt;*Language*&gt; is the appropriate language code for the URL.</span></span>

    <span data-ttu-id="d082f-114">例如，若要使用西班牙语创建值的本地化版本 `HelpdeskURL` ，请将参数命名为**HelpdeskURL \ _es**。</span><span class="sxs-lookup"><span data-stu-id="d082f-114">For example, to create a localized version of the `HelpdeskURL` value in Spanish, name the parameter **HelpdeskURL\_es-es**.</span></span>

    <span data-ttu-id="d082f-115">语言文件夹的名称也可以是语言中性名称**es** ，而不是**es**。</span><span class="sxs-lookup"><span data-stu-id="d082f-115">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="d082f-116">如果最终用户的浏览器设置为**es** ，并且该文件夹不存在，则会以递归方式检索和检查父区域设置（在 .net 中定义），并在 &lt; &gt; 最终成为默认 Notice.txt 文件之前解析到 MBAM 自助服务安装目录\\SelfServiceWebsite\\es\\Notice.txt。</span><span class="sxs-lookup"><span data-stu-id="d082f-116">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="d082f-117">此递归回退模拟 .NET 资源加载规则。</span><span class="sxs-lookup"><span data-stu-id="d082f-117">This recursive fallback mimics the .NET resource loading rules.</span></span>

    <span data-ttu-id="d082f-118">有关可使用的有效语言代码的列表，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="d082f-118">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="d082f-119">在 "**值**" 字段中，键入 `HelpdeskURL` 要向最终用户显示的值的本地化版本。</span><span class="sxs-lookup"><span data-stu-id="d082f-119">In the **Value** field, type the localized version of the `HelpdeskURL` value that you want to display to end users.</span></span>



## <span data-ttu-id="d082f-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="d082f-120">Related topics</span></span>


[<span data-ttu-id="d082f-121">为组织自定义自助服务门户</span><span class="sxs-lookup"><span data-stu-id="d082f-121">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

 
## <span data-ttu-id="d082f-122">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="d082f-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="d082f-123">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="d082f-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="d082f-124">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="d082f-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




