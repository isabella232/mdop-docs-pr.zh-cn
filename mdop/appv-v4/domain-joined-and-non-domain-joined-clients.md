---
title: 加入域和未加入域的客户端
description: 加入域和未加入域的客户端
author: dansimp
ms.assetid: a935dc98-de60-45f3-ab74-2444ce082e88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4385ab3f26bb867dd649fe768e1500c9d015ffa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803007"
---
# 加入域和未加入域的客户端


App-v 桌面客户端可以配置为允许连接到网络，无论客户端是加入域还是未加入域。

## 加入域的客户端


已加入域但内部网络外部的客户可以通过使用 VPN 连接与 App-v 基础结构通信。 如果你希望向用户提供离开内部网络但仍在应用 V 基础结构中进行通信的功能，你的环境需要极少的设置。 由于用户已是域的一部分，因此只需确保客户端支持缓存的凭据。 这是默认配置，对此设置的任何更改均可通过组策略完成。

如应用程序-V 安全最佳做法指南中所述，用户将尝试将其用户票证发送到 App-v 基础结构进行身份验证。 如果票证已过期，它将还原为使用 NTLM 和计算机上的缓存凭据。 若要允许漫游，管理员必须确保内部访问的发布服务器在外部的名称中可用于正确解析的名称。

## 非域联接的客户端


不加入域但需要在 App-v 基础结构中进行通信的客户端必须配置为确保对 App-v 基础结构的身份验证成功。 App-v 桌面客户端不允许提示发布刷新过程，因此必须将客户端配置为向 App-v 管理服务器提供正确的凭据。

发布服务器配置为从非域加入的客户端发布刷新时，要求客户端访问的外部名称配置为发布服务器的证书上的公用名称或使用者备用名称（SAN）。

## 相关主题


[如何为 Windows Vista 分配正确的凭据](how-to-assign--the-proper-credentials-for-windows-vista.md)

[如何为 Windows XP 分配正确的凭据](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





