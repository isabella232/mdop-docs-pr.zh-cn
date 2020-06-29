---
title: 计划 App-V 5.0 的高可用性
description: 计划 App-V 5.0 的高可用性
author: dansimp
ms.assetid: 6d9a6492-23f8-465c-82e5-49c863594156
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ebf586de7cae19d40d76c9c0c845f93e7bd9021b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798309"
---
# 计划 App-V 5.0 的高可用性


Microsoft Application Virtualization 5.0 （App-v 5.0）系统配置可以利用维护高级别可用服务的选项。

使用以下部分中的信息帮助你了解在高可用性配置中部署 app-v 5.0 的选项。

-   [Microsoft SQL Server 群集支持](#bkmk-sqlcluster)

-   [对 IIS 网络负载平衡的支持](#bkmk-iisloadbal)

-   [在运行（SCS）模式时支持群集文件服务器](#bkmk-clusterscsmode)

-   [Microsoft SQL Server 镜像支持](#bkmk-sqlmirroring)

-   [Microsoft SQL Server 始终支持的支持](#bkmk-sqlalwayson)

## <a href="" id="bkmk-sqlcluster"></a>Microsoft SQL Server 群集支持


你可以在运行 Microsoft SQL Server 群集的计算机上运行 App-v 管理数据库和报告数据库。 但是，必须使用脚本安装数据库。

有关说明，请参阅[如何使用 SQL 脚本部署 App-v 数据库](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)。

## <a href="" id="bkmk-iisloadbal"></a>对 IIS 网络负载平衡的支持


你可以使用 Internet 信息服务（IIS）网络负载平衡为运行 app-v 5 a.x 管理、发布和报告服务（通过 IIS 部署）的计算机配置高可用环境。

有关为运行 Windows Server 操作系统的计算机配置 IIS 和网络负载平衡的详细信息，请参阅以下内容：

-   提供有关配置 Internet Information Services （IIS）7.0 的信息。

    [获得高可用性和可伸缩性-ARR 和 NLB](https://go.microsoft.com/fwlink/?LinkId=316369) （https://go.microsoft.com/fwlink/?LinkId=316369)

-   配置 Microsoft Windows Server

    [网络负载平衡](https://go.microsoft.com/fwlink/?LinkId=316370)（ https://go.microsoft.com/fwlink/?LinkId=316370) 。

    此信息还适用于 Windows Server2008、Windows Server2008R2 或 Windows Server2012 中的 IIS 网络负载平衡（NLB）群集。

    **注意** Windows Server2012 中的 IIS 网络负载平衡功能通常与 Windows Server2008R2 中的功能相同。 但是，在 Windows Server2012 中更改了一些任务的详细信息。 有关执行任务的新方法的信息，请参阅[Windows server 2012 R2 预览版和 Windows server 2012 （）中的常见管理任务和导航](https://go.microsoft.com/fwlink/?LinkId=316371) https://go.microsoft.com/fwlink/?LinkId=316371) 。

     

## <a href="" id="bkmk-clusterscsmode"></a>在运行（SCS）模式时支持群集文件服务器


支持在群集文件服务器的共享内容存储（SCS）模式下运行 app-v 5.0。

以下步骤可用于启用此配置：

-   将 app-v 5.0 配置为在客户端 SCS 模式下运行。 有关配置 App-v 5.0 SCS 模式的详细信息，请参阅[如何为共享内容存储模式安装 app-v 5.0 客户端](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)。

-   使用虚拟 SAN 配置在 Microsoft Server2012 横向扩展模式和预**2012**模式下配置的文件服务器群集。

以下步骤可用于验证配置：

1.  在发布服务器上添加程序包。 有关添加程序包的详细信息，请参阅[如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)。

2.  在运行 App-v 5.0 客户端的计算机上执行发布刷新，然后打开一个应用程序。

3.  切换群集节点中的 "发布更新" 和 "中流"，以确保故障转移正常工作。

有关配置 Windows Server 故障转移群集的详细信息，请参阅以下内容：

-   [清单：创建群集文件服务器](https://go.microsoft.com/fwlink/?LinkId=316372)（ https://go.microsoft.com/fwlink/?LinkId=316372) 。

-   [在 Windows Server 2012 故障转移群集中使用群集共享卷](https://go.microsoft.com/fwlink/?LinkId=316373)（ https://go.microsoft.com/fwlink/?LinkId=316373) 。

## <a href="" id="bkmk-sqlmirroring"></a>Microsoft SQL Server 镜像支持


使用 Microsoft SQL Server 镜像（应用程序 V 5.0 管理服务器数据库是使用两个 SQL Server 实例镜像的），支持 app-v 5.0 管理服务器数据库。

有关配置 Microsoft SQL Server 镜像的详细信息，请查看以下内容：

-   [如何：准备镜像数据库以进行镜像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=316375) （https://go.microsoft.com/fwlink/?LinkId=316375)

-   [使用 Windows 身份验证（SQL Server Management Studio）建立数据库镜像会话](https://go.microsoft.com/fwlink/?LinkId=316377)（https://go.microsoft.com/fwlink/?LinkId=316377)

以下步骤可用于验证配置：

1.  启动 Microsoft SQL Server 镜像会话。

2.  选择 "**故障转移**" 以指定新的主 Microsoft SQL Server 实例。

3.  验证在故障转移后，app-v 5.0 管理服务器是否继续正常工作。

可以修改管理服务器上的连接字符串，以包括**故障转移合作伙伴 = &lt; server2 &gt; **。 这仅有助于当镜像的主映像故障转移到辅助设备，并且运行 App-V 5.0 客户端的计算机执行全新连接时（如重启后）。

使用以下步骤修改连接字符串以包括**故障转移合作伙伴 = &lt; server2 &gt; **：

**重要提示** 本主题介绍如何使用注册表编辑器更改 Windows 注册表。 如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。 在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。 Microsoft 无法保证更改注册表时可能出现的问题可以解决。 更改注册表的风险由您自己承担。

 

1.  登录管理服务器，然后打开**注册表编辑器**。

2.  导航到**HKEY \ _LOCAL \ _MACHINE**  \\  **软件**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**。

3.  通过 "**故障转移合作伙伴 = &lt; &gt; Server2**" 修改**管理 \ _SQL \ _CONNECTION \ _STRING**值。

4.  使用 IIS 控制台重新启动管理服务。

    **注意** 由于 Microsoft sql Server 2012 提供了**AlwaysOn**功能，因此数据库镜像位于 Microsoft sql Server2012 的过时数据库引擎功能列表中。

     

有关详细信息，请单击以下任一链接：

-   [如何：准备镜像数据库以进行镜像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=394235) （ https://go.microsoft.com/fwlink/?LinkId=394235) 。

-   [如何：配置数据库镜像会话（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=394236) （ https://go.microsoft.com/fwlink/?LinkId=394236) 。

-   [使用 Windows 身份验证（SQL Server Management Studio）（即 SQL Server Management Studio）建立数据库镜像会话](https://go.microsoft.com/fwlink/?LinkId=394237) https://go.microsoft.com/fwlink/?LinkId=394237) 。

-   [SQL Server 2012 中已过时的数据库引擎功能](https://go.microsoft.com/fwlink/?LinkId=394238)（ https://go.microsoft.com/fwlink/?LinkId=394238) 。

## <a href="" id="bkmk-sqlalwayson"></a>对 Microsoft SQL Server 的支持始终在配置上


App-v 5.0 管理服务器数据库支持通过 "**始终启用**" 配置对运行 Microsoft SQL server 的计算机进行部署。

## 相关主题


[计划部署 App-V](planning-to-deploy-app-v.md)

 

 





