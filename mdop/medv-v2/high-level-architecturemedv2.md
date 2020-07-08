---
title: 高级别体系结构
description: 高级别体系结构
author: dansimp
ms.assetid: a00edb9f-207b-4f32-9e8f-522ea2739d2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a5db4a56b2abfb0df19b0d6d86f4bf88380c2bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804139"
---
# 高级别体系结构


本部分介绍 Microsoft 企业桌面虚拟化（MED-V）2.0 的高级别系统体系结构和组件设计。

## 系统体系结构


MED-V 增强了 Windows 虚拟 PC，可在一个设备上运行两个操作系统、添加虚拟图像、基于组策略的资源调配和集中管理。 通过使用 MED-V，你可以在任何运行 Windows 7 专业版、企业版或 Windows 7 旗舰版的基于 Windows 的桌面上轻松配置、部署和管理公司的 Windows 虚拟 PC 映像。 MED-V 解决方案包括以下组件：

<a href="" id="---------------med-v-host"></a> **MED-V 主机**  
Windows 7 环境，其中包括 MED-V 主机代理、电子软件分发（ESD）系统、注册表管理系统和 MED-V 来宾。 MED-V 主机与 MED-V 来宾交互，以便可以处理某些设置函数和系统信息。

<a href="" id="-------------------med-v-host-agent"></a> **MED-V 主机代理**  
MED-V 主机中包含的用于提供与 MED-V 来宾通信的信道的 MED-V 软件。 它还提供了首次设置和应用程序发布等功能。

**注意** 安装 MED-V 并安装其所需组件后，必须配置 MED-V-V。 MED-V 的配置称为 "首次设置"。

 

<a href="" id="esd-system"></a>**ESD 系统**  
你的现有软件分发方法，可让你部署和安装 MED-V 创建的 MED-V 工作区程序包文件。

<a href="" id="registry-management-system"></a>**注册表管理系统**  
管理组策略设置和首选项的现有方法。

<a href="" id="windows-virtual-pc-image"></a>**Windows 虚拟 PC 映像**  
管理员定义的虚拟机，其中包含以下组件：

<a href="" id="corporate-operating-system"></a>**企业操作系统**  
您的标准企业操作系统。

<a href="" id="management-and-security-tools"></a>**管理和安全工具**  
您的标准管理和安全工具，例如病毒防护。

<a href="" id="-----------------------med-v-guest"></a> **MED-V 来宾**  
Windows XP SP3 环境，作为在 Windows 7 上运行的 Windows 虚拟 PC 的一部分，其中包含以下组件：

<a href="" id="---------------------------med-v-guest-agent"></a> **MED-V 来宾代理**  
MED-V 来宾中包含的 MED-V 软件，提供与 MED-V 主机通信的信道。 它还支持 MED-V 主机代理，其功能类似于第一次设置时执行。

**注意** MED-V 来宾代理将在首次设置时自动安装。

 

<a href="" id="esd-client"></a>**ESD 客户端**  
ESD 系统的可选部分，用于安装 ESD 系统的软件包和报告状态。

## 相关主题


[规划应用程序操作系统兼容性](planning-for-application-operating-system-compatibility.md)

[为 MED-V 准备部署环境](prepare-the-deployment-environment-for-med-v.md)

 

 





