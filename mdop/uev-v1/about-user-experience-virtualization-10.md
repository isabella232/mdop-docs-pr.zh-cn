---
title: 关于用户体验虚拟化 1.0
description: 关于用户体验虚拟化 1.0
author: dansimp
ms.assetid: 3758b100-35a8-4e10-ac08-f583fb8ddbd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6010f9c4ebc260eec0324fb880dc2c92fd675130
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803223"
---
# <span data-ttu-id="af5d1-103">关于用户体验虚拟化 1.0</span><span class="sxs-lookup"><span data-stu-id="af5d1-103">About User Experience Virtualization 1.0</span></span>


<span data-ttu-id="af5d1-104">Microsoft 用户体验虚拟化（UE-V）监视用户对应用程序设置和 Windows 操作系统设置所做的更改。</span><span class="sxs-lookup"><span data-stu-id="af5d1-104">Microsoft User Experience Virtualization (UE-V) monitors the changes that are made by users to application settings and Windows operating system settings.</span></span> <span data-ttu-id="af5d1-105">将捕获用户设置并将其集中到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="af5d1-105">The user settings are captured and centralized to a settings storage location.</span></span> <span data-ttu-id="af5d1-106">然后，这些设置可应用于用户访问的不同计算机，包括桌面计算机、便携式计算机和虚拟桌面基础结构（VDI）会话。</span><span class="sxs-lookup"><span data-stu-id="af5d1-106">These settings can then be applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="af5d1-107">用户体验虚拟化使用设置位置模板指定监视和集中的用户计算机上的应用程序和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="af5d1-107">User Experience Virtualization uses settings location templates to specify what applications and Windows settings on the user computers are monitored and centralized.</span></span> <span data-ttu-id="af5d1-108">设置位置模板是一个 XML 文件，用于指定与每个应用程序或操作系统设置相关联的文件和注册表位置。</span><span class="sxs-lookup"><span data-stu-id="af5d1-108">The settings location template is an XML file that specifies which file and registry locations are associated with each application or operating system setting.</span></span> <span data-ttu-id="af5d1-109">该模板不包含设置的值;它仅包含要监视的设置的位置。</span><span class="sxs-lookup"><span data-stu-id="af5d1-109">The template does not contain values for the settings; it contains only the locations of the settings that are to be monitored.</span></span>

<span data-ttu-id="af5d1-110">当用户在其计算机上工作时，由 UE-V 监视应用程序设置和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="af5d1-110">The application settings and Windows settings are monitored by UE-V when users are working on their computers.</span></span> <span data-ttu-id="af5d1-111">当用户关闭应用程序时，应用程序设置的值存储在设置存储服务器上。</span><span class="sxs-lookup"><span data-stu-id="af5d1-111">The values for the application settings are stored on the settings storage server when the user closes the application.</span></span> <span data-ttu-id="af5d1-112">当用户注销、计算机处于锁定状态或从计算机远程断开连接时，将存储 Windows 设置的值。</span><span class="sxs-lookup"><span data-stu-id="af5d1-112">The values for the Windows settings are stored when the user logs off, when the computer is locked, or when they disconnect remotely from a computer.</span></span>

<span data-ttu-id="af5d1-113">管理员可以创建 UE-V 设置位置模板来指定将漫游的企业应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="af5d1-113">An administrator can create a UE-V settings location template to specify which enterprise application settings will roam.</span></span> <span data-ttu-id="af5d1-114">UE-V 包含一组针对某些 Microsoft 应用程序和 Windows 设置的设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="af5d1-114">UE-V includes a set of settings location templates for some Microsoft applications and Windows settings.</span></span> <span data-ttu-id="af5d1-115">有关 UE-V 中的默认应用程序和设置的列表，请参阅[规划要与 ue-v 1.0 同步的应用程序](planning-which-applications-to-synchronize-with-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="af5d1-115">For a list of default applications and settings in UE-V, see [Planning Which Applications to Synchronize with UE-V 1.0](planning-which-applications-to-synchronize-with-ue-v-10.md).</span></span>

## <span data-ttu-id="af5d1-116">UEV 1.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="af5d1-116">UEV 1.0 Release Notes</span></span>


<span data-ttu-id="af5d1-117">有关详细信息，以及未使其进入文档的最新消息，请参阅[Microsoft 用户体验虚拟化（ue-v）1.0 发行说明](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="af5d1-117">For more information, and for late-breaking news that did not make it into the documentation, see [Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes](microsoft-user-experience-virtualization--ue-v--10-release-notes.md).</span></span>

## <span data-ttu-id="af5d1-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="af5d1-118">Related topics</span></span>


[<span data-ttu-id="af5d1-119">用户体验虚拟化 1.0 入门</span><span class="sxs-lookup"><span data-stu-id="af5d1-119">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="af5d1-120">Microsoft 用户体验虚拟化 (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="af5d1-120">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="af5d1-121">UE-V 1.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="af5d1-121">High-Level Architecture for UE-V 1.0</span></span>](high-level-architecture-for-ue-v-10.md)

 

 





