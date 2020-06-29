---
title: 使用 Configuration Manager 部署 MBAM
description: 使用 Configuration Manager 部署 MBAM
author: dansimp
ms.assetid: 89d03e29-457a-471d-b893-e0b74a83ec50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c6cffc1cf51a26aeaa94fcb265199c19f0f34abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803371"
---
# <span data-ttu-id="bc8c6-103">使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="bc8c6-103">Deploying MBAM with Configuration Manager</span></span>


<span data-ttu-id="bc8c6-104">以下过程介绍了如何使用 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 部署 Microsoft BitLocker 管理和监视（MBAM） usingthe 推荐的配置，这将在[配置管理器中使用 MBAM](getting-started---using-mbam-with-configuration-manager.md)中介绍。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-104">The following procedures describe how to deploy Microsoft BitLocker Administration and Monitoring (MBAM) with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager by usingthe recommended configuration, which is described in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="bc8c6-105">建议的配置是在一个或多个 Microsoft BitLocker 管理和监视服务器上安装管理和监视功能，并在单独的服务器上安装 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-105">The recommended configuration is to install the Administration and Monitoring features on one or more Microsoft BitLocker Administration and Monitoring servers, and install Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager on a separate server.</span></span>

<span data-ttu-id="bc8c6-106">开始安装之前，请确保已满足系统必备和硬件和软件要求，以便通过使用[Configuration Manager 部署 MBAM 来](planning-to-deploy-mbam-with-configuration-manager-2.md)将 MBAM 与 configuration manager 一起安装。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-106">Before you start the installation, ensure that you have met the prerequisites and hardware and software requirements for installing MBAM with Configuration Manager by reviewing [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="bc8c6-107">如果你必须使用 Configuration Manager 拓扑重新安装 MBAM，你将需要首先删除某些 Configuration Manager 对象。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-107">If you ever have to reinstall MBAM with the Configuration Manager topology, you will need to remove certain Configuration Manager objects first.</span></span> <span data-ttu-id="bc8c6-108">有关详细信息，请阅读[知识文库文章](https://go.microsoft.com/fwlink/?LinkId=286306)。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-108">Read the [Knowledge Base article](https://go.microsoft.com/fwlink/?LinkId=286306) for more information.</span></span>

<span data-ttu-id="bc8c6-109">将 MBAM 与 Configuration Manager 一起安装的步骤分为以下类别。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-109">The steps to install MBAM with Configuration Manager are grouped into the following categories.</span></span> <span data-ttu-id="bc8c6-110">完成每个类别的步骤以完成安装。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-110">Complete the steps for each category to complete the installation.</span></span>

## <span data-ttu-id="bc8c6-111">如何创建或编辑 mof 文件</span><span class="sxs-lookup"><span data-stu-id="bc8c6-111">How to Create or Edit the mof Files</span></span>


<span data-ttu-id="bc8c6-112">若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，你必须编辑**配置 mof**文件，并根据你使用的 Configuration Manager 版本编辑或创建 Sms \ _def mof 文件。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-112">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the **Configuration.mof** file, and either edit or create the Sms\_def.mof file, depending on which version of Configuration Manager you are using.</span></span>

[<span data-ttu-id="bc8c6-113">如何创建或编辑 mof 文件</span><span class="sxs-lookup"><span data-stu-id="bc8c6-113">How to Create or Edit the mof Files</span></span>](how-to-create-or-edit-the-mof-files.md)

## <span data-ttu-id="bc8c6-114">如何使用 Configuration Manager 安装 MBAM</span><span class="sxs-lookup"><span data-stu-id="bc8c6-114">How to Install MBAM with Configuration Manager</span></span>


<span data-ttu-id="bc8c6-115">本部分提供了有关如何在 Configuration Manager 服务器上安装以下内容的步骤： MBAM。数据库服务器上的恢复和审核数据库;以及管理和监视服务器上的管理和监视服务器功能。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-115">This section provides steps about how to install the following: MBAM on the Configuration Manager Server; the Recovery and Audit Databases on the Database Server; and the Administration and Monitoring Server features on the Administration and Monitoring Server.</span></span>

[<span data-ttu-id="bc8c6-116">如何使用 Configuration Manager 安装 MBAM</span><span class="sxs-lookup"><span data-stu-id="bc8c6-116">How to Install MBAM with Configuration Manager</span></span>](how-to-install-mbam-with-configuration-manager.md)

## <span data-ttu-id="bc8c6-117">如何验证 Configuration Manager 服务器上的 MBAM Server 功能安装</span><span class="sxs-lookup"><span data-stu-id="bc8c6-117">How to Validate the MBAM Server Feature Installation on the Configuration Manager Server</span></span>


<span data-ttu-id="bc8c6-118">Microsoft BitLocker 管理和监视安装完成后，请验证安装是否已成功设置 Configuration Manager 服务器所需的所有必要 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="bc8c6-118">When the Microsoft BitLocker Administration and Monitoring installation is complete, validate that the installation has successfully set up all the necessary MBAM features required for the Configuration Manager Server.</span></span>

[<span data-ttu-id="bc8c6-119">如何使用 Configuration Manager 验证 MBAM 安装</span><span class="sxs-lookup"><span data-stu-id="bc8c6-119">How to Validate the MBAM Installation with Configuration Manager</span></span>](how-to-validate-the-mbam-installation-with-configuration-manager.md)

## <span data-ttu-id="bc8c6-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="bc8c6-120">Related topics</span></span>


[<span data-ttu-id="bc8c6-121">结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bc8c6-121">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





