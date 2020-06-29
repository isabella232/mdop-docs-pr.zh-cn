---
title: 为 UE-V 准备你的环境
description: 为 UE-V 准备你的环境
author: dansimp
ms.assetid: c93d3b33-e032-451a-9e1b-8534e1625396
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8f806f3c326bad5204a7f1ee69e11b61177e3cce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803610"
---
# 为 UE-V 准备你的环境


Microsoft 用户体验虚拟化（UE-V）通过使用设置存储位置在计算机之间漫游设置。 设置存储位置是一个文件共享，应在 UE-V Agent 部署期间进行配置。 它必须定义为 "设置存储位置" 或 "作为 Active Directory 主目录"。 此外，管理员应将时间服务器配置为支持一致同步。 若要为 UE-V 准备环境，应考虑以下事项：

-   [Ue-v 设置存储](#bkmk-uevsettingsstorage)：

    -   [定义设置存储位置](#bkmk-definingsettingsstoragelocation)

    -   [通过 UE-V 使用 Active Directory 主目录](#bkmk-usingactivedirectoryhomedirectory)

-   [同步 UE-V 设置同步的计算机时钟](#bkmk-synchronizecomputerclocks)

-   [性能和容量规划](#bkmk-performancecapacityplanning)

有关操作系统和计算机要求的详细信息，请参阅[ue-v 1.0 支持的配置](supported-configurations-for-ue-v-10.md)。

## <a href="" id="bkmk-uevsettingsstorage"></a>UE-V 设置存储


你可以使用以下两种配置之一定义用户体验虚拟化设置存储：设置存储位置或 Active Directory 主目录。

### <a href="" id="bkmk-definingsettingsstoragelocation"></a>定义设置存储位置

UE-V 设置存储位置是可由 UE-V 用户访问的标准网络共享。 在定义设置存储位置之前，必须创建根目录。 将在共享上存储设置的用户必须具有对该存储位置的读/写权限。 UE-V Agent 将在此根目录下创建特定于用户的文件夹。 设置存储位置通过设置**SettingsStoragePath**配置选项来定义。 可通过以下方式配置此选项：

-   通过命令行参数或在批处理脚本中安装 UE-V agent 期间。

-   使用组策略。

-   在安装之后，使用 PowerShell 或 WMI。

路径必须位于服务器和共享的通用命名约定（UNC）路径中。 例如， **\\\\server\\settingsshare\\**。 此配置选项支持使用变量来启用特定的漫游方案。

你可以将 `%username%` 变量与服务器的 UNC 路径配合使用，并进行共享。 这将在用户登录的所有计算机或会话上提供相同的设置体验。 在以下情况下，请考虑此配置：

1.  企业中的用户具有多个同样配置的物理计算机，并且每个用户的设置在所有计算机上都应该是相同的。

2.  企业中的用户使用虚拟桌面基础结构（VDI）池，应在每个用户的 VDI 会话中保留设置。

3.  企业中的用户有一台物理计算机，另外还使用 VDI。 无论使用物理计算机还是 VDI 会话，每个用户的设置体验都应相同。

4.  多个用户使用多个企业计算机。 每个用户的设置体验在所有计算机上都应该是相同的。

你可以将 **%username%\\%computername%** 变量与服务器的 UNC 路径一起使用，并进行共享。 这将保留每台计算机的设置体验。 在以下情况下，请考虑此配置：

1.  企业中的用户拥有多台物理计算机，并且您希望保留每台计算机的设置体验。

2.  企业计算机由多个用户使用。 应为用户登录的每台计算机保留设置体验。

UE-V agent 基于 UE-V `SettingsStoragePath` 配置设置和定义的变量动态创建特定于用户的设置存储路径。

UE-V agent 将动态创建 `SettingsPackages` 在每个特定于用户的存储位置中指定的隐藏系统文件夹。 UE-V agent 读取并将设置写入到由注册的 UE-V 设置位置模板定义的位置。

如果用户的一组托管计算机的设置存储位置相同，则适用的 UE-V 设置由 "最后一次写入的 wins" 规则确定。 在一台计算机上运行的代理独立于在其他计算机上运行的代理读取和写入设置位置。 最后写入的设置和值是在下一个代理从设置存储位置读取时应用的设置。 有关详细信息，请参阅[部署 ue-v 1.0 的设置存储位置](deploying-the-settings-storage-location-for-ue-v-10.md)。

### <a href="" id="bkmk-usingactivedirectoryhomedirectory"></a>通过 UE-V 使用 Active Directory 主目录

如果在部署代理时没有为 UE-V 配置设置存储位置，则用户的 Active Directory （AD）主目录将用于存储设置位置程序包。 UE-V agent 将在每个用户的广告主目录的根下动态创建 "设置存储" 文件夹。 如果未另外定义设置存储位置（SettingsStoragePath），则代理仅使用 Active Directory 主目录。

## <a href="" id="bkmk-synchronizecomputerclocks"></a>同步 UE-V 设置同步的计算机时钟


运行 UE-V agent 以同步设置的计算机必须使用时间服务器。 时间戳用于确定是否需要从设置存储位置同步设置。 如果计算机时钟不准确，则较旧的设置可能会覆盖较新的设置，或者新设置可能不会保存到设置存储位置。 使用时间服务器使 UE-V 能够保持一致的设置体验。

## <a href="" id="bkmk-performancecapacityplanning"></a>性能和容量规划


UE-V 的容量要求可以通过使用标准磁盘容量和网络运行状况监视来确定。 UE-V 使用服务器消息块（SMB）共享存储设置程序包。 设置包的大小根据特定应用程序的设置信息而有所不同。 虽然大多数设置程序包较小，但同步可能较大的文件（如桌面映像）可能会导致性能较差，尤其是在速度较慢的网络上。 若要最大限度地减少网络延迟问题，应在用户计算机所在的同一本地网络上创建设置存储位置。

默认情况下，如果网络速度较慢或设置包较大，则 UE-V 同步将在2秒钟后超时。 你可以通过组策略配置超时。 有关如何设置超时的详细信息，请参阅[通过组策略对象配置 ue-v](configuring-ue-v-with-group-policy-objects.md)。

## 相关主题


[Microsoft 用户体验虚拟化 (UE-V) 1.0](index.md)

[规划 UE-V 1.0](planning-for-ue-v-10.md)

[UE-V 1.0 支持的配置](supported-configurations-for-ue-v-10.md)

 

 





