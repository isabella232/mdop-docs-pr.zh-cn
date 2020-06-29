---
title: 如何使用 Configuration Manager 验证 MBAM 安装
description: 如何使用 Configuration Manager 验证 MBAM 安装
author: dansimp
ms.assetid: 8e268539-91c3-4e8a-baae-faf3605da818
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 500c6f6ee5138b5677bf1fa20e2627a56981df1f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803208"
---
# <span data-ttu-id="e324b-103">如何使用 Configuration Manager 验证 MBAM 安装</span><span class="sxs-lookup"><span data-stu-id="e324b-103">How to Validate the MBAM Installation with Configuration Manager</span></span>


<span data-ttu-id="e324b-104">使用配置管理器安装 Microsoft BitLocker 管理和监视（MBAM）后，通过完成以下步骤验证安装是否已成功设置 MBAM 的所有必要功能。</span><span class="sxs-lookup"><span data-stu-id="e324b-104">After installing Microsoft BitLocker Administration and Monitoring (MBAM) with Configuration Manager, validate that the installation has successfully set up all the necessary features for MBAM by completing the following steps.</span></span>

**<span data-ttu-id="e324b-105">通过 Configuration Manager 验证 MBAM Server 功能安装</span><span class="sxs-lookup"><span data-stu-id="e324b-105">To validate the MBAM Server feature installation with Configuration Manager</span></span>**

1.  <span data-ttu-id="e324b-106">在部署 System Center Configuration Manager 的服务器上，打开 **"控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="e324b-106">On the server where System Center Configuration Manager is deployed, open **Control Panel**.</span></span> <span data-ttu-id="e324b-107">选择用于卸载或更改程序的程序。</span><span class="sxs-lookup"><span data-stu-id="e324b-107">Select the program that is used to uninstall or change a program.</span></span> <span data-ttu-id="e324b-108">验证 " **Microsoft BitLocker 管理和监视**" 是否显示在 "程序和功能" 列表中。</span><span class="sxs-lookup"><span data-stu-id="e324b-108">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the list of programs and features.</span></span>

    <span data-ttu-id="e324b-109">**注意** 若要验证安装，必须使用在每台服务器上具有本地计算机管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="e324b-109">**Note** To validate the installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>

     

2.  <span data-ttu-id="e324b-110">使用 Configuration Manager 控制台确认显示名为 "MBAM 支持的计算机" 的新集合。</span><span class="sxs-lookup"><span data-stu-id="e324b-110">Use the Configuration Manager console to confirm that a new collection, called “MBAM Supported Computers,” is displayed.</span></span>

    <span data-ttu-id="e324b-111">若要查看 Configuration Manager 2007 的集合，请执行以下操作：单击 "**网站数据库**" （ &lt; **SiteCode** &gt;  -  &lt; **服务器名** &gt; 、 &lt; **SiteName** &gt; ）、"**计算机管理**"。</span><span class="sxs-lookup"><span data-stu-id="e324b-111">To view the collection with Configuration Manager 2007: Click **Site Database** (&lt;**SiteCode**&gt; - &lt;**ServerName**&gt;, &lt;**SiteName**&gt;), **Computer Management**.</span></span>

    <span data-ttu-id="e324b-112">要查看具有 SystemCenter2012 ConfigurationManager 的集合，请执行以下操作：单击 "**资源和合规性**" 工作区，**设备集合**。</span><span class="sxs-lookup"><span data-stu-id="e324b-112">To view the collection with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Device Collections**.</span></span>

3.  <span data-ttu-id="e324b-113">使用 Configuration Manager 控制台验证 " **MBAM** " 文件夹中是否列出以下报表：</span><span class="sxs-lookup"><span data-stu-id="e324b-113">Use the Configuration Manager console to verify that the following reports are listed in the **MBAM** folder:</span></span>

    -   <span data-ttu-id="e324b-114">BitLocker 计算机合规性</span><span class="sxs-lookup"><span data-stu-id="e324b-114">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="e324b-115">BitLocker 企业合规性仪表板</span><span class="sxs-lookup"><span data-stu-id="e324b-115">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="e324b-116">BitLocker 企业合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="e324b-116">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="e324b-117">BitLocker 企业合规性摘要</span><span class="sxs-lookup"><span data-stu-id="e324b-117">BitLocker Enterprise Compliance Summary</span></span>

    <span data-ttu-id="e324b-118">若要查看 Configuration Manager 2007 的报表，请单击 "**报告**"、"**报告服务**"、"\\ &lt; **服务器名** &gt; "、"**报告文件夹**"</span><span class="sxs-lookup"><span data-stu-id="e324b-118">To view the reports with Configuration Manager 2007: Click **Reporting**, **Reporting Services**, \\\\&lt;**ServerName**&gt;, **Report Folders**</span></span>

    <span data-ttu-id="e324b-119">查看带有 SystemCenter2012 ConfigurationManager 的报表：单击 "**监视**" 工作区、"**报告**" 和 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="e324b-119">To view the reports with SystemCenter2012 ConfigurationManager: Click the **Monitoring** workspace, **Reporting**, **Reports**.</span></span>

4.  <span data-ttu-id="e324b-120">使用 Configuration Manager 控制台确认已列出配置基线 "BitLocker 保护"。</span><span class="sxs-lookup"><span data-stu-id="e324b-120">Use the Configuration Manager console to confirm that the configuration baseline “BitLocker Protection” is listed.</span></span>

    <span data-ttu-id="e324b-121">若要查看配置管理器的配置基线2007：单击 "**所需配置管理**"、"**配置基线**"。</span><span class="sxs-lookup"><span data-stu-id="e324b-121">To view the configuration baselines with Configuration Manager 2007: Click **Desired Configuration Management**, **Configuration Baselines**.</span></span>

    <span data-ttu-id="e324b-122">通过 SystemCenter2012 ConfigurationManager 查看配置基线：单击 "**资源和合规性**" 工作区、"**合规性设置**"、"**配置基线**"。</span><span class="sxs-lookup"><span data-stu-id="e324b-122">To view the configuration baselines with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Compliance Settings**, **Configuration Baselines**.</span></span>

5.  <span data-ttu-id="e324b-123">使用 Configuration Manager 控制台确认显示以下新配置项目：</span><span class="sxs-lookup"><span data-stu-id="e324b-123">Use the Configuration Manager console to confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="e324b-124">BitLocker 固定数据驱动器保护</span><span class="sxs-lookup"><span data-stu-id="e324b-124">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="e324b-125">BitLocker 操作系统驱动器保护</span><span class="sxs-lookup"><span data-stu-id="e324b-125">BitLocker Operating System Drive Protection</span></span>

    <span data-ttu-id="e324b-126">若要查看 Configuration Manager 2007 的配置项目，请单击 "**所需的配置管理**"、"**配置项目**"。</span><span class="sxs-lookup"><span data-stu-id="e324b-126">To view the configuration items with Configuration Manager 2007: Click **Desired Configuration Management**, **Configuration Items**.</span></span>

    <span data-ttu-id="e324b-127">若要查看 SystemCenter2012 ConfigurationManager 的配置项目，请执行以下操作：单击 "**资源和合规性**" 工作区、**合规性设置**、**配置项目**。</span><span class="sxs-lookup"><span data-stu-id="e324b-127">To view the configuration items with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Compliance Settings**, **Configuration Items**.</span></span>

## <span data-ttu-id="e324b-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="e324b-128">Related topics</span></span>


[<span data-ttu-id="e324b-129">使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="e324b-129">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





