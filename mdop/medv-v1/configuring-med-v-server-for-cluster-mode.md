---
title: 将 MED-V 服务器配置为群集模式
description: 将 MED-V 服务器配置为群集模式
author: dansimp
ms.assetid: 41f0b2a3-4ce9-48e1-a6fb-4c13c4228515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddb7dd5af65d8a465c5c1884bb27a3027621bac1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804024"
---
# <span data-ttu-id="a4b69-103">将 MED-V 服务器配置为群集模式</span><span class="sxs-lookup"><span data-stu-id="a4b69-103">Configuring MED-V Server for Cluster Mode</span></span>


<span data-ttu-id="a4b69-104">你可以在群集模式下配置 MED-V 服务器。</span><span class="sxs-lookup"><span data-stu-id="a4b69-104">You can configure the MED-V server in cluster mode.</span></span> <span data-ttu-id="a4b69-105">在群集模式中，将使用两个服务器，并将两个服务器标识为相互的所有文件都放置在文件系统上。</span><span class="sxs-lookup"><span data-stu-id="a4b69-105">In cluster mode, two servers are used and all files identified as mutual to both servers are placed on a file system.</span></span> <span data-ttu-id="a4b69-106">服务器从文件系统访问文件，而不是本地存储文件。</span><span class="sxs-lookup"><span data-stu-id="a4b69-106">The server accesses the files from the file system rather than storing the files locally.</span></span>

## <a href="" id="bkmk-howtoconfigurethemedvserverinclustermode"></a>


**<span data-ttu-id="a4b69-107">在群集模式下配置 MED-V 服务器</span><span class="sxs-lookup"><span data-stu-id="a4b69-107">To configure the MED-V server in cluster mode</span></span>**

1.  <span data-ttu-id="a4b69-108">在其中一个服务器上安装和配置 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a4b69-108">Install and configure MED-V on one of the servers.</span></span>

2.  <span data-ttu-id="a4b69-109">在所有服务器都可以访问的中心位置创建共享网络。</span><span class="sxs-lookup"><span data-stu-id="a4b69-109">Create a shared network in a central location where all of the servers can access it.</span></span>

3.  <span data-ttu-id="a4b69-110">将\* &lt; InstallDir &gt; /Servers/ConfigurationServer\*文件夹的内容复制到共享网络。</span><span class="sxs-lookup"><span data-stu-id="a4b69-110">Copy the contents of the *&lt;InstallDir&gt;/Servers/ConfigurationServer* folder to the shared network.</span></span>

4.  <span data-ttu-id="a4b69-111">在所有指定的服务器上安装 MED-V 服务器。</span><span class="sxs-lookup"><span data-stu-id="a4b69-111">Install MED-V server on all designated servers.</span></span>

5.  <span data-ttu-id="a4b69-112">在共享网络上，分配对所有 MED-V 服务器系统帐户的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="a4b69-112">On the shared network, assign full access to all MED-V server system accounts.</span></span>

6.  <span data-ttu-id="a4b69-113">在每台服务器上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a4b69-113">On each server, do the following:</span></span>

    1.  <span data-ttu-id="a4b69-114">在\* &lt; InstallDir &gt; /Servers/ServerConfiguration.xml*文件中，将* &lt; StorePath &gt; \*的值设置为共享网络路径。</span><span class="sxs-lookup"><span data-stu-id="a4b69-114">In the *&lt;InstallDir&gt;/Servers/ServerConfiguration.xml* file, set the value of *&lt;StorePath&gt;* to the shared network path.</span></span>

    2.  <span data-ttu-id="a4b69-115">将\* &lt; InstsallDir &gt; /Servers/KeyPair.xml\*文件从原始服务器复制到所有 med-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="a4b69-115">Copy the *&lt;InstsallDir&gt;/Servers/KeyPair.xml* file from the original server to all MED-V servers.</span></span>

    3.  <span data-ttu-id="a4b69-116">重新启动 MED-V 服务。</span><span class="sxs-lookup"><span data-stu-id="a4b69-116">Restart the MED-V service.</span></span>

<span data-ttu-id="a4b69-117">**注意** 如果所有服务器都具有相同的本地设置（如侦听端口、IIS 服务器、管理权限、报表数据库等），则\* &lt; InstallDir &gt; /Servers/ServerSettings.xml\*也可以由所有服务器共享。</span><span class="sxs-lookup"><span data-stu-id="a4b69-117">**Note** If all servers have the same local settings (such as listening ports, IIS server, management permissions, report database, and so on), the *&lt;InstallDir&gt;/Servers/ServerSettings.xml* can be shared by all servers as well.</span></span>

 

## <span data-ttu-id="a4b69-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="a4b69-118">Related topics</span></span>


[<span data-ttu-id="a4b69-119">MED-V 基础结构规划和设计</span><span class="sxs-lookup"><span data-stu-id="a4b69-119">MED-V Infrastructure Planning and Design</span></span>](med-v-infrastructure-planning-and-design.md)

 

 





