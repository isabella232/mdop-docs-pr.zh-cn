---
title: 如何使用 DaRT 恢复映像恢复本地计算机
description: 如何使用 DaRT 恢复映像恢复本地计算机
author: dansimp
ms.assetid: f679d522-49ab-429c-93d0-294c3f3e5639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1b5faa0eb9ac24b33c66f1d5262a050b92e11e52
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803542"
---
# 如何使用 DaRT 恢复映像恢复本地计算机


当您在遇到问题的最终用户计算机上物理显示时，请使用这些说明来恢复计算机。

**如何使用 DaRT 恢复映像恢复本地计算机**

1.  使用 Microsoft 诊断和恢复工具集（DaRT）8.0 恢复映像启动最终用户计算机。

    当计算机启动到 DaRT 8.0 恢复映像时，将出现 " **NetStart** " 对话框。

2.  当系统询问您是否要初始化网络服务时，请选择下列操作之一：

    **是**-假定 DHCP 服务器在网络上存在，并且尝试从服务器获取 IP 地址的尝试。 如果网络使用静态 IP 地址而不是 DHCP，则可以在以后使用 DaRT 中的**Tcp/ip 配置**工具指定静态 ip 地址。

    **No** -跳过网络初始化过程。

3.  指明是否要重新映射驱动器号。 当您运行 Windows online 时，系统卷通常映射到驱动器 C。但是，当你在 WinRE 下运行 Windows 时，原始系统卷可能会映射到其他驱动器，这可能会引起混淆。 如果您决定重新映射，DaRT 将尝试映射脱机驱动器号以匹配联机驱动器号。 仅在启动过程中稍后选择了脱机操作系统时，才会执行重映射。

4.  在 "**系统恢复选项**" 对话框中，选择一个键盘布局。

5.  检查显示的系统根目录、所安装的操作系统类型和分区大小。 如果您没有看到您的操作系统列出，并且怀疑缺少驱动程序可能导致故障，请单击 "**加载驱动程序**" 以加载可疑驱动程序，然后插入设备的安装媒体并选择驱动程序。

6.  选择要修复或诊断的安装，然后单击 "**下一步**"。

    **注意**  
    如果 Windows 恢复环境（WinRE）检测到或怀疑 Windows 8 在最后一次尝试时未正确启动，则**启动修复**可能会开始自动运行。



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. 在 "**系统恢复选项**" 窗口中，单击 " **Microsoft 诊断和恢复工具集**"。

   将打开 "**诊断和恢复工具集**" 窗口。 现在，你可以运行在创建 DaRT 恢复映像时所包含的任何单个工具或向导。

你可以单击 "**诊断和恢复工具集**" 窗口上的 "**帮助**"，打开客户端帮助文件，该文件提供运行单个 DaRT 工具所需的详细说明和信息。 您也可以在 "**诊断和恢复工具集**" 窗口中单击 "**解决方案向导**"，根据向导提供的简短面试，选择适合情况的最佳工具。

有关任何 DaRT 工具的一般信息，请参阅[DaRT 8.0 中的工具概述](overview-of-the-tools-in-dart-80-dart-8.md)。

**如何在命令提示符处运行 DaRT**

- 若要在命令提示符处运行 DaRT，请指定**netstart.exe**命令，然后使用以下任一参数：

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <tbody>
  <tr class="odd">
  <td align="left"><p><strong>参数</strong></p></td>
  <td align="left"><p><strong>描述</strong></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>-网络</p></td>
  <td align="left"><p>初始化网络服务。</p></td>
  </tr>
  <tr class="odd">
  <td align="left"><p>-重新装载</p></td>
  <td align="left"><p>重新映射驱动器号。</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>-提示</p></td>
  <td align="left"><p>显示要求最终用户指定是否初始化网络并重新映射驱动器的消息。</p>
  <div class="alert">
  <strong>警告</strong><br/><p>最终用户对提示的响应将覆盖 "网络" 和 "-重新装载" 开关。</p>
  </div>
  <div>

  </div></td>
  </tr>
  </tbody>
  </table>



## 相关主题


[DaRT 8.0 的操作](operations-for-dart-80-dart-8.md)

[使用 DaRT 8.0 恢复计算机](recovering-computers-using-dart-80-dart-8.md)









