---
title: 规划 Sequencer 安全
description: 规划 Sequencer 安全
author: dansimp
ms.assetid: 8043cb02-476d-4c28-a850-903a8ac5b2d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf1e85e24d93d373add38b5efe51ceb40faae24e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798866"
---
# 规划 Sequencer 安全


配置应用程序虚拟化（app-v）时尽可能早地合并推荐实施做法，以使 Sequencer 实现正常运行并更安全。 如果你已配置了排序器，请使用以下最佳做法指南来重新访问你的设计决策，并从安全角度分析这些决策。

**重要提示**  
App-v Sequencer 将收集和部署运行 Sequencer 的计算机上记录的所有应用程序信息。 你应该确保访问运行 Sequencer 的计算机的所有用户都具有管理凭据。 具有用户帐户凭据的用户不应具有控制程序包内容和程序包文件的访问权限。 如果你正在运行远程桌面服务（以前称为终端服务）的计算机上进行排序，请确保它是专用于序列化的计算机，并且在排序期间没有与用户帐户凭据连接的用户。



## 排序器安全最佳做法


在实现和使用 Application Virtualization （App-v） Sequencer 时，请考虑以下方案和相关的最佳做法：

-   **在运行 sequencer 的计算机上进行病毒扫描**-建议扫描运行 sequencer 的计算机以查找病毒，然后在排序过程中禁用运行 sequencer 的计算机上的所有防病毒和恶意软件检测软件。 这将加快排序过程，并防止防病毒软件组件和反恶意软件组件干扰排序过程。 接下来在未运行 Sequencer 的计算机上安装序列化程序包，并且在成功安装后，扫描该计算机以查找病毒。 如果发现病毒，则应联系软件制造商，通知他们受感染的源文件，并在没有病毒的情况下请求更新的安装源。 或者，可以在安装阶段后对 Sequencer 进行扫描，如果发现了病毒，请按照上述说明联系软件制造商。

    **注意**  
    如果在应用程序中检测到病毒，则不应将应用程序部署到目标计算机。



-   **捕获 ntfs 文件上的访问控制列表（acl）**-app-v Sequencer 捕获在产品安装期间监视的文件的 NTFS 文件系统权限。 此功能使你能够更准确地复制应用程序的预期行为，就像它是在本地安装且未虚拟化。 在某些情况下，应用程序可能会存储用户不打算在应用程序文件中访问的信息。 例如，应用程序可以将凭据信息存储在应用程序内的文件中。 如果在程序包上未强制使用 Acl，则用户有可能查看并在应用程序外部使用此信息。

    **注意**  
    不应序列化存储未加密的特定于安全的信息（如密码等）的应用程序。



~~~
During the installation phase, you can modify the default permissions of the files if necessary. After completion of the sequencing process, but before saving the package, you can choose whether to enforce security descriptors that were captured during the installation of the application. By default, App-V will enforce the security descriptors specified during the installation of the application. If you turn off security descriptor enforcement, you should test the application to ensure the removal of associated Access Control Lists (ACL) will not cause the application to perform unexpectedly.
~~~

-   **Sequencer 不捕获注册表 acl**，尽管 sequencer 会在序列化的安装阶段捕获 NTFS 文件系统 acl，但不会捕获注册表的 acl。 用户将对虚拟应用程序（服务除外）的所有注册表项具有完全访问权限。 但是，如果用户修改了虚拟应用程序的注册表，则该更改将存储在特定的应用商店（**uservol _sftfs \ _v1**）中，并且不会影响其他用户。

-   **应用程序服务**-V 为属于虚拟化应用程序的应用程序服务提供支持。 但是，在虚拟环境中，其运行的安全上下文将受到限制。 虚拟环境中唯一支持的安全上下文是本地系统、本地服务和网络服务。 在排序期间，如果为除支持的三个应用程序服务指定了安全上下文，则会在虚拟环境中应用本地系统安全上下文。 如果将应用程序服务配置为使用本地服务或网络服务，它将在虚拟环境中生效。 在排序过程中，可以使用这三种安全上下文来配置服务帐户。

-   **保留的安全信息**-当排序应用程序时，你可以作为用户安装应用程序，也可以开发自动方法来在监视时安装应用程序。 未从程序包中排除的所有内容将作为该程序包的一部分捕获，因此应用程序将具有在虚拟化环境中运行所需的资源。 某些应用程序在安装期间存储敏感的安全信息（如密码）;如果保持不受保护，则其他用户可以访问此安全信息，这些用户有权访问程序包。 在安装过程中，如果应用程序安装要求输入密码或其他安全敏感信息，请查看文档以确保它不会保留（安装后删除），或者，如果已保留，则它将受到保护（已加密）。

-   **保护虚拟应用程序包**的安全-始终将虚拟应用程序包保存在网络上的安全位置，以防止程序包被篡改或损坏。

## 相关主题


[规划安全和保护](planning-for-security-and-protection.md)









