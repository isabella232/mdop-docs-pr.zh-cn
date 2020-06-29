---
title: 迁移 UE-V 2 x-blade 设置程序包
description: 迁移 UE-V 2 x-blade 设置程序包
author: dansimp
ms.assetid: f79381f4-e142-405c-b728-5c048502aa70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0aa1f1c36594d69de40306dfa70a4a0cf5c86dbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803784"
---
# <span data-ttu-id="27708-103">迁移 UE-V 2 x-blade 设置程序包</span><span class="sxs-lookup"><span data-stu-id="27708-103">Migrating UE-V 2.x Settings Packages</span></span>


<span data-ttu-id="27708-104">在 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 部署的生命周期中，你可能需要在迁移到新服务器或执行备份时重新定位用户设置包。</span><span class="sxs-lookup"><span data-stu-id="27708-104">In the lifecycle of a Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 deployment, you might have to relocate the user settings packages either when you migrate to a new server or when you perform backups.</span></span> <span data-ttu-id="27708-105">在以下情况下，可能需要迁移设置程序包：</span><span class="sxs-lookup"><span data-stu-id="27708-105">Settings packages might have to be migrated in the following scenarios:</span></span>

-   <span data-ttu-id="27708-106">将现有服务器硬件升级到新式服务器。</span><span class="sxs-lookup"><span data-stu-id="27708-106">Upgrade of existing server hardware to a more modern server.</span></span>

-   <span data-ttu-id="27708-107">将设置存储位置从测试服务器迁移到生产服务器。</span><span class="sxs-lookup"><span data-stu-id="27708-107">Migration of a settings storage location share from a test server to a production server.</span></span>

<span data-ttu-id="27708-108">只需复制文件和文件夹，就不会保留安全设置和权限。</span><span class="sxs-lookup"><span data-stu-id="27708-108">Simply copying the files and folders does not preserve the security settings and permissions.</span></span> <span data-ttu-id="27708-109">以下步骤介绍了如何将设置包及其 NTFS 文件系统权限正确复制到新共享。</span><span class="sxs-lookup"><span data-stu-id="27708-109">The following steps describe how to correctly copy the settings package along with their NTFS file system permissions to a new share.</span></span>

**<span data-ttu-id="27708-110">在迁移到新服务器时保留 UE-V 2 设置程序包</span><span class="sxs-lookup"><span data-stu-id="27708-110">To preserve UE-V 2 settings packages when you migrate to a new server</span></span>**

1.  <span data-ttu-id="27708-111">在其他服务器上的新位置中，创建一个新文件夹，例如 MySettings。</span><span class="sxs-lookup"><span data-stu-id="27708-111">In a new location on a different server, create a new folder, for example, MySettings.</span></span>

2.  <span data-ttu-id="27708-112">对旧服务器上的旧文件夹共享禁用共享。</span><span class="sxs-lookup"><span data-stu-id="27708-112">Disable sharing for the old folder share on the old server.</span></span>

3.  <span data-ttu-id="27708-113">通过 Robocopy 将现有设置包复制到新服务器</span><span class="sxs-lookup"><span data-stu-id="27708-113">To copy the existing settings packages to the new server with Robocopy</span></span>

    ``` syntax
    C:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    <span data-ttu-id="27708-114">**注意** 若要监视复制进度，请使用日志查看器（如 Trace32）打开 MySettings.txt。</span><span class="sxs-lookup"><span data-stu-id="27708-114">**Note** To monitor the copy progress, open MySettings.txt with a log viewer such as Trace32.</span></span>

     

4.  <span data-ttu-id="27708-115">向新共享授予共享级别的权限。</span><span class="sxs-lookup"><span data-stu-id="27708-115">Grant share-level permissions to the new share.</span></span> <span data-ttu-id="27708-116">保留由 Robocopy 设置的 NTFS 文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="27708-116">Leave the NTFS file system permissions as they were set by Robocopy.</span></span>

    <span data-ttu-id="27708-117">在运行 UE-V Agent 的计算机上，将**SettingsStoragePath**配置设置更新为新共享的通用命名约定（UNC）路径。</span><span class="sxs-lookup"><span data-stu-id="27708-117">On computers that run the UE-V Agent, update the **SettingsStoragePath** configuration setting to the Universal Naming Convention (UNC) path of the new share.</span></span>

    <span data-ttu-id="27708-118">已**获得有关 ue-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="27708-118">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="27708-119">在[此处](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="27708-119">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="27708-120">是否**遇到了 ue-v 问题**？</span><span class="sxs-lookup"><span data-stu-id="27708-120">**Got a UE-V issue**?</span></span> <span data-ttu-id="27708-121">使用[Ue-v TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="27708-121">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="27708-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="27708-122">Related topics</span></span>


[<span data-ttu-id="27708-123">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="27708-123">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

 

 





