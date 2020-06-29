---
title: 如何将 MBAM 客户端部署到台式机或笔记本电脑
description: 如何将 MBAM 客户端部署到台式机或笔记本电脑
author: dansimp
ms.assetid: 3a7639e0-468e-4496-8be2-ed29b8e07c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b67533a555da4dabec6654ed3f95f91ad8d37bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803576"
---
# <span data-ttu-id="74ccf-103">如何将 MBAM 客户端部署到台式机或笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="74ccf-103">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="74ccf-104">本主题介绍如何将 MBAM 客户端部署到最终用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="74ccf-104">This topic explains how to deploy the MBAM Client to end users’ computers.</span></span> <span data-ttu-id="74ccf-105">你可以通过电子软件分发系统（如 Active Directory 域服务或 MicrosoftSystemCenterConfiguration 管理器）部署 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="74ccf-105">You can deploy the MBAM Client through an electronic software distribution system, such as Active Directory Domain Services or MicrosoftSystemCenterConfiguration Manager.</span></span>

<span data-ttu-id="74ccf-106">若要将 MBAM 客户端部署为 Windows 部署的一部分，请参阅[如何通过将 MBAM 用作 Windows 部署的一部分来启用 BitLocker](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="74ccf-106">To deploy the MBAM Client as part of a Windows deployment, see [How to Enable BitLocker by Using MBAM as Part of a Windows Deployment](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md).</span></span>

<span data-ttu-id="74ccf-107">在开始 MBAM 客户端部署之前，请查看[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="74ccf-107">Before you start the MBAM Client deployment, review the [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

**<span data-ttu-id="74ccf-108">将 MBAM 客户端部署到台式计算机或膝上型计算机</span><span class="sxs-lookup"><span data-stu-id="74ccf-108">To deploy the MBAM Client to desktop or laptop computers</span></span>**

1.  <span data-ttu-id="74ccf-109">找到 MBAM 软件附带的 MBAM 客户端安装文件。</span><span class="sxs-lookup"><span data-stu-id="74ccf-109">Locate the MBAM Client installation files that are provided with the MBAM software.</span></span>

2.  <span data-ttu-id="74ccf-110">使用 Active Directory 域服务或企业软件部署工具（如 MicrosoftSystemCenterConfiguration Manager）将 Windows Installer 程序包部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="74ccf-110">Use Active Directory Domain Services or an enterprise software deployment tool like MicrosoftSystemCenterConfiguration Manager to deploy the Windows Installer package to target computers.</span></span>

3.  <span data-ttu-id="74ccf-111">配置分发设置或组策略设置以运行 MBAM 客户端安装文件。</span><span class="sxs-lookup"><span data-stu-id="74ccf-111">Configure the distribution settings or Group Policy settings to run the MBAM Client installation file.</span></span>

    <span data-ttu-id="74ccf-112">成功安装后，MBAM 客户端将应用从域控制器收到的组策略设置以开始 BitLocker 驱动器加密和管理功能。</span><span class="sxs-lookup"><span data-stu-id="74ccf-112">After successful installation, the MBAM Client applies the Group Policy settings that are received from a domain controller to begin BitLocker Drive Encryption and management functions.</span></span>

    <span data-ttu-id="74ccf-113">**重要提示** 如果远程桌面协议连接处于活动状态，MBAM 客户端不会启动 BitLocker 驱动器加密操作。</span><span class="sxs-lookup"><span data-stu-id="74ccf-113">**Important** The MBAM Client does not start BitLocker Drive Encryption actions if a remote desktop protocol connection is active.</span></span> <span data-ttu-id="74ccf-114">必须关闭所有远程控制台连接，并且用户必须在 BitLocker 驱动器加密开始之前登录到物理控制台会话。</span><span class="sxs-lookup"><span data-stu-id="74ccf-114">All remote console connections must be closed and a user must be logged on to a physical console session before BitLocker Drive Encryption begins.</span></span>

     


## <span data-ttu-id="74ccf-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="74ccf-115">Related topics</span></span>
[<span data-ttu-id="74ccf-116">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="74ccf-116">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="74ccf-117">规划 MBAM 2.5 客户端部署</span><span class="sxs-lookup"><span data-stu-id="74ccf-117">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

 

## <span data-ttu-id="74ccf-118">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="74ccf-118">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="74ccf-119">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="74ccf-119">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="74ccf-120">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="74ccf-120">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





