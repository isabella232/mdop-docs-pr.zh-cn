---
title: 安装 MED-V 的先决条件
description: 安装 MED-V 的先决条件
author: dansimp
ms.assetid: cf3c0906-23eb-4c4a-8951-a65741720f95
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2b432b8c2b06e171eb339aab6c7b15efb20d5919
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803674"
---
# <span data-ttu-id="22d70-103">安装 MED-V 的先决条件</span><span class="sxs-lookup"><span data-stu-id="22d70-103">MED-V Installation Prerequisites</span></span>


<span data-ttu-id="22d70-104">以下是安装 MED-V 的先决条件：</span><span class="sxs-lookup"><span data-stu-id="22d70-104">The following are prerequisites for installing MED-V:</span></span>

[<span data-ttu-id="22d70-105">Active Directory 要求</span><span class="sxs-lookup"><span data-stu-id="22d70-105">Active Directory Requirements</span></span>](#bkmk-activedirectoryrequirements)

[<span data-ttu-id="22d70-106">报表数据库</span><span class="sxs-lookup"><span data-stu-id="22d70-106">Report Database</span></span>](#bkmk-howtoinstallthereportdatabase)

[<span data-ttu-id="22d70-107">防病毒/备份软件配置</span><span class="sxs-lookup"><span data-stu-id="22d70-107">Antivirus/Backup Software Configuration</span></span>](#bkmk-antivirusbackupsoftwareconfiguration)

[<span data-ttu-id="22d70-108">Microsoft Virtual PC 2007 SP1</span><span class="sxs-lookup"><span data-stu-id="22d70-108">Microsoft Virtual PC 2007 SP1</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1)

## <a href="" id="bkmk-activedirectoryrequirements"></a><span data-ttu-id="22d70-109">Active Directory 要求</span><span class="sxs-lookup"><span data-stu-id="22d70-109">Active Directory Requirements</span></span>


<span data-ttu-id="22d70-110">配置 MED-V 服务器时，如果用户不属于服务器所属的同一域，则必须在域之间设置信任。</span><span class="sxs-lookup"><span data-stu-id="22d70-110">When configuring the MED-V server, if users are not part of the same domain the server belongs to, a trust must be set between the domains.</span></span>

## <a href="" id="bkmk-howtoinstallthereportdatabase"></a><span data-ttu-id="22d70-111">如何安装报表数据库</span><span class="sxs-lookup"><span data-stu-id="22d70-111">How to Install the Report Database</span></span>


<span data-ttu-id="22d70-112">存储所有 MED-V 工作区日志需要报表数据库。</span><span class="sxs-lookup"><span data-stu-id="22d70-112">The report database is required for storing all MED-V workspace logs.</span></span> <span data-ttu-id="22d70-113">然后，日志数据库用于生成 MED-V 报告。</span><span class="sxs-lookup"><span data-stu-id="22d70-113">The log database is then used for generating MED-V reports.</span></span> <span data-ttu-id="22d70-114">有关报表的信息，请参阅[Med-v 报告](med-v-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="22d70-114">For information about reports, see [MED-V Reporting](med-v-reporting.md).</span></span>

<span data-ttu-id="22d70-115">SQL Server 可以安装在 MED-V 服务器所在的同一台服务器上，也可以安装在远程服务器上。</span><span class="sxs-lookup"><span data-stu-id="22d70-115">SQL Server can be installed on the same server as the MED-V server or on a remote server.</span></span> <span data-ttu-id="22d70-116">如果在远程服务器上安装，请参阅[在远程服务器上安装 SQL server](#bkmk-installingsqlserveronaremoteserver)。</span><span class="sxs-lookup"><span data-stu-id="22d70-116">If installing on a remote server, see [Installing SQL Server on a Remote Server](#bkmk-installingsqlserveronaremoteserver).</span></span>

### <a href="" id="bkmk-installingsqlserveronaremoteserver"></a><span data-ttu-id="22d70-117">在远程服务器上安装 SQL Server</span><span class="sxs-lookup"><span data-stu-id="22d70-117">Installing SQL Server on a Remote Server</span></span>

**<span data-ttu-id="22d70-118">在远程服务器上安装 SQL Server</span><span class="sxs-lookup"><span data-stu-id="22d70-118">To install SQL Server on a remote server</span></span>**

1.  <span data-ttu-id="22d70-119">在远程服务器上配置以下内容：</span><span class="sxs-lookup"><span data-stu-id="22d70-119">Configure the following on the remote server:</span></span>

    -   <span data-ttu-id="22d70-120">实例名称-默认实例</span><span class="sxs-lookup"><span data-stu-id="22d70-120">Instance name—Default instance</span></span>

    -   <span data-ttu-id="22d70-121">身份验证模式—混合模式</span><span class="sxs-lookup"><span data-stu-id="22d70-121">Authentication mode—Mixed mode</span></span>

    -   <span data-ttu-id="22d70-122">用户-创建的默认用户是 "sa"</span><span class="sxs-lookup"><span data-stu-id="22d70-122">User—The default user created is “sa”</span></span>

    -   <span data-ttu-id="22d70-123">密码-所需密码</span><span class="sxs-lookup"><span data-stu-id="22d70-123">Password—Desired password</span></span>

    -   <span data-ttu-id="22d70-124">排序规则设置-默认</span><span class="sxs-lookup"><span data-stu-id="22d70-124">Collation Settings—Default</span></span>

    -   <span data-ttu-id="22d70-125">使用情况报告设置中的错误-默认</span><span class="sxs-lookup"><span data-stu-id="22d70-125">Error in usage report settings—Default</span></span>

2.  <span data-ttu-id="22d70-126">在 MED-V 服务器上安装以下文件：</span><span class="sxs-lookup"><span data-stu-id="22d70-126">Install the following files on the MED-V server:</span></span>

    -   <span data-ttu-id="22d70-127">若要为 Microsoft SQL Server2008 安装管理包对象集合的先决条件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server2008 Native 客户端](https://go.microsoft.com/fwlink/?LinkId=164039)。</span><span class="sxs-lookup"><span data-stu-id="22d70-127">To install the prerequisites for the management pack objects collection for Microsoft SQL Server2008, download [Microsoft SQL Server2008 Native Client](https://go.microsoft.com/fwlink/?LinkId=164039) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="22d70-128">若要为 Microsoft SQL Server2005 安装管理包对象集合的先决条件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server2005 Native 客户端](https://go.microsoft.com/fwlink/?LinkId=164038)。</span><span class="sxs-lookup"><span data-stu-id="22d70-128">To install the prerequisites for the management pack objects collection for Microsoft SQL Server2005, download [Microsoft SQL Server2005 Native Client](https://go.microsoft.com/fwlink/?LinkId=164038) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="22d70-129">若要为 Microsoft SQL Server2008 安装所需的 dll 文件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server 2008 管理对象集合](https://go.microsoft.com/fwlink/?LinkId=164041)。</span><span class="sxs-lookup"><span data-stu-id="22d70-129">To install the required dll files for Microsoft SQL Server2008, download [Microsoft SQL Server 2008 Management Objects Collection](https://go.microsoft.com/fwlink/?LinkId=164041) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="22d70-130">若要为 Microsoft SQL Server2005 安装所需的 dll 文件，请从 Microsoft 下载中心下载[MICROSOFT Sql Server2005 管理对象](https://go.microsoft.com/fwlink/?LinkId=164040)。</span><span class="sxs-lookup"><span data-stu-id="22d70-130">To install the required dll files for Microsoft SQL Server2005, download [Microsoft SQL Server2005 Management Objects](https://go.microsoft.com/fwlink/?LinkId=164040) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="22d70-131">若要安装为 SQL Server2008 提供其他值的独立安装程序包，请从 Microsoft 下载中心下载[MICROSOFT SQL Server2008 功能包](https://go.microsoft.com/fwlink/?LinkId=163960)。</span><span class="sxs-lookup"><span data-stu-id="22d70-131">To install the stand-alone install packages that provide additional value for SQL Server2008, download the [Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="22d70-132">若要安装为 SQL Server2005 提供其他值的独立安装程序包，请从 Microsoft 下载中心下载[MICROSOFT SQL Server2005 的功能包]( https://go.microsoft.com/fwlink/?LinkId=163961)。</span><span class="sxs-lookup"><span data-stu-id="22d70-132">To install the stand-alone install packages that provide additional value for SQL Server2005, download the [Feature Pack for Microsoft SQL Server2005]( https://go.microsoft.com/fwlink/?LinkId=163961) from the Microsoft Download Center.</span></span>

    <span data-ttu-id="22d70-133">有关这些文件的详细信息，请参阅 microsoft 下载中心的 microsoft [Sql Server2008 功能包](https://go.microsoft.com/fwlink/?LinkId=163960)（ https://go.microsoft.com/fwlink/?LinkId=163960) 或 microsoft [Sql Server2005 的功能包](https://go.microsoft.com/fwlink/?LinkId=163961)，请参阅 microsoft 下载中心（） https://go.microsoft.com/fwlink/?LinkId=163961) 。</span><span class="sxs-lookup"><span data-stu-id="22d70-133">For more information about these files, see [Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960) on the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=163960) or [Feature Pack for Microsoft SQL Server2005](https://go.microsoft.com/fwlink/?LinkId=163961) on the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=163961).</span></span>

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a><span data-ttu-id="22d70-134">防病毒/备份软件配置</span><span class="sxs-lookup"><span data-stu-id="22d70-134">Antivirus/Backup Software Configuration</span></span>


<span data-ttu-id="22d70-135">为了防止防病毒活动影响虚拟桌面的性能，建议在主机上运行的任何防病毒或备份处理中排除以下虚拟机文件类型：</span><span class="sxs-lookup"><span data-stu-id="22d70-135">To prevent antivirus activity from affecting the performance of the virtual desktop, it is recommended where possible to exclude the following virtual machine file types from any antivirus or backup processing running on the host:</span></span>

-   <span data-ttu-id="22d70-136">\*.VMC</span><span class="sxs-lookup"><span data-stu-id="22d70-136">\*.VMC</span></span>

-   <span data-ttu-id="22d70-137">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="22d70-137">\*.VUD</span></span>

-   <span data-ttu-id="22d70-138">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="22d70-138">\*.VSV</span></span>

-   <span data-ttu-id="22d70-139">\*.CKM</span><span class="sxs-lookup"><span data-stu-id="22d70-139">\*.CKM</span></span>

-   <span data-ttu-id="22d70-140">\*.EVHD</span><span class="sxs-lookup"><span data-stu-id="22d70-140">\*.EVHD</span></span>

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1"></a><span data-ttu-id="22d70-141">如何安装和配置 Microsoft Virtual PC2007 SP1</span><span class="sxs-lookup"><span data-stu-id="22d70-141">How to Install and Configure Microsoft Virtual PC2007 SP1</span></span>


<span data-ttu-id="22d70-142">**重要提示** 如果主计算机上存在虚拟 PC for Windows，请在安装 Virtual PC2007 SP1 之前将其卸载。</span><span class="sxs-lookup"><span data-stu-id="22d70-142">**Important** If Virtual PC for Windows exists on the host computer, uninstall it before installing Virtual PC2007 SP1.</span></span>

 

**<span data-ttu-id="22d70-143">安装 Microsoft Virtual PC2007 SP1</span><span class="sxs-lookup"><span data-stu-id="22d70-143">To install Microsoft Virtual PC2007 SP1</span></span>**

1.  <span data-ttu-id="22d70-144">从 Microsoft 下载中心[虚拟 PC 2007 sp1](https://go.microsoft.com/fwlink/?LinkId=142994)下载虚拟 PC2007 SP1。</span><span class="sxs-lookup"><span data-stu-id="22d70-144">Download Virtual PC2007 SP1 from the Microsoft Download Center [Virtual PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=142994).</span></span>

2.  <span data-ttu-id="22d70-145">在主机计算机上运行安装文件，然后按照向导操作。</span><span class="sxs-lookup"><span data-stu-id="22d70-145">Run the installation file on the host computer, and follow the wizard.</span></span>

3.  <span data-ttu-id="22d70-146">在提升模式下在主机计算机上安装 Virtual PC2007 SP1 更新。</span><span class="sxs-lookup"><span data-stu-id="22d70-146">Install Virtual PC2007 SP1 update on the host computer in elevated mode.</span></span>

    <span data-ttu-id="22d70-147">有关详细信息，请参阅[虚拟 PC 2007 SP1 的修补程序包说明](https://go.microsoft.com/fwlink/?LinkId=150575)。</span><span class="sxs-lookup"><span data-stu-id="22d70-147">For more information, see [the description of the hotfix package for Virtual PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=150575).</span></span>

    <span data-ttu-id="22d70-148">**注意** 运行 Virtual PC2007 SP1 需要虚拟 PC2007 SP1 更新。</span><span class="sxs-lookup"><span data-stu-id="22d70-148">**Note** The Virtual PC2007 SP1 update is required for running Virtual PC2007 SP1.</span></span>

     

## <span data-ttu-id="22d70-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="22d70-149">Related topics</span></span>


[<span data-ttu-id="22d70-150">支持的配置</span><span class="sxs-lookup"><span data-stu-id="22d70-150">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

 

 





