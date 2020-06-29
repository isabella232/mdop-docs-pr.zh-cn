---
title: 在 MED-V 工作区上安装和删除应用程序
description: 在 MED-V 工作区上安装和删除应用程序
author: dansimp
ms.assetid: 24f32720-51ab-4385-adfe-4f5a65e45fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 22cb98c167b53b1b206b8b5be2ba18fc0fba4f06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804124"
---
# 在 MED-V 工作区上安装和删除应用程序


与主机操作系统不兼容的应用程序可以在 MED-V 工作区中运行，并在 MED-V 工作区中打开，其方式与从主机打开的方式相同，在 "**开始**" 菜单上或使用本地主机快捷方式。

部署 MED-V 工作区后，你可以使用多种不同的选项在 MED-V 工作区中安装和删除应用程序。 这些选项包括以下内容：

-   [使用组策略](#bkmk-grouppolicy)

-   [使用电子软件分发系统](#bkmk-esd)

-   [使用应用程序虚拟化（app-v）](#bkmk-appv)

-   [更新核心图像](#bkmk-coreimage)

**重要提示** 若要确保已安装的应用程序自动发布到主机，请在虚拟机上为**所有用户**安装该应用程序。 有关应用程序发布的详细信息，请参阅[如何在 Med-v 工作区发布和取消发布应用程序](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)。

 

**提示** MED-V 不支持用于内容处理的来宾到主机重定向，例如，在 Internet Explorer 的 MED-V 工作区中双击 Microsoft Word 文档。 因此，必须在 MED-V 工作区中安装所需的应用程序（如 Microsoft Word），以便提供最终用户可能期望的默认内容处理功能。

 

## <a href="" id="bkmk-grouppolicy"></a> 使用组策略添加和删除应用程序


你可以使用组策略和组策略对象向你的企业中的所有或某些 MED-V 工作区分配或发布应用程序。 对于分配的应用程序，当最终用户登录到其计算机时，应用程序将显示在 "**开始**" 菜单上。 当用户首次选择新应用程序时，应用程序将安装并已准备好使用。 对于已发布的应用程序，应用程序不会显示在 "**开始**" 菜单上。 只有最终用户可以使用**控制面板**中的 "**添加或删除程序**" 或打开与应用程序关联的文件来安装。

你还可以使用组策略和组策略对象，方法与从 MED-V 工作区中删除应用程序相同。

有关如何使用组策略添加和删除应用程序的详细信息，请参阅[组策略软件安装](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

## <a href="" id="bkmk-esd"></a> 使用 ESD 系统添加和删除应用程序


电子软件分发（ESD）系统旨在通过网络连接将软件和其他信息高效部署到许多不同的计算机。 如果你的组织使用 ESD 系统部署软件，则可以使用它在 MED-V 工作区上添加和删除应用程序，就像在物理计算机上添加和删除应用程序一样。

## <a href="" id="bkmk-appv"></a> 使用 APP-V 添加和删除应用程序


Microsoft Application Virtualization （App-v）提供管理功能，使应用程序可用于最终用户计算机，而无需直接在这些计算机上安装应用程序。 如果你的组织具有你使用 Windows XP 中的 App-v 进行排序的应用程序，并对其重新排序将延迟迁移到 Windows 7，你可能需要将 MED-V 和 app-v 结合使用。

你可以将 MED-V 与 App-v 结合使用，在已部署的 MED-V 工作区上添加和删除虚拟应用程序。 若要以这种方式管理应用程序，必须首先在 MED-V 来宾操作系统上安装 app-v 代理。 然后，你可以在 MED-V 工作区中使用 app-v 添加和删除虚拟应用程序。

有关如何安装和使用 app-v 的信息，请参阅[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。

**重要提示** 发布到 MED-V 工作区的 app-v 应用程序具有无法从主计算机重定向到来宾虚拟机的文件类型关联。 但是，最终用户仍可以通过单击 "**文件**"，然后单击已发布的 app-v 应用程序上的 "**打开**" 来访问这些文件类型。

若要强制重定向这些文件类型关联，请通过在来宾虚拟机中的命令提示符处键入以下内容来对映射的文件类型关联进行查询 app-v： **sftmime/QUERY OBJ： type**。 然后，在主计算机中映射这些文件类型关联。

 

## <a href="" id="bkmk-coreimage"></a> 在核心映像上添加和删除应用程序


尽管不会被视为 MED-V 最佳做法，但你可以直接在核心映像上添加和删除应用程序。 添加或删除应用程序后，你可以将 MED-V 工作区重新部署到你的企业，就像最初部署它一样。

有关如何在核心映像上添加或删除应用程序的详细信息，请参阅[在 Windows 虚拟 PC 映像上安装应用程序](installing-applications-on-a-windows-virtual-pc-image.md)。

**重要提示** 我们不推荐这种管理应用程序的方法。 如果你在核心映像上添加或删除应用程序，并将 MED-V 工作区重新部署到你的企业，首次必须再次运行安装程序，并且虚拟机上保存的所有数据都将丢失。

 

**注意** 即使应用程序已安装到 MED-V 工作区中，你可能还需要先发布该应用程序，然后才能向最终用户提供该应用程序。 例如，如果安装未在 "**开始**" 菜单上自动创建快捷方式，则可能必须发布已安装的应用程序。 同样，若要取消发布应用程序，您可能需要手动从 "**开始**" 菜单中删除快捷方式。

默认情况下，当自动创建和启用快捷方式时，大部分应用程序会在安装时发布。

 

## 相关主题


[如何测试应用程序发布](how-to-test-application-publishing.md)

[如何在 MED-V 工作区上发布和取消发布应用程序](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





