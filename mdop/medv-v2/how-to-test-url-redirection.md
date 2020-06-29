---
title: 如何测试 URL 重定向
description: 如何测试 URL 重定向
author: dansimp
ms.assetid: 38d80088-da1d-4098-b27e-76f9e78f81dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d964cf9d0114d3085d7e8952eebc82486b7b76cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803570"
---
# 如何测试 URL 重定向


第一次测试完成后，你可以通过执行以下任务来验证 URL 重定向功能是否按预期工作。

**重要提示** 必须运行 MED-V 主机代理才能使 URL 重定向正常工作。

<a href="" id="bkmk-urlredir"></a>**测试 URL 重定向**

1.  在主计算机中打开 Internet Explorer 浏览器，然后输入您指定用于重定向的 URL。

2.  验证网页是否已在来宾虚拟机上的 Internet Explorer 中打开。

3.  对要测试的每个 URL 重复此过程。

**测试是否可以添加或删除 URL**

1.  从 MED-V 工作区添加或删除 URL。

    有关如何在 MED-V 工作区上添加和删除要重定向的 Url 的信息，请参阅[管理 MED-V URL 重定向](manage-med-v-url-redirection.md)。

2.  如果你已将 URL 添加到重定向列表，请重复执行 "[测试 URL 重定向](#bkmk-urlredir)" 中的步骤，以验证新 URL 是否按预期重定向。

3.  如果从重定向列表中删除了 URL，请按照以下步骤验证是否已删除 URL：

    1.  在主计算机中打开 Internet Explorer 浏览器，然后输入从重定向列表中删除的 URL。

    2.  验证网页是否已在主机计算机上的 Internet Explorer 中打开，而不是在来宾虚拟机上打开。

        **注意** 可能需要几秒钟才能使 URL 重定向发生更改。

**注意** 如果您在验证 URL 重定向设置时遇到任何问题，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。

在 MED-V 工作区中完成 URL 重定向测试后，可以测试其他配置以验证它们是否按预期运行。

在完成对 MED-V 工作区程序包的测试并验证它是否按预期运行后，你可以将 MED-V 工作区部署到你的企业。

## 相关主题

[如何测试应用程序发布](how-to-test-application-publishing.md)

[如何验证首次安装设置](how-to-verify-first-time-setup-settings.md)

[部署 MED-V 工作区程序包](deploying-the-med-v-workspace-package.md)

 

 





