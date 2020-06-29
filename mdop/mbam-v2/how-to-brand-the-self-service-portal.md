---
title: 如何设置自助服务门户的外观
description: 如何设置自助服务门户的外观
author: dansimp
ms.assetid: 3ef9e951-7c42-4f7f-b131-3765d39b3207
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe4f4efc5852042671711ba5780cc78055957ba8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803710"
---
# <span data-ttu-id="e4901-103">如何设置自助服务门户的外观</span><span class="sxs-lookup"><span data-stu-id="e4901-103">How to Brand the Self-Service Portal</span></span>


<span data-ttu-id="e4901-104">安装 Microsoft BitLocker 管理和监视（MBAM）自助服务门户后，你可以通过你的公司名称、技术支持 URL 和 "注意" 文本为自助服务门户提供品牌。</span><span class="sxs-lookup"><span data-stu-id="e4901-104">After you install the Microsoft BitLocker Administration and Monitoring (MBAM) Self-Service Portal, you can brand the Self-Service Portal with your company name, Help Desk URL, and “notice” text.</span></span> <span data-ttu-id="e4901-105">你还可以更改 "会话超时" 设置，以使最终用户的会话在指定的非活动期后过期。</span><span class="sxs-lookup"><span data-stu-id="e4901-105">You can also change the Session Timeout setting to make the end user’s session expire after a specified period of inactivity.</span></span>

**<span data-ttu-id="e4901-106">设置自助服务门户的会话超时和品牌</span><span class="sxs-lookup"><span data-stu-id="e4901-106">To set the session time-out and branding for the Self-Service Portal</span></span>**

1.  <span data-ttu-id="e4901-107">若要为最终用户的会话设置超时时间，请启动**Internet Information Services 管理器**，或运行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="e4901-107">To set the time-out period for the end user’s session, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

2.  <span data-ttu-id="e4901-108">浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **ASP.NET** &gt; **会话状态**，并将 " **Cookie 设置**" 下的**超时**值更改为最终用户的自助服务门户会话将过期的分钟数。</span><span class="sxs-lookup"><span data-stu-id="e4901-108">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **ASP.NET** &gt; **Session State**, and change the **Time-out** value under **Cookie Settings** to the number of minutes after which the end user’s Self-Service Portal session will expire.</span></span> <span data-ttu-id="e4901-109">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="e4901-109">The default is 5.</span></span> <span data-ttu-id="e4901-110">若要禁用设置以使其不会超时，请将该值设置为**0**。</span><span class="sxs-lookup"><span data-stu-id="e4901-110">To disable the setting so that there is no time-out, set the value to **0**.</span></span>

3.  <span data-ttu-id="e4901-111">若要设置自助服务门户的品牌项目，请启动**Internet Information Services 管理器**，或运行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="e4901-111">To set the branding items for the Self-Service Portal, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

4.  <span data-ttu-id="e4901-112">浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **应用程序设置**。</span><span class="sxs-lookup"><span data-stu-id="e4901-112">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

5.  <span data-ttu-id="e4901-113">从 "**名称**" 列中，选择要更改的项目，并更改默认值以反映要使用的名称。</span><span class="sxs-lookup"><span data-stu-id="e4901-113">From the **Name** column, select the item that you want to change, and change the default value to reflect the name that you want to use.</span></span> <span data-ttu-id="e4901-114">下表列出了可以设置的值。</span><span class="sxs-lookup"><span data-stu-id="e4901-114">The following table lists the values that you can set.</span></span>

    **<span data-ttu-id="e4901-115">注意</span><span class="sxs-lookup"><span data-stu-id="e4901-115">Caution</span></span>**  
    <span data-ttu-id="e4901-116">不要更改 "名称" 列中的值（公司名称 \ \*），因为它将导致自助服务门户停止工作。</span><span class="sxs-lookup"><span data-stu-id="e4901-116">Do not change the value in the Name column (CompanyName\*), as it will cause the Self-Service Portal to stop working.</span></span>



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Default Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CompanyName*</p></td>
<td align="left"><p>Contoso IT</p></td>
</tr>
<tr class="even">
<td align="left"><p>HelpdeskText*</p></td>
<td align="left"><p>Contact Help Desk or IT Department</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HelpdeskUrl*</p></td>
<td align="left"><p>Http://www.microsoft.com</p></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/jQuery/jquery-1.7.2.min.js</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MicrosoftAjaxPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/3.5/MicrosoftAjax.js</p></td>
</tr>
<tr class="even">
<td align="left"><p>MicrosoftMvcAjaxPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/mvc/2.0/MicrosoftMvcValidation.js</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NoticeTextPath</p></td>
<td align="left"><p>Notice.txt</p>
<div class="alert">
<strong>Note</strong>  
<p>You can edit the Notice text either by using the IIS Manager or by opening and changing the Notice.txt file in the installation directory.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>
~~~



## <span data-ttu-id="e4901-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="e4901-117">Related topics</span></span>


[<span data-ttu-id="e4901-118">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="e4901-118">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









