---
title: 关于 Microsoft Application Virtualization 4.5
description: 关于 Microsoft Application Virtualization 4.5
author: dansimp
ms.assetid: 39f45a6f-ac55-4fd7-8a83-865e1a7034f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 30f285680ab24e9c638ff8a200946925074bddf1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802452"
---
# <span data-ttu-id="5af2d-103">关于 Microsoft Application Virtualization 4.5</span><span class="sxs-lookup"><span data-stu-id="5af2d-103">About Microsoft Application Virtualization 4.5</span></span>


<span data-ttu-id="5af2d-104">以前称为 SoftGrid 应用程序虚拟化，Microsoft Application Virtualization （app-v）4.5 是产品的第一个 Microsoft 品牌版本。</span><span class="sxs-lookup"><span data-stu-id="5af2d-104">Formerly known as SoftGrid Application Virtualization, Microsoft Application Virtualization (App-V) 4.5 is the first Microsoft-branded release of the product.</span></span> <span data-ttu-id="5af2d-105">它包括新功能，使企业 IT 组织可以轻松地支持大规模的全球应用程序虚拟化实施。</span><span class="sxs-lookup"><span data-stu-id="5af2d-105">It includes new capabilities that make it easy for enterprise IT organizations to support large-scale, global application virtualization implementations.</span></span>

-   <span data-ttu-id="5af2d-106">动态虚拟化： app-v 4.5 提供了控制虚拟应用程序交互的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5af2d-106">Dynamic Virtualization: App-V 4.5 provides the flexibility to control virtual application interaction.</span></span> <span data-ttu-id="5af2d-107">想要合并虚拟环境并实现更快、更轻松管理的管理员可以使用产品的动态套件合成，这种组合可以将中间件应用程序的程序包序列化和管理与主应用程序分开。</span><span class="sxs-lookup"><span data-stu-id="5af2d-107">Administrators who want to consolidate virtual environments and enable faster, easier administration, can use the product’s Dynamic Suite Composition, which sequences and manages packages for middleware applications separately from the main application.</span></span> <span data-ttu-id="5af2d-108">它通过消除中间件的冗余包装来缩小可能的包大小。</span><span class="sxs-lookup"><span data-stu-id="5af2d-108">It shrinks potential package size by eliminating redundant packaging of middleware.</span></span> <span data-ttu-id="5af2d-109">这允许多个 Web 应用程序与虚拟化应用程序的同一单个实例进行通信，例如 Microsoft .NET Framework 或 Sun Java 运行时环境（JRE）。</span><span class="sxs-lookup"><span data-stu-id="5af2d-109">This lets multiple Web applications communicate with the same single instance of a virtualized application of, for example, Microsoft .NET Framework or Sun Java Runtime Environment (JRE).</span></span> <span data-ttu-id="5af2d-110">简化了通用虚拟中间件的更新，并更新了一个虚拟应用程序，而不是多个虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="5af2d-110">Updates for the common virtual middleware are simplified and one virtual application is updated instead of several.</span></span> <span data-ttu-id="5af2d-111">这种 "多对一" 功能大大降低了更新的成本。</span><span class="sxs-lookup"><span data-stu-id="5af2d-111">This “many-to-one” capability greatly reduces the cost of updates.</span></span> <span data-ttu-id="5af2d-112">它还使部署和管理应用程序变得更轻松，这些应用程序使用多个插件和外接程序，并改进了对不同用户组的插件分发的管理。</span><span class="sxs-lookup"><span data-stu-id="5af2d-112">It also makes it easier to deploy and manage applications that use multiple plug-ins and add-ins, and improves management of plug-in distribution to different user groups.</span></span>

-   <span data-ttu-id="5af2d-113">扩展的可伸缩性：在三种灵活的部署模式下进行选择：</span><span class="sxs-lookup"><span data-stu-id="5af2d-113">Extended Scalability: Choose among three flexible deployment modes:</span></span>

    1.  <span data-ttu-id="5af2d-114">应用程序虚拟化管理服务器（作为 Microsoft 桌面优化包的一部分提供）和适用于远程桌面服务程序包的 Microsoft Application 虚拟化，支持动态流（包括程序包和活动升级），并且需要 Microsoft Active Directory 域服务和 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="5af2d-114">Application Virtualization Management Server, which ships as part of the Microsoft Desktop Optimization Pack and Microsoft Application Virtualization for Remote Desktop Services packages, enables dynamic streaming including package and active upgrades, and requires Microsoft Active Directory Domain Services and Microsoft SQL Server.</span></span>

    2.  <span data-ttu-id="5af2d-115">应用程序虚拟化流服务器，它还作为 Microsoft 桌面优化包和 Microsoft Application Virtualization 适用于远程桌面服务程序包的一部分提供，提供应用程序流，包括程序包和活动升级（不使用 Active Directory 域服务和数据库开销），并允许管理员部署到现有服务器或向电子软件交付（ESD）系统添加流。</span><span class="sxs-lookup"><span data-stu-id="5af2d-115">Application Virtualization Streaming Server, a lightweight version which also ships as part of the Microsoft Desktop Optimization Pack and Microsoft Application Virtualization for Remote Desktop Services packages, offers application streaming including package and active upgrades without the Active Directory Domain Services and database overheads, and enables administrators to deploy to existing servers or add streaming to Electronic Software Delivery (ESD) systems.</span></span>

    3.  <span data-ttu-id="5af2d-116">独立模式使虚拟应用程序能够在不进行流处理的情况下运行，并且可与 Microsoft 终结点配置管理器和第三方 ESD 系统互操作。</span><span class="sxs-lookup"><span data-stu-id="5af2d-116">Standalone mode enables virtual applications to run without streaming and is interoperable with Microsoft Endpoint Configuration Manager and third-party ESD systems.</span></span>

-   <span data-ttu-id="5af2d-117">全球化：产品通过11种语言进行本地化，包括支持使用特殊字符的外语应用程序，并支持外语 Active Directory 和服务器以及运行时区域设置检测。</span><span class="sxs-lookup"><span data-stu-id="5af2d-117">Globalization: The product is localized across 11 languages, includes support for foreign language applications that use special characters, and supports foreign language Active Directory and servers and runtime locale detection.</span></span>

-   <span data-ttu-id="5af2d-118">Microsoft 安全标准： Microsoft Application Virtualization （App-v）4.5 符合 Microsoft 安全标准，包括可信赖的计算、安全的 Windows 倡议和安全开发生命周期。</span><span class="sxs-lookup"><span data-stu-id="5af2d-118">Microsoft Security Standards: Microsoft Application Virtualization (App-V) 4.5 complies with Microsoft security standards including Trustworthy Computing, Secure Windows Initiative and Security Development Lifecycle.</span></span> <span data-ttu-id="5af2d-119">它包括对面向 Internet 的方案的支持，并提供了默认的安全默认配置框。</span><span class="sxs-lookup"><span data-stu-id="5af2d-119">It includes support for Internet-facing scenarios and provides Secure by Default configuration out of the box.</span></span>

## <span data-ttu-id="5af2d-120">本部分内容</span><span class="sxs-lookup"><span data-stu-id="5af2d-120">In This Section</span></span>


<a href="" id="microsoft-application-virtualization-management-system-release-notes"></a>[<span data-ttu-id="5af2d-121">Microsoft Application Virtualization 管理系统发行说明</span><span class="sxs-lookup"><span data-stu-id="5af2d-121">Microsoft Application Virtualization Management System Release Notes</span></span>](microsoft-application-virtualization-management-system-release-notes.md)  
<span data-ttu-id="5af2d-122">提供有关 Microsoft Application Virtualization （App-v）4.5 的已知问题的最新信息。</span><span class="sxs-lookup"><span data-stu-id="5af2d-122">Provides the most up-to-date information about known issues with Microsoft Application Virtualization (App-V) 4.5.</span></span>

 

 





