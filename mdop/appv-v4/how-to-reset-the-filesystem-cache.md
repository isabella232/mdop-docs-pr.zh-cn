---
title: 如何重置 FileSystem 缓存
description: 如何重置 FileSystem 缓存
author: dansimp
ms.assetid: 7777259d-8c21-4c06-9384-9599b69f9828
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 680634d98f8aac048af605c62029a0ee6b20af03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801127"
---
# <span data-ttu-id="87f0c-103">如何重置 FileSystem 缓存</span><span class="sxs-lookup"><span data-stu-id="87f0c-103">How to Reset the FileSystem Cache</span></span>


<span data-ttu-id="87f0c-104">重置文件系统缓存不是通常需要的操作。</span><span class="sxs-lookup"><span data-stu-id="87f0c-104">Resetting the FileSystem cache is not something that should usually be necessary.</span></span> <span data-ttu-id="87f0c-105">但是，如果你需要完全重置文件系统缓存（可能是出于疑难解答目的），则可以使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="87f0c-105">However if you need to completely reset the FileSystem cache, perhaps for troubleshooting purposes, you can use the following procedure.</span></span> <span data-ttu-id="87f0c-106">执行此操作需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="87f0c-106">Administrative rights are required to perform this action.</span></span>

**<span data-ttu-id="87f0c-107">重置文件系统缓存</span><span class="sxs-lookup"><span data-stu-id="87f0c-107">To reset the FileSystem cache</span></span>**

1.  <span data-ttu-id="87f0c-108">将以下注册表值设置为0（零）：</span><span class="sxs-lookup"><span data-stu-id="87f0c-108">Set the following registry value to 0 (zero):</span></span>

    <span data-ttu-id="87f0c-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span><span class="sxs-lookup"><span data-stu-id="87f0c-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span></span>

2.  <span data-ttu-id="87f0c-110">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="87f0c-110">Restart the computer.</span></span>

## <span data-ttu-id="87f0c-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="87f0c-111">Related topics</span></span>


[<span data-ttu-id="87f0c-112">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="87f0c-112">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





