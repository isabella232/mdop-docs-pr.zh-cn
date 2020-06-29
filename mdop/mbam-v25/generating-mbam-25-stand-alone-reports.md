---
title: 生成 MBAM 2.5 独立报告
description: 生成 MBAM 2.5 独立报告
author: dansimp
ms.assetid: 0ec623ff-5155-4906-aef2-20cdc0f84667
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: e1c6b33de26cce5d9ad8d20461dbe0ea0f138c78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803305"
---
# 生成 MBAM 2.5 独立报告


使用独立拓扑配置 Microsoft BitLocker 管理和监视（MBAM）时，你可以生成报告以监视 BitLocker 驱动器加密使用情况和合规性。 本主题包含以下过程：

-   [打开 "管理和监视" 网站](#bkmk-openadmin)

-   [生成企业合规性报告](#bkmk-enterprise)

-   [生成计算机合规性报告](#bkmk-computercomp)

-   [生成恢复密钥审核报告](#bkmk-recoverykey)

有关独立报表的说明，请参阅[了解 MBAM 2.5 独立的报表](understanding-mbam-25-stand-alone-reports.md)。

**注意** 若要运行报表，您必须是在 Active Directory 域服务中配置的**MBAM Report Users**组的成员。 有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md)。

 

<a href="" id="bkmk-openadmin"></a>**打开 "管理和监视" 网站**

1.  打开 web 浏览器并导航到 "管理和监视" 网站。 管理和监视网站的默认 URL 为：

    *http （s）：// &lt; MBAMAdministrationServerName &gt; ： &lt; port &gt; /Helpdesk*

2.  在左窗格中，单击 "**报表**"。 从顶部的菜单栏中，选择要运行的报表。

    在计算机丢失或被盗时，MBAM 客户端数据将保留在合规性和审核数据库中以供历史参考。 运行企业报告时，我们建议你使用相应的开始日期和结束日期将报表的时间范围从一到两周范围内的范围增加到报表数据准确性。

    生成报表后，可将结果保存为不同格式，如 HTML、Microsoft Word 和 Microsoft Excel。

    **注意** 配置 SQL Server Reporting Services （SSRS）以使用安全套接字层（SSL），然后再配置管理和监视网站。 如果出于任何原因，未将 SSRS 配置为使用 SSL，则在配置管理和监视网站时，报表的 URL 将设置为 HTTP，而不是 HTTPS。 如果随后转到 "管理和监视" 网站并选择报表，则会显示以下消息： "仅显示安全内容"。 若要显示报表，请单击 "**显示所有内容**"。

     

<a href="" id="bkmk-enterprise"></a>**生成企业合规性报告**

1.  从 "管理和监视" 网站，从左侧导航窗格中选择 "**报表**" 节点，选择 "**企业合规性报表**"，然后选择要使用的筛选器。 企业合规性报告的可用筛选器包括：

    -   **合规性状态**。 使用此筛选器指定报表的符合性状态类型（例如，合规或不符合）。

    -   **错误状态**。 使用此筛选器指定报表的错误状态类型（例如，无错误或错误）。

2.  单击 "**查看报表**" 以显示所选报表。

3.  选择计算机名称以查看计算机合规性报告中有关计算机的信息。

4.  选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。

<a href="" id="bkmk-computercomp"></a>**生成计算机合规性报告**

1.  从 "管理和监视" 网站中，从左侧导航窗格中选择 "**报表**" 节点，然后选择 "**计算机合规性报告**"。 使用 "计算机合规性报告" 搜索**用户名**或**计算机名称**。

2.  单击 "**查看报表**" 以查看计算机合规性报告。

3.  选择计算机名称以在计算机合规性报告中显示有关计算机的详细信息。

4.  选择计算机名称旁边的加号（+）以查看有关计算机上的卷的信息。

    **注意** 如果计算机匹配或超过 MBAM 组策略设置的要求，则认为 MBAM 客户端计算机合规。

<a href="" id="bkmk-recoverykey"></a>**生成恢复密钥审核报告**

1.  从 "管理和监视" 网站中，选择左侧导航窗格中的 "**报表**" 节点，然后选择 "**恢复审核报告**"。 为恢复密钥审核报告选择筛选器。 用于恢复密钥审核的可用筛选器如下所示：

    -   **帮助台用户**。 此筛选器使用户能够指定申请者的用户名。 申请者是帮助台中代表最终用户访问密钥的人员。

    -   **最终用户**。 此筛选器使用户能够指定 requestee 的用户名。 Requestee 是呼叫帮助台以获取恢复密钥的最终用户。

    -   **请求结果**。 此筛选器使用户能够指定报表要基于的请求结果类型（如成功或失败）。 例如，用户可能希望查看失败的键访问尝试。

    -   **键类型**。 此筛选器使用户能够指定报表要基于的密钥类型（例如，恢复密钥密码或 TPM 密码哈希）。

    -   **开始日期**。 此筛选器用于定义用户要报告的日期范围的开始日期部分。

    -   **结束日期**。 此筛选器用于定义用户要报告的日期范围的结束日期部分。

2.  单击 "**查看报表**" 以查看报表。



## 相关主题


[监视和报告 BitLocker 与 MBAM 2.5 的相容性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[了解 MBAM 2.5 独立报告](understanding-mbam-25-stand-alone-reports.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





