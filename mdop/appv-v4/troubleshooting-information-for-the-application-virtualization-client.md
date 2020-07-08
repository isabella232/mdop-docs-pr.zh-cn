---
title: Application Virtualization Client 的故障排除信息
description: Application Virtualization Client 的故障排除信息
author: dansimp
ms.assetid: 260a8dad-847f-4ec0-b7dd-6e6bc52017ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2ab332f5f3b7f8cdc40f6d35e8712d55028a60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798722"
---
# Application Virtualization Client 的故障排除信息


本主题包含可用于解决应用程序虚拟化（app-v）客户端上的各种问题的信息。

## 发布刷新速度非常慢


如果在特定计算机上发布的刷新时间比预期长得多，并且客户端配置为使用**IconSourceRoot**设置，请确定**IconSourceRoot**是否包含无效的 URL。 无效 URL 将在发布刷新期间产生很长的延迟。

## 用户无法连接到服务器并转到断开连接的操作模式


当你使用配置了 RTSPS 协议的 app-v 管理服务器时，如果用户无法连接，并且它们进入断开连接的操作模式，请确定服务器上正在使用的证书是否有效。 无效证书将阻止用户连接，并将导致用户进入断开连接的操作模式。

## <a href="" id="users-experience-slow-performance-when-applications-are-not-fully-cached-"></a>应用程序不完全缓存时用户遇到性能较慢的情况


当应用程序不完全缓存时，用户在启动或使用该应用程序时偶尔会遇到暂时的缓慢或间歇性性能。 可能出现这种情况的可能原因，例如，当 App-v 客户端正在自动加载应用程序的过程中时，或者正在处理不连续的请求时。 当应用程序完全缓存时，这些问题将不再出现。

## <a href="" id="error-displayed-after-an-update-is-removed-"></a>删除更新后显示的错误


必须使用正确的 Windows Installer 3.1 命令格式从 App-v 客户端中删除更新，如下所示：

`Msiexec /I {F82584A0-D706-4D2D-9BC1-7E6D8BE3BB0F} MSIPATCHREMOVE={BE3DD018-9A1F-40FD-9538-C0A995CBD254} /qb /l*v "Uninstall.log"`

使用较旧的命令格式 `msiexec /package <GUID> /uninstall <GUID>` 将导致错误 6003 "应用程序虚拟化客户端无法启动"。

## 尝试启动应用程序时出现错误代码 0A-0000E01E


错误代码 0A-0000E01E 表示序列化的应用程序包可能已损坏。 解决方案是 resequence 软件包。

## 用户无法访问在问答：驱动器上创建的文件


如果用户将文件保存到**Q：** 驱动器，则无法检索它们，因为它们对驱动器没有读取权限。 用户不应将文件保存到**Q：** 驱动器。

## 用户收到1D1 错误


当打开的软件描述符（OSD）文件中错误地设置了文件流 URL 时，App-v 客户端将返回一个1d1 错误，而不是 "找不到文件" 错误。 此错误表示应用程序启动失败，用户已强制进入断开连接操作模式。 更正文件流 URL。

## 与某些应用程序相关联的错误图标


当要在发布操作中使用图标时，App-v 客户端首先确定它是否已有图标的缓存副本，方法是查看其原始源路径与给定于发布操作的图标路径相匹配的项目的图标缓存。 如果 App-v 客户端找到匹配项，它将使用已缓存的图标;否则，它会将新图标下载到缓存中。 如果图标的路径是暂存目录，或者它为新图标或程序包重用，则缓存中的查找可能会从上一个操作中选择错误的图标。

## 启动应用程序时，系统会提示用户提供凭据


如果用户尝试启动一个系统管理员限制访问的虚拟应用程序，系统可能会提示用户输入凭据。 用户应键入有权启动该应用程序的帐户的用户名和密码，然后按 ENTER。

## 将 App-v 客户端升级到版本4.5 后，发布刷新失败


如果用户数据目录以前放置在非标准位置（%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*用户名*%）中，则在计算机上没有管理员权限的用户将发现在升级 app-v 客户端后发布刷新失败。 在升级期间，App-v 客户端全局数据目录及其所有子目录仅使用管理员的受限访问权限进行配置。 在升级之前更改用户数据目录以使其不是全局数据目录的子目录，可以避免此问题。

## 安装失败后需要重启


如果客户端安装因任何原因而失败，并且如果随后尝试安装客户端也失败，请检查 Windows Installer 日志以查看它是否显示错误 "sftplay 失败，错误 = 1072"。 如果是这样，请重新启动计算机，然后再次尝试安装客户端。

## 修复损坏的虚拟应用程序


如果由于任何原因，使用 Windows 安装程序包（MSI）文件安装的虚拟应用程序包损坏，请重新安装程序包。 Windows 安装程序中提供的修复功能不会更新用户卷。

## 相关主题


[Application Virtualization Client 参考](application-virtualization-client-reference.md)

 

 





