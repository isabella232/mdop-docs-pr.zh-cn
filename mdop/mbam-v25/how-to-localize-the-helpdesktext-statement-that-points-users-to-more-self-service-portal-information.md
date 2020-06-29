---
title: 如何本地化指示用户了解更多自助服务门户信息的“HelpdeskText”声明
description: 如何本地化指示用户了解更多自助服务门户信息的“HelpdeskText”声明
author: dansimp
ms.assetid: 09ba2a07-3186-45d9-adef-4034c70ae7cf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2367424185da813a46fa52f3614c03083864f75f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803365"
---
# <span data-ttu-id="67d7e-103">如何本地化指示用户了解更多自助服务门户信息的“HelpdeskText”声明</span><span class="sxs-lookup"><span data-stu-id="67d7e-103">How to Localize the “HelpdeskText” Statement that Points Users to More Self-Service Portal Information</span></span>


<span data-ttu-id="67d7e-104">你可以配置自助服务门户 "HelpdeskText" 语句的本地化版本，这将通知最终用户使用自助服务门户时如何获取更多帮助。</span><span class="sxs-lookup"><span data-stu-id="67d7e-104">You can configure a localized version of the Self-Service Portal "HelpdeskText" statement, which informs end users about how to get additional help when they are using the Self-Service Portal.</span></span> <span data-ttu-id="67d7e-105">如果为语句配置本地化的文本，如以下说明中所述，MBAM 显示本地化版本。</span><span class="sxs-lookup"><span data-stu-id="67d7e-105">If you configure localized text for the statement, as described in the following instructions, MBAM displays the localized version.</span></span> <span data-ttu-id="67d7e-106">如果 MBAM 未找到本地化版本，它将显示**HelpdeskText**参数中的值。</span><span class="sxs-lookup"><span data-stu-id="67d7e-106">If MBAM does not find the localized version, it displays the value that is in the **HelpdeskText** parameter.</span></span>

<span data-ttu-id="67d7e-107">**注意** 在以下说明中， *SelfService*是自助服务门户的默认虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="67d7e-107">**Note** In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="67d7e-108">当您配置了自助服务门户时，您可能使用了其他名称。</span><span class="sxs-lookup"><span data-stu-id="67d7e-108">You might have used a different name when you configured the Self-Service Portal.</span></span>

 

**<span data-ttu-id="67d7e-109">显示 HelpdeskText 语句的本地化版本</span><span class="sxs-lookup"><span data-stu-id="67d7e-109">To display a localized version of the HelpdeskText statement</span></span>**

1.  <span data-ttu-id="67d7e-110">在配置了自助服务门户的服务器上，浏览到 " **Sites** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **应用程序设置**" 网站。</span><span class="sxs-lookup"><span data-stu-id="67d7e-110">On the server where you configured the Self-Service Portal, browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

2.  <span data-ttu-id="67d7e-111">在 "**操作**" 窗格中，单击 "**添加**" 以打开 "**添加应用程序设置**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="67d7e-111">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="67d7e-112">在 "**名称**" 字段中，键入**HelpdeskText**\ _ &lt; *语言* &gt; ，其中 &lt; *语言* &gt; 是文本的相应语言代码。</span><span class="sxs-lookup"><span data-stu-id="67d7e-112">In the **Name** field, type **HelpdeskText**\_&lt;*Language*&gt;, where &lt;*Language*&gt; is the appropriate language code for the text.</span></span>

    <span data-ttu-id="67d7e-113">例如，若要使用西班牙语创建本地化的 HelpdeskText 语句，请将参数命名为**HelpdeskText \ _es**。</span><span class="sxs-lookup"><span data-stu-id="67d7e-113">For example, to create a localized HelpdeskText statement in Spanish, name the parameter **HelpdeskText\_es-es**.</span></span>

    <span data-ttu-id="67d7e-114">语言文件夹的名称也可以是语言中性名称**es** ，而不是**es**。</span><span class="sxs-lookup"><span data-stu-id="67d7e-114">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="67d7e-115">如果最终用户的浏览器设置为**es** ，并且该文件夹不存在，则会以递归方式检索和检查父区域设置（在 .net 中定义），并在 &lt; &gt; 最终成为默认 Notice.txt 文件之前解析到 MBAM 自助服务安装目录\\SelfServiceWebsite\\es\\Notice.txt。</span><span class="sxs-lookup"><span data-stu-id="67d7e-115">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="67d7e-116">此递归回退模拟 .NET 资源加载规则。</span><span class="sxs-lookup"><span data-stu-id="67d7e-116">This recursive fallback mimics the .NET resource loading rules.</span></span>

    <span data-ttu-id="67d7e-117">有关可使用的有效语言代码的列表，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="67d7e-117">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="67d7e-118">在 "**值**" 字段中，键入要向最终用户显示的本地化文本。</span><span class="sxs-lookup"><span data-stu-id="67d7e-118">In the **Value** field, type the localized text that you want to display to end users.</span></span>



## <span data-ttu-id="67d7e-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="67d7e-119">Related topics</span></span>


[<span data-ttu-id="67d7e-120">为组织自定义自助服务门户</span><span class="sxs-lookup"><span data-stu-id="67d7e-120">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

 

## <span data-ttu-id="67d7e-121">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="67d7e-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="67d7e-122">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="67d7e-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="67d7e-123">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="67d7e-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



