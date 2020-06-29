---
title: 如何设置定期发布刷新
description: 如何设置定期发布刷新
author: dansimp
ms.assetid: c358c765-cb88-4881-b4e7-0a2e87304870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5bbea1c661d6cb5a78f0bb9de29538e0222cda6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801063"
---
# 如何设置定期发布刷新


你可以使用以下过程将客户端配置为定期刷新 App-v 服务器中的发布信息。 在配置客户端后，刷新操作为 "自动"。 这些设置配置客户端的默认设置，以便此计算机上的所有用户都能看到相同的设置。

**注意** 执行此过程后，在登录后首次刷新后，将根据新设置刷新发布信息。 第一次刷新发生时，服务器可能会用不同的设置替代计算机设置，具体取决于其配置方式。 "**属性**" 对话框中的 "**刷新**" 选项卡显示本地配置的客户端计算机设置和可能已由发布服务器为用户配置的任何设置。

 

**定期刷新应用程序虚拟化服务器中的发布信息**

1.  单击 "**范围**" 窗格中的 "**发布服务器**"。

2.  在 "**结果**" 窗格中，右键单击所需服务器，然后从弹出菜单中选择 "**属性**"。

3.  在 "**属性**" 对话框中的 "**刷新**" 选项卡上，选中 "**刷新配置间隔**" 复选框，然后输入一个表示字段中的频率的数字。 然后从下拉菜单中选择 "**分钟**"、"**小时**"、"**天**"。

    **注意** 此设置将使客户在每次已配置的时间段内刷新发布信息。 如果在执行刷新时用户未登录，则当用户下一次登录时，将发生刷新。 随后将为下一期间再次启动计时器。

     

4.  单击 "**应用**" 以更改配置。

5.  完成服务器配置后，单击 **"确定"** 退出对话框并返回到 Application Virtualization 客户端管理控制台。

## 相关主题


[如何在 Application Virtualization Client Management Console 中配置客户端](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





