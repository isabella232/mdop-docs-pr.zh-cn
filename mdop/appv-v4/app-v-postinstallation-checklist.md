---
title: App-V 安装后清单
description: App-V 安装后清单
author: dansimp
ms.assetid: 74db297e-a744-4287-bcc6-0e096ca8b57a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79728bd2043076b20eb37ba0b1fa6f834a0d94bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802363"
---
# <span data-ttu-id="a783a-103">App-V 安装后清单</span><span class="sxs-lookup"><span data-stu-id="a783a-103">App-V Postinstallation Checklist</span></span>


<span data-ttu-id="a783a-104">以下清单提供了要考虑的项目的高级列表，并概述了在完成 Microsoft Application Virtualization （app-v）管理服务器、App-v 流式处理服务器和 App-v 桌面客户端安装后应执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="a783a-104">The following checklist provides a high-level list of items to consider and outlines the steps you should take after you have completed the installation of the Microsoft Application Virtualization (App-V) Management Server, App-V Streaming Server, and the App-V Desktop Client.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a783a-105">步骤</span><span class="sxs-lookup"><span data-stu-id="a783a-105">Step</span></span></th>
<th align="left"><span data-ttu-id="a783a-106">参考</span><span class="sxs-lookup"><span data-stu-id="a783a-106">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a783a-107">为 App-v 管理服务器或流式处理服务器服务创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="a783a-107">Create firewall exceptions for the App-V Management Server or Streaming Server services.</span></span></p></td>
<td align="left"><p><a href="configuring-the-firewall-for-the-app-v-servers.md" data-raw-source="[Configuring the Firewall for the App-V Servers](configuring-the-firewall-for-the-app-v-servers.md)"><span data-ttu-id="a783a-108">为 App-V Server 配置防火墙</span><span class="sxs-lookup"><span data-stu-id="a783a-108">Configuring the Firewall for the App-V Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a783a-109">通过发布、流式处理和测试默认应用程序验证 App-v 系统是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="a783a-109">Verify that the App-V system is functioning correctly by publishing, streaming, and testing the default application.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-the-default-application.md" data-raw-source="[How to Install and Configure the Default Application](how-to-install-and-configure-the-default-application.md)"><span data-ttu-id="a783a-110">如何安装和配置默认应用程序</span><span class="sxs-lookup"><span data-stu-id="a783a-110">How to Install and Configure the Default Application</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a783a-111">通过 <strong> ApplicationSourceRoot </strong> 、 <strong> IconSourceRoot </strong> 和 <strong> OSDSourceRoot </strong> 设置，将 app-v 客户端配置为使用 app-v 流式处理服务器或其他服务器进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="a783a-111">Configure the App-V Client to use the App-V Streaming Server or other server for streaming by means of the <strong>ApplicationSourceRoot</strong>, <strong>IconSourceRoot</strong>, and <strong>OSDSourceRoot</strong> settings.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-client-for-application-package-retrieval.md" data-raw-source="[How to Configure the Client for Application Package Retrieval](how-to-configure-the-client-for-application-package-retrieval.md)"><span data-ttu-id="a783a-112">如何配置客户端以进行应用程序包检索</span><span class="sxs-lookup"><span data-stu-id="a783a-112">How to Configure the Client for Application Package Retrieval</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a783a-113">了解如何使用已排序应用程序包的 .msi 文件版本进行脱机部署。</span><span class="sxs-lookup"><span data-stu-id="a783a-113">Understand how to use the .msi file version of sequenced application packages for offline deployment.</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-virtual-application-on-the-client.md" data-raw-source="[How to Publish a Virtual Application on the Client](how-to-publish-a-virtual-application-on-the-client.md)"><span data-ttu-id="a783a-114">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="a783a-114">How to Publish a Virtual Application on the Client</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a783a-115">可选配置 app-v 数据库的 SQL Server 数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="a783a-115">(Optional) Configure SQL Server database mirroring for the App-V database.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md" data-raw-source="[How to Configure Microsoft SQL Server Mirroring Support for App-V](how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md)"><span data-ttu-id="a783a-116">如何为 App-V 配置 Microsoft SQL Server 镜像支持</span><span class="sxs-lookup"><span data-stu-id="a783a-116">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a783a-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="a783a-117">Related topics</span></span>


[<span data-ttu-id="a783a-118">Application Virtualization 部署和升级清单</span><span class="sxs-lookup"><span data-stu-id="a783a-118">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





