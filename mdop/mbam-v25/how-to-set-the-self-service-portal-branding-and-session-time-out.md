---
title: 如何设置自助服务门户的外观和会话超时
description: 如何设置自助服务门户的外观和会话超时
author: dansimp
ms.assetid: 031eedfc-fade-4d2f-8771-b329e1d38c0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e222880b2d5557ef15cd7a4efd6421b9972541f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798069"
---
# <span data-ttu-id="08c42-103">如何设置自助服务门户的外观和会话超时</span><span class="sxs-lookup"><span data-stu-id="08c42-103">How to Set the Self-Service Portal Branding and Session Time-out</span></span>


<span data-ttu-id="08c42-104">配置自助服务门户后，你可以用公司名称、技术支持 URL 和 "注意" 文本标记它。</span><span class="sxs-lookup"><span data-stu-id="08c42-104">After you configure the Self-Service Portal, you can brand it with your company name, Help Desk URL, and "notice" text.</span></span> <span data-ttu-id="08c42-105">你还可以更改会话超时设置，以使最终用户的会话在指定的非活动期后过期。</span><span class="sxs-lookup"><span data-stu-id="08c42-105">You can also change the Session Time-out setting to make the end user’s session expire after a specified period of inactivity.</span></span>

**<span data-ttu-id="08c42-106">注意</span><span class="sxs-lookup"><span data-stu-id="08c42-106">Note</span></span>**  
<span data-ttu-id="08c42-107">你还可以使用**Enable-MbamWebApplication** Windows PowerShell CMDLET 或 MBAM Server 配置向导来标记自助服务门户。</span><span class="sxs-lookup"><span data-stu-id="08c42-107">You can also brand the Self-Service Portal by using the **Enable-MbamWebApplication** Windows PowerShell cmdlet or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="08c42-108">有关使用该向导的说明，请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="08c42-108">For instructions on using the wizard, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>



**<span data-ttu-id="08c42-109">注意</span><span class="sxs-lookup"><span data-stu-id="08c42-109">Note</span></span>**  
<span data-ttu-id="08c42-110">在以下说明中， *SelfService*是自助服务门户的默认虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="08c42-110">In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="08c42-111">当您配置了自助服务门户时，您可能使用了其他名称。</span><span class="sxs-lookup"><span data-stu-id="08c42-111">You might have used a different name when you configured the Self-Service Portal.</span></span>



**<span data-ttu-id="08c42-112">设置自助服务门户的会话超时和品牌</span><span class="sxs-lookup"><span data-stu-id="08c42-112">To set the session time-out and branding for the Self-Service Portal</span></span>**

1.  <span data-ttu-id="08c42-113">若要为最终用户的会话设置超时时间，请启动**Internet Information Services 管理器**，或运行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="08c42-113">To set the time-out period for the end user’s session, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

2.  <span data-ttu-id="08c42-114">浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **ASP.NET** &gt; **会话状态**，并将 " **Cookie 设置**" 下的**超时**值更改为最终用户的自助服务门户会话过期的分钟数。</span><span class="sxs-lookup"><span data-stu-id="08c42-114">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **ASP.NET** &gt; **Session State**, and change the **Time-out** value under **Cookie Settings** to the number of minutes after which the end user’s Self-Service Portal session expires.</span></span> <span data-ttu-id="08c42-115">默认值为**5**。</span><span class="sxs-lookup"><span data-stu-id="08c42-115">The default value is **5**.</span></span> <span data-ttu-id="08c42-116">若要禁用设置以使其不会超时，请将该值设置为**0**。</span><span class="sxs-lookup"><span data-stu-id="08c42-116">To disable the setting so that there is no time-out, set the value to **0**.</span></span>

3.  <span data-ttu-id="08c42-117">若要设置自助服务门户的品牌项目，请启动**Internet Information Services 管理器**或运行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="08c42-117">To set the branding items for the Self-Service Portal, start the **Internet Information Services Manager** or run **inetmgr.exe**.</span></span>

4.  <span data-ttu-id="08c42-118">浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **应用程序设置**。</span><span class="sxs-lookup"><span data-stu-id="08c42-118">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

5.  <span data-ttu-id="08c42-119">在 "**名称**" 列中，选择要更改的项目，并更改默认值以反映要使用的名称。</span><span class="sxs-lookup"><span data-stu-id="08c42-119">In the **Name** column, select the item that you want to change, and change the default value to reflect the name that you want to use.</span></span> <span data-ttu-id="08c42-120">下表列出了可以设置的值。</span><span class="sxs-lookup"><span data-stu-id="08c42-120">The following table lists the values that you can set.</span></span>

    **<span data-ttu-id="08c42-121">注意</span><span class="sxs-lookup"><span data-stu-id="08c42-121">Caution</span></span>**  
    <span data-ttu-id="08c42-122">不要更改 "名称" 列中的值（公司名称 \ \*），因为它将导致自助服务门户停止工作。</span><span class="sxs-lookup"><span data-stu-id="08c42-122">Do not change the value in the Name column (CompanyName\*), as it will cause Self-Service Portal to stop working.</span></span>



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Default value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ClientValidationEnabled</p></td>
<td align="left"><p>true</p></td>
</tr>
<tr class="even">
<td align="left"><p>CompanyName</p></td>
<td align="left"><p>Contoso IT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DisplayNotice</p></td>
<td align="left"><p>true</p></td>
</tr>
<tr class="even">
<td align="left"><p>HelpdeskText</p></td>
<td align="left"><p>Contact Helpdesk or IT Department</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HelpdeskUrl</p></td>
<td align="left"><p>#</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, the HelpdeskUrl default value is empty.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryPath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390515](//go.microsoft.com/fwlink/?LinkID=390515)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery-1.10.2.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>jQueryValidatePath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390516](//go.microsoft.com/fwlink/?LinkID=390516)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery.validate.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryValidateUnobtrusivePath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390517](//go.microsoft.com/fwlink/?LinkID=390517)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery.validate.unobtrusive.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>NoticeTextPath</p></td>
<td align="left"><p>Notice.txt</p>
<div class="alert">
<strong>Note</strong>  
<p>You can edit the notice text either by using the Internet Information Services (IIS) Manager or by opening and changing the Notice.txt file in the installation directory.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>UnobtrusiveJavaScriptEnabled</p></td>
<td align="left"><p>true</p></td>
</tr>
</tbody>
</table>
~~~





## <span data-ttu-id="08c42-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="08c42-123">Related topics</span></span>


[<span data-ttu-id="08c42-124">为组织自定义自助服务门户</span><span class="sxs-lookup"><span data-stu-id="08c42-124">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)



## <span data-ttu-id="08c42-125">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="08c42-125">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="08c42-126">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="08c42-126">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="08c42-127">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="08c42-127">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





