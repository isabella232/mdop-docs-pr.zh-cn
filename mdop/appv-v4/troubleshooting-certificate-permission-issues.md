---
title: 解决证书权限问题
description: 解决证书权限问题
author: dansimp
ms.assetid: 06b8cbbc-93fd-44aa-af39-2d780792d3c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 728c35b9f51c8f2e18db8acd63708c70bb5d3100
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798725"
---
# 解决证书权限问题


在安装 app-v 4.5 后，如果未使用网络服务的正确 ACL 配置私钥，则会在 NT 事件日志中记录一个事件，并在该文件中放置一个条目 `Sft-server.log` 。

## 错误消息


### Windows Server2003

事件 ID 36870-尝试访问 SSL 服务器凭据私钥时发生严重错误。 从加密模块返回的错误代码为0x80090016。

### Windows Server2008

事件 ID 36870-尝试访问 SSL 服务器凭据私钥时发生严重错误。 从加密模块返回的错误代码为0x8009030d。

## Sft-server


位于目录中的文件中将放置以下错误 `sft-server.log` `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` ：

无法加载证书。 错误代码 \ [-2146893043 \]。 确保网络服务帐户对证书及其相应的私钥文件具有正确的访问权限。

 

 





