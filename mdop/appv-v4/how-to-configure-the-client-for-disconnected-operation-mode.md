---
title: 如何为断开连接操作模式配置客户端
description: 如何为断开连接操作模式配置客户端
author: dansimp
ms.assetid: 3b48464a-b8b4-494b-93e3-9a6d9bd74652
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1c917d87996a26b330551deb04b1828c31fd3c73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801568"
---
# <span data-ttu-id="3bb9e-103">如何为断开连接操作模式配置客户端</span><span class="sxs-lookup"><span data-stu-id="3bb9e-103">How to Configure the Client for Disconnected Operation Mode</span></span>


<span data-ttu-id="3bb9e-104">已断开连接模式启用应用程序虚拟化（app-v）桌面客户端或应用程序虚拟化（以前称为终端服务）客户端，以便在客户端无法连接到 app-v 管理服务器时运行存储在客户端的文件系统缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bb9e-104">The disconnected operation mode enables the Application Virtualization (App-V) Desktop Client or the Application Virtualization (App-V) Client for Remote Desktop Services (formerly Terminal Services) to run applications that are stored in the file system cache of the client when the client cannot connect to the App-V Management Server.</span></span>

<span data-ttu-id="3bb9e-105">**重要提示** 在大型组织中，多个远程桌面会话主机（以前称为终端服务器）服务器（以前称为终端服务器）在服务器场中链接以支持许多用户，使用单个 App-v 管理服务器支持服务器场可表示单个故障点。</span><span class="sxs-lookup"><span data-stu-id="3bb9e-105">**Important** In a large organization where multiple Remote Desktop Session Host (RD°Session Host) servers (formerly Terminal Servers) are linked in a farm to support many users, using a single App-V Management Server to support the farm represents a single point of failure.</span></span> <span data-ttu-id="3bb9e-106">若要提供高可用性来支持 RDSession 主机场，请考虑将两个或更多个 App-v 管理服务器链接到使用同一数据库。</span><span class="sxs-lookup"><span data-stu-id="3bb9e-106">To provide high availability to support the RDSession Host farm, consider linking two or more App-V Management Servers to use the same database.</span></span>

 

**<span data-ttu-id="3bb9e-107">启用断开连接的操作模式</span><span class="sxs-lookup"><span data-stu-id="3bb9e-107">To enable disconnected operation mode</span></span>**

-   <span data-ttu-id="3bb9e-108">将以下注册表项的值设置为1，以启用断开连接的操作模式：</span><span class="sxs-lookup"><span data-stu-id="3bb9e-108">Set the following registry key value equal to 1 to enable disconnected operation mode:</span></span>

    <span data-ttu-id="3bb9e-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="3bb9e-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span></span>

**<span data-ttu-id="3bb9e-110">设置断开连接操作模式使用的时间限制</span><span class="sxs-lookup"><span data-stu-id="3bb9e-110">To set a time limit on disconnected operation mode use</span></span>**

1.  <span data-ttu-id="3bb9e-111">将以下注册表项值设置为1：</span><span class="sxs-lookup"><span data-stu-id="3bb9e-111">Set the following registry key value to 1:</span></span>

    <span data-ttu-id="3bb9e-112">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="3bb9e-112">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span></span>

2.  <span data-ttu-id="3bb9e-113">将以下注册表项值设置为要限制断开连接操作模式的分钟数。</span><span class="sxs-lookup"><span data-stu-id="3bb9e-113">Set the following registry key value to the number of minutes you want to limit disconnected operation mode.</span></span> <span data-ttu-id="3bb9e-114">值的有效范围为1–999999。</span><span class="sxs-lookup"><span data-stu-id="3bb9e-114">The valid range of values is 1–999999.</span></span> <span data-ttu-id="3bb9e-115">默认值为90天或129600分钟。</span><span class="sxs-lookup"><span data-stu-id="3bb9e-115">The default value is 90 days or 129,600 minutes.</span></span>

    <span data-ttu-id="3bb9e-116">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\DOTimeoutMinutes</span><span class="sxs-lookup"><span data-stu-id="3bb9e-116">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\DOTimeoutMinutes</span></span>

**<span data-ttu-id="3bb9e-117">为断开连接操作模式配置远程桌面服务客户端</span><span class="sxs-lookup"><span data-stu-id="3bb9e-117">To configure the Client for Remote Desktop Services for disconnected operation mode</span></span>**

1.  <span data-ttu-id="3bb9e-118">将以下注册表项值设置为1，以启用断开连接的操作模式：</span><span class="sxs-lookup"><span data-stu-id="3bb9e-118">Set the following registry key value to 1 to enable disconnected operation mode:</span></span>

    <span data-ttu-id="3bb9e-119">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="3bb9e-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span></span>

2.  <span data-ttu-id="3bb9e-120">将以下注册表项值设置为0（零），以允许无限制地使用已断开的操作模式：</span><span class="sxs-lookup"><span data-stu-id="3bb9e-120">Set the following registry key value to 0 (zero) to allow unlimited use of disconnected operation mode:</span></span>

    <span data-ttu-id="3bb9e-121">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="3bb9e-121">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span></span>

3.  <span data-ttu-id="3bb9e-122">确保将所有程序包预加载到缓存中，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="3bb9e-122">Ensure that all packages are preloaded into the cache to improve performance.</span></span>

## <span data-ttu-id="3bb9e-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="3bb9e-123">Related topics</span></span>


[<span data-ttu-id="3bb9e-124">断开连接操作模式</span><span class="sxs-lookup"><span data-stu-id="3bb9e-124">Disconnected Operation Mode</span></span>](disconnected-operation-mode.md)

[<span data-ttu-id="3bb9e-125">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="3bb9e-125">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





