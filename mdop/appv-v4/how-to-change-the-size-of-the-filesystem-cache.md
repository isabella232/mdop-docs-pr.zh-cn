---
title: 如何更改 FileSystem 缓存的大小
description: 如何更改 FileSystem 缓存的大小
author: dansimp
ms.assetid: 6ed17ba3-293b-4482-b3fa-31e5f606dad6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63c98d53ccb31e8eb64bc70d3d79b2198c506e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801643"
---
# <span data-ttu-id="77caa-103">如何更改 FileSystem 缓存的大小</span><span class="sxs-lookup"><span data-stu-id="77caa-103">How to Change the Size of the FileSystem Cache</span></span>


<span data-ttu-id="77caa-104">你可以使用命令行更改文件系统缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="77caa-104">You can change the size of the FileSystem cache by using the command line.</span></span> <span data-ttu-id="77caa-105">此操作需要完整地重置缓存，并且它需要管理权限。</span><span class="sxs-lookup"><span data-stu-id="77caa-105">This action requires a complete reset of the cache, and it requires administrative rights.</span></span>

**<span data-ttu-id="77caa-106">更改文件系统缓存的大小</span><span class="sxs-lookup"><span data-stu-id="77caa-106">To change the size of the FileSystem cache</span></span>**

1.  <span data-ttu-id="77caa-107">将以下注册表值设置为0（零）：</span><span class="sxs-lookup"><span data-stu-id="77caa-107">Set the following registry value to 0 (zero):</span></span>

    <span data-ttu-id="77caa-108">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span><span class="sxs-lookup"><span data-stu-id="77caa-108">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span></span>

2.  <span data-ttu-id="77caa-109">将以下注册表值设置为包含程序包所需的最大缓存大小（以 MB 为单位），例如，8192 MB：</span><span class="sxs-lookup"><span data-stu-id="77caa-109">Set the following registry value to the maximum cache size, in MB, that is necessary to hold the packages—for example, 8192 MB:</span></span>

    <span data-ttu-id="77caa-110">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\FileSize</span><span class="sxs-lookup"><span data-stu-id="77caa-110">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\FileSize</span></span>

3.  <span data-ttu-id="77caa-111">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="77caa-111">Restart the computer.</span></span>

## <span data-ttu-id="77caa-112">相关主题</span><span class="sxs-lookup"><span data-stu-id="77caa-112">Related topics</span></span>


[<span data-ttu-id="77caa-113">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="77caa-113">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





