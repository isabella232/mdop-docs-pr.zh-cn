---
title: MBAM 1.0 的高可用性
description: MBAM 1.0 的高可用性
author: dansimp
ms.assetid: 5869ecf8-1056-4c32-aecb-838a37e05d39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1227967d647cbfbc16967b5936066fd73d2412e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803753"
---
# <span data-ttu-id="73752-103">MBAM 1.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="73752-103">High Availability for MBAM 1.0</span></span>


<span data-ttu-id="73752-104">本主题介绍了如何配置 Microsoft BitLocker 管理和监视（MBAM）的高可用性安装。</span><span class="sxs-lookup"><span data-stu-id="73752-104">This topic describes how to configure a highly available installation of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

## <span data-ttu-id="73752-105">MBAM 的高可用性方案</span><span class="sxs-lookup"><span data-stu-id="73752-105">High Availability Scenarios for MBAM</span></span>


<span data-ttu-id="73752-106">Microsoft BitLocker 管理和监视（MBAM）设计为可容错。</span><span class="sxs-lookup"><span data-stu-id="73752-106">Microsoft BitLocker Administration and Monitoring (MBAM) is designed to be fault-tolerant.</span></span> <span data-ttu-id="73752-107">如果服务器不可用，则用户不会受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="73752-107">If a server becomes unavailable, the users should not be negatively affected.</span></span> <span data-ttu-id="73752-108">例如，如果 MBAM 代理无法连接到 MBAM web 服务器，则不应提示用户执行操作。</span><span class="sxs-lookup"><span data-stu-id="73752-108">For example, if the MBAM agent cannot connect to the MBAM web server, users should not be prompted for action.</span></span>

<span data-ttu-id="73752-109">规划 MBAM 安装时，请考虑以下可能会影响 MBAM 服务可用性的问题：</span><span class="sxs-lookup"><span data-stu-id="73752-109">When you plan your MBAM installation, consider the following concerns that can affect the availability of the MBAM service:</span></span>

-   <span data-ttu-id="73752-110">驱动器加密和恢复密码-如果无法 escrowed 恢复密码，则不会在客户端计算机上启动加密。</span><span class="sxs-lookup"><span data-stu-id="73752-110">Drive encryption and recovery password – If a recovery password cannot be escrowed, the encryption will not start on the client computer.</span></span>

-   <span data-ttu-id="73752-111">合规性状态数据上载-如果托管合规性状态报告服务的服务器不可用，则合规性数据将不会保持最新。</span><span class="sxs-lookup"><span data-stu-id="73752-111">Compliance status data upload – If the server that hosts the compliance status report service is not available, the compliance data will not remain current.</span></span>

-   <span data-ttu-id="73752-112">技术支持恢复密钥访问-如果帮助台无法访问 MBAM 数据库信息，他们将无法向用户提供恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="73752-112">Help Desk recovery key access - If the Help Desk cannot access MBAM database information, they will be unable to provide recovery keys to users.</span></span>

-   <span data-ttu-id="73752-113">报表的可用性-如果托管合规性和审核报告的服务器不可用，则报表将不可用。</span><span class="sxs-lookup"><span data-stu-id="73752-113">Availability of reports – Reports will not be available if the server that hosts the Compliance and Audit Reports is not available.</span></span>

<span data-ttu-id="73752-114">MBAM 高可用性的主要关注是 BitLocker 密钥恢复可用性。</span><span class="sxs-lookup"><span data-stu-id="73752-114">The main concern for MBAM high availability is BitLocker key recovery availability.</span></span> <span data-ttu-id="73752-115">如果帮助台无法提供恢复密钥，则被锁定的用户无法解锁其计算机。</span><span class="sxs-lookup"><span data-stu-id="73752-115">If the help desk cannot provide recovery keys, users who are locked out cannot unlock their computers.</span></span> <span data-ttu-id="73752-116">若要避免此问题，请考虑实现冗余 web 服务器和数据库以确保高可用性。</span><span class="sxs-lookup"><span data-stu-id="73752-116">To avoid this problem, consider implementing redundant web servers and databases to ensure high availability.</span></span>

<span data-ttu-id="73752-117">有关 MBAM 可伸缩性和高可用性的详细信息，请参阅[MBAM 的可伸缩性白皮书](https://go.microsoft.com/fwlink/p/?LinkId=229025)（ https://go.microsoft.com/fwlink/p/?LinkId=229025) 。</span><span class="sxs-lookup"><span data-stu-id="73752-117">For more information about MBAM scalability and high availability, see the [MBAM Scalability White Paper](https://go.microsoft.com/fwlink/p/?LinkId=229025) (https://go.microsoft.com/fwlink/p/?LinkId=229025).</span></span>

<span data-ttu-id="73752-118">有关 Microsoft SQL Server 的高可用性的一般指南，请参阅[高可用性](https://go.microsoft.com/fwlink/p/?LinkId=221504)（ https://go.microsoft.com/fwlink/p/?LinkId=221504) 。</span><span class="sxs-lookup"><span data-stu-id="73752-118">For general guidance on high availability for Microsoft SQL Server, see [High Availability](https://go.microsoft.com/fwlink/p/?LinkId=221504) (https://go.microsoft.com/fwlink/p/?LinkId=221504).</span></span>

<span data-ttu-id="73752-119">有关 web 服务器可用性和可伸缩性的一般指南，请参阅[可用性和可伸缩性](https://go.microsoft.com/fwlink/p/?LinkId=221503)（ https://go.microsoft.com/fwlink/p/?LinkId=221503) 。</span><span class="sxs-lookup"><span data-stu-id="73752-119">For general guidance on availability and scalability for web servers, see [Availability and Scalability](https://go.microsoft.com/fwlink/p/?LinkId=221503) (https://go.microsoft.com/fwlink/p/?LinkId=221503).</span></span>

## <span data-ttu-id="73752-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="73752-120">Related topics</span></span>


[<span data-ttu-id="73752-121">维护 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="73752-121">Maintaining MBAM 1.0</span></span>](maintaining-mbam-10.md)

 

 





