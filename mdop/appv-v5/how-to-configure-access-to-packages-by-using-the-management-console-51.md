---
title: 如何使用管理控制台配置对程序包的访问权限
description: 如何使用管理控制台配置对程序包的访问权限
author: dansimp
ms.assetid: 4fd39bc2-d814-46de-a108-1c21fa404e8a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c6c8f930fb1fbd82432f6d43dae8b9bed7a563c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798540"
---
# 如何使用管理控制台配置对程序包的访问权限


在部署 app-v 5.1 虚拟化程序包之前，必须配置将允许访问和运行应用程序的 Active Directory 域服务（AD DS）安全组。 安全组可能包含计算机或用户。 将程序包 Entitling 到计算机组将程序包全局发布到该组中的所有计算机。

使用以下过程配置对虚拟化程序包的访问权限。

**授予对 app-v 5.1 程序包的访问权限**

1.  查找要配置的程序包：

    1.  打开 app-v 5.1 管理控制台。

    2.  若要显示**广告访问**页面，请右键单击要配置的程序包，然后选择 "**编辑 active directory 访问**"。 或者，选择程序包，然后单击 "**广告访问**" 窗格中的 "**编辑**"。

2.  为程序包预配安全组：

    1.  转到 "**查找有效的 ACTIVE DIRECTORY 名称" 和 "授予访问权限**" 页面。

    2.  使用 "设置**mydomain**  \\  名称 **" 格式**，键入 Active Directory 组对象的名称或部分名称，然后单击 "**检查**"。

        **注意** 确保为你要搜索的组提供相关联的域名。

         

3.  若要授予对程序包的访问权限，请选择所需的组，然后单击 "**授予访问权限**"。 新添加的组将显示在**具有 ACCESS 窗格的广告实体**中。

4.  

    若要接受默认配置设置并关闭**广告访问**页，请单击 "**关闭**"。

    若要自定义特定组的配置，请单击 "**分配的配置**" 下拉列表，然后选择 "**自定义**"。 若要配置自定义配置，请单击 "**编辑**"。 授予访问权限后，单击 "**关闭**"。

**删除对 app-v 5.1 程序包的访问权限**

1.  查找要配置的程序包：

    1.  打开 app-v 5.1 管理控制台。

    2.  若要显示**广告访问**页面，请右键单击要配置的程序包，然后选择 "**编辑 active directory 访问**"。 或者，选择程序包，然后单击 "**广告访问**" 窗格中的 "**编辑**"。

2.  选择要删除的组，然后单击 "**删除**"。

3.  若要关闭**广告访问**页面，请单击 "**关闭**"。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)

 

 





