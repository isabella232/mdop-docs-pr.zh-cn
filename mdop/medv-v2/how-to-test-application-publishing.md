---
title: 如何测试应用程序发布
description: 如何测试应用程序发布
author: dansimp
ms.assetid: 17ba2e12-50a0-4f41-8300-f61f09db9f6c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 8dffb4f79ac89c7d419b27640f4f05364bd69e5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804063"
---
# 如何测试应用程序发布


第一次测试完成后，你可以通过执行以下任务来验证应用程序发布功能是否按预期工作。

<a href="" id="bkmk-apppub"></a>**测试应用程序发布**

1.  验证你指定用于发布的应用程序是否可见。

    单击 "**开始**"，然后单击 "**所有程序**" 并搜索指定的应用程序。

    在某些情况下，你可能会在同一应用程序中安装两次，一次在一台主机上，一次在来宾上。 如果在主机 "**开始**" 菜单上将具有相同名称的已发布应用程序发布到同一位置，则它通过将虚拟机名称添加到快捷方式名称来区别于主机应用程序快捷方式。 例如，对于名为 "MEDVHost1" 的虚拟机，主机应用程序可能是 "记事本"，而发布的应用程序可能是 "Notepad （MEDVHost1）"。

2.  验证应用程序是否按预期方式工作。

    在主机上，启动已发布的应用程序，并验证它们是否在来宾上的 Windows XP SP3 中打开。 应用程序必须显示在主机桌面端的 Windows XP 风格的窗口中。

3.  如果适用，请验证文档重定向是否按预期工作。

    如果来宾上已发布的应用程序必须打开主机系统驱动器上的文件夹，请确保它可以打开指定的文件夹。

    **重要提示** 由于 Windows 虚拟 PC 不支持从已共享的文件夹创建共享，因此从共享文件夹（如位于网络上的 "我的文档" 文件夹）打开的任何文档都不会发生重定向。 有关详细信息，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。

验证已发布的应用程序已安装并正常运行后，你可以测试是否可以从 MED-V 工作区添加或删除应用程序。

**测试是否可以添加或删除应用程序**

1.  从 MED-V 工作区添加或删除应用程序。

    有关如何从 MED-V 工作区添加和删除应用程序的信息，请参阅[管理部署到 Med-v 工作区的应用程序](managing-applications-deployed-to-med-v-workspaces.md)。

2.  如果添加了应用程序，请重复执行以下步骤[来测试应用程序发布](#bkmk-apppub)，以验证新应用程序是否按预期方式工作。

3.  如果删除了应用程序，请单击 "**开始**"，然后单击 "**所有程序**"，验证删除的所有应用程序是否不再列出。

**注意** 如果在验证应用程序发布设置时遇到任何问题，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。

在完成应用程序发布的测试后，可以测试其他 MED-V 工作区配置，以验证它们是否按预期运行。

在完成对 MED-V 工作区程序包的测试并验证它是否按预期运行后，你可以将 MED-V 工作区部署到你的企业。

## 相关主题

[如何测试 URL 重定向](how-to-test-url-redirection.md)

[如何验证首次安装设置](how-to-verify-first-time-setup-settings.md)

[部署 MED-V 工作区程序包](deploying-the-med-v-workspace-package.md)

 

 





