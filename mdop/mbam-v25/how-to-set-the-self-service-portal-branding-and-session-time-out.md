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
# 如何设置自助服务门户的外观和会话超时


配置自助服务门户后，你可以用公司名称、技术支持 URL 和 "注意" 文本标记它。 你还可以更改会话超时设置，以使最终用户的会话在指定的非活动期后过期。

**注意**  
你还可以使用**Enable-MbamWebApplication** Windows PowerShell CMDLET 或 MBAM Server 配置向导来标记自助服务门户。 有关使用该向导的说明，请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。



**注意**  
在以下说明中， *SelfService*是自助服务门户的默认虚拟目录名称。 当您配置了自助服务门户时，您可能使用了其他名称。



**设置自助服务门户的会话超时和品牌**

1.  若要为最终用户的会话设置超时时间，请启动**Internet Information Services 管理器**，或运行**inetmgr.exe**。

2.  浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **ASP.NET** &gt; **会话状态**，并将 " **Cookie 设置**" 下的**超时**值更改为最终用户的自助服务门户会话过期的分钟数。 默认值为**5**。 若要禁用设置以使其不会超时，请将该值设置为**0**。

3.  若要设置自助服务门户的品牌项目，请启动**Internet Information Services 管理器**或运行**inetmgr.exe**。

4.  浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **应用程序设置**。

5.  在 "**名称**" 列中，选择要更改的项目，并更改默认值以反映要使用的名称。 下表列出了可以设置的值。

    **注意**  
    不要更改 "名称" 列中的值（公司名称 \ *），因为它将导致自助服务门户停止工作。



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





## 相关主题


[为组织自定义自助服务门户](customizing-the-self-service-portal-for-your-organization.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





