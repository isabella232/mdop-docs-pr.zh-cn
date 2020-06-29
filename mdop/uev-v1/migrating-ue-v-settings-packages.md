---
title: 迁移 UE-V 设置包
description: 迁移 UE-V 设置包
author: dansimp
ms.assetid: 93d99254-3e17-4e96-92ad-87059d8554a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0087f334e916c06e7611d2671d0b50e7d1dd916
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803322"
---
# <span data-ttu-id="bc041-103">迁移 UE-V 设置包</span><span class="sxs-lookup"><span data-stu-id="bc041-103">Migrating UE-V Settings Packages</span></span>


<span data-ttu-id="bc041-104">在 Microsoft 用户体验虚拟化（UE-V）部署的生命周期内，你可能需要在迁移到新服务器或备份时重新定位用户设置包。</span><span class="sxs-lookup"><span data-stu-id="bc041-104">In the lifecycle of a Microsoft User Experience Virtualization (UE-V) deployment, you might need to relocate the user settings packages either when migrating to a new server or for backup purposes.</span></span> <span data-ttu-id="bc041-105">在以下情况下可能需要迁移设置程序包：</span><span class="sxs-lookup"><span data-stu-id="bc041-105">Migration of settings packages might be needed in the following scenarios:</span></span>

-   <span data-ttu-id="bc041-106">将现有服务器硬件升级到新式服务器。</span><span class="sxs-lookup"><span data-stu-id="bc041-106">Upgrade of existing server hardware to a more modern server.</span></span>

-   <span data-ttu-id="bc041-107">将设置存储位置的迁移从实验室共享到生产服务器。</span><span class="sxs-lookup"><span data-stu-id="bc041-107">Migration of a settings storage location share from a lab to a production server.</span></span>

<span data-ttu-id="bc041-108">只需复制文件和文件夹将不会保留安全设置和权限。</span><span class="sxs-lookup"><span data-stu-id="bc041-108">Simply copying the files and folders will not preserve the security settings and permissions.</span></span> <span data-ttu-id="bc041-109">以下所述步骤将正确地将设置程序包文件复制到新共享的 NTFS 权限。</span><span class="sxs-lookup"><span data-stu-id="bc041-109">The following described steps will properly copy the settings package files with their NTFS permissions to a new share.</span></span>

**<span data-ttu-id="bc041-110">如何在迁移到新服务器时保留 UE-V 设置程序包</span><span class="sxs-lookup"><span data-stu-id="bc041-110">How to preserve UE-V settings packages when migrating to a new server</span></span>**

1.  <span data-ttu-id="bc041-111">在其他服务器上的新位置中，创建一个新文件夹;例如，MySettings。</span><span class="sxs-lookup"><span data-stu-id="bc041-111">In a new location on a different server, create a new folder; for example, MySettings.</span></span>

2.  <span data-ttu-id="bc041-112">对旧服务器上的旧文件夹共享禁用共享。</span><span class="sxs-lookup"><span data-stu-id="bc041-112">Disable sharing for the old folder share on the old server.</span></span>

3.  <span data-ttu-id="bc041-113">通过命令行将现有设置包从 Robocopy 移动到新服务器。</span><span class="sxs-lookup"><span data-stu-id="bc041-113">Move the existing settings packages to the new server with Robocopy from the command line.</span></span> <span data-ttu-id="bc041-114">例如：</span><span class="sxs-lookup"><span data-stu-id="bc041-114">For example:</span></span>

    ``` syntax
    c:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    <span data-ttu-id="bc041-115">**注意** 若要监视复制进度，请使用日志文件阅读器（如 Trace32）打开 MySettings.txt。</span><span class="sxs-lookup"><span data-stu-id="bc041-115">**Note** To monitor the copy progress, open MySettings.txt with a log file reader such as Trace32.</span></span>

     

4.  <span data-ttu-id="bc041-116">向新共享授予共享级别的权限。</span><span class="sxs-lookup"><span data-stu-id="bc041-116">Grant share-level permissions to the new share.</span></span> <span data-ttu-id="bc041-117">保留由 Robocopy 设置的 NTFS 权限。</span><span class="sxs-lookup"><span data-stu-id="bc041-117">Leave the NTFS permissions as they were set by Robocopy.</span></span>

    <span data-ttu-id="bc041-118">在运行 UE-V agent 的计算机上，将 SettingsStoragePath 配置设置更新为新共享的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="bc041-118">On computers that run the UE-V agent, update the SettingsStoragePath configuration setting to the UNC path of the new share.</span></span>

## <span data-ttu-id="bc041-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="bc041-119">Related topics</span></span>


[<span data-ttu-id="bc041-120">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="bc041-120">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="bc041-121">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="bc041-121">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





