---
title: 如何在分布式服务器上安装 MBAM 语言更新
description: 如何在分布式服务器上安装 MBAM 语言更新
author: dansimp
ms.assetid: 5ddc64c6-0417-4a04-843e-b5e18d9f1a52
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6758463c6fc038c4d6ea86c0d49804f29bb543d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803820"
---
# <span data-ttu-id="2b3e4-103">如何在分布式服务器上安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="2b3e4-103">How to Install the MBAM Language Update on Distributed Servers</span></span>


<span data-ttu-id="2b3e4-104">Microsoft BitLocker 管理和监视（MBAM）包括可在一台或多台计算机上运行的四个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes four server roles that can be run on one or more computers.</span></span> <span data-ttu-id="2b3e4-105">但是，只有两个 MBAM 服务器功能需要更新才能支持 MBAM 1.0 语言版本和 MBAM 策略模板的安装。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-105">However, only two MBAM Server features require the update to support the installation of the MBAM 1.0 language release and the MBAM Policy Template.</span></span> <span data-ttu-id="2b3e4-106">在具有安装在多台计算机上的 MBAM 服务器功能的配置中，仅需要更新以下服务器功能：</span><span class="sxs-lookup"><span data-stu-id="2b3e4-106">In configurations with the MBAM Server features installed on multiple computers, only the following server features need to be updated:</span></span>

-   <span data-ttu-id="2b3e4-107">MBAM 合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="2b3e4-107">The MBAM Compliance and Audit Reports</span></span>

-   <span data-ttu-id="2b3e4-108">MBAM 管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="2b3e4-108">The MBAM Administration and Monitoring Server</span></span>

<span data-ttu-id="2b3e4-109">**重要提示** 必须按以下顺序更新 MBAM 服务器功能：合规性和审核报告，然后是管理和监视服务器。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-109">**Important** The MBAM server features must be updated in this order: Compliance and Audit Reports first, and then the Administration and Monitoring Server.</span></span> <span data-ttu-id="2b3e4-110">MBAM 组策略模板可以随时更新，而无需考虑顺序。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-110">The MBAM Group Policy templates can be updated at any time without concern for sequence.</span></span>

 

**<span data-ttu-id="2b3e4-111">在 "MBAM 合规性" 和 "审核报表服务器" 功能上安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="2b3e4-111">To install the MBAM Language Update on the MBAM Compliance and Audit Report Server feature</span></span>**

1.  <span data-ttu-id="2b3e4-112">在运行 MBAM 合规性和审核报告功能的计算机上，找到并运行 "MBAM 语言更新设置向导" （MBAMsetup.exe）。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-112">On the computer running the MBAM Compliance and Audit Report feature, locate and run the MBAM Language Update setup wizard (MBAMsetup.exe).</span></span>

2.  <span data-ttu-id="2b3e4-113">完成合规性和审核报告的向导，然后关闭向导。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-113">Complete the wizard for the Compliance and Audit Reports and then close the wizard.</span></span>

**<span data-ttu-id="2b3e4-114">在 "MBAM 管理和监视服务器" 功能上安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="2b3e4-114">To install the MBAM Language Update on the MBAM Administration and Monitoring Server feature</span></span>**

1.  <span data-ttu-id="2b3e4-115">在运行 MBAM 管理和监视功能的计算机上，打开 "Internet 信息服务（IIS）管理" 控制台，转到 "**网站**"，然后关闭 "Microsoft BitLocker 管理和监视网站"。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-115">On the computer that is running the MBAM Administration and Monitoring feature, open the Internet Information Services (IIS) management console, go to **Sites**, and then shut down the Microsoft BitLocker Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="2b3e4-116">选择编辑 MBAM 网站的绑定，然后修改网站的绑定。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-116">Choose to edit the bindings for the MBAM website, and then modify the bindings of the site.</span></span> <span data-ttu-id="2b3e4-117">例如，将端口从443更改为9443。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-117">For example, change the port from 443 to 9443.</span></span>

3.  <span data-ttu-id="2b3e4-118">找到并运行 MBAM 语言更新设置向导（MBAMsetup.exe）。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-118">Locate and run the MBAM Language Update setup wizard (MBAMsetup.exe).</span></span> <span data-ttu-id="2b3e4-119">完成 "管理和监视服务器" 功能的向导，然后关闭向导。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-119">Complete the wizard for the Administration and Monitoring Server feature and then close the wizard.</span></span>

4.  <span data-ttu-id="2b3e4-120">升级服务器数据库后，打开 IIS 管理控制台并查看 Microsoft BitLocker 管理和监视网站的绑定。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-120">After you upgrade the server database, open IIS Management Console and review the bindings of the Microsoft BitLocker Administration and Monitoring website.</span></span>

5.  <span data-ttu-id="2b3e4-121">删除旧绑定并确保剩余的绑定具有正确的 MBAM 企业配置的主机名、证书和端口号。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-121">Delete the old binding and ensure that the remaining binding has the correct host name, certificate, and port number for the MBAM enterprise configuration.</span></span>

6.  <span data-ttu-id="2b3e4-122">重新启动 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-122">Restart the MBAM web site.</span></span>

7.  <span data-ttu-id="2b3e4-123">测试 MBAM 网站功能：</span><span class="sxs-lookup"><span data-stu-id="2b3e4-123">Test the MBAM web site functionality:</span></span>

    -   <span data-ttu-id="2b3e4-124">打开 MBAM web 界面，确保你可以获取客户端的恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-124">Open the MBAM web interface and ensure that you can obtain a recovery key for a client.</span></span>

    -   <span data-ttu-id="2b3e4-125">强制加密新的或手动解密的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-125">Enforce encryption of a new or manually decrypted client computer.</span></span>

        <span data-ttu-id="2b3e4-126">**注意** 仅当 MBAM 客户端可以与恢复和硬件数据库通信时，才会打开它。</span><span class="sxs-lookup"><span data-stu-id="2b3e4-126">**Note** The MBAM client opens only if it can communicate with the Recovery and Hardware database.</span></span>

         

## <span data-ttu-id="2b3e4-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="2b3e4-127">Related topics</span></span>


[<span data-ttu-id="2b3e4-128">部署 MBAM 1.0 语言版本更新</span><span class="sxs-lookup"><span data-stu-id="2b3e4-128">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





