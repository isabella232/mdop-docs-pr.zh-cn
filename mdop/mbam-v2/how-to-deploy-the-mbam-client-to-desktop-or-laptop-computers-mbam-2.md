---
title: 如何将 MBAM 客户端部署到台式机或笔记本电脑
description: 如何将 MBAM 客户端部署到台式机或笔记本电脑
author: dansimp
ms.assetid: 56744922-bfdd-48f6-ae01-645ff53b64a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 49340ae970dafc9d263f5564e7981a402da40f19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798188"
---
# <span data-ttu-id="e8a81-103">如何将 MBAM 客户端部署到台式机或笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="e8a81-103">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="e8a81-104">Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="e8a81-104">The Microsoft BitLocker Administration and Monitoring (MBAM) client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="e8a81-105">通过电子软件分发系统（如 Active Directory 域服务或 MicrosoftSystemCenterConfigurationManager）部署客户端，可以将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="e8a81-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services or MicrosoftSystemCenterConfigurationManager.</span></span>

<span data-ttu-id="e8a81-106">**注意** 若要查看 Microsoft BitLocker 管理和监视客户端系统要求，请参阅[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="e8a81-106">**Note** To review the Microsoft BitLocker Administration and Monitoring Client system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>

 

**<span data-ttu-id="e8a81-107">将 MBAM 客户端部署到台式计算机或膝上型计算机</span><span class="sxs-lookup"><span data-stu-id="e8a81-107">To deploy the MBAM Client to desktop or laptop computers</span></span>**

1.  <span data-ttu-id="e8a81-108">找到 MBAM 软件附带的 MBAM 客户端安装文件。</span><span class="sxs-lookup"><span data-stu-id="e8a81-108">Locate the MBAM client installation files that are provided with the MBAM software.</span></span>

2.  <span data-ttu-id="e8a81-109">使用 Active Directory 域服务或企业软件部署工具（如 MicrosoftSystemCenterConfigurationManager）将 Windows Installer 程序包部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="e8a81-109">Use Active Directory Domain Services or an enterprise software deployment tool like MicrosoftSystemCenterConfigurationManager to deploy the Windows Installer package to target computers.</span></span>

3.  <span data-ttu-id="e8a81-110">配置分发设置或组策略以运行 MBAM 客户端安装文件。</span><span class="sxs-lookup"><span data-stu-id="e8a81-110">Configure the distribution settings or Group Policy to run the MBAM Client installation file.</span></span> <span data-ttu-id="e8a81-111">成功安装后，MBAM 客户端将应用从域控制器收到的组策略设置以开始 BitLocker 加密和管理功能。</span><span class="sxs-lookup"><span data-stu-id="e8a81-111">After successful installation, the MBAM Client applies the Group Policy settings that are received from a domain controller to begin BitLocker encryption and management functions.</span></span> <span data-ttu-id="e8a81-112">有关 MBAM 组策略设置的详细信息，请参阅[规划 MBAM 2.0 组策略要求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="e8a81-112">For more information about MBAM group policy settings, see [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md).</span></span>

    <span data-ttu-id="e8a81-113">**重要提示** 如果远程桌面协议连接处于活动状态，MBAM 客户端将不会启动 BitLocker 加密操作。</span><span class="sxs-lookup"><span data-stu-id="e8a81-113">**Important** The MBAM Client will not start BitLocker encryption actions if a remote desktop protocol connection is active.</span></span> <span data-ttu-id="e8a81-114">必须先关闭所有远程控制台连接，然后才可开始 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="e8a81-114">All remote console connections must be closed before BitLocker encryption will begin.</span></span>

     

## <span data-ttu-id="e8a81-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="e8a81-115">Related topics</span></span>


[<span data-ttu-id="e8a81-116">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="e8a81-116">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

 

 





