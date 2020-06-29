---
title: 如何安装 MBAM 2.0 组策略模板
description: 如何安装 MBAM 2.0 组策略模板
author: dansimp
ms.assetid: bc193232-d060-4285-842e-d194a74dd3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6420fc4d499de05ed740b038b40aff6a9cd8a05f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803931"
---
# <span data-ttu-id="8bcec-103">如何安装 MBAM 2.0 组策略模板</span><span class="sxs-lookup"><span data-stu-id="8bcec-103">How to Install the MBAM 2.0 Group Policy Template</span></span>


<span data-ttu-id="8bcec-104">除了服务器相关的 Microsoft BitLocker 管理和监视（MBAM）功能之外，服务器设置应用程序还包括 Microsoft BitLocker 管理和监视组策略模板。</span><span class="sxs-lookup"><span data-stu-id="8bcec-104">In addition to the server-related Microsoft BitLocker Administration and Monitoring (MBAM) features, the server setup application includes an Microsoft BitLocker Administration and Monitoring Group Policy template.</span></span> <span data-ttu-id="8bcec-105">此模板可安装在任何能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的计算机上。</span><span class="sxs-lookup"><span data-stu-id="8bcec-105">This template can be installed on any computer capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="8bcec-106">以下步骤介绍了如何安装 MBAM 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="8bcec-106">The following steps describe how to install the MBAM Group Policy template.</span></span>

<span data-ttu-id="8bcec-107">**注意** 请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。</span><span class="sxs-lookup"><span data-stu-id="8bcec-107">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="8bcec-108">安装 MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="8bcec-108">To install the MBAM Group Policy template</span></span>**

1.  <span data-ttu-id="8bcec-109">在要安装 MBAM 的服务器上，运行**MBAMSetup.exe**以启动 MBAM 安装向导。</span><span class="sxs-lookup"><span data-stu-id="8bcec-109">On the server where you want to install MBAM, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="8bcec-110">在 "**欢迎**" 页面上，选择 "**客户体验改善计划**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="8bcec-110">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="8bcec-111">阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="8bcec-111">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="8bcec-112">默认情况下，将选择安装所有 Microsoft BitLocker 管理和监视功能。</span><span class="sxs-lookup"><span data-stu-id="8bcec-112">By default, all Microsoft BitLocker Administration and Monitoring features are selected for installation.</span></span> <span data-ttu-id="8bcec-113">清除 "**策略模板**" 之外的所有功能选项，然后单击 "**下一步**" 以继续安装。</span><span class="sxs-lookup"><span data-stu-id="8bcec-113">Clear all feature options except for **Policy Template**, and then click **Next** to continue the installation.</span></span>

    <span data-ttu-id="8bcec-114">**注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="8bcec-114">**Note** The installation wizard checks the prerequisites for your installation and displays prerequisites that are missing.</span></span> <span data-ttu-id="8bcec-115">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="8bcec-115">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="8bcec-116">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="8bcec-116">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="8bcec-117">满足所有先决条件后，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="8bcec-117">Once all prerequisites are met, the installation will resume.</span></span>

     

5.  <span data-ttu-id="8bcec-118">有关如何以及在何处安装模板的特定步骤，请参阅[如何下载和部署 MDOP 组策略（admx）模板](https://technet.microsoft.com/library/dn659707.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8bcec-118">For specific steps about how and where to install the templates, see [How to Download and Deploy MDOP Group Policy (.admx) Templates](https://technet.microsoft.com/library/dn659707.aspx).</span></span>

6.  <span data-ttu-id="8bcec-119">在 "Microsoft BitLocker 管理和监视设置向导" 显示所选功能的安装页面后，单击 "**完成**" 关闭 MBAM 设置。</span><span class="sxs-lookup"><span data-stu-id="8bcec-119">After the Microsoft BitLocker Administration and Monitoring Setup wizard displays installation pages for the selected features, click **Finish** to close MBAM Setup.</span></span>

## <span data-ttu-id="8bcec-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="8bcec-120">Related topics</span></span>


[<span data-ttu-id="8bcec-121">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="8bcec-121">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





