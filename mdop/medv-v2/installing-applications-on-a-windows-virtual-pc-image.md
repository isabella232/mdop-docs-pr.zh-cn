---
title: 在 Windows Virtual PC 映像上安装应用程序
description: 在 Windows Virtual PC 映像上安装应用程序
author: dansimp
ms.assetid: 32651eff-e3c6-4ef4-947d-2beddc695eac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bf73fec0b33b37c2553dfe6f923917aa926b8e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804047"
---
# 在 Windows Virtual PC 映像上安装应用程序


创建用于 Microsoft 企业桌面虚拟化（MED-V）2.0 的 Windows 虚拟电脑映像后，你可以在运行 MED-V （如电子软件分发（ESD）系统和防病毒软件）的情况下安装其他有用的组件。

以下部分提供的信息可帮助你在 MED-V 映像上安装软件。

**小心** 若要在部署后轻松使用 MED-V 工作区管理，我们建议你将在 MED-V 映像上安装的组件数限制为所需的组件或在使用 MED-V 时有用的组件。 例如，虽然它们不是运行 MED-V 所必需的，但你可以安装 ESD 系统，以便稍后将应用程序安装到 MED-V 工作区和防病毒软件中，以便在映像上进行安全保护。

 

**在 MED-V 映像上安装软件**

1.  如果当前未在运行，请打开你的 MED-V 虚拟机。

    1.  单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc** "，然后单击 " **windows 虚拟 pc**"。

    2.  双击 "MED-V 虚拟机"。

2.  从虚拟机操作系统内，找到要安装的软件的安装文件。

3.  按照软件供应商提供的安装说明进行操作。

    **注意** 安装完成后，你可能需要关闭并重新启动虚拟机。

     

对于要在 MED-V 映像上安装的任何软件或应用程序，请重复这些步骤。 我们建议你限制在映像上预安装的应用程序数。 在映像上安装应用程序和其他软件的建议过程是立即预安装 ESD 系统，稍后再使用它将软件部署到映像。 或者，也可以使用组策略或 App-v 在 MED-V 工作区中添加或删除应用程序。 有关详细信息，请参阅[管理部署到 Med-v 工作区的应用程序](managing-applications-deployed-to-med-v-workspaces.md)。

有关如何在虚拟映像上安装软件的详细信息，请参阅以下文章：

-   [发布和使用虚拟应用程序](https://go.microsoft.com/fwlink/?LinkId=195926)（ https://go.microsoft.com/fwlink/?LinkId=195926) 。

-   [Windows 虚拟电脑帮助](https://go.microsoft.com/fwlink/?LinkId=182378)（ https://go.microsoft.com/fwlink/?LinkId=182378) 。

在你安装了 MED-V 映像上所需的所有软件后，你的映像已准备好进行打包。

## 相关主题


[为 MED-V 配置 Windows Virtual PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)

[准备 MED-V 映像](prepare-a-med-v-image.md)

 

 





