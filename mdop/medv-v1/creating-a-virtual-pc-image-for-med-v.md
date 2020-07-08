---
title: 为 MED-V 创建虚拟 PC 映像
description: 为 MED-V 创建虚拟 PC 映像
author: dansimp
ms.assetid: 5e02ea07-25b9-41a5-a803-d70c55eef586
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 84e45f9ff7213abdd6288bcd750238436d3ab68c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803413"
---
# 为 MED-V 创建虚拟 PC 映像


若要创建 MED-V 的虚拟 PC （VPC）映像，必须执行以下操作：

1.  [创建 VPC 图像](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)。

2.  [将 med-v 工作区 .msi 程序包安装到 VPC 映像上](#bkmk-howtoinstallthemedvworkspacemsipackage)。

3.  [在 VPC 映像上运行 med-v 虚拟机先决条件工具](#bkmk-howtorunthevirtualmachineprerequisitestool)。

4.  [在 VPC 映像上手动配置虚拟机先决条件](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites)。

5.  [为 med-v 映像配置 Sysprep](#bkmk-howtoconfiguresysprepformedvimages) （可选）。

6.  [关闭 Microsoft 虚拟 PC](#bkmk-turningoffmicrosoftvirtualpc)。

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a>使用 Microsoft 虚拟 PC 创建虚拟 PC 映像


若要使用 Microsoft 虚拟 PC 创建虚拟 PC 映像，请参阅虚拟 PC 文档。

有关详细信息，请参阅以下内容：

-   [Windows 虚拟电脑帮助](https://go.microsoft.com/fwlink/?LinkId=182378)

-   [创建虚拟机并安装来宾操作系统](https://go.microsoft.com/fwlink/?LinkId=182379)

## <a href="" id="bkmk-howtoinstallthemedvworkspacemsipackage"></a>如何安装 MED-V 工作区 .msi 程序包


创建虚拟 PC 映像后，将 MED-V 工作区 .msi 程序包安装到该映像上。

**安装 MED-V 工作区映像**

1.  启动虚拟机，然后将 MED-V 工作区 .msi 程序包复制到其中。

    "MED-V" 工作区 .msi 程序包称为 " *MED-V\_workspace\_x.msi*"，其中*x*是版本号。

    例如， *MED-V\_workspace\_1.0.65.msi*。

2.  双击 "MED-V" 工作区 .msi 程序包，然后按照安装向导中的说明进行操作。

    **注意**  
    当发布新的 MED-V 版本并更新现有虚拟 PC 映像时，请卸载现有的 MED-V 工作区 .msi 程序包，重新启动计算机，然后安装新的 MED-V 工作区 .msi 程序包。



~~~
**Note**  
After the MED-V workspace .msi package is installed, other products that replace GINA cannot be installed.
~~~



## <a href="" id="bkmk-howtorunthevirtualmachineprerequisitestool"></a>如何运行虚拟机先决条件工具


虚拟机（VM）先决条件工具是一个向导，可自动执行若干先决条件。

**注意**  
尽管许多参数在向导中是可配置的，但 MED-V 的正常运行所需的属性不可配置。



**运行虚拟机先决条件工具**

1.  安装 MED-V 工作区 .msi 程序包后，在 Windows 的 "**开始**" 菜单上，选择 "**所有程序" &gt; med-v &gt; VM 先决条件工具**。

    **注意**  
    运行虚拟机先决条件工具的用户必须具有本地管理员权限，并且必须是唯一登录的用户。



~~~
The **MED-V VM Prerequisite Wizard Welcome** page appears.
~~~

2. 单击“下一步”****。

3. 在 " **Windows 设置**" 页面上，从以下 "可配置属性" 中，选择要配置的属性：

   -   **清除用户的个人历史记录信息**

   -   **清除本地配置文件临时目录**

   -   **在以下 Windows 事件中禁用声音：开始、登录、注销**

   **注意**  
   不要在组策略中启用 Windows 页面保护程序。



4. 单击“下一步”****。

5. 在 " **Internet Explorer 设置**" 页面上，从以下 "可配置属性" 中，选择要配置的属性：

   -   **不要使用自动完成功能**

   -   **禁止重复使用 windows 启动快捷方式**

   -   **清除浏览历史记录**

   -   **在 Internet Explorer 7 中启用选项卡式浏览**

6. 单击“下一步”****。

7. 在 " **Windows 服务**" 页面上，从以下 "可配置属性" 中，选择要配置的属性：

   -   **安全中心服务**

   -   **任务计划程序服务**

   -   **自动更新服务**

   -   **系统还原服务**

   -   **索引服务**

   -   **无线零配置**

   -   **快速用户切换兼容性**

8. 单击“下一步”****。

9. 在 " **Windows 自动登录**" 页面上，执行下列操作：

   1.  选中 "**启用 Windows 自动登录**" 复选框。

   2.  分配**用户名**和**密码**。

10. 单击 "**应用**"，然后在出现的确认框中，单击 **"是"**。

11. 在 "**摘要**" 页面上，单击 "**完成**" 退出向导

**注意**  
验证组策略不覆盖 "先决条件" 工具中设置的强制设置。



## <a href="" id="bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites"></a>如何配置 MED-V 虚拟机手动安装先决条件


某些配置无法通过虚拟机先决条件工具进行配置，必须手动执行。

-   虚拟机设置

    建议在 Microsoft Virtual PC 控制台中配置以下虚拟机设置：

    -   禁用软盘驱动器。

    -   禁用撤消-磁盘（**设置 " &gt; 撤消-磁盘**"）。

    -   确保图像只有一个虚拟 CPU。

    -   消除虚拟机和用户之间的交互，它们与已发布的应用程序（如需要用户输入的消息）无关。

-   图像设置

    在映像内配置下列手动设置：

    1.  在 "**电源选项属性**" 窗口中，禁用休眠和睡眠。

    2.  应用最新的 Windows 更新。

    3.  在 " **Windows 启动和故障恢复**" 对话框中的 "**系统故障**" 部分中，清除 "**自动重新启动**" 复选框。

    4.  确保图像使用 VLK 许可证密钥。

-   安装 VPC 添加

    在 "**操作**" 菜单上，选择 "**安装或更新虚拟机添加**"。

-   配置打印

    你可以通过以下任一方式配置 MED-V 工作区中的打印：

    -   将打印机添加到虚拟机。

    -   允许打印在主机计算机上配置的打印机。

## <a href="" id="bkmk-howtoconfiguresysprepformedvimages"></a>如何配置用于 MED-V 映像的 Sysprep


在 MED-V 工作区中，可以配置 Sysprep，以便分配唯一的安全 ID （SID），特别是在单台计算机上运行多个 MED-V 工作区时。 建议不要使用 Sysprep 加入域;请改为使用 MED-V join 域脚本操作，如[如何设置脚本操作](how-to-set-up-script-actions.md)中所述。

**注意**  
Sysprep 是适用于 Windows 操作系统的 Microsoft 系统准备实用工具。



**在 MED-V 工作区中配置 Sysprep**

1.  在名为*Sysprep*的系统驱动器的根目录中创建目录。

2.  从 Windows 安装 CD 中，将*deploy.cab*提取到系统驱动器的根目录，或从 Microsoft 网站下载最新的部署工具更新。

    -   对于 Windows 2000，请参阅适用[于 windows 2000 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143001)。

    -   对于 Windows XP，请参阅适用[于 WINDOWS xp 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143000)。

3.  运行**安装管理器**（setupmgr.exe）。

4.  按照安装管理器向导。

配置 Sysprep 并创建 MED-V 工作区后，必须执行 Sysprep。

**运行 Sysprep**

1.  在位于系统驱动器根目录下的 Sysprep 文件夹中，运行 "系统准备工具" （Sysprep.exe）。

2.  在出现的 "警告消息" 框中，单击 **"确定"**。

3.  在 " **Sysprep 属性**" 对话框中，选择 "**不重置激活的宽限期**"，然后**使用 "最小化安装**" 复选框。

4.  单击 "重新**封装**"。

5.  如果对显示的确认消息框中列出的信息不满意，请单击 "**取消**" 并更改选择。

6.  单击 **"确定"** 完成系统准备过程。

## <a href="" id="bkmk-turningoffmicrosoftvirtualpc"></a>关闭 Microsoft Virtual PC


安装并配置所有组件后，关闭 "Microsoft 虚拟 PC"，然后选择 "**关闭**"。

## 相关主题


创建 MED-V 图像[如何设置脚本操作](how-to-set-up-script-actions.md)









