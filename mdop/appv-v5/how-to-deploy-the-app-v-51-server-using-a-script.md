---
title: 如何使用脚本部署 App-V 5.1 Server
description: 如何使用脚本部署 App-V 5.1 Server
author: dansimp
ms.assetid: 15c33d7b-9b61-4dbc-8674-399bb33e5f7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/20/2020
ms.openlocfilehash: 579ca685f677aaaa4f5ebb6ac8d2969fdcbe2cd2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798468"
---
# <span data-ttu-id="580a6-103">如何使用脚本部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="580a6-103">How to Deploy the App-V 5.1 Server Using a Script</span></span>

<span data-ttu-id="580a6-104">为了使用命令行成功完成**appv\_server\_setup.exe**服务器设置，必须指定和组合多个参数。</span><span class="sxs-lookup"><span data-stu-id="580a6-104">In order to complete the **appv\_server\_setup.exe** Server setup successfully using the command line, you must specify and combine multiple parameters.</span></span>

## <span data-ttu-id="580a6-105">使用脚本安装 app-v 5.1 服务器</span><span class="sxs-lookup"><span data-stu-id="580a6-105">Install the App-V 5.1 server using a script</span></span>

- <span data-ttu-id="580a6-106">有关使用命令行安装 App-v 5.1 服务器的信息，请使用以下信息。</span><span class="sxs-lookup"><span data-stu-id="580a6-106">Use the following information about installing the App-V 5.1 server using the command line.</span></span>

    > [!NOTE]
    > <span data-ttu-id="580a6-107">通过键入以下命令，还可以使用命令行来访问下表中的信息： " **appv\_server\_setup.exe/？"**。</span><span class="sxs-lookup"><span data-stu-id="580a6-107">The information in the following tables can also be accessed using the command line by typing the following command: **appv\_server\_setup.exe /?**.</span></span>

### <span data-ttu-id="580a6-108">在本地计算机上安装管理服务器和管理数据库</span><span class="sxs-lookup"><span data-stu-id="580a6-108">Install the Management server and Management database on a local machine</span></span>

<span data-ttu-id="580a6-109">以下参数对于 Microsoft SQL Server 的默认实例和自定义实例均有效：</span><span class="sxs-lookup"><span data-stu-id="580a6-109">The following parameters are valid with both the default and custom instance of Microsoft SQL Server:</span></span>

- <span data-ttu-id="580a6-110">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-110">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="580a6-111">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-111">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="580a6-112">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-112">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-113">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-113">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-114">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="580a6-114">/DB_PREDEPLOY_MANAGEMENT</span></span>
- <span data-ttu-id="580a6-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>
- <span data-ttu-id="580a6-116">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-116">/MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="580a6-117">示例：使用 Microsoft SQL Server 的自定义实例</span><span class="sxs-lookup"><span data-stu-id="580a6-117">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement"
```

### <span data-ttu-id="580a6-118">使用本地计算机上的现有管理数据库安装管理服务器</span><span class="sxs-lookup"><span data-stu-id="580a6-118">Install the Management server using an existing Management database on a local machine</span></span>

<span data-ttu-id="580a6-119">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-119">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-120">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-120">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="580a6-121">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-121">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="580a6-122">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-122">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-123">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-123">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-124">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-124">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="580a6-125">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-125">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-126">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-126">/EXISTING_MANAGEMENT_DB_NAME</span></span>

<span data-ttu-id="580a6-127">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（以*斜体*的默认实例为差）：</span><span class="sxs-lookup"><span data-stu-id="580a6-127">To use a custom instance of Microsoft SQL Server, use the following parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-128">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-128">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="580a6-129">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-129">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="580a6-130">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-130">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-131">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-131">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-132">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-132">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="580a6-133">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-133">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-134">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-134">/EXISTING_MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="580a6-135">示例：使用 Microsoft SQL Server 的自定义实例</span><span class="sxs-lookup"><span data-stu-id="580a6-135">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### <span data-ttu-id="580a6-136">使用远程计算机上的现有管理数据库安装管理服务器</span><span class="sxs-lookup"><span data-stu-id="580a6-136">Install the Management server using an existing Management database on a remote machine</span></span>

<span data-ttu-id="580a6-137">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-137">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-138">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-138">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="580a6-139">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-139">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="580a6-140">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-140">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-141">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-141">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-142">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-142">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="580a6-143">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-143">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-144">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-144">/EXISTING_MANAGEMENT_DB_NAME</span></span>

<span data-ttu-id="580a6-145">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-145">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-146">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-146">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="580a6-147">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-147">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="580a6-148">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-148">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-149">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-149">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-150">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-150">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="580a6-151">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-151">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-152">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-152">/EXISTING_MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="580a6-153">示例：使用 Microsoft SQL Server 的自定义实例：</span><span class="sxs-lookup"><span data-stu-id="580a6-153">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME="SqlServermachine.domainName" /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### <span data-ttu-id="580a6-154">在同一台计算机上安装管理数据库和管理服务器</span><span class="sxs-lookup"><span data-stu-id="580a6-154">Install the Management database and the Management Server on the same computer</span></span>

<span data-ttu-id="580a6-155">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-155">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-156">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="580a6-156">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="580a6-157">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-157">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-158">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-158">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="580a6-159">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-159">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="580a6-160">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-160">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="580a6-161">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-161">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-162">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="580a6-162">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="580a6-163">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-163">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-164">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-164">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="580a6-165">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-165">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="580a6-166">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-166">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="580a6-167">示例：使用 Microsoft SQL Server 的自定义实例</span><span class="sxs-lookup"><span data-stu-id="580a6-167">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_SERVER_MACHINE_USE_LOCAL /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="580a6-168">在不同于管理服务器的计算机上安装管理数据库</span><span class="sxs-lookup"><span data-stu-id="580a6-168">Install the Management database on a different computer than the Management server</span></span>

<span data-ttu-id="580a6-169">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-169">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-170">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="580a6-170">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="580a6-171">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-171">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-172">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-172">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="580a6-173">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-173">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="580a6-174">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-174">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="580a6-175">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-175">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-176">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="580a6-176">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="580a6-177">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-177">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-178">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-178">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="580a6-179">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-179">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="580a6-180">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-180">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="580a6-181">示例：使用 Microsoft SQL Server 的自定义实例</span><span class="sxs-lookup"><span data-stu-id="580a6-181">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="580a6-182">安装发布服务器</span><span class="sxs-lookup"><span data-stu-id="580a6-182">Install the publishing server</span></span>

<span data-ttu-id="580a6-183">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="580a6-183">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span>

- <span data-ttu-id="580a6-184">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-184">/PUBLISHING_SERVER</span></span>
- <span data-ttu-id="580a6-185">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-185">/PUBLISHING_MGT_SERVER</span></span>
- <span data-ttu-id="580a6-186">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-186">/PUBLISHING_WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-187">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-187">/PUBLISHING_WEBSITE_PORT</span></span>

**<span data-ttu-id="580a6-188">示例：使用 Microsoft SQL Server 的自定义实例：</span><span class="sxs-lookup"><span data-stu-id="580a6-188">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /PUBLISHING_SERVER /PUBLISHING_MGT_SERVER="http://ManagementServerName:ManagementPort" /PUBLISHING_WEBSITE_NAME="Microsoft AppV Publishing Service" /PUBLISHING_WEBSITE_PORT="8081"
```

### <span data-ttu-id="580a6-189">在本地计算机上安装报表服务器和报告数据库</span><span class="sxs-lookup"><span data-stu-id="580a6-189">Install the Reporting server and Reporting database on a local machine</span></span>

<span data-ttu-id="580a6-190">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-190">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-191">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-191">/REPORTING _SERVER</span></span>
- <span data-ttu-id="580a6-192">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-192">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-193">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-193">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-194">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="580a6-194">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="580a6-195">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-195">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-196">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-196">/REPORTING _DB_NAME</span></span>

<span data-ttu-id="580a6-197">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-197">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-198">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-198">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="580a6-199">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-199">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="580a6-200">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-200">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-201">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-201">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-202">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="580a6-202">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="580a6-203">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-203">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-204">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-204">/REPORTING _DB_NAME</span></span>

**<span data-ttu-id="580a6-205">示例：使用 Microsoft SQL Server 的自定义实例：</span><span class="sxs-lookup"><span data-stu-id="580a6-205">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="580a6-206">安装报告服务器并使用本地计算机上的现有报告数据库</span><span class="sxs-lookup"><span data-stu-id="580a6-206">Install the Reporting server and using an existing Reporting database on a local machine</span></span>

<span data-ttu-id="580a6-207">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-207">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-208">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-208">/REPORTING _SERVER</span></span>
- <span data-ttu-id="580a6-209">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-209">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-210">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-210">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-211">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-211">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="580a6-212">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-212">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-213">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-213">/EXISTING_REPORTING _DB_NAME</span></span>

<span data-ttu-id="580a6-214">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-214">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-215">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-215">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="580a6-216">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-216">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="580a6-217">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-217">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-218">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-218">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-219">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-219">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="580a6-220">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-220">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-221">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-221">/EXISTING_REPORTING _DB_NAME</span></span>

**<span data-ttu-id="580a6-222">示例：使用 Microsoft SQL Server 的自定义实例：</span><span class="sxs-lookup"><span data-stu-id="580a6-222">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="580a6-223">使用远程计算机上的现有报告数据库安装报告服务器</span><span class="sxs-lookup"><span data-stu-id="580a6-223">Install the Reporting server using an existing Reporting database on a remote machine</span></span>

<span data-ttu-id="580a6-224">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-224">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-225">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-225">/REPORTING _SERVER</span></span>
- <span data-ttu-id="580a6-226">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-226">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-227">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-227">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-228">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-228">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="580a6-229">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-229">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-230">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-230">/EXISTING_REPORTING _DB_NAME</span></span>

<span data-ttu-id="580a6-231">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-231">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-232">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-232">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="580a6-233">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-233">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="580a6-234">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-234">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="580a6-235">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-235">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="580a6-236">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-236">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="580a6-237">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-237">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-238">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-238">/EXISTING_REPORTING _DB_NAME</span></span>

**<span data-ttu-id="580a6-239">示例：使用 Microsoft SQL Server 的自定义实例：</span><span class="sxs-lookup"><span data-stu-id="580a6-239">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME="SqlServerMachine.DomainName" /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="580a6-240">在报表服务器所在的同一台计算机上安装报告数据库</span><span class="sxs-lookup"><span data-stu-id="580a6-240">Install the Reporting database on the same computer as the Reporting server</span></span>

<span data-ttu-id="580a6-241">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-241">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-242">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="580a6-242">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="580a6-243">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-243">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="580a6-244">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-244">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="580a6-245">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-245">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="580a6-246">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-246">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="580a6-247">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-247">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-248">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="580a6-248">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="580a6-249">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-249">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="580a6-250">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-250">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="580a6-251">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-251">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="580a6-252">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-252">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="580a6-253">示例：使用 Microsoft SQL Server 的自定义实例：</span><span class="sxs-lookup"><span data-stu-id="580a6-253">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_SERVER_MACHINE_USE_LOCAL /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="580a6-254">在不同于报告服务器的计算机上安装报告数据库</span><span class="sxs-lookup"><span data-stu-id="580a6-254">Install the Reporting database on a different computer than the Reporting server</span></span>

<span data-ttu-id="580a6-255">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-255">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="580a6-256">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="580a6-256">/DB_PREDEPLOY_REPORTING</span></span>
- <span data-ttu-id="580a6-257">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-257">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>
- <span data-ttu-id="580a6-258">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-258">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="580a6-259">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-259">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="580a6-260">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-260">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="580a6-261">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：</span><span class="sxs-lookup"><span data-stu-id="580a6-261">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="580a6-262">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="580a6-262">/DB_PREDEPLOY_REPORTING</span></span>
- <span data-ttu-id="580a6-263">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-263">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>
- <span data-ttu-id="580a6-264">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-264">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="580a6-265">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-265">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="580a6-266">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-266">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="580a6-267">示例：使用 Microsoft SQL Server 的自定义实例：</span><span class="sxs-lookup"><span data-stu-id="580a6-267">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
 appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="580a6-268">参数定义</span><span class="sxs-lookup"><span data-stu-id="580a6-268">Parameter Definitions</span></span>

#### <span data-ttu-id="580a6-269">常规参数</span><span class="sxs-lookup"><span data-stu-id="580a6-269">General Parameters</span></span>

| <span data-ttu-id="580a6-270">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-270">Parameter</span></span> | <span data-ttu-id="580a6-271">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-271">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-272">/QUIET</span><span class="sxs-lookup"><span data-stu-id="580a6-272">/QUIET</span></span> | <span data-ttu-id="580a6-273">指定静默安装。</span><span class="sxs-lookup"><span data-stu-id="580a6-273">Specifies silent install.</span></span> |
| <span data-ttu-id="580a6-274">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="580a6-274">/UNINSTALL</span></span> | <span data-ttu-id="580a6-275">指定卸载。</span><span class="sxs-lookup"><span data-stu-id="580a6-275">Specifies an uninstall.</span></span> |
| <span data-ttu-id="580a6-276">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="580a6-276">/LAYOUT</span></span> | <span data-ttu-id="580a6-277">指定布局操作。</span><span class="sxs-lookup"><span data-stu-id="580a6-277">Specifies layout action.</span></span> <span data-ttu-id="580a6-278">这会将 MSIs 和脚本文件提取到一个文件夹中，而不会实际安装该产品。</span><span class="sxs-lookup"><span data-stu-id="580a6-278">This extracts the MSIs and script files to a folder without actually installing the product.</span></span> <span data-ttu-id="580a6-279">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-279">No value is expected.</span></span> |
| <span data-ttu-id="580a6-280">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="580a6-280">/LAYOUTDIR</span></span> | <span data-ttu-id="580a6-281">指定布局目录。</span><span class="sxs-lookup"><span data-stu-id="580a6-281">Specifies the layout directory.</span></span> <span data-ttu-id="580a6-282">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-282">Takes a string.</span></span> <span data-ttu-id="580a6-283">示例用法： **/LAYOUTDIR = "C:\\Application Virtualization Server"**</span><span class="sxs-lookup"><span data-stu-id="580a6-283">Example usage: **/LAYOUTDIR="C:\\Application Virtualization Server"**</span></span> |
| <span data-ttu-id="580a6-284">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="580a6-284">/INSTALLDIR</span></span> | <span data-ttu-id="580a6-285">指定安装目录。</span><span class="sxs-lookup"><span data-stu-id="580a6-285">Specifies the installation directory.</span></span> <span data-ttu-id="580a6-286">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-286">Takes a string.</span></span> <span data-ttu-id="580a6-287">示例用法： **/INSTALLDIR = "C:\\program files Files\\Application Virtualization\\Server"**</span><span class="sxs-lookup"><span data-stu-id="580a6-287">Example usage: **/INSTALLDIR="C:\\Program Files\\Application Virtualization\\Server"**</span></span> |
| <span data-ttu-id="580a6-288">/MUOPTIN</span><span class="sxs-lookup"><span data-stu-id="580a6-288">/MUOPTIN</span></span> | <span data-ttu-id="580a6-289">启用 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="580a6-289">Enables Microsoft Update.</span></span> <span data-ttu-id="580a6-290">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-290">No value is expected.</span></span> |
| <span data-ttu-id="580a6-291">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="580a6-291">/ACCEPTEULA</span></span> | <span data-ttu-id="580a6-292">接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="580a6-292">Accepts the license agreement.</span></span> <span data-ttu-id="580a6-293">这是无人参与安装所必需的。</span><span class="sxs-lookup"><span data-stu-id="580a6-293">This is required for an unattended installation.</span></span> <span data-ttu-id="580a6-294">示例用法： **/ACCEPTEULA**或 **/ACCEPTEULA = 1**</span><span class="sxs-lookup"><span data-stu-id="580a6-294">Example usage: **/ACCEPTEULA** or **/ACCEPTEULA=1**</span></span> |

#### <span data-ttu-id="580a6-295">管理服务器安装参数</span><span class="sxs-lookup"><span data-stu-id="580a6-295">Management Server Installation Parameters</span></span>

|<span data-ttu-id="580a6-296">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-296">Parameter</span></span> |<span data-ttu-id="580a6-297">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-297">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-298">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-298">/MANAGEMENT_SERVER</span></span> | <span data-ttu-id="580a6-299">指定将安装管理服务器。</span><span class="sxs-lookup"><span data-stu-id="580a6-299">Specifies that the management server will be installed.</span></span> <span data-ttu-id="580a6-300">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="580a6-300">No value is expected</span></span> |
| <span data-ttu-id="580a6-301">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-301">/MANAGEMENT_ADMINACCOUNT</span></span> | <span data-ttu-id="580a6-302">指定将允许管理员访问管理服务器的帐户。</span><span class="sxs-lookup"><span data-stu-id="580a6-302">Specifies the account that will be allowed Administrator access to the management server.</span></span> <span data-ttu-id="580a6-303">这可以是用户帐户或组。</span><span class="sxs-lookup"><span data-stu-id="580a6-303">This can be a user account or a group.</span></span> <span data-ttu-id="580a6-304">示例用法： **/MANAGEMENT_ADMINACCOUNT = "mydomain\\admin"**。</span><span class="sxs-lookup"><span data-stu-id="580a6-304">Example usage: **/MANAGEMENT_ADMINACCOUNT="mydomain\\admin"**.</span></span> <span data-ttu-id="580a6-305">如果未指定 **/MANAGEMENT_SERVER** ，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-305">If **/MANAGEMENT_SERVER** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="580a6-306">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-306">/MANAGEMENT_WEBSITE_NAME</span></span> | <span data-ttu-id="580a6-307">指定将为管理服务创建的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-307">Specifies name of the website that will be created for the management service.</span></span> <span data-ttu-id="580a6-308">示例用法： **/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V 管理服务"**</span><span class="sxs-lookup"><span data-stu-id="580a6-308">Example usage: **/MANAGEMENT_WEBSITE_NAME="Microsoft App-V Management Service"**</span></span> |
| <span data-ttu-id="580a6-309">MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-309">MANAGEMENT_WEBSITE_PORT</span></span> | <span data-ttu-id="580a6-310">指定管理服务将使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="580a6-310">Specifies the port number that will be used by the management service will use.</span></span> <span data-ttu-id="580a6-311">示例用法： **/MANAGEMENT_WEBSITE_PORT = 82**</span><span class="sxs-lookup"><span data-stu-id="580a6-311">Example usage: **/MANAGEMENT_WEBSITE_PORT=82**</span></span> |

#### <span data-ttu-id="580a6-312">管理服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="580a6-312">Parameters for the Management Server Database</span></span>

| <span data-ttu-id="580a6-313">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-313">Parameter</span></span> | <span data-ttu-id="580a6-314">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-314">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-315">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="580a6-315">/DB_PREDEPLOY_MANAGEMENT</span></span> | <span data-ttu-id="580a6-316">指定将安装管理数据库。</span><span class="sxs-lookup"><span data-stu-id="580a6-316">Specifies that the management database will be installed.</span></span> <span data-ttu-id="580a6-317">您必须有足够的数据库权限才能完成此安装。</span><span class="sxs-lookup"><span data-stu-id="580a6-317">You must have sufficient database permissions to complete this installation.</span></span> <span data-ttu-id="580a6-318">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-318">No value is expected.</span></span> |
| <span data-ttu-id="580a6-319">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-319">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="580a6-320">指示应使用默认 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="580a6-320">Indicates that the default SQL instance should be used.</span></span> <span data-ttu-id="580a6-321">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-321">No value is expected.</span></span> |
| <span data-ttu-id="580a6-322">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-322">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="580a6-323">指定应用于创建新数据库的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-323">Specifies the name of the custom SQL instance that should be used to create a new database.</span></span> <span data-ttu-id="580a6-324">示例用法： **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**。</span><span class="sxs-lookup"><span data-stu-id="580a6-324">Example usage: **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**.</span></span> <span data-ttu-id="580a6-325">如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-325">If **/DB_PREDEPLOY_MANAGEMENT** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="580a6-326">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-326">/MANAGEMENT_DB_NAME</span></span> | <span data-ttu-id="580a6-327">指定应创建的新管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-327">Specifies the name of the new management database that should be created.</span></span> <span data-ttu-id="580a6-328">示例用法： **/MANAGEMENT_DB_NAME = "AppVMgmtDB"**。</span><span class="sxs-lookup"><span data-stu-id="580a6-328">Example usage: **/MANAGEMENT_DB_NAME="AppVMgmtDB"**.</span></span> <span data-ttu-id="580a6-329">如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-329">If **/DB_PREDEPLOY_MANAGEMENT** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="580a6-330">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-330">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span> | <span data-ttu-id="580a6-331">指示是否在本地服务器上安装了将访问该数据库的管理服务器。</span><span class="sxs-lookup"><span data-stu-id="580a6-331">Indicates if the management server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="580a6-332">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-332">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="580a6-333">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-333">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span> | <span data-ttu-id="580a6-334">指定将安装管理服务器的远程计算机的计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="580a6-334">Specifies the machine account of the remote machine that the management server will be installed on.</span></span> <span data-ttu-id="580a6-335">示例用法： **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\\computername"**</span><span class="sxs-lookup"><span data-stu-id="580a6-335">Example usage: **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="domain\\computername"**</span></span> |
| <span data-ttu-id="580a6-336">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-336">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span> | <span data-ttu-id="580a6-337">指示将用于安装管理服务器的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="580a6-337">Indicates the Administrator account that will be used to install the management server.</span></span> <span data-ttu-id="580a6-338">示例用法： **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"**</span><span class="sxs-lookup"><span data-stu-id="580a6-338">Example usage: **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT ="domain\\alias"**</span></span> |

#### <span data-ttu-id="580a6-339">用于安装发布服务器的参数</span><span class="sxs-lookup"><span data-stu-id="580a6-339">Parameters for Installing Publishing Server</span></span>

| <span data-ttu-id="580a6-340">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-340">Parameter</span></span> | <span data-ttu-id="580a6-341">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-341">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-342">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-342">/PUBLISHING_SERVER</span></span> | <span data-ttu-id="580a6-343">指定将安装发布服务器。</span><span class="sxs-lookup"><span data-stu-id="580a6-343">Specifies that the Publishing Server will be installed.</span></span> <span data-ttu-id="580a6-344">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-344">No value is expected.</span></span> |
| <span data-ttu-id="580a6-345">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-345">/PUBLISHING_MGT_SERVER</span></span> | <span data-ttu-id="580a6-346">指定发布服务器将连接到的管理服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="580a6-346">Specifies the URL to Management Service the Publishing server will connect to.</span></span> <span data-ttu-id="580a6-347">示例用法： \*\*http:// &lt; 管理服务器名称 &gt; ： &lt; 管理服务器端口号 &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="580a6-347">Example usage: **http://&lt;management server name&gt;:&lt;Management server port number&gt;**.</span></span> <span data-ttu-id="580a6-348">如果未使用 **/PUBLISHING_SERVER** ，此参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-348">If **/PUBLISHING_SERVER** is not used, this parameter will be ignored.</span></span> |
| <span data-ttu-id="580a6-349">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-349">/PUBLISHING_WEBSITE_NAME</span></span> | <span data-ttu-id="580a6-350">指定将为发布服务创建的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-350">Specifies name of the website that will be created for the publishing service.</span></span> <span data-ttu-id="580a6-351">示例用法： **/PUBLISHING_WEBSITE_NAME = "Microsoft App-V 发布服务"**</span><span class="sxs-lookup"><span data-stu-id="580a6-351">Example usage: **/PUBLISHING_WEBSITE_NAME="Microsoft App-V Publishing Service"**</span></span> |
| <span data-ttu-id="580a6-352">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-352">/PUBLISHING_WEBSITE_PORT</span></span> | <span data-ttu-id="580a6-353">指定发布服务使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="580a6-353">Specifies the port number used by the publishing service.</span></span> <span data-ttu-id="580a6-354">示例用法： **/PUBLISHING_WEBSITE_PORT = 83**</span><span class="sxs-lookup"><span data-stu-id="580a6-354">Example usage: **/PUBLISHING_WEBSITE_PORT=83**</span></span> |

#### <span data-ttu-id="580a6-355">用于报告服务器的参数</span><span class="sxs-lookup"><span data-stu-id="580a6-355">Parameters for Reporting Server</span></span>

| <span data-ttu-id="580a6-356">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-356">Parameter</span></span> | <span data-ttu-id="580a6-357">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-357">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-358">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="580a6-358">/REPORTING_SERVER</span></span> | <span data-ttu-id="580a6-359">指定将安装报表服务器。</span><span class="sxs-lookup"><span data-stu-id="580a6-359">Specifies that the Reporting Server will be installed.</span></span> <span data-ttu-id="580a6-360">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-360">No value is expected.</span></span> |
| <span data-ttu-id="580a6-361">/REPORTING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-361">/REPORTING_WEBSITE_NAME</span></span> | <span data-ttu-id="580a6-362">指定将为报告服务创建的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-362">Specifies name of the website that will be created for the Reporting Service.</span></span> <span data-ttu-id="580a6-363">示例用法： **/REPORTING_WEBSITE_NAME = "Microsoft App-V ReportingService"**</span><span class="sxs-lookup"><span data-stu-id="580a6-363">Example usage: **/REPORTING_WEBSITE_NAME="Microsoft App-V ReportingService"**</span></span> |
| <span data-ttu-id="580a6-364">/REPORTING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="580a6-364">/REPORTING_WEBSITE_PORT</span></span> | <span data-ttu-id="580a6-365">指定报表服务将使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="580a6-365">Specifies the port number that the Reporting Service will use.</span></span> <span data-ttu-id="580a6-366">示例用法： **/REPORTING_WEBSITE_PORT = 82**</span><span class="sxs-lookup"><span data-stu-id="580a6-366">Example usage: **/REPORTING_WEBSITE_PORT=82**</span></span> |

#### <span data-ttu-id="580a6-367">用于使用现有报表服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="580a6-367">Parameters for using an Existing Reporting Server Database</span></span>

| <span data-ttu-id="580a6-368">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-368">Parameter</span></span> | <span data-ttu-id="580a6-369">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-369">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-370">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-370">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span> | <span data-ttu-id="580a6-371">指示本地服务器上安装了 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="580a6-371">Indicates that the Microsoft SQL Server is installed on the local server.</span></span> <span data-ttu-id="580a6-372">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-372">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="580a6-373">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-373">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span> | <span data-ttu-id="580a6-374">指定安装 SQL Server 的远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-374">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="580a6-375">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-375">Takes a string.</span></span> <span data-ttu-id="580a6-376">示例用法： **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"**</span><span class="sxs-lookup"><span data-stu-id="580a6-376">Example usage: **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME="mycomputer1"**</span></span> |
| <span data-ttu-id="580a6-377">/EXISTING_ 报告 _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-377">/EXISTING_ REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="580a6-378">指示要使用的默认 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="580a6-378">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="580a6-379">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-379">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="580a6-380">/EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-380">/EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="580a6-381">指定应使用的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-381">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="580a6-382">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-382">Takes a string.</span></span> <span data-ttu-id="580a6-383">示例用法： **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**</span><span class="sxs-lookup"><span data-stu-id="580a6-383">Example usage: **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**</span></span> |
| <span data-ttu-id="580a6-384">/EXISTING_ 报告 _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-384">/EXISTING_ REPORTING _DB_NAME</span></span> | <span data-ttu-id="580a6-385">指定应使用的现有报告数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-385">Specifies the name of the existing Reporting database that should be used.</span></span> <span data-ttu-id="580a6-386">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-386">Takes a string.</span></span> <span data-ttu-id="580a6-387">示例用法： **/EXISTING_REPORTING_DB_NAME = "AppVReporting"**</span><span class="sxs-lookup"><span data-stu-id="580a6-387">Example usage: **/EXISTING_REPORTING_DB_NAME="AppVReporting"**</span></span> |

#### <span data-ttu-id="580a6-388">用于安装报表服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="580a6-388">Parameters for installing Reporting Server Database</span></span>

| <span data-ttu-id="580a6-389">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-389">Parameter</span></span> | <span data-ttu-id="580a6-390">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-390">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-391">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="580a6-391">/DB_PREDEPLOY_REPORTING</span></span> | <span data-ttu-id="580a6-392">指定将安装报告数据库。</span><span class="sxs-lookup"><span data-stu-id="580a6-392">Specifies that the Reporting Database will be installed.</span></span> <span data-ttu-id="580a6-393">此安装需要 DBA 权限。</span><span class="sxs-lookup"><span data-stu-id="580a6-393">DBA permissions are required for this installation.</span></span> <span data-ttu-id="580a6-394">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-394">No value is expected.</span></span> |
| <span data-ttu-id="580a6-395">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-395">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="580a6-396">指定应使用的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-396">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="580a6-397">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-397">Takes a string.</span></span> <span data-ttu-id="580a6-398">示例用法： **/REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**</span><span class="sxs-lookup"><span data-stu-id="580a6-398">Example usage: **/REPORTING_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**</span></span> |
| <span data-ttu-id="580a6-399">/REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-399">/REPORTING_DB_NAME</span></span> | <span data-ttu-id="580a6-400">指定应创建的新报告数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-400">Specifies the name of the new Reporting database that should be created.</span></span> <span data-ttu-id="580a6-401">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-401">Takes a string.</span></span> <span data-ttu-id="580a6-402">示例用法： **/REPORTING_DB_NAME = "AppVMgmtDB"**</span><span class="sxs-lookup"><span data-stu-id="580a6-402">Example usage: **/REPORTING_DB_NAME="AppVMgmtDB"**</span></span> |
| <span data-ttu-id="580a6-403">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-403">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span> | <span data-ttu-id="580a6-404">指示将访问数据库的报表服务器安装在本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="580a6-404">Indicates that the Reporting server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="580a6-405">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-405">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="580a6-406">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-406">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span> | <span data-ttu-id="580a6-407">指定将安装报表服务器的远程计算机的计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="580a6-407">Specifies the machine account of the remote machine that the Reporting server will be installed on.</span></span> <span data-ttu-id="580a6-408">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-408">Takes a string.</span></span> <span data-ttu-id="580a6-409">示例用法： **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"**</span><span class="sxs-lookup"><span data-stu-id="580a6-409">Example usage: **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="domain\computername"**</span></span> |
| <span data-ttu-id="580a6-410">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="580a6-410">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span> | <span data-ttu-id="580a6-411">指示将用于安装 app-v 报告服务器的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="580a6-411">Indicates the Administrator account that will be used to install the App-V Reporting Server.</span></span> <span data-ttu-id="580a6-412">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-412">Takes a string.</span></span> <span data-ttu-id="580a6-413">示例用法： **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"**</span><span class="sxs-lookup"><span data-stu-id="580a6-413">Example usage: **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="domain\\alias"**</span></span> |

#### <span data-ttu-id="580a6-414">用于使用现有管理服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="580a6-414">Parameters for using an existing Management Server Database</span></span>

| <span data-ttu-id="580a6-415">参数</span><span class="sxs-lookup"><span data-stu-id="580a6-415">Parameter</span></span> | <span data-ttu-id="580a6-416">信息</span><span class="sxs-lookup"><span data-stu-id="580a6-416">Information</span></span> |
|--|--|
| <span data-ttu-id="580a6-417">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="580a6-417">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span> | <span data-ttu-id="580a6-418">指示 SQL Server 安装在本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="580a6-418">Indicates that the SQL Server is installed on the local server.</span></span> <span data-ttu-id="580a6-419">开关参数，因此不需要任何值。如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-419">Switch parameter so no value is expected.If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="580a6-420">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-420">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span> | <span data-ttu-id="580a6-421">指定安装 SQL Server 的远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-421">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="580a6-422">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="580a6-422">Takes a string.</span></span> <span data-ttu-id="580a6-423">示例用法： **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"**</span><span class="sxs-lookup"><span data-stu-id="580a6-423">Example usage: **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME="mycomputer1"**</span></span> |
| <span data-ttu-id="580a6-424">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="580a6-424">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="580a6-425">指示要使用的默认 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="580a6-425">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="580a6-426">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="580a6-426">Switch parameter so no value is expected.</span></span> <span data-ttu-id="580a6-427">如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-427">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="580a6-428">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="580a6-428">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="580a6-429">指定将使用的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-429">Specifies the name of the custom SQL instance that will be used.</span></span> <span data-ttu-id="580a6-430">示例用法 **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement"**。</span><span class="sxs-lookup"><span data-stu-id="580a6-430">Example usage **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE="AppVManagement"**.</span></span> <span data-ttu-id="580a6-431">如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-431">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="580a6-432">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="580a6-432">/EXISTING_MANAGEMENT_DB_NAME</span></span> | <span data-ttu-id="580a6-433">指定应使用的现有管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="580a6-433">Specifies the name of the existing management database that should be used.</span></span> <span data-ttu-id="580a6-434">示例用法： **/EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB"**。</span><span class="sxs-lookup"><span data-stu-id="580a6-434">Example usage: **/EXISTING_MANAGEMENT_DB_NAME="AppVMgmtDB"**.</span></span> <span data-ttu-id="580a6-435">如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="580a6-435">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |

<span data-ttu-id="580a6-436">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="580a6-436">Got an App-V issue?</span></span> <span data-ttu-id="580a6-437">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="580a6-437">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="580a6-438">相关主题</span><span class="sxs-lookup"><span data-stu-id="580a6-438">Related topics</span></span>

[<span data-ttu-id="580a6-439">部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="580a6-439">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)
