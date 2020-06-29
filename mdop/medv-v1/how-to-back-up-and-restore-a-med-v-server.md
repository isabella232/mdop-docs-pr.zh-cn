---
title: 如何备份和还原 MED-V 服务器
description: 如何备份和还原 MED-V 服务器
author: dansimp
ms.assetid: 8d05e3a4-279b-4ce6-a319-8a09e7a30c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51cfe3727896ed68a1fd67441174a294a1073cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803298"
---
# <span data-ttu-id="85010-103">如何备份和还原 MED-V 服务器</span><span class="sxs-lookup"><span data-stu-id="85010-103">How to Back Up and Restore a MED-V Server</span></span>


<span data-ttu-id="85010-104">可以备份服务器上的 XML 文件，然后在服务器上的数据丢失的情况下还原。</span><span class="sxs-lookup"><span data-stu-id="85010-104">XML files located on the server can be backed up and then restored in case of loss of data on the server.</span></span>

**<span data-ttu-id="85010-105">备份 MED-V 服务器</span><span class="sxs-lookup"><span data-stu-id="85010-105">To back up a MED-V server</span></span>**

-   <span data-ttu-id="85010-106">备份位于\* &lt; InstallDir &gt; \\Servers\\ConfigurationServer\*中的以下文件：</span><span class="sxs-lookup"><span data-stu-id="85010-106">Back up the following files, located in *&lt;InstallDir&gt;\\Servers\\ConfigurationServer*:</span></span>

    <span data-ttu-id="85010-107">**注意** 如果配置已更改为默认值，则文件可能存储在其他位置。</span><span class="sxs-lookup"><span data-stu-id="85010-107">**Note** If the configuration has been changed from the default, the files might be stored in a different location.</span></span>

     

    -   <span data-ttu-id="85010-108">ClientPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="85010-108">ClientPolicy.xml</span></span>

    -   <span data-ttu-id="85010-109">ClientSettings.xml</span><span class="sxs-lookup"><span data-stu-id="85010-109">ClientSettings.xml</span></span>

    -   <span data-ttu-id="85010-110">ConfigurationFiles.xml</span><span class="sxs-lookup"><span data-stu-id="85010-110">ConfigurationFiles.xml</span></span>

    -   <span data-ttu-id="85010-111">OrganizationPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="85010-111">OrganizationPolicy.xml</span></span>

    -   <span data-ttu-id="85010-112">WorkspaceKeys.xml</span><span class="sxs-lookup"><span data-stu-id="85010-112">WorkspaceKeys.xml</span></span>

    <span data-ttu-id="85010-113">**注意** ServerSettings.xml 文件也可以备份。</span><span class="sxs-lookup"><span data-stu-id="85010-113">**Note** The ServerSettings.xml file can be backed up as well.</span></span> <span data-ttu-id="85010-114">但是，如果特定配置已更改（例如，在原始服务器上，则 MED-V VM 目录位于 "*C:\\Vms*" 中，在新服务器上不存在此类目录），可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="85010-114">However, if a specific configuration has been changed (for example, on the original server, the MED-V VMS directory is located in "*C:\\Vms*" and such a directory does not exist on the new server), it can cause an error.</span></span>

     

**<span data-ttu-id="85010-115">还原 MED-V 服务器</span><span class="sxs-lookup"><span data-stu-id="85010-115">To restore a MED-V server</span></span>**

1.  <span data-ttu-id="85010-116">安装新的 MED-V 服务器。</span><span class="sxs-lookup"><span data-stu-id="85010-116">Install a new MED-V server.</span></span>

2.  <span data-ttu-id="85010-117">将备份文件复制到以下目录：</span><span class="sxs-lookup"><span data-stu-id="85010-117">Copy the backup files to the following directory:</span></span>

    *<span data-ttu-id="85010-118">&lt;InstallDir &gt; \\Servers\\ConfigurationServer</span><span class="sxs-lookup"><span data-stu-id="85010-118">&lt;InstallDir&gt;\\Servers\\ConfigurationServer</span></span>*

3.  <span data-ttu-id="85010-119">重新启动 MED-V 服务。</span><span class="sxs-lookup"><span data-stu-id="85010-119">Restart the MED-V service.</span></span>

 

 





