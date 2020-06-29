---
title: 部署疑难解答
description: 部署疑难解答
author: dansimp
ms.assetid: 9ee980f2-4e77-4020-9f0e-8c2ffdc390ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe9677175c9538bc070d2adea17a96351397d9a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803260"
---
# 部署疑难解答


本主题包含的信息可帮助你解决 Microsoft 企业桌面虚拟化（MED-V）2.0 中的部署问题。

## 对 MED-V 部署中的问题进行故障排除


在部署 MED-V 时可能会出现以下问题。 该解决方案可帮助解决此问题。

**如果仅为当前用户安装 MED-V，则会出现问题。** MED-V 仅支持安装用于所有用户的 MED-V 工作区包装程序、MED-V 主机代理和 MED-V 工作区。 为当前用户安装仅会在组件安装和 MED-V 工作区的设置中导致失败。

**解决方案**

安装 MED-V 组件时，切勿使用 " **ALLUSERS =" "** 选项。

**MED-V 需要以独占方式使用虚拟化堆栈。** 一次只能在计算机上运行一个虚拟化堆栈。 Windows 虚拟 PC 必须使用虚拟堆栈，而 MED-V 依赖于 Windows 虚拟 PC。 因此，如果你尝试在运行使用虚拟堆栈的其他应用程序时尝试部署或使用 MED-V，则不能运行或成功安装 MED-V。

**解决方案**

在安装或运行 MED-V 之前，请关闭运行使用虚拟化堆栈的任何应用程序。

**卸载后，快捷方式仍然保留。** 默认情况下，卸载 MED-V 时，将删除最终用户的 "**开始**" 菜单中的快捷方式。 但是，在某些情况下（例如，对于运行漫游配置文件的最终用户而言），MED-V 发布的应用程序的快捷方式将保留在最终用户的 "**开始**" 菜单中。

**解决方案**

若要手动删除 "**开始**" 菜单上的剩余快捷方式，请右键单击快捷方式，然后单击 "**删除**"。

**在 MED-V 工作区中禁用登录消息组策略设置。** 如果在 MED-V 工作区中启用了 Windows XP 登录消息，则最终用户必须在每次需要打开 MED-V 虚拟应用程序时登录。 这会产生较差的用户体验。

**解决方案**

在 MED-V 虚拟机中禁用以下组策略设置：

**交互式登录: 试图登录的用户的消息文本**

**交互式登录: 试图登录的用户的消息标题**

## 相关主题


[操作疑难解答](operations-troubleshooting-medv2.md)

 

 





