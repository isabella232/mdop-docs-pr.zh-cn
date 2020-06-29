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
# <span data-ttu-id="e9bf5-103">解决证书权限问题</span><span class="sxs-lookup"><span data-stu-id="e9bf5-103">Troubleshooting Certificate Permission Issues</span></span>


<span data-ttu-id="e9bf5-104">在安装 app-v 4.5 后，如果未使用网络服务的正确 ACL 配置私钥，则会在 NT 事件日志中记录一个事件，并在该文件中放置一个条目 `Sft-server.log` 。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-104">After the installation of App-V4.5, if the private key has not been configured with the proper ACL for the Network Service, an event is logged in the NT Event Log and an entry is placed in the `Sft-server.log` file.</span></span>

## <span data-ttu-id="e9bf5-105">错误消息</span><span class="sxs-lookup"><span data-stu-id="e9bf5-105">Error Messages</span></span>


### <span data-ttu-id="e9bf5-106">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="e9bf5-106">Windows Server2003</span></span>

<span data-ttu-id="e9bf5-107">事件 ID 36870-尝试访问 SSL 服务器凭据私钥时发生严重错误。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-107">Event ID 36870—A fatal error occurred when attempting to access the SSL server credential private key.</span></span> <span data-ttu-id="e9bf5-108">从加密模块返回的错误代码为0x80090016。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-108">The error code returned from the cryptographic module is 0x80090016.</span></span>

### <span data-ttu-id="e9bf5-109">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="e9bf5-109">Windows Server2008</span></span>

<span data-ttu-id="e9bf5-110">事件 ID 36870-尝试访问 SSL 服务器凭据私钥时发生严重错误。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-110">Event ID 36870—A fatal error occurred when attempting to access the SSL server credential private key.</span></span> <span data-ttu-id="e9bf5-111">从加密模块返回的错误代码为0x8009030d。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-111">The error code returned from the cryptographic module is 0x8009030d.</span></span>

## <span data-ttu-id="e9bf5-112">Sft-server</span><span class="sxs-lookup"><span data-stu-id="e9bf5-112">Sft-server.log</span></span>


<span data-ttu-id="e9bf5-113">位于目录中的文件中将放置以下错误 `sft-server.log` `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` ：</span><span class="sxs-lookup"><span data-stu-id="e9bf5-113">The following error is placed in the `sft-server.log` file located in the `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` directory:</span></span>

<span data-ttu-id="e9bf5-114">无法加载证书。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-114">Certificate could not be loaded.</span></span> <span data-ttu-id="e9bf5-115">错误代码 \ [-2146893043 \]。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-115">Error code \[-2146893043\].</span></span> <span data-ttu-id="e9bf5-116">确保网络服务帐户对证书及其相应的私钥文件具有正确的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e9bf5-116">Make sure that the Network Service account has proper access to the certificate and its corresponding private key file.</span></span>

 

 





