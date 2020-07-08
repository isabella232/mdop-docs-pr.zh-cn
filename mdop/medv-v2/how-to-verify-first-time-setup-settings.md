---
title: 如何验证首次安装设置
description: 如何验证首次安装设置
author: dansimp
ms.assetid: e8a07d4c-5786-4455-ac43-2deac4042efd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859d627ec90fbc26d18019062d5e316f907cec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798192"
---
# 如何验证首次安装设置


测试首次设置运行或完成后，你可以通过执行以下任务来验证你在 MED-V 工作区中配置的设置。

**注意** 有关如何在部署后监视整个企业中首次设置成功完成的信息，请参阅[监视 Med-v 工作区部署](monitoring-med-v-workspace-deployments.md)。

 

**首次设置时验证设置**

1.  首次运行安装程序时，请验证以下各项：

    如果你指定了**无人参与**模式，请验证是否在首次运行设置时未显示虚拟机。

    如果指定了参与模式，请验证虚拟机是否显示，以及是否显示需要用户输入的所有字段。

2.  你还可以通过在首次设置运行时查看虚拟机来监视第一次完成的设置过程。 为此，请执行下列步骤：

    1.  打开 Windows 虚拟 PC 控制台。

        单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc**"，然后单击 " **windows 虚拟 pc**"。

    2.  如果尚未运行 MED-V，请启动它。

        如果在短时间内尚不存在，则会在虚拟机列表中显示一个虚拟机，其中包含已部署的 MED-V 工作区的名称。

    3.  双击 "MED-V 虚拟机" 将其打开。

        你可以在设置 MED-V 虚拟机时看到它，并且你可以对最小化安装过程进行故障排除。 验证不同屏幕中的信息，例如配置网络设置、计算机域加入信息、来宾代理配置、设置个人设置和关机。

    4.  当首次设置完成时，虚拟机将自动关闭。

        **注意** 你可以随时关闭虚拟机窗口，并且首次继续安装。

         

**首次设置完成后验证设置**

1.  确保首次安装成功完成。

2.  验证 MED-V 工作区是否设置正确。

    1.  打开 Windows 虚拟 PC 控制台。

        单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc**"，然后单击 " **windows 虚拟 pc**"。

    2.  双击已安装的 MED-V 工作区。

        如果 MED-V 工作区已经在运行虚拟应用程序，系统可能会提示你关闭该应用程序，然后才能打开虚拟机。

    3.  在 MED-V 工作区中，右键单击 **"我的电脑**"，然后单击 "**属性**"。

    4.  验证 MED-V 工作区是否加入了正确的域。 如果适用于你的组织，请通过指定两个不同的域来测试域加入，以验证来宾域是否被主机域重写。

    5.  验证 MED-V 工作区是否加入了您指定的域组织单位。

    6.  如果你指定了计算机名称掩码，请验证新计算机名称是否与指定的名称相匹配。

3.  验证指定的区域设置是否正确。

    1.  在 MED-V 工作区中，单击 "**开始**"，然后单击 "**控制面板"**。

    2.  验证指定的配置设置，例如 "**日期和时间**" 以及 "**区域和语言**"。

**注意** 如果您在验证首次设置设置时遇到任何问题，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。

 

验证你的首次设置是否正确后，你可以测试其他 MED-V 工作区配置，以验证它们是否按预期运行，例如应用程序发布和 URL 重定向。

完成 MED-V 工作区程序包的所有测试并验证它是否按预期运行后，你可以将 MED-V 工作区部署到你的企业。

## 相关主题


[如何测试应用程序发布](how-to-test-application-publishing.md)

[如何测试 URL 重定向](how-to-test-url-redirection.md)

[部署 MED-V 工作区程序包](deploying-the-med-v-workspace-package.md)

[管理 MED-V 工作区设置](manage-med-v-workspace-settings.md)

 

 





