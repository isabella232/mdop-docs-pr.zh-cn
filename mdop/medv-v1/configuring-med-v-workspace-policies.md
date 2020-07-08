---
title: 配置 MED-V 工作区策略
description: 配置 MED-V 工作区策略
author: dansimp
ms.assetid: 0eaed981-cbf3-4b16-a4b7-4705c5705dc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84bdae38b1c801e2c2be2a3dd1d12dd2ca7d932d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803652"
---
# 配置 MED-V 工作区策略


MED-V 工作区策略是一组可配置的设置，用于定义虚拟化环境和应用程序在主机上的执行方式。 本部分中的主题介绍 MED-V 工作区策略中的所有可配置设置，以及这些设置对 MED-V 工作区的影响。

以下 MED-V 工作区类型可用：

-   **持久性**-在持久的 med-v 工作区中，用户对 med-v 工作区所做的所有更改和添加都保存在会话之间的 med-v 工作区中。 此外，永久的 MED-V 工作区通常在域环境中使用。

-   **Revertible**-在 Revertible med-v 工作区中，在每个会话完成时（即，在停止 med-v 工作区时），med-v 工作区在部署过程中将还原为其原始状态。 在会话之间的 MED-V 工作区中，不会保存用户所做的任何更改或添加。 不能在域环境中使用 revertible MED-V 工作区。

在部署 MED-V 工作区之前，请务必确定你创建的 MED-V 工作区的类型，因为不建议在向用户部署策略后重新配置 MED-V 工作区的类型。

**注意** 配置策略时，未填写的必填字段旁边会显示一个警告符号。 如果未填写必填字段，则该符号也会显示在选项卡上。

 

## 本部分内容


<a href="" id="how-to-apply-general-settings-to-a-med-v-workspace"></a>[如何将常规设置应用于 MED-V 工作区](how-to-apply-general-settings-to-a-med-v-workspace.md)  
介绍 MED-V 工作区的常规设置，以及如何将它们应用于策略。

<a href="" id="how-to-apply-virtual-machine-settings-to-a-med-v-workspace"></a>[如何将虚拟机设置应用于 MED-V 工作区](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)  
描述 MED-V 工作区的虚拟机设置，以及如何将它们应用于策略。

<a href="" id="how-to-configure-a-domain-user-or-group"></a>[如何配置域用户或组](how-to-configure-a-domain-user-or-groupmedvv2.md)  
介绍如何配置域用户和组。

<a href="" id="how-to-configure-published-applications"></a>[如何配置已发布的应用程序](how-to-configure-published-applicationsmedvv2.md)  
介绍已发布的应用程序和菜单，以及如何将它们应用于策略。

<a href="" id="how-to-configure-web-settings-for-a-med-v-workspace"></a>[如何为 MED-V 工作区配置 Web 设置](how-to-configure-web-settings-for-a-med-v-workspace.md)  
介绍了可用于 MED-V 工作区的 Web 设置，以及如何将它们应用于策略。

<a href="" id="how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace"></a>[如何为 MED-V 工作区配置虚拟机设置](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace.md)  
介绍 MED-V 工作区的虚拟机设置，以及如何将其应用于策略。

<a href="" id="how-to-apply-network-settings-to-a-med-v-workspace"></a>[如何将网络设置应用于 MED-V 工作区](how-to-apply-network-settings-to-a-med-v-workspace.md)  
描述 MED-V 工作区的网络设置，以及如何将它们应用于策略。

<a href="" id="how-to-apply-performance-settings-to-a-med-v-workspace"></a>[如何将性能设置应用于 MED-V 工作区](how-to-apply-performance-settings-to-a-med-v-workspace.md)  
介绍 MED-V 工作区的性能设置，以及如何将它们应用于策略。

<a href="" id="how-to-import-and-export-a-policy"></a>[如何导入和导出策略](how-to-import-and-export-a-policy.md)  
介绍如何导入和导出策略。

 

 





