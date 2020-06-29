---
title: MED-V 1.0 SP1 升级清单
description: MED-V 1.0 SP1 升级清单
author: dansimp
ms.assetid: 1a462b37-8c7a-4826-9175-0b1b701d345b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9c418eff8dfb6146204d7d9212d42e49db000fb1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804134"
---
# <span data-ttu-id="73056-103">MED-V 1.0 SP1 升级清单</span><span class="sxs-lookup"><span data-stu-id="73056-103">MED-V 1.0 SP1 Upgrade Checklist</span></span>


<span data-ttu-id="73056-104">若要将 Microsoft 企业版桌面虚拟化（MED-V）1.0 升级到 MED-V 1.0 服务 Pack1 （SP1），必须升级客户端。</span><span class="sxs-lookup"><span data-stu-id="73056-104">To upgrade Microsoft Enterprise Desktop Virtualization (MED-V)1.0 to MED-V1.0 Service Pack1 (SP1), the client must be upgraded.</span></span> <span data-ttu-id="73056-105">服务器可以选择升级。</span><span class="sxs-lookup"><span data-stu-id="73056-105">The server can optionally be upgraded.</span></span>

## <span data-ttu-id="73056-106">服务器升级</span><span class="sxs-lookup"><span data-stu-id="73056-106">Server Upgrade</span></span>


**<span data-ttu-id="73056-107">将 MED-V 1.0 服务器升级到 MED-V 1.0 SP1</span><span class="sxs-lookup"><span data-stu-id="73056-107">To upgrade the MED-V1.0 server to MED-V1.0 SP1</span></span>**

1.  <span data-ttu-id="73056-108">备份位于\* &lt; InstallDir &gt; /Servers/ConfigurationServer\*目录中的以下文件：</span><span class="sxs-lookup"><span data-stu-id="73056-108">Back up the following files that are located in the *&lt;InstallDir&gt; / Servers / ConfigurationServer* directory:</span></span>

    -   <span data-ttu-id="73056-109">OrganizationalPolicy.XML</span><span class="sxs-lookup"><span data-stu-id="73056-109">OrganizationalPolicy.XML</span></span>

    -   <span data-ttu-id="73056-110">ClientPolicy.XML</span><span class="sxs-lookup"><span data-stu-id="73056-110">ClientPolicy.XML</span></span>

    -   <span data-ttu-id="73056-111">WorkspaceKeys.XML</span><span class="sxs-lookup"><span data-stu-id="73056-111">WorkspaceKeys.XML</span></span>

2.  <span data-ttu-id="73056-112">备份\* &lt; InstallDir &gt; /服务器/ServerSettings.xml\*文件。</span><span class="sxs-lookup"><span data-stu-id="73056-112">Back up the *&lt;InstallDir&gt; / Servers / ServerSettings.xml* file.</span></span>

3.  <span data-ttu-id="73056-113">卸载 MED-V 1.0 服务器。</span><span class="sxs-lookup"><span data-stu-id="73056-113">Uninstall the MED-V1.0 server.</span></span>

4.  <span data-ttu-id="73056-114">安装 MED-V 1.0 SP1 服务器。</span><span class="sxs-lookup"><span data-stu-id="73056-114">Install the MED-V1.0 SP1 server.</span></span>

5.  <span data-ttu-id="73056-115">将备份文件还原到相应的目录。</span><span class="sxs-lookup"><span data-stu-id="73056-115">Restore the backup files to the appropriate directories.</span></span>

6.  <span data-ttu-id="73056-116">重新启动 MED-V 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="73056-116">Restart the MED-V server service.</span></span>

<span data-ttu-id="73056-117">**注意** 如果服务器配置已更改为默认值，则文件可能存储在其他位置。</span><span class="sxs-lookup"><span data-stu-id="73056-117">**Note** If the server configuration has been changed from the default, the files might be stored in a different location.</span></span>

 

## <span data-ttu-id="73056-118">客户端升级</span><span class="sxs-lookup"><span data-stu-id="73056-118">Client Upgrade</span></span>


<span data-ttu-id="73056-119">若要将 MED-V 1.0 客户端升级到 MED-V 1.0 SP1，请在 MED-V 1.0 客户端上安装 .msp 文件。</span><span class="sxs-lookup"><span data-stu-id="73056-119">To upgrade the MED-V1.0 client to MED-V1.0 SP1, install the .msp file on a MED-V1.0 client.</span></span> <span data-ttu-id="73056-120">客户端和 MED-V 将自动升级。</span><span class="sxs-lookup"><span data-stu-id="73056-120">The client and MED-V are automatically upgraded.</span></span>

 

 





