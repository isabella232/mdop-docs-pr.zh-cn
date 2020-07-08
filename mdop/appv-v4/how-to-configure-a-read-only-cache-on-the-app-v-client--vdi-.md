---
title: 如何在 App-V Client (VDI) 上配置只读缓存
description: 如何在 App-V Client (VDI) 上配置只读缓存
author: dansimp
ms.assetid: 7a41e017-9e23-4a6a-a659-04d23f008b83
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 114f9dfbf55a3f62b6bc8bec6b37a659ffbfaf56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801619"
---
# 如何在 App-V Client (VDI) 上配置只读缓存


在 Microsoft Application Virtualization （App-v）4.6 中，客户端支持使用共享的只读缓存。 共享的只读缓存使客户能够在虚拟桌面基础结构（VDI）系统中高效使用磁盘空间，用户在其中运行在数据中心服务器环境中托管的虚拟机（VM）上的应用程序，并在存储区域网络（SAN）上共享网络存储。 以下过程概述了在任一主 VDI 体系结构（称为 "共用 VM" 或 "静态 VM"）中实现 App-v 客户端所需的过程。 假定你熟悉 App V 系统及其组件的计划、部署和操作，以及 VDI 服务器的操作和管理。）。 有关 App-v 的详细信息，请参阅[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkId=122939)（https://go.microsoft.com/fwlink/?LinkId=122939)

**注意** 这些过程中概述的详细信息仅用作示例。 你可以使用不同的方法来完成整个过程。

 

## 在 VDI 方案中部署 app-v 客户端


你可以使用已填充所有用户所需的所有应用程序的共享只读缓存，在 VDI 方案中部署 app-v 客户端。 然后，配置 VDI 主 VM 映像，以便所有 App-v 客户端都使用相同的缓存文件。 用户通过使用 App-v 发布过程向用户授予对特定应用程序的访问权限。 由于缓存已预加载了所有应用程序，因此当用户启动应用程序时，不会发生流。 但是，用于预填充缓存的程序包必须放置在支持实时流协议（RTSP）流的 app-v 服务器上，并且授予对 App-v 客户端的访问权限。 如果使用 App-v 管理服务器发布应用程序，则可以使用它来提供此流函数。

部署过程由四个主要任务组成：

-   创建和填充主共享缓存文件

-   将共享缓存文件复制到 VDI 服务器存储

-   在 VDI 主映像上配置 App-v 客户端软件

-   在初始部署后管理共享缓存文件的更新部署周期

这些任务需要仔细规划。 我们建议你为你的组织准备并记录可重复执行的流程。 这对于主共享缓存文件的初始准备和部署尤其重要，对于应用程序更新，每个更新都需要更新主共享缓存。 使用以下过程完成这些主要任务。

**注意** 虽然你可以使用多种不同的方法发布应用程序，但以下过程基于用于发布的 app-v 管理服务器的使用。

 

**在池中的 VM VDI 或静态 VM VDI 方案中配置初始部署的只读缓存**

1. 在 VDI 服务器上的 VM 中设置和配置 app-v 管理服务器，以提供用户身份验证和发布支持。

2. 将此管理服务器的内容文件夹填充给所有用户所需的所有应用程序包。

3. 设置已安装 App-v 客户端的暂存计算机。 使用具有对所有应用程序的访问权限的帐户登录到暂存计算机，以便将整个应用程序集发布到计算机，然后将应用程序流式传输到缓存，以便完全加载这些应用程序。

   **重要提示**  
   暂存计算机必须使用与应用 V 客户端将运行的 Vm 所使用的相同操作系统类型和系统体系结构。

     

4. 在安全模式下重新启动暂存计算机以确保驱动程序未启动，这将锁定缓存文件。

   **注意**  
   或者，你可以停止和禁用应用程序虚拟化服务，然后重新启动计算机。 复制文件后，请记住启用并再次启动服务。

     

5. 将 Sftfs 缓存文件复制到 VDI 服务器的 SAN，其中所有 Vm 都可以访问它，例如在共享文件夹中。 将组的 "文件夹访问权限" 设置为 "对所有人只读"，并对将管理缓存文件更新的管理员拥有 "完全控制"。 可以从注册表中获取缓存文件的位置 AppFS\\FileName。

   **重要提示**  
   你必须将 FSD 文件放在具有与本地连接的存储性能（如 SAN）等效的响应性和可靠性的位置。

     

6. 在 VDI 主 VM 镜像上安装 app-v 桌面客户端，然后将其配置为使用只读缓存，方法是将以下注册表项值添加到客户端上的 AppFS 项。 AppFS 键位于 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\AppFS。

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">项</th>
   <th align="left">类型</th>
   <th align="left">值</th>
   <th align="left">用途</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>FileName</p></td>
   <td align="left"><p>字符串</p></td>
   <td align="left"><p>FSD 的路径</p></td>
   <td align="left"><p>指定共享缓存文件的路径，例如 \VDIServername\Sharefolder\SFTFS。FSD （必需）。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReadOnlyFSD</p></td>
   <td align="left"><p>DWORD</p></td>
   <td align="left"><p>raid-1</p></td>
   <td align="left"><p>将客户端配置为以只读模式运行。 这可确保客户端不会尝试将更新传输到程序包缓存。 （必需）</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ErrorLogLocation</p></td>
   <td align="left"><p>字符串</p></td>
   <td align="left"><p>错误日志（.etl）文件的路径</p></td>
   <td align="left"><p>用于指定错误日志路径的条目。 建议您使用. 使用本地路径，如 C:\Logs\Sftfs.etl）。</p></td>
   </tr>
   </tbody>
   </table>

     

7. 将主 VM 映像客户端配置为使用发布服务器，并在登录时使用发布刷新。 当用户登录到 VDI 系统并且其 VM 是从主 VM 映像生成时，将发生发布刷新周期并发布其帐户已获得授权的所有应用程序。 这些应用程序从共享缓存中运行。

**在池中的 VM 方案中为程序包升级配置客户端**

1.  完成应用程序包的升级和测试。

2.  升级 app-v 服务器上的程序包。 然后，将新版本的应用程序发布并流式传输到暂存计算机上的客户端，以便它们完全加载到缓存中。

3.  在安全模式下重新启动暂存计算机，以确保驱动程序未启动。

    **注意** 或者，您可以在 services.msc 中停止和禁用应用程序虚拟化服务，然后重新启动计算机。 复制文件后，请记住启用并再次启动服务。

     

4.  将 Sftfs 缓存文件复制到 VDI 服务器的 SAN，其中所有 Vm 都可以访问它，例如在共享文件夹中。 你可以使用不同的文件名，例如，SFTFS \ _V2。FSD，以区分新版本。

5.  若要在 VDI 主机 VM 映像上配置 app-v 桌面客户端以使用更新的共享缓存文件，请将 AppFS 注册表项文件名值更改为指向已更新文件的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD. 当用户注销然后再次登录时，将使用已更新的主映像为其创建新的 VM。 将保留所有用户设置并将其应用到新 VM。 然后他们有权访问已更新的应用程序。

**在静态 VM 方案中为程序包升级配置客户端**

1.  完成应用程序包的升级和测试。

2.  升级 app-v 服务器上的程序包。 然后，将新版本的应用程序发布并流式传输到暂存计算机上的客户端，以便将应用程序完全加载到缓存中。

3.  在安全模式下重新启动暂存计算机，以确保不会启动驱动程序。

    **注意** 或者，您可以在 services.msc 中停止和禁用应用程序虚拟化服务，然后重新启动计算机。 复制文件后，请记住启用并再次启动服务。

     

4.  将 Sftfs 缓存文件复制到 VDI 服务器的 SAN，其中所有 Vm 都可以访问它，例如在共享文件夹中。 你可以使用不同的文件名，例如，SFTFS \ _V2。FSD，以区分新版本。

5.  若要在 VDI 主机 VM 映像上配置 app-v 桌面客户端以使用更新的共享缓存文件，请将 AppFS 注册表项文件名值更改为指向已更新文件的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD. 这可确保新用户获得新版本。

6.  创建编辑 AppFS 键文件名的脚本，以将其设置为更新缓存的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD. 将此脚本配置为当用户注销或登录时运行，以便在 App-v 客户端驱动程序启动之前运行，例如使用组策略设置。 当用户注销并再次登录时，其现有 VM 将更新，并且它们将使用缓存的更新副本。 然后，他们有权访问已更新的应用程序。

## 升级缓存时如何使用符号链接


在每次部署包含新的或已升级的程序包的新缓存文件时，你可以使用以下操作系统中的符号链接： Windows Vista、Windows 7 和 Windows Server 2008，而不是修改 AppFS 项文件名值。 有关符号链接的详细信息，请参阅[符号链接](https://go.microsoft.com/fwlink/?LinkId=157626)（ https://go.microsoft.com/fwlink/?LinkId=157626) 。 相比之下，Windows XP 不支持使用符号链接，您必须改用交接点。 有关联接的详细信息，请参阅 Microsoft 知识库中的[文章 205524](https://go.microsoft.com/fwlink/?LinkId=182553) （ https://go.microsoft.com/fwlink/?LinkId=182553) 以及工具[连接 v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) （） https://go.microsoft.com/fwlink/?LinkId=182554) 。

**配置符号链接以引用缓存**

1.  在初始部署阶段，在 VDI 服务器主机操作系统上以本地管理员身份打开命令提示符窗口。

2.  使用 MKLINK 命令创建符号链接，然后将其配置为指向 Sftfs 文件。

    **     mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd**

3.  在 VDI 主 VM 映像上，使用 "以**管理员身份运行**" 选项打开命令提示符窗口，并授予远程链接权限，以便 VM 可以访问 VDI 主机操作系统上的符号链接。 默认情况下，禁用远程链接权限。

    **fsutil behavior set SymlinkEvaluation R2R：1**

    **注意** 在存储服务器上，必须启用相应的链接权限。 根据 link 和 Sftfs 文件的位置，权限为**L2L： 1**或**L2R： 1**或**R2L** ： 1**或 R2R：1。**

     

4.  在 VDI 主 VM 镜像上配置 app-v 桌面客户端时，将 AppFS 项文件名值设置为等于使用符号链接的 FSD 文件的 UNC 路径;例如，将其设置为 \\\\VDIHostserver\\Symlinkname。 当 App-v 客户端首次访问缓存时，符号链接将向客户端传递一个指向缓存文件的句柄。 只要客户端运行，客户端就会继续使用该句柄。 即使现有客户端已打开旧的共享缓存，符号链接的值也可以安全更新。

5.  当必须升级程序包或将新程序包添加到缓存时，请对静态 VM 或共用 VM 方案执行升级过程中的步骤1到步骤5。 然后，删除符号链接并重新创建以指向共享缓存文件的新版本。 重新启动 VM 时，客户端将收到缓存的更新副本的句柄，因为 VM 使用包含更新符号链接的路径。 然后，用户有权访问新的和更新的应用程序。

## 相关主题


[如何安装 Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)

[如何手动安装 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何使用命令行安装客户端](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





