---
title: MBAM 2.0 的高可用性
description: MBAM 2.0 的高可用性
author: dansimp
ms.assetid: 244ee013-9e2a-48d2-b842-4e10594fd74f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6482a099d96aee731f81368b8b787325e592c453
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803626"
---
# <span data-ttu-id="cabc6-103">MBAM 2.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="cabc6-103">High Availability for MBAM 2.0</span></span>


<span data-ttu-id="cabc6-104">本主题提供有关 Microsoft BitLocker 管理和监视（MBAM）的高可用性安装的基本信息。</span><span class="sxs-lookup"><span data-stu-id="cabc6-104">This topic provides basic information about a highly available installation of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="cabc6-105">在此版本的 MBAM 中不完全支持高可用性方案，因此此处未介绍它们。</span><span class="sxs-lookup"><span data-stu-id="cabc6-105">High-availability scenarios are not fully supported in this version of MBAM, so they are not described here.</span></span> <span data-ttu-id="cabc6-106">建议你搜索相关博客和论坛，用户在这里介绍他们在其环境中如何成功配置 MBAM 的高可用性。</span><span class="sxs-lookup"><span data-stu-id="cabc6-106">It is recommended that you search related blogs and forums, where users describe how they have successfully configured high availability for MBAM in their environments.</span></span>

## <span data-ttu-id="cabc6-107">MBAM 的高可用性方案</span><span class="sxs-lookup"><span data-stu-id="cabc6-107">High Availability Scenarios for MBAM</span></span>


<span data-ttu-id="cabc6-108">Microsoft BitLocker 管理和监视设计为具有容错能力。</span><span class="sxs-lookup"><span data-stu-id="cabc6-108">Microsoft BitLocker Administration and Monitoring is designed to be fault-tolerant.</span></span> <span data-ttu-id="cabc6-109">如果服务器不可用，则不会对用户产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="cabc6-109">If a server becomes unavailable, users should not be negatively affected.</span></span> <span data-ttu-id="cabc6-110">例如，如果 MBAM 代理无法连接到 MBAM web 服务器，则不应提示用户执行操作。</span><span class="sxs-lookup"><span data-stu-id="cabc6-110">For example, if the MBAM agent cannot connect to the MBAM web server, users should not be prompted for action.</span></span>

<span data-ttu-id="cabc6-111">规划 MBAM 安装时，请考虑以下项目，这些项目可能会影响 MBAM 服务的可用性：</span><span class="sxs-lookup"><span data-stu-id="cabc6-111">When you plan your MBAM installation, consider the following items, which can affect the availability of the MBAM service:</span></span>

-   <span data-ttu-id="cabc6-112">驱动器加密和恢复密码-如果无法 escrowed 恢复密码，则不会在客户端计算机上开始加密。</span><span class="sxs-lookup"><span data-stu-id="cabc6-112">Drive encryption and recovery password – If a recovery password cannot be escrowed, the encryption does not start on the client computer.</span></span>

-   <span data-ttu-id="cabc6-113">合规性状态数据上载-如果托管合规性状态报告服务的服务器不可用，则合规性数据不会保持最新。</span><span class="sxs-lookup"><span data-stu-id="cabc6-113">Compliance status data upload – If the server that hosts the compliance status report service is not available, the compliance data does not remain current.</span></span>

-   <span data-ttu-id="cabc6-114">技术支持恢复密钥访问-如果帮助台无法访问 MBAM 数据库信息，技术支持无法向用户提供恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="cabc6-114">Help Desk recovery key access - If the Help Desk cannot access MBAM database information, the Help Desk cannot provide recovery keys to users.</span></span>

-   <span data-ttu-id="cabc6-115">报表的可用性-如果托管合规性和审核报告的服务器不可用，则报告将不可用。</span><span class="sxs-lookup"><span data-stu-id="cabc6-115">Availability of reports –If the server that hosts the Compliance and Audit Reports is not available, reports will not be available.</span></span>

## <a href="" id="how-the-mbam-backup-uses-the-volume-shadow-copy-service--vss--"></a><span data-ttu-id="cabc6-116">MBAM 备份如何使用卷影复制服务（VSS）</span><span class="sxs-lookup"><span data-stu-id="cabc6-116">How the MBAM Backup Uses the Volume Shadow Copy Service (VSS)</span></span>


<span data-ttu-id="cabc6-117">MBAM 2.0 提供了一个卷影复制服务（VSS）编写器，它称为 Microsoft BitLocker 管理和管理编写器，可促进合规性和审核数据库和恢复数据库的备份。</span><span class="sxs-lookup"><span data-stu-id="cabc6-117">MBAM2.0 provides a Volume Shadow Copy Service (VSS) writer, called the Microsoft BitLocker Administration and Management Writer, which facilitates the backup of the Compliance and Audit Database and the Recovery Database.</span></span>

<span data-ttu-id="cabc6-118">MBAM 服务器 Windows Installer 注册 MBAM VSS 书写器。</span><span class="sxs-lookup"><span data-stu-id="cabc6-118">The MBAM Server Windows Installer registers the MBAM VSS Writer.</span></span> <span data-ttu-id="cabc6-119">在 VSS 写入程序注册过程中，任何失败都会导致 MBAM 服务器安装回滚。</span><span class="sxs-lookup"><span data-stu-id="cabc6-119">Any failure during the VSS writer registration causes the MBAM Server installation to roll back.</span></span> <span data-ttu-id="cabc6-120">在将合规性和审核数据库以及恢复数据库安装在不同服务器上的拓扑中，在每台服务器上注册了一个单独的 MBAM VSS 编写器实例。</span><span class="sxs-lookup"><span data-stu-id="cabc6-120">In a topology where the Compliance and Audit Database and the Recovery Database are installed on different servers, a separate instance of MBAM VSS Writer is registered on each server.</span></span> <span data-ttu-id="cabc6-121">MBAM VSS 编写器依赖于 SQL Server VSS 书写器。</span><span class="sxs-lookup"><span data-stu-id="cabc6-121">The MBAM VSS Writer is dependent on the SQL Server VSS Writer.</span></span> <span data-ttu-id="cabc6-122">SQL Server VSS 编写器已注册为 Microsoft SQL Server 安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="cabc6-122">The SQL Server VSS Writer is registered as part of the Microsoft SQL Server installation.</span></span> <span data-ttu-id="cabc6-123">使用 VSS 编写器执行备份的任何备份技术均可发现 MBAM VSS 书写器。</span><span class="sxs-lookup"><span data-stu-id="cabc6-123">Any backup technology that uses VSS writers to perform backup can discover the MBAM VSS Writer.</span></span>

## <span data-ttu-id="cabc6-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="cabc6-124">Related topics</span></span>


[<span data-ttu-id="cabc6-125">维护 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="cabc6-125">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)

 

 





