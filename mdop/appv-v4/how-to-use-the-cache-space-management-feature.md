---
title: 如何使用缓存空间管理功能
description: 如何使用缓存空间管理功能
author: dansimp
ms.assetid: 60965660-c015-46a8-88ac-54cbc050fe33
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fcb9cc4bc076e1acf52fb1c03797384c45b82f7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798965"
---
# <span data-ttu-id="39b09-103">如何使用缓存空间管理功能</span><span class="sxs-lookup"><span data-stu-id="39b09-103">How to Use the Cache Space Management Feature</span></span>


<span data-ttu-id="39b09-104">文件系统缓存空间管理功能使用最近最少使用的（LRU）算法，并且默认情况下处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="39b09-104">The FileSystem cache space management feature uses a Least Recently Used (LRU) algorithm and is enabled by default.</span></span> <span data-ttu-id="39b09-105">如果新程序包所需的空间超过缓存中的可用空间，应用程序虚拟化（app-v）客户端将使用此功能来确定它可以从缓存中删除的现有程序包（如果有），以便为新程序包腾出空间。</span><span class="sxs-lookup"><span data-stu-id="39b09-105">If the space that is required for a new package would exceed the available free space in the cache, the Application Virtualization (App-V) Client uses this feature to determine which, if any, existing packages it can delete from the cache to make room for the new package.</span></span> <span data-ttu-id="39b09-106">如果上次访问日期比在 MinPkgAge 注册表值中指定的值旧，客户端将删除该程序包。</span><span class="sxs-lookup"><span data-stu-id="39b09-106">The client deletes the package with the oldest last-accessed date if it is older than the value specified in the MinPkgAge registry value.</span></span> <span data-ttu-id="39b09-107">使用文件系统缓存空间管理功能还有助于避免缓存空间不足的问题。</span><span class="sxs-lookup"><span data-stu-id="39b09-107">Use of the FileSystem cache space management feature can also help to avoid low cache space problems.</span></span>

<span data-ttu-id="39b09-108">如有必要，将删除多个软件包。</span><span class="sxs-lookup"><span data-stu-id="39b09-108">More than one package is deleted if necessary.</span></span> <span data-ttu-id="39b09-109">锁定的程序包不会被删除。</span><span class="sxs-lookup"><span data-stu-id="39b09-109">Packages that are locked are not deleted.</span></span>

<span data-ttu-id="39b09-110">**注意** 若要确保缓存为所有可能部署的程序包分配了足够的空间，请在配置客户端时使用 "**使用可用磁盘空间阈值**" 设置，以便缓存可以根据需要增长。</span><span class="sxs-lookup"><span data-stu-id="39b09-110">**Note** To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="39b09-111">或者，提前确定应用 V 缓存所需的磁盘空间量，并在安装时设置相应的缓存大小。</span><span class="sxs-lookup"><span data-stu-id="39b09-111">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span>

 

<span data-ttu-id="39b09-112">缓存空间管理功能由 UnloadLeastRecentlyUsed 注册表值控制。</span><span class="sxs-lookup"><span data-stu-id="39b09-112">The cache space management feature is controlled by the UnloadLeastRecentlyUsed registry value.</span></span> <span data-ttu-id="39b09-113">值1启用该功能，值0（零）将禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="39b09-113">A value of 1 enables the feature, and a value of 0 (zero) disables it.</span></span>

**<span data-ttu-id="39b09-114">启用或禁用缓存空间管理功能</span><span class="sxs-lookup"><span data-stu-id="39b09-114">To enable or disable the cache space management feature</span></span>**

-   <span data-ttu-id="39b09-115">将以下注册表值设置为1，以启用 LRU 算法。</span><span class="sxs-lookup"><span data-stu-id="39b09-115">Set the following registry value to 1 to enable the LRU algorithm.</span></span> <span data-ttu-id="39b09-116">将其设置为0（零）以禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="39b09-116">Set it to 0 (zero) to disable the feature.</span></span>

    <span data-ttu-id="39b09-117">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed</span><span class="sxs-lookup"><span data-stu-id="39b09-117">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed</span></span>

**<span data-ttu-id="39b09-118">控制可以丢弃哪些程序包</span><span class="sxs-lookup"><span data-stu-id="39b09-118">To control which packages can be discarded</span></span>**

-   <span data-ttu-id="39b09-119">若要确定何时可以选择要放弃的程序包，请将以下注册表值设置为等于自上次访问程序包后所需的最少天数。</span><span class="sxs-lookup"><span data-stu-id="39b09-119">To determine when the package can be selected for discard, set the following registry value to equal the minimum number of days you want to elapse since the package was last accessed.</span></span> <span data-ttu-id="39b09-120">不会放弃最近使用过的程序包。</span><span class="sxs-lookup"><span data-stu-id="39b09-120">Packages that have been used more recently are not discarded.</span></span>

    <span data-ttu-id="39b09-121">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge</span><span class="sxs-lookup"><span data-stu-id="39b09-121">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge</span></span>

    <span data-ttu-id="39b09-122">**小心** 此注册表项的最大值为0x00011111。</span><span class="sxs-lookup"><span data-stu-id="39b09-122">**Caution** The maximum value for this registry key is 0x00011111.</span></span> <span data-ttu-id="39b09-123">较大值将阻止缓存空间管理功能的正确操作。</span><span class="sxs-lookup"><span data-stu-id="39b09-123">Larger values will prevent the correct operation of the cache space management feature.</span></span>

     

## <span data-ttu-id="39b09-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="39b09-124">Related topics</span></span>


[<span data-ttu-id="39b09-125">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="39b09-125">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





