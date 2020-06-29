---
title: 如何使用脚本部署 App-V 5.0 Server
description: 如何使用脚本部署 App-V 5.0 Server
author: dansimp
ms.assetid: b91a35c8-df9e-4065-9187-abafbe565b84
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: aeb16d166fe7b1c4bb418c212024c49f6b151b94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798478"
---
# <span data-ttu-id="e8e0e-103">如何使用脚本部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="e8e0e-103">How to Deploy the App-V 5.0 Server Using a Script</span></span>


<span data-ttu-id="e8e0e-104">为了使用命令行成功完成**appv\_server\_setup.exe**服务器设置，必须指定和组合多个参数。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-104">In order to complete the **appv\_server\_setup.exe** Server setup successfully using the command line, you must specify and combine multiple parameters.</span></span>

<span data-ttu-id="e8e0e-105">有关使用命令行安装 App-v 5.0 服务器的详细信息，请使用下表。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-105">Use the following tables for more information about installing the App-V 5.0 server using the command line.</span></span>

>[!NOTE]
> <span data-ttu-id="e8e0e-106">通过键入以下命令，还可以使用命令行访问下表中的信息：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-106">The information in the following tables can also be accessed using the command line by typing the following command:</span></span>
>```
> appv\_server\_setup.exe /?
>```

## <span data-ttu-id="e8e0e-107">常见参数和示例</span><span class="sxs-lookup"><span data-stu-id="e8e0e-107">Common parameters and Examples</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-108">在本地计算机上安装管理服务器和管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-108">To Install the Management server and Management database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-109">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-109">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-110">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-110">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-111">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-111">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-112">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-112">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-113">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-113">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-114">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-114">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-116">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-116">/MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-117">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-117">To use a custom instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-118">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-118">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-119">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-119">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-120">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-120">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-121">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-121">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-122">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-122">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-123">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-123">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-124">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-124">/MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-125">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-125">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-126">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-126">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-127">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-127">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="e8e0e-128">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-128">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="e8e0e-129">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-129">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="e8e0e-130">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-130">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="e8e0e-131">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-131">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="e8e0e-132">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-132">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-133">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-133">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>
     
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-134">使用本地计算机上的现有管理数据库安装管理服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-134">To Install the Management server using an existing Management database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-135">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-135">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-136">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-136">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-137">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-137">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-138">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-138">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-139">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-139">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-140">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-140">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-141">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-141">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-142">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-142">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-143">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-143">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-144">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-144">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-145">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-145">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-146">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-146">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-147">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-147">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-148">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-148">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-149">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-149">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-150">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-150">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-151">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-151">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-152">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-152">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-153">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-153">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="e8e0e-154">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-154">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="e8e0e-155">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-155">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="e8e0e-156">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-156">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="e8e0e-157">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-157">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="e8e0e-158">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-158">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE =”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-159">/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-159">/EXISTING_MANAGEMENT_DB_NAME =”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>  

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-160">在远程计算机上使用现有管理数据库安装管理服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-160">To install the Management server using an existing Management database on a remote machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-161">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-161">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-162">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-162">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-163">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-163">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-164">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-164">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-165">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-165">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-166">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-166">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-167">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-167">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-168">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-168">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-169">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-169">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-170">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-170">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-171">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-171">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-172">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-172">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-173">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-173">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-174">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-174">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-175">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-175">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-176">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-176">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-177">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-177">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-178">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-178">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-179">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-179">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="e8e0e-180">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-180">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="e8e0e-181">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-181">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="e8e0e-182">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-182">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="e8e0e-183">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME = "SqlServermachine"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-183">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME=”SqlServermachine.domainName”</span></span></p>
    <p><span data-ttu-id="e8e0e-184">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-184">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE =”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-185">/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-185">/EXISTING_MANAGEMENT_DB_NAME =”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-186">在同一台计算机上安装管理数据库和管理服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-186">To Install the Management database and the Management Server on the same computer.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-187">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-187">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-188">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-188">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-189">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-189">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-190">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-190">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-191">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-191">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-192">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-192">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-193">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-193">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-194">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-194">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-195">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-195">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-196">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-196">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-197">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-197">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-198">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-198">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-199">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-199">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-200">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-200">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-201">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-201">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="e8e0e-202">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-202">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-203">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-203">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p>
    <p><span data-ttu-id="e8e0e-204">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-204">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="e8e0e-205">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-205">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-206">在不同于管理服务器的计算机上安装管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-206">To install the Management database on a different computer than the Management server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-207">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-207">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-208">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-208">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-209">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-209">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-210">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-210">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-211">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-211">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-212">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-212">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-213">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-213">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-214">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-214">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-215">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-215">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-216">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-216">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-217">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-217">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-218">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-218">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-219">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-219">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-220">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-220">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-221">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-221">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="e8e0e-222">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-222">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-223">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-223">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p>
    <p><span data-ttu-id="e8e0e-224">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "Domain\MachineAccount"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-224">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT=”Domain\MachineAccount”</span></span></p>
    <p><span data-ttu-id="e8e0e-225">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-225">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-226">安装发布服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-226">To Install the publishing server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-227">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-227">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-228">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-228">/PUBLISHING_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-229">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-229">/PUBLISHING_MGT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-230">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-230">/PUBLISHING_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-231">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-231">/PUBLISHING_WEBSITE_PORT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-232">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-232">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-233">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-233">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-234">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-234">/PUBLISHING_SERVER</span></span></p>
    <p><span data-ttu-id="e8e0e-235">/PUBLISHING_MGT_SERVER = " http://ManagementServerName:ManagementPort "</span><span class="sxs-lookup"><span data-stu-id="e8e0e-235">/PUBLISHING_MGT_SERVER=”http://ManagementServerName:ManagementPort”</span></span></p>
    <p><span data-ttu-id="e8e0e-236">/PUBLISHING_WEBSITE_NAME = "Microsoft AppV 发布服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-236">/PUBLISHING_WEBSITE_NAME=”Microsoft AppV Publishing Service”</span></span></p>
    <p><span data-ttu-id="e8e0e-237">/PUBLISHING_WEBSITE_PORT = "8081"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-237">/PUBLISHING_WEBSITE_PORT=”8081”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-238">在本地计算机上安装报表服务器和报告数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-238">To Install the Reporting server and Reporting database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-239">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-239">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-240">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-240">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-241">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-241">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-242">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-242">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-243">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-243">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-244">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-244">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-245">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-245">/REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-246">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-246">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-247">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-247">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-248">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-248">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-249">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-249">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-250">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-250">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-251">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-251">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-252">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-252">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-253">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-253">/REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-254">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-254">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-255">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-255">/appv_server_setup.exe /QUIET</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-256">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-256">/REPORTING_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-257">/REPORTING_WEBSITE_NAME = "Microsoft AppV 报告服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-257">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-258">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-258">/REPORTING_WEBSITE_PORT=”8082”</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-259">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-259">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-260">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-260">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-261">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-261">/REPORTING_DB_NAME=”AppVReporting”</span></span></p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-262">安装报告服务器并使用本地计算机上的现有报告数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-262">To Install the Reporting server and using an existing Reporting database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-263">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-263">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-264">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-264">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-265">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-265">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-266">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-266">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-267">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-267">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-268">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-268">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-269">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-269">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-270">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-270">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-271">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-271">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-272">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-272">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-273">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-273">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-274">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-274">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-275">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-275">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-276">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-276">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-277">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-277">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-278">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-278">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-279">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-279">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-280">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-280">/REPORTING_SERVER</span></span></p>
    <p><span data-ttu-id="e8e0e-281">/REPORTING_WEBSITE_NAME = "Microsoft AppV 报告服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-281">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p>
    <p><span data-ttu-id="e8e0e-282">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-282">/REPORTING_WEBSITE_PORT=”8082”</span></span></p>
    <p><span data-ttu-id="e8e0e-283">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-283">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="e8e0e-284">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-284">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-285">/EXITING_REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-285">/EXITING_REPORTING_DB_NAME=”AppVReporting”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-286">使用远程计算机上的现有报告数据库安装报告服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-286">To Install the Reporting server using an existing Reporting database on a remote machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-287">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-287">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-288">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-288">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-289">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-289">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-290">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-290">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-291">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-291">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-292">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-292">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-293">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-293">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-294">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-294">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-295">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-295">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-296">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-296">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-297">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-297">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-298">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-298">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-299">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-299">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-300">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-300">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-301">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-301">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-302">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-302">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-303">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-303">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-304">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-304">/REPORTING_SERVER</span></span></p>
    <p><span data-ttu-id="e8e0e-305">/REPORTING_WEBSITE_NAME = "Microsoft AppV 报告服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-305">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p>
    <p><span data-ttu-id="e8e0e-306">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-306">/REPORTING_WEBSITE_PORT=”8082”</span></span></p>
    <p><span data-ttu-id="e8e0e-307">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME = "SqlServerMachine"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-307">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME=”SqlServerMachine.DomainName”</span></span></p>
    <p><span data-ttu-id="e8e0e-308">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-308">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-309">/EXITING_REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-309">/EXITING_REPORTING_DB_NAME=”AppVReporting”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-310">在报表服务器所在的同一台计算机上安装报告数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-310">To install the Reporting database on the same computer as the Reporting server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-311">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-311">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-312">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-312">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-313">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-313">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-314">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-314">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-315">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-315">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-316">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-316">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-317">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-317">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-318">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-318">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-319">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-319">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-320">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-320">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-321">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-321">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-322">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-322">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-323">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-323">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-324">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-324">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-325">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-325">/DB_PREDEPLOY_REPORTING</span></span></p>
    <p><span data-ttu-id="e8e0e-326">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-326">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-327">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-327">/REPORTING_DB_NAME=”AppVReporting”</span></span></p>
    <p><span data-ttu-id="e8e0e-328">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-328">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="e8e0e-329">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-329">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-330">在不同于报表服务器的计算机上安装报告数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-330">To install the Reporting database on a different computer than the Reporting server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-331">若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-331">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-332">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-332">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-333">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-333">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-334">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-334">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-335">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-335">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-336">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-336">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-337">若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-337">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e8e0e-338">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-338">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-339">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-339">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-340">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-340">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-341">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-341">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="e8e0e-342">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-342">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="e8e0e-343">使用 Microsoft SQL Server 的自定义实例示例：</span><span class="sxs-lookup"><span data-stu-id="e8e0e-343">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="e8e0e-344">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-344">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="e8e0e-345">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-345">/DB_PREDEPLOY_REPORTING</span></span></p>
    <p><span data-ttu-id="e8e0e-346">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-346">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="e8e0e-347">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-347">/REPORTING_DB_NAME=”AppVReporting”</span></span></p>
    <p><span data-ttu-id="e8e0e-348">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "Domain\MachineAccount"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-348">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT=”Domain\MachineAccount”</span></span></p>
    <p><span data-ttu-id="e8e0e-349">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-349">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

## <span data-ttu-id="e8e0e-350">参数定义</span><span class="sxs-lookup"><span data-stu-id="e8e0e-350">Parameter Definitions</span></span>

### <span data-ttu-id="e8e0e-351">常规参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-351">General Parameters</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-352">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-352">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-353">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-353">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-354">/QUIET</span><span class="sxs-lookup"><span data-stu-id="e8e0e-354">/QUIET</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-355">指定静默安装。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-355">Specifies silent install.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-356">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-356">/UNINSTALL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-357">指定卸载。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-357">Specifies an uninstall.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-358">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-358">/LAYOUT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-359">指定布局操作。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-359">Specifies layout action.</span></span> <span data-ttu-id="e8e0e-360">这会将 MSIs 和脚本文件提取到一个文件夹中，而不会实际安装该产品。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-360">This extracts the MSIs and script files to a folder without actually installing the product.</span></span> <span data-ttu-id="e8e0e-361">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-361">No value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-362">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="e8e0e-362">/LAYOUTDIR</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-363">指定布局目录。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-363">Specifies the layout directory.</span></span> <span data-ttu-id="e8e0e-364">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-364">Takes a string.</span></span> <span data-ttu-id="e8e0e-365">例如，/LAYOUTDIR = "C:\Application 虚拟化服务器"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-365">For example, /LAYOUTDIR=”C:\Application Virtualization Server”</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-366">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="e8e0e-366">/INSTALLDIR</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-367">指定安装目录。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-367">Specifies the installation directory.</span></span> <span data-ttu-id="e8e0e-368">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-368">Takes a string.</span></span> <span data-ttu-id="e8e0e-369">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-369">E.g.</span></span> <span data-ttu-id="e8e0e-370">/INSTALLDIR = "C:\Program Files\Application Virtualization\Server"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-370">/INSTALLDIR=”C:\Program Files\Application Virtualization\Server”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-371">/MUOPTIN</span><span class="sxs-lookup"><span data-stu-id="e8e0e-371">/MUOPTIN</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-372">启用 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-372">Enables Microsoft Update.</span></span> <span data-ttu-id="e8e0e-373">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="e8e0e-373">No value is expected</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-374">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="e8e0e-374">/ACCEPTEULA</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-375">接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-375">Accepts the license agreement.</span></span> <span data-ttu-id="e8e0e-376">这是无人参与安装所必需的。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-376">This is required for an unattended installation.</span></span> <span data-ttu-id="e8e0e-377">示例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-377">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="e8e0e-378">管理服务器安装参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-378">Management Server Installation Parameters</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-379">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-379">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-380">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-380">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-381">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-381">/MANAGEMENT_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-382">指定将安装管理服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-382">Specifies that the management server will be installed.</span></span> <span data-ttu-id="e8e0e-383">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="e8e0e-383">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-384">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-384">/MANAGEMENT_ADMINACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-385">指定允许管理员访问管理服务器的帐户此帐户可以是单个用户帐户或组。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-385">Specifies the account that will be allowed to Administrator access to the management server This account can be an individual user account or a group.</span></span> <span data-ttu-id="e8e0e-386">示例用法： <strong> /MANAGEMENT_ADMINACCOUNT = "mydomain\admin" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-386">Example usage: <strong>/MANAGEMENT_ADMINACCOUNT=”mydomain\admin”</strong>.</span></span> <span data-ttu-id="e8e0e-387">如果 <strong> </strong> 未指定/MANAGEMENT_SERVER，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-387">If <strong>/MANAGEMENT_SERVER</strong> is not specified, this will be ignored.</span></span> <span data-ttu-id="e8e0e-388">指定将允许管理员访问管理服务器的帐户。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-388">Specifies the account that will be allowed to Administrator access to the management server.</span></span> <span data-ttu-id="e8e0e-389">这可以是用户帐户或组。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-389">This can be a user account or a group.</span></span> <span data-ttu-id="e8e0e-390">例如， <strong> /MANAGEMENT_ADMINACCOUNT = &quot; mydomain\admin &quot; </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-390">For example, <strong>/MANAGEMENT_ADMINACCOUNT=&quot;mydomain\admin&quot;</strong>.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-391">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-391">/MANAGEMENT_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-392">指定将为管理服务创建的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-392">Specifies name of the website that will be created for the management service.</span></span> <span data-ttu-id="e8e0e-393">例如，/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V 管理服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-393">For example, /MANAGEMENT_WEBSITE_NAME=”Microsoft App-V Management Service”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-394">MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-394">MANAGEMENT_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-395">指定管理服务将使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-395">Specifies the port number that will be used by the management service will use.</span></span> <span data-ttu-id="e8e0e-396">例如，/MANAGEMENT_WEBSITE_PORT = 82。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-396">For example, /MANAGEMENT_WEBSITE_PORT=82.</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="e8e0e-397">管理服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-397">Parameters for the Management Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-398">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-398">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-399">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-399">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-400">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-400">/DB_PREDEPLOY_MANAGEMENT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-401">指定将安装管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-401">Specifies that the management database will be installed.</span></span> <span data-ttu-id="e8e0e-402">您必须有足够的数据库权限才能完成此安装。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-402">You must have sufficient database permissions to complete this installation.</span></span> <span data-ttu-id="e8e0e-403">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="e8e0e-403">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-404">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-404">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-405">指示应使用默认 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-405">Indicates that the default SQL instance should be used.</span></span> <span data-ttu-id="e8e0e-406">不应为任何值。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-406">No value is expected.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-407">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-407">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-408">指定应用于创建新数据库的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-408">Specifies the name of the custom SQL instance that should be used to create a new database.</span></span> <span data-ttu-id="e8e0e-409">示例用法： <strong> /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-409">Example usage: <strong>/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE=”MYSQLSERVER”</strong>.</span></span> <span data-ttu-id="e8e0e-410">如果未指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-410">If /DB_PREDEPLOY_MANAGEMENT is not specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-411">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-411">/MANAGEMENT_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-412">指定应创建的新管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-412">Specifies the name of the new management database that should be created.</span></span> <span data-ttu-id="e8e0e-413">示例用法： <strong> /MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-413">Example usage: <strong>/MANAGEMENT_DB_NAME=”AppVMgmtDB”</strong>.</span></span> <span data-ttu-id="e8e0e-414">如果未指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-414">If /DB_PREDEPLOY_MANAGEMENT is not specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-415">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-415">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-416">指示是否在本地服务器上安装了将访问该数据库的管理服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-416">Indicates if the management server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="e8e0e-417">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-417">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-418">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-418">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-419">指定将安装管理服务器的远程计算机的计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-419">Specifies the machine account of the remote machine that the management server will be installed on.</span></span> <span data-ttu-id="e8e0e-420">示例用法： <strong> /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-420">Example usage: <strong>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT=”domain\computername”</span></span></strong></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-421">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-421">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-422">指示将用于安装管理服务器的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-422">Indicates the Administrator account that will be used to install the management server.</span></span> <span data-ttu-id="e8e0e-423">示例用法： <strong> /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\alias"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-423">Example usage: <strong>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT =”domain\alias”</span></span></strong></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="e8e0e-424">用于安装发布服务器的参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-424">Parameters for Installing Publishing Server</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-425">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-425">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-426">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-426">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-427">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-427">/PUBLISHING_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-428">指定将安装发布服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-428">Specifies that the Publishing Server will be installed.</span></span> <span data-ttu-id="e8e0e-429">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="e8e0e-429">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-430">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-430">/PUBLISHING_MGT_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-431">指定发布服务器将连接到的管理服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-431">Specifies the URL to Management Service the Publishing server will connect to.</span></span> <span data-ttu-id="e8e0e-432">示例用法： <strong> http:// &lt; 管理服务器名称 &gt; ： &lt; 管理服务器端口号 &gt; </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-432">Example usage: <strong>http://&lt;management server name&gt;:&lt;Management server port number&gt;</strong>.</span></span> <span data-ttu-id="e8e0e-433">如果未使用/PUBLISHING_SERVER，此参数将被忽略</span><span class="sxs-lookup"><span data-stu-id="e8e0e-433">If /PUBLISHING_SERVER is not used, this parameter will be ignored</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-434">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-434">/PUBLISHING_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-435">指定将为发布服务创建的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-435">Specifies name of the website that will be created for the publishing service.</span></span> <span data-ttu-id="e8e0e-436">例如，/PUBLISHING_WEBSITE_NAME = "Microsoft App-V 发布服务"</span><span class="sxs-lookup"><span data-stu-id="e8e0e-436">For example, /PUBLISHING_WEBSITE_NAME=”Microsoft App-V Publishing Service”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-437">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-437">/PUBLISHING_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-438">指定发布服务使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-438">Specifies the port number used by the publishing service.</span></span> <span data-ttu-id="e8e0e-439">例如，/PUBLISHING_WEBSITE_PORT = 83</span><span class="sxs-lookup"><span data-stu-id="e8e0e-439">For example, /PUBLISHING_WEBSITE_PORT=83</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="e8e0e-440">用于报告服务器的参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-440">Parameters for Reporting Server</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-441">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-441">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-442">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-442">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-443">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="e8e0e-443">/REPORTING_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-444">指定将安装报表服务器。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-444">Specifies that the Reporting Server will be installed.</span></span> <span data-ttu-id="e8e0e-445">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="e8e0e-445">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-446">/REPORTING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-446">/REPORTING_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-447">指定将为报告服务创建的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-447">Specifies name of the website that will be created for the Reporting Service.</span></span> <span data-ttu-id="e8e0e-448">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-448">E.g.</span></span> <span data-ttu-id="e8e0e-449">/REPORTING_WEBSITE_NAME = &quot; Microsoft App-V ReportingService&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-449">/REPORTING_WEBSITE_NAME=&quot;Microsoft App-V ReportingService&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-450">/REPORTING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-450">/REPORTING_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-451">指定报表服务将使用的端口号。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-451">Specifies the port number that the Reporting Service will use.</span></span> <span data-ttu-id="e8e0e-452">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-452">E.g.</span></span> <span data-ttu-id="e8e0e-453">/REPORTING_WEBSITE_PORT = 82</span><span class="sxs-lookup"><span data-stu-id="e8e0e-453">/REPORTING_WEBSITE_PORT=82</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

### <span data-ttu-id="e8e0e-454">用于使用现有报表服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-454">Parameters for using an Existing Reporting Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-455">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-455">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-456">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-456">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-457">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-457">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-458">指示本地服务器上安装了 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-458">Indicates that the Microsoft SQL Server is installed on the local server.</span></span> <span data-ttu-id="e8e0e-459">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-459">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-460">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-460">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-461">指定安装 SQL Server 的远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-461">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="e8e0e-462">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-462">Takes a string.</span></span> <span data-ttu-id="e8e0e-463">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-463">E.g.</span></span> <span data-ttu-id="e8e0e-464">/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-464">/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME=&quot;mycomputer1&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-465">/EXISTING_ 报告 <em> DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-465">/EXISTING_ REPORTING <em>DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-466">指示要使用的默认 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-466">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="e8e0e-467">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-467">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-468">/EXISTING </em> REPORTING_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-468">/EXISTING</em> REPORTING_DB_CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-469">指定应使用的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-469">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="e8e0e-470">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-470">Takes a string.</span></span> <span data-ttu-id="e8e0e-471">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-471">E.g.</span></span> <span data-ttu-id="e8e0e-472">/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-472">/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE=&quot;MYSQLSERVER&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-473">/EXISTING_ 报告 _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-473">/EXISTING_ REPORTING _DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-474">指定应使用的现有报告数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-474">Specifies the name of the existing Reporting database that should be used.</span></span> <span data-ttu-id="e8e0e-475">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-475">Takes a string.</span></span> <span data-ttu-id="e8e0e-476">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-476">E.g.</span></span> <span data-ttu-id="e8e0e-477">/EXISTING_REPORTING_DB_NAME = &quot; AppVReporting&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-477">/EXISTING_REPORTING_DB_NAME=&quot;AppVReporting&quot;</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="e8e0e-478">用于安装报表服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-478">Parameters for installing Reporting Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-479">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-479">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-480">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-480">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-481">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="e8e0e-481">/DB_PREDEPLOY_REPORTING</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-482">指定将安装报告数据库。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-482">Specifies that the Reporting Database will be installed.</span></span> <span data-ttu-id="e8e0e-483">此安装需要 DBA 权限。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-483">DBA permissions are required for this installation.</span></span> <span data-ttu-id="e8e0e-484">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="e8e0e-484">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-485">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-485">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-486">指定应使用的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-486">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="e8e0e-487">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-487">Takes a string.</span></span> <span data-ttu-id="e8e0e-488">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-488">E.g.</span></span> <span data-ttu-id="e8e0e-489">/REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-489">/REPORTING_DB_ CUSTOM_SQLINSTANCE=&quot;MYSQLSERVER&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-490">/REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-490">/REPORTING_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-491">指定应创建的新报告数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-491">Specifies the name of the new Reporting database that should be created.</span></span> <span data-ttu-id="e8e0e-492">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-492">Takes a string.</span></span> <span data-ttu-id="e8e0e-493">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-493">E.g.</span></span> <span data-ttu-id="e8e0e-494">/REPORTING_DB_NAME = &quot; AppVMgmtDB&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-494">/REPORTING_DB_NAME=&quot;AppVMgmtDB&quot;</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-495">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-495">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-496">指示将访问数据库的报表服务器安装在本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-496">Indicates that the Reporting server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="e8e0e-497">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-497">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-498">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-498">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-499">指定将安装报表服务器的远程计算机的计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-499">Specifies the machine account of the remote machine that the Reporting server will be installed on.</span></span> <span data-ttu-id="e8e0e-500">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-500">Takes a string.</span></span> <span data-ttu-id="e8e0e-501">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-501">E.g.</span></span> <span data-ttu-id="e8e0e-502">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot; domain\computername&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-502">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot;domain\computername&quot;</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-503">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-503">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-504">指示将用于安装 app-v 报告服务器的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-504">Indicates the Administrator account that will be used to install the App-V Reporting Server.</span></span> <span data-ttu-id="e8e0e-505">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-505">Takes a string.</span></span> <span data-ttu-id="e8e0e-506">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-506">E.g.</span></span> <span data-ttu-id="e8e0e-507">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot; domain\alias&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-507">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot;domain\alias&quot;</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="e8e0e-508">用于使用现有管理服务器数据库的参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-508">Parameters for using an existing Management Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e8e0e-509">参数</span><span class="sxs-lookup"><span data-stu-id="e8e0e-509">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e8e0e-510">信息</span><span class="sxs-lookup"><span data-stu-id="e8e0e-510">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-511">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e8e0e-511">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-512">指示 SQL Server 安装在本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-512">Indicates that the SQL Server is installed on the local server.</span></span> <span data-ttu-id="e8e0e-513">开关参数，因此不需要任何值。如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-513">Switch parameter so no value is expected.If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-514">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-514">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-515">指定安装 SQL Server 的远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-515">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="e8e0e-516">接受字符串。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-516">Takes a string.</span></span> <span data-ttu-id="e8e0e-517">例如</span><span class="sxs-lookup"><span data-stu-id="e8e0e-517">E.g.</span></span> <span data-ttu-id="e8e0e-518">/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</span><span class="sxs-lookup"><span data-stu-id="e8e0e-518">/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME=&quot;mycomputer1&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-519">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e8e0e-519">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-520">指示要使用的默认 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-520">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="e8e0e-521">开关参数，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-521">Switch parameter so no value is expected.</span></span> <span data-ttu-id="e8e0e-522">如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-522">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e8e0e-523">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="e8e0e-523">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-524">指定将使用的自定义 SQL 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-524">Specifies the name of the custom SQL instance that will be used.</span></span> <span data-ttu-id="e8e0e-525">示例用法 <strong> /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-525">Example usage <strong>/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE=”AppVManagement”</strong>.</span></span> <span data-ttu-id="e8e0e-526">如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-526">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e8e0e-527">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e8e0e-527">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e8e0e-528">指定应使用的现有管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-528">Specifies the name of the existing management database that should be used.</span></span> <span data-ttu-id="e8e0e-529">示例用法： <strong> /EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-529">Example usage: <strong>/EXISTING_MANAGEMENT_DB_NAME=”AppVMgmtDB”</strong>.</span></span> <span data-ttu-id="e8e0e-530">如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-530">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p>
    <p></p>
    <p><strong><span data-ttu-id="e8e0e-531">已获得有关 App-v 的建议 </strong> ？</span><span class="sxs-lookup"><span data-stu-id="e8e0e-531">Got a suggestion for App-V</strong>?</span></span> <span data-ttu-id="e8e0e-532">在此处添加或投票 <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)"> 建议 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-532">Add or vote on suggestions <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)">here</a>.</span></span> <strong><span data-ttu-id="e8e0e-533">是否有应用程序-V issu </strong> e？</span><span class="sxs-lookup"><span data-stu-id="e8e0e-533">Got an App-V issu</strong>e?</span></span> <span data-ttu-id="e8e0e-534">使用 app-v <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)"> TechNet 论坛 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e8e0e-534">Use the <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)">App-V TechNet Forum</a>.</span></span></p></td>
</tr>
</tbody>
</table>
  

## <span data-ttu-id="e8e0e-535">相关主题</span><span class="sxs-lookup"><span data-stu-id="e8e0e-535">Related topics</span></span>

[<span data-ttu-id="e8e0e-536">部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="e8e0e-536">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

 

 





