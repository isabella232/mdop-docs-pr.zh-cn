---
ms.reviewer: ''
title: 如何从 app-v 5.0 应用程序使用 app-v 4.6 应用程序
description: 如何从 app-v 5.0 应用程序使用 app-v 4.6 应用程序
ms.assetid: 4e78cb32-9c8b-478e-ae8b-c474a7e42487
author: msfttracyp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 8b29e861b97d18e427f6a8247a1f731be2dc0889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798347"
---
# 如何从 app-v 5.0 应用程序使用 app-v 4.6 应用程序

*注意：** App-V 4.6 已退出主流支持。 以下情况适用于 App-v 4.6 SP3 程序包。

使用以下过程，在独立客户端上运行 app-v 4.6 应用程序和 app-v 5.0 应用程序。

**在独立客户端上运行应用程序**

1.  选择你的环境中可彼此打开的两个应用程序。 例如，Microsoft Outlook 和 Adobe Acrobat Reader。 您可以访问使用 Adobe Acrobat 创建的电子邮件附件。

2.  转换程序包，或使用 App-v 5.0 格式为任何一个应用程序创建新的程序包。 有关转换程序包的详细信息，请参阅[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定计算机上所有用户](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)的已转换的 App-v 5.0 程序包，或者[如何将应用程序 v 4.6 程序包中的扩展点迁移到特定用户](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)的 app-v 5.0。

3.  使用 App-v 5.0 管理控制台添加和预配程序包。 有关添加和预配程序包的详细信息，请参阅[如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)以及[如何使用管理控制台配置对程序包的访问](how-to-configure-access-to-packages-by-using-the-management-console-50.md)。

4.  转换后的应用程序现在使用 App-v 5.0 运行，您可以从另一个应用程序中打开一个应用程序。 例如，如果将 Microsoft Office 程序包转换为 app-v 5.0 程序包，并且 Adobe Acrobat 仍以 App-v 4.6 程序包的形式运行，则可以使用 Microsoft Outlook 打开 Adobe Acrobat 阅读器附件。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 








