---
title: 管理 MED-V 工作区的软件更新
description: 管理 MED-V 工作区的软件更新
author: dansimp
ms.assetid: a28d6dcd-cb9f-46ba-8dac-1d990837a3a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 696238a2f5ad9b7e5120f75f6cd09d890d12519b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803643"
---
# 管理 MED-V 工作区的软件更新


你可以使用多种不同的选项在已部署的 MED-V 工作区中提供应用程序的软件更新。

**注意** 有关如何指定用于定义 MED-V 如何接收自动更新的配置设置的信息，请参阅[管理 Med-v 工作区的自动更新](managing-automatic-updates-for-med-v-workspaces.md)。

 

**在 MED-V 工作区中更新软件**

1.  **使用电子软件分发系统**

    如果你的组织使用电子软件分发系统（ESD）系统部署软件，则可以使用它来提供 MED-V 工作区上的应用程序的软件更新，就像在物理计算机上提供应用程序更新一样。

2.  **使用组策略**

    如果你的组织使用组策略部署软件，则可以使用它为 MED-V 工作区上的应用程序提供软件更新，就像在物理计算机上提供应用程序更新一样。

3.  **使用应用程序虚拟化（app-v）**

    如果使用 MED-V 与 App-v 结合使用，则可以按照 App-v 工作区中的应用程序更新软件更新，以执行更新软件所需的步骤。 有关详细信息，请参阅[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。

4.  **更新核心映像中的软件**

    尽管不会被视为 MED-V 最佳做法，但你可以将软件更新安装到核心映像上的应用程序。 安装更新后，你可以将 MED-V 工作区重新部署到你的企业，就像最初部署它一样。

    **重要提示** 我们不推荐这种管理软件更新的方法。 此外，如果你更新核心映像中的软件并将 MED-V 工作区重新部署到你的企业，首次必须再次运行安装程序，并且虚拟机中保存的所有数据都将丢失。

     

## 相关主题


[管理 MED-V 工作区的自动更新](managing-automatic-updates-for-med-v-workspaces.md)

[如何测试应用程序发布](how-to-test-application-publishing.md)

[如何在 MED-V 工作区上发布和取消发布应用程序](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





