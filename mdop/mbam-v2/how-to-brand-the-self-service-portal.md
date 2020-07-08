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
# 如何设置自助服务门户的外观


安装 Microsoft BitLocker 管理和监视（MBAM）自助服务门户后，你可以通过你的公司名称、技术支持 URL 和 "注意" 文本为自助服务门户提供品牌。 你还可以更改 "会话超时" 设置，以使最终用户的会话在指定的非活动期后过期。

**设置自助服务门户的会话超时和品牌**

1.  若要为最终用户的会话设置超时时间，请启动**Internet Information Services 管理器**，或运行**inetmgr.exe**。

2.  浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **ASP.NET** &gt; **会话状态**，并将 " **Cookie 设置**" 下的**超时**值更改为最终用户的自助服务门户会话将过期的分钟数。 默认值为 5。 若要禁用设置以使其不会超时，请将该值设置为**0**。

3.  若要设置自助服务门户的品牌项目，请启动**Internet Information Services 管理器**，或运行**inetmgr.exe**。

4.  浏览到**网站** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **应用程序设置**。

5.  从 "**名称**" 列中，选择要更改的项目，并更改默认值以反映要使用的名称。 下表列出了可以设置的值。

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



## 相关主题


[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









