---
title: 如何在单个服务器上安装 MBAM 语言更新
description: 如何在单个服务器上安装 MBAM 语言更新
author: dansimp
ms.assetid: e6fe59a3-a3e1-455c-a059-1f23ee083cf6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94814158335430aba433c180cdba83d0cf15b760
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803631"
---
# <span data-ttu-id="695dc-103">如何在单个服务器上安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="695dc-103">How to Install the MBAM Language Update on a Single Server</span></span>


<span data-ttu-id="695dc-104">Microsoft BitLocker 管理和监视（MBAM）包括可在一台或多台计算机上运行的四个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="695dc-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes four server roles that can be run on one or more computers.</span></span> <span data-ttu-id="695dc-105">但是，只有两个 MBAM 服务器功能才需要更新以支持安装 MBAM 1.0 语言版本和 MBAM 策略模板。</span><span class="sxs-lookup"><span data-stu-id="695dc-105">However, only two MBAM Server features require the update to support installation of the MBAM 1.0 language release and the MBAM Policy Template.</span></span> <span data-ttu-id="695dc-106">若要更新一台计算机上安装的全部三个 MBAM 功能，请执行本主题中所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="695dc-106">To update all three of the required MBAM features to be installed on one computer, perform the steps described in this topic.</span></span>

**<span data-ttu-id="695dc-107">在单个服务器上安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="695dc-107">To install the MBAM language update on a single server</span></span>**

1.  <span data-ttu-id="695dc-108">打开 "Internet 信息服务（IIS）管理" 控制台，转到 "**网站**"，然后关闭 Microsoft BitLocker 管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="695dc-108">Open the Internet Information Services (IIS) Management Console, go to **Sites**, and then shut down the Microsoft BitLocker Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="695dc-109">编辑 MBAM 网站的绑定，然后暂时修改该网站的绑定。</span><span class="sxs-lookup"><span data-stu-id="695dc-109">Edit the bindings for the MBAM website, and then temporarily modify the bindings of the site.</span></span> <span data-ttu-id="695dc-110">例如，将端口从443更改为9443。</span><span class="sxs-lookup"><span data-stu-id="695dc-110">For example, change the port from 443 to 9443.</span></span>

3.  <span data-ttu-id="695dc-111">找到并运行 MBAM 安装向导（MBAMsetup.exe），然后选择以下三个功能：</span><span class="sxs-lookup"><span data-stu-id="695dc-111">Locate and run the MBAM setup wizard (MBAMsetup.exe) and select the following three features:</span></span>

    1.  <span data-ttu-id="695dc-112">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="695dc-112">Compliance and Audit Reports</span></span>

    2.  <span data-ttu-id="695dc-113">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="695dc-113">Administration and Monitoring Server</span></span>

    3.  <span data-ttu-id="695dc-114">组策略模板</span><span class="sxs-lookup"><span data-stu-id="695dc-114">Group Policy Templates</span></span>

    <span data-ttu-id="695dc-115">**重要提示** 必须按以下顺序更新 MBAM 服务器功能：合规性和审核报告，然后是 "管理和监视服务器"。</span><span class="sxs-lookup"><span data-stu-id="695dc-115">**Important** The MBAM server features must be updated in the following order: Compliance and Audit Reports first, then Administration and Monitoring Server.</span></span> <span data-ttu-id="695dc-116">组策略模板可以随时更新，而无需考虑顺序。</span><span class="sxs-lookup"><span data-stu-id="695dc-116">The Group Policy templates can be updated at any time without concern for sequence.</span></span>

     

4.  <span data-ttu-id="695dc-117">升级服务器数据库后，打开 IIS 管理控制台并查看 Microsoft BitLocker 管理和监视网站的绑定。</span><span class="sxs-lookup"><span data-stu-id="695dc-117">After you upgrade the server database, open the IIS Management Console and review the bindings of the Microsoft BitLocker Administration and Monitoring website.</span></span>

5.  <span data-ttu-id="695dc-118">删除其中一个绑定，并确保剩余的绑定具有正确的 MBAM 企业配置的主机名、证书和端口号。</span><span class="sxs-lookup"><span data-stu-id="695dc-118">Delete one of the bindings and ensure that the remaining binding has the correct host name, certificate, and port number for the MBAM enterprise configuration.</span></span>

6.  <span data-ttu-id="695dc-119">重新启动 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="695dc-119">Restart the MBAM website.</span></span>

7.  <span data-ttu-id="695dc-120">测试 MBAM 网站功能：</span><span class="sxs-lookup"><span data-stu-id="695dc-120">Test the MBAM website functionality:</span></span>

    -   <span data-ttu-id="695dc-121">打开 MBAM web 界面，确保你可以获取客户端的恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="695dc-121">Open the MBAM web interface and ensure you can fetch a recovery key for a client.</span></span>

    -   <span data-ttu-id="695dc-122">强制加密新的或手动解密的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="695dc-122">Enforce encryption of a new or manually decrypted client computer.</span></span>

        <span data-ttu-id="695dc-123">**注意** 仅当 MBAM 客户端可以与恢复和硬件数据库通信时，才会打开它。</span><span class="sxs-lookup"><span data-stu-id="695dc-123">**Note** The MBAM client opens only if it can communicate with the Recovery and Hardware database.</span></span>

         

## <span data-ttu-id="695dc-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="695dc-124">Related topics</span></span>


[<span data-ttu-id="695dc-125">部署 MBAM 1.0 语言版本更新</span><span class="sxs-lookup"><span data-stu-id="695dc-125">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





