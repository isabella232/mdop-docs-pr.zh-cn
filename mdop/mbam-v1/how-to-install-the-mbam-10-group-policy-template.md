---
title: 如何安装 MBAM 1.0 组策略模板
description: 如何安装 MBAM 1.0 组策略模板
author: dansimp
ms.assetid: 451a50b0-939c-47ad-9248-a138deade550
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a055c84fb6b1645592b53d957daf157a6055880
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803748"
---
# <span data-ttu-id="46b29-103">如何安装 MBAM 1.0 组策略模板</span><span class="sxs-lookup"><span data-stu-id="46b29-103">How to Install the MBAM 1.0 Group Policy Template</span></span>


<span data-ttu-id="46b29-104">除了 Microsoft BitLocker 管理和监视（MBAM）的服务器相关功能之外，服务器设置应用程序还包含一个 MBAM 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="46b29-104">In addition to the server-related features of Microsoft BitLocker Administration and Monitoring (MBAM), the server setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="46b29-105">你可以在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的任何计算机上安装此模板。</span><span class="sxs-lookup"><span data-stu-id="46b29-105">You can install this template on any computer that is capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="46b29-106">以下步骤介绍了如何安装 MBAM 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="46b29-106">The following steps describe how to install the MBAM Group Policy template.</span></span>

<span data-ttu-id="46b29-107">**注意** 请确保在32位服务器上使用32位设置，并在64服务器上使用64位设置。</span><span class="sxs-lookup"><span data-stu-id="46b29-107">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="46b29-108">安装 MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="46b29-108">To install the MBAM Group Policy template</span></span>**

1.  <span data-ttu-id="46b29-109">启动 MBAM 安装向导;然后，单击 "欢迎" 页面上的 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="46b29-109">Start the MBAM installation wizard; then, click **Install** on the Welcome page.</span></span>

2.  <span data-ttu-id="46b29-110">阅读并接受 Microsoft 软件许可条款，然后单击 "**下一步**" 继续安装。</span><span class="sxs-lookup"><span data-stu-id="46b29-110">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="46b29-111">默认情况下，将选择所有 MBAM 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="46b29-111">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="46b29-112">清除 "**策略模板**" 之外的所有功能选项，然后单击 "**下一步**" 以继续安装。</span><span class="sxs-lookup"><span data-stu-id="46b29-112">Clear all feature options except for **Policy Template**, and then click **Next** to continue the installation.</span></span>

    <span data-ttu-id="46b29-113">**注意** 安装向导将检查安装的先决条件，并显示缺少的必备条件。</span><span class="sxs-lookup"><span data-stu-id="46b29-113">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="46b29-114">如果满足所有先决条件，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="46b29-114">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="46b29-115">如果检测到缺少先决条件，则必须解决缺少的先决条件，然后再次单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="46b29-115">If a missing prerequisite is detected, you must resolve the missing prerequisite and then click **Check prerequisites again**.</span></span> <span data-ttu-id="46b29-116">满足所有先决条件后，安装将继续。</span><span class="sxs-lookup"><span data-stu-id="46b29-116">Once all prerequisites are met, the installation will resume.</span></span>

     

4.  <span data-ttu-id="46b29-117">MBAM 安装向导显示所选功能的安装页面后，单击 "**完成**" 关闭 MBAM 设置。</span><span class="sxs-lookup"><span data-stu-id="46b29-117">After the MBAM Setup wizard displays installation pages for the selected features, click **Finish** to close MBAM Setup.</span></span>

## <span data-ttu-id="46b29-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="46b29-118">Related topics</span></span>


[<span data-ttu-id="46b29-119">部署 MBAM 1.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="46b29-119">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)

 

 





