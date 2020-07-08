---
title: MED-V 事件日志消息
description: MED-V 事件日志消息
author: dansimp
ms.assetid: 7ba7344d-153b-4cc4-a00a-5d42aee9986b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d8dcf1cce48d6c1e29d46b4db7ac1550aa9477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803296"
---
# MED-V 事件日志消息


Microsoft 企业桌面虚拟化（MED-V）2.0 的日志文件提供了有关如何在你的企业中部署和管理 MED-V 的详细信息，并帮助验证功能或帮助解决问题。

## 事件 Id


以下是 MED-V 事件 Id 的列表，可帮助解决在部署或管理 MED-V 时可能遇到的问题。

### Fts

显示首次设置的事件 Id。

### 事件 ID 3066

启动虚拟机操作失败。

<a href="" id="description"></a>**描述**  
你用于创建 MED-V 工作区的虚拟硬盘（VHD）存在潜在问题。

<a href="" id="solution"></a>**解决方案**  
验证你是否可以使用适用于 MED-V 的 VHD 创建虚拟机以及它是否可以启动。

### 事件 ID 3071

虚拟机准备失败。

<a href="" id="description"></a>**描述**  
首次设置时出现问题，可能是由许多不同的问题导致的。 其中包括网络连接问题。

<a href="" id="solution"></a>**解决方案**  
重新启动 MED-V 主机代理，以便首次重新运行设置。

### 事件 ID 3078

虚拟机准备失败。

<a href="" id="description"></a>**描述**  
你用于创建 MED-V 工作区的 VHD 存在潜在问题。

<a href="" id="solution"></a>**解决方案**  
验证你是否可以使用适用于 MED-V 的 VHD 创建虚拟机以及它是否可以启动。

### 事件 ID 3079

重试虚拟机准备。

<a href="" id="description"></a>**描述**  
MED-V 正在尝试准备虚拟机。

<a href="" id="solution"></a>**解决方案**  
不需要执行任何操作。 第一次设置完成。

### 事件 ID 3080

在准备虚拟机时，客户端已停止。

<a href="" id="description"></a>**描述**  
MED-V 在尝试准备虚拟机时意外停止。

<a href="" id="solution"></a>**解决方案**  
启动 MED-V 主机代理并让第一次设置完成

### 事件 ID 3084

虚拟机无效。 首次需要重新运行设置。

<a href="" id="description"></a>**描述**  
MED-V 主机代理检测到虚拟机有问题。

<a href="" id="solution"></a>**解决方案**  
不需要执行任何操作。 第一次设置完成。

### 事件 ID 3099

调用以启动虚拟机失败。

<a href="" id="description"></a>**描述**  
用于创建 MED-V 工作区的 VHD 存在潜在问题。

<a href="" id="solution"></a>**解决方案**  
验证你是否可以使用适用于 MED-V 的 VHD 创建虚拟机以及它是否可以打开。

### VM 管理

### 事件 ID 4022

向 VM 发出命令时出现 VMManagerException 严重错误。

<a href="" id="description"></a>**描述**  
最终用户尝试通过注销或关闭 MED-V 主机来退出 MED-V，并且已超过 VMTaskTimeout 配置设置。

<a href="" id="solution"></a>**解决方案**  
重启 MED-V。

### 事件 ID 4028

虚拟机操作超时。

<a href="" id="description"></a>**描述**  
最终用户尝试通过注销或关闭主机来退出 MED-V，并且已超过 VMTaskTimeout 配置设置。

<a href="" id="solution"></a>**解决方案**  
重启 MED-V。

### 事件 ID 4038

Vmsal 向用户发布了一条错误消息。

<a href="" id="description"></a>**描述**  
向最终用户显示一条错误消息，指出 MED-V 无法启动虚拟应用程序。

<a href="" id="solution"></a>**解决方案**  
如果错误在一行中记录了两次或多次，请停止 MED-V 并使用 Windows 虚拟 PC 控制台连接到虚拟机，并尝试以全屏方式启动应用程序。

### 事件 ID 4040

由于 TerminalServices 未在来宾中初始化，因此回收添加。

<a href="" id="description"></a>**描述**  
由于未在虚拟机上初始化远程桌面服务，因此 MED-V 已重新启动虚拟机。

<a href="" id="solution"></a>**解决方案**  
如果错误在一行中记录了两次或更多次，请停止 MED-V 并使用 Windows 虚拟 PC 控制台连接到虚拟机。

### 事件 ID 4042

无法在来宾中回收添加项。

<a href="" id="description"></a>**描述**  
MED-V 无法在虚拟机上回收虚拟机添加内容。

<a href="" id="solution"></a>**解决方案**  
如果错误在一行中记录了两次或更多次，请停止 MED-V 并使用 Windows 虚拟 PC 控制台连接到虚拟机。

### 事件 ID 4043

无法在虚拟机中重置已过期的密码。

<a href="" id="description"></a>**描述**  
最终用户在虚拟机过期之前，未重置该密码。 因此，用户可能无法访问网络资源或保存工作。

<a href="" id="solution"></a>**解决方案**  
关闭 MED-V 来宾，然后重新启动它。

### URL 重定向

### 事件 ID 5005

无法从配置获取 VM 名称;无法启动来宾浏览器。

<a href="" id="description"></a>**描述**  
URL 重定向无法从配置获取 MED-V 工作区名称。 因此，它无法通知 Windows 虚拟 PC 在 MED-V 工作区浏览器中打开重定向的 URL。

<a href="" id="solution"></a>**解决方案**  
确保 MED-V 工作区名称已设置，并且它与 C:\\Users\\ &lt; *用户*\\Virtual machine 目录中的虚拟机名称相匹配 &gt; 。 MED-V 工作区名称位于 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。

例如，如果用户为 "Matt"，而工作区名称为 "mattsworkspace"，则 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值应为 "mattsworkspace"，并且应存在名为 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的文件

### 事件 ID 5006

无法创建管道服务器。

<a href="" id="description"></a>**描述**  
URL 重定向服务无法创建与 Internet Explorer 通信的管道服务器。

<a href="" id="solution"></a>**解决方案**  
检查系统事件日志以尝试创建路径的文件或资源，其路径开始如下所示： "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_"，以用户的用户名和域名结尾。 如果事件日志中未显示此项，请重新启动计算机。

### ConfigMgr （来宾）

### 事件 ID 7001

主机网络配置数据格式不正确。

<a href="" id="description"></a>**描述**  
从主机收到的网络配置的 XML 字符串格式不正确，或者从主机返回的网络信息无法写入 XML 文档。

<a href="" id="solution"></a>**解决方案**  
重新启动主机和虚拟机。

### 事件 ID 7005

已检测到主机网络配置的更改，但无法应用，因为主机网络配置数据的格式不正确。

<a href="" id="description"></a>**描述**  
对主机网络配置所做的更改已传递到虚拟机，但由于出现错误，无法在虚拟机中进行处理。 此错误可能是由格式不正确的数据或无法将信息设置到 Windows Management Instrumentation （WMI） CCMNetworkAdapter 实例导致的。

<a href="" id="solution"></a>**解决方案**  
重新启动主机和虚拟机。

### ConfigMgr （主机）

### 事件 ID 8006

找不到虚拟机。

<a href="" id="description"></a>**描述**  
Windows Virtual 电脑7找不到虚拟机。 虚拟机可能已被删除、移动、删除或访问被拒绝。

<a href="" id="solution"></a>**解决方案**  
重新安装虚拟机。

### 事件 ID 8008

无法检索工作站的网络配置信息。

<a href="" id="description"></a>**描述**  
无法从 MED-V 主机收集网络配置信息，很可能是因为 .NET Framework 中的系统调用失败。 如果从 MED-V 主机返回的网络信息无法写入 XML 文档，也可能会发生此错误。

<a href="" id="solution"></a>**解决方案**  
重新启动主机工作站。

### 事件 ID 8010

无法在虚拟机中设置网络配置数据。

<a href="" id="description"></a>**描述**  
无法将 MED-V hostnetwork 地址转换（NAT）传递到虚拟机，很可能是因为虚拟机处于错误状态，或者未安装或启用 Windows 虚拟 PC 添加。

<a href="" id="solution"></a>**解决方案**  
关闭并重新启动虚拟机。 此外，你可能需要重新安装虚拟机。

### 事件 ID 8011

无法在虚拟机中重置网络配置数据。

<a href="" id="description"></a>**描述**  
无法将 MED-V hostnetwork 配置（桥）传递到虚拟机，很可能是因为虚拟机处于错误状态，或者未安装或启用 Windows 虚拟 PC 添加。

<a href="" id="solution"></a>**解决方案**  
关闭并重新启动虚拟机。 此外，你可能需要重新安装虚拟机。

### 打印机重定向

### 事件 ID 9001

文件权限错误。

<a href="" id="description"></a>**描述**  
最终用户无权访问打开或创建用于读取的 MED-V 打印机文件所需的文件夹。

<a href="" id="solution"></a>**解决方案**  
验证 User\\AppData\\ 路径是否可访问以及用户是否有权读取和写入该路径。 例如，如果用户是 "Matt"，则路径 C:\\Users\\Matt\\AppData\\ 以及其中的所有文件都应具有 "读取" 和 "写入" 权限。 如果存在，则路径 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 和其中的所有文件都应具有读写权限。

### 事件 ID 9002

文件权限错误。

<a href="" id="description"></a>**描述**  
最终用户无权访问打开或创建用于写入的 MED-V 打印机文件所需的文件夹。

<a href="" id="solution"></a>**解决方案**  
确保可以访问 User\\AppData\\ 路径，并且用户有权读取和写入该路径。 例如，如果用户是 "Matt"，则路径 C:\\Users\\Matt\\AppData\\ 和其中的所有文件都应具有 "读取" 和 "写入" 权限。 如果存在，则路径 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 和其中的所有文件都应具有读写权限。

### 事件 ID 9004

无法创建存储 MEDV 打印机文件的路径。

<a href="" id="description"></a>**描述**  
打印机重定向服务无法访问文件或创建存储打印机信息所需的目录。

<a href="" id="solution"></a>**解决方案**  
验证 User\\AppData\\ 路径是否可访问以及用户是否有权读取和写入该路径。 例如，如果用户是 "Matt"，则路径 C:\\Users\\Matt\\AppData\\ 和其中的所有文件都应具有 "读取" 和 "写入" 权限。 如果存在，则路径 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 和其中的所有文件都应具有读写权限。

### 事件 ID 9005

无法从配置获取 VM 名称;无法启动来宾安装程序。 无法更新 MED-V-未检测到主机网络。

<a href="" id="description"></a>**描述**  
打印机重定向服务无法从 MED-V 配置获取 MED-V 工作区名称，并且无法通知 Windows 虚拟 PC 在 MED-V 来宾上启动安装程序。

<a href="" id="solution"></a>**解决方案**  
确保 MED-V 工作区名称已设置，并且它与 C:\\Users\\ &lt; *用户*\\Virtual machine 目录中的虚拟机名称相匹配 &gt; 。 MED-V 工作区名称位于 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。

例如，如果用户为 "Matt"，而工作区名称为 "mattsworkspace"，则 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值应为 "mattsworkspace"，并且应存在名为 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的文件

### 应用程序发布

### 事件 ID 10015

协调过程中发生文件系统错误。 "协调" 过程不会处理文件名 &lt; *，* &gt; 但会继续处理任何其他更改。

<a href="" id="description"></a>**描述**  
创建或删除快捷方式时发生未经授权的访问或 i/o 错误。

<a href="" id="solution"></a>**解决方案**  
检查文件路径是否可访问，以及用户是否具有创建或删除指定文件的权限。

### 事件 ID 10021

错误 &lt; *\ _information* &gt; ，文件操作 &lt; *操作 \ _name* &gt; 文件 &lt; *文件名* &gt; 时出错。

<a href="" id="description"></a>**描述**  
创建或删除快捷方式时发生未经授权的访问或 i/o 错误。

<a href="" id="solution"></a>**解决方案**  
检查文件路径是否可访问，以及用户是否具有创建或删除指定文件的权限。

### 来宾修补

### 事件 ID 11001

来宾唤醒任务使用消息。

<a href="" id="description"></a>**描述**  
/GuestWakeup 选项的 MedvHost.exe 未正确执行，或者命令的格式不正确。

<a href="" id="solution"></a>**解决方案**  
确保执行以下格式的命令：

Medvhost.exe/GuestWakeup/d： &lt; *duration \ _in \ _minutes* &gt; /v： " &lt; *workspace \ _name* &gt; "，其中

&lt;*duration \ _in \ _minutes* &gt;虚拟机应保持唤醒状态的分钟数（默认值为240）和

&lt;*工作区 \ _name* &gt;是应唤醒的虚拟机的名称。

### 事件 ID 11002

无法更新 MED-V-未检测到主机网络。

<a href="" id="description"></a>**描述**  
由于未检测到主机网络连接，无法完成来宾修补。

<a href="" id="solution"></a>**解决方案**  
在运行来宾修补之前，请将 MED-V 主机连接到活动网络连接。

### 事件 ID 11003

无法更新 MED-V-未在 A/C powerFailed 上运行的主机，无法创建管道服务器。

<a href="" id="description"></a>**描述**  
来宾修补无法完成，因为主机似乎是使用电池电源而不是电源线运行的。

<a href="" id="solution"></a>**解决方案**  
在运行来宾修补之前，请将主机连接到电源线。

### 客户 UX

### 事件 ID 14003

以下托盘状态消息太长，无法显示： &lt; *纸盒 \ _status \ _message*&gt;

<a href="" id="description"></a>**描述**  
MED-V 为任务栏工具提示或气球消息创建了一个太长的意外字符串。 因此，所显示的邮件已被截断。

<a href="" id="solution"></a>**解决方案**  
这是一个很少的错误，在 MED-V 随机创建工具提示文本时可能会发生此错误。 没有解决方案。

### 事件 ID 14004

由于未处理的异常，MED-V 已停止。

<a href="" id="description"></a>**描述**  
未处理的异常导致 MED-V 停止意外停止。

<a href="" id="solution"></a>**解决方案**  
重启 MED-V。

### 事件 ID 14005

服务器试图创建互斥体，但它已经存在。

<a href="" id="description"></a>**描述**  
MedvHost.exe 的第二个实例停留在内存中。

<a href="" id="solution"></a>**解决方案**  
打开 TaskManager 并结束所有 MedvHost.exe 进程。

### 事件 ID 14006

修改或删除注册表值 &lt; *注册表 \ _value*时出错 &gt; 。

<a href="" id="description"></a>**描述**  
MED-V 无法修改注册表中的指定条目。

<a href="" id="solution"></a>**解决方案**  
确保安装或卸载具有管理凭据的 MED-V。

### 事件 ID 14007

指定的文件（ &lt; *文件名* &gt; ）无效。

<a href="" id="description"></a>**描述**  
在安装或卸载期间，已将损坏的临时文件传递到了 MED-V 主机。

<a href="" id="solution"></a>**解决方案**  
删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。

### 事件 ID 14008

找不到文件： &lt; *filename* &gt; 。

<a href="" id="description"></a>**描述**  
在安装或卸载期间，找不到所需 temp 文件的路径。

<a href="" id="solution"></a>**解决方案**  
删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。

### 事件 ID 14009

无法读取参数文件 &lt; *文件名* &gt; 。

<a href="" id="description"></a>**描述**  
在安装或卸载过程中，MED-V 无法读取临时文件。

<a href="" id="solution"></a>**解决方案**  
删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。 此外，验证用户是否具有 Temp 文件夹的必需权限。

### 事件 ID 14010

反序列化参数文件文件名时出错 &lt; *filename* &gt; 。

<a href="" id="description"></a>**描述**  
在安装或卸载过程中，MED-V 遇到损坏的临时文件。

<a href="" id="solution"></a>**解决方案**  
删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。 此外，验证用户是否具有 Temp 文件夹的必需权限。

### 事件 ID 14011

反序列化参数文件文件名时发生意外错误 &lt; *filename* &gt; 。

<a href="" id="description"></a>**描述**  
在安装或卸载过程中，MED-V 遇到损坏的临时文件。

<a href="" id="solution"></a>**解决方案**  
删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。 此外，验证用户是否具有 Temp 文件夹的必需权限。

### 事件 ID 14012

在 &lt; 为用户用户名设置文件夹*文件夹 \ _name*的设置权限时发生意外错误 &gt; &lt; *username* &gt; 。

<a href="" id="description"></a>**描述**  
当 MED-V 无法在安装期间设置某些文件夹的权限和权限时，将出现错误。

<a href="" id="solution"></a>**解决方案**  
检查下列文件夹的管理员权限：

@"%ProgramData%\\Microsoft\\Medv\\AllUsers"

@"%ProgramData%\\Microsoft\\Medv\\MedvLock"

@"%ProgramData%\\Microsoft\\Medv\\Monitoring"

### 事件 ID 14013

创建锁定文件时出现意外错误。

<a href="" id="description"></a>**描述**  
当 MED-V 在安装期间无法在 @ "%ProgramData%\\Microsoft\\Medv\\MedvLock" 文件夹中创建文件时，会出现错误。

<a href="" id="solution"></a>**解决方案**  
检查 MedvLock 文件夹的管理员权限。

## 相关主题


[MED-V 故障排除](troubleshooting-med-vmedv2.md)

 

 





