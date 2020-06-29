---
title: App-V Desktop Client 安全性
description: App-V Desktop Client 安全性
author: dansimp
ms.assetid: 216b9c16-7bb4-4f94-b9d8-810501285008
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 26add6f855780113613cf1591c41722643954477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803144"
---
# <span data-ttu-id="24f07-103">App-V Desktop Client 安全性</span><span class="sxs-lookup"><span data-stu-id="24f07-103">App-V Desktop Client Security</span></span>


<span data-ttu-id="24f07-104">App-v 桌面客户端提供了许多在产品的早期版本中不可用的安全增强功能。</span><span class="sxs-lookup"><span data-stu-id="24f07-104">The App-V Desktop Client provides many security enhancements that were not available in previous versions of the product.</span></span> <span data-ttu-id="24f07-105">默认情况下，这些更改通过客户端设置的配置提供更高的安全级别。</span><span class="sxs-lookup"><span data-stu-id="24f07-105">These changes provide higher levels of security by default and through configuration of the client settings.</span></span>

<span data-ttu-id="24f07-106">**注意** 在计算机上安装 app-v 桌面客户端时，该软件默认为最安全的设置。</span><span class="sxs-lookup"><span data-stu-id="24f07-106">**Note** When you install the App-V Desktop Client on a computer, the software defaults to the most secure settings.</span></span> <span data-ttu-id="24f07-107">但是，升级时，客户端的以前设置将保持不变。</span><span class="sxs-lookup"><span data-stu-id="24f07-107">However, when upgrading, the previous settings of the client persist.</span></span>

 

<span data-ttu-id="24f07-108">默认情况下，仅使用允许非管理用户执行发布刷新和流应用程序所需的权限配置 app-v 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="24f07-108">By default, the App-V Desktop Client is configured only with the permissions required to allow a non-administrative user to perform a publishing refresh and stream applications.</span></span> <span data-ttu-id="24f07-109">App-v 桌面客户端中提供的其他安全增强功能包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="24f07-109">Additional security enhancements provided in the App-V Desktop Client include the following:</span></span>

-   <span data-ttu-id="24f07-110">默认情况下，仅当发布刷新过程才允许 OSD 缓存更新。</span><span class="sxs-lookup"><span data-stu-id="24f07-110">By default, an OSD cache update is allowed only by the publishing refresh process.</span></span>

-   <span data-ttu-id="24f07-111">`sftlog.txt`只有具有客户端本地管理访问权限的帐户才能访问日志文件（）。</span><span class="sxs-lookup"><span data-stu-id="24f07-111">The log file (`sftlog.txt`) is accessible only by accounts with local administrative access to the client.</span></span>

-   <span data-ttu-id="24f07-112">日志文件现在具有最大大小。</span><span class="sxs-lookup"><span data-stu-id="24f07-112">The log file now has a maximum size.</span></span>

-   <span data-ttu-id="24f07-113">日志文件通过 "存档设置" 进行管理。</span><span class="sxs-lookup"><span data-stu-id="24f07-113">The log files are managed through archive settings.</span></span>

-   <span data-ttu-id="24f07-114">系统事件日志记录现已执行。</span><span class="sxs-lookup"><span data-stu-id="24f07-114">System Event logging is now performed.</span></span>

## <span data-ttu-id="24f07-115">权限</span><span class="sxs-lookup"><span data-stu-id="24f07-115">Permissions</span></span>


<span data-ttu-id="24f07-116">安装桌面客户端后，可以通过 MMC 配置其他安全设置，也可以使用 Microsoft 提供的注册表或 ADM 模板配置单个客户端上的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="24f07-116">After you install the Desktop Client, you can configure other security settings through the MMC, or on an individual client by using the registry or the ADM Template provided by Microsoft.</span></span> <span data-ttu-id="24f07-117">App-v 桌面客户端具有权限，你可以将其设置为限制非管理用户访问桌面客户端的所有功能。</span><span class="sxs-lookup"><span data-stu-id="24f07-117">The App-V Desktop Client has permissions that you can set to restrict non-administrative users from accessing all the features of the Desktop Client.</span></span> <span data-ttu-id="24f07-118">有关权限的完整列表，请参阅应用程序-V 客户端帮助文件或 App-v 操作指南。</span><span class="sxs-lookup"><span data-stu-id="24f07-118">For a full list of permissions, please see the App-V Client Help file or App-V Operations Guide.</span></span>

<span data-ttu-id="24f07-119">**重要提示** 请仔细考虑更改访问权限的后果，尤其是在多个用户共享的系统上（如终端服务器）。</span><span class="sxs-lookup"><span data-stu-id="24f07-119">**Important** Carefully consider the consequences of changing access rights, especially on systems that are shared by multiple users, such as Terminal Servers.</span></span>

 

<span data-ttu-id="24f07-120">**注意** 如果环境中的用户具有其计算机的本地管理员权限，则将忽略权限。</span><span class="sxs-lookup"><span data-stu-id="24f07-120">**Note** If users in the environment have local administrator privileges for their computers, the permissions are ignored.</span></span>

 

### <span data-ttu-id="24f07-121">ADM 模板</span><span class="sxs-lookup"><span data-stu-id="24f07-121">ADM Template</span></span>

<span data-ttu-id="24f07-122">Microsoft Application Virtualization （App-v）引入了可用于通过组策略配置最常见的客户端设置的 ADM 模板。</span><span class="sxs-lookup"><span data-stu-id="24f07-122">Microsoft Application Virtualization (App-V) introduces an ADM Template that you can use to configure the most common client settings through Group Policies.</span></span> <span data-ttu-id="24f07-123">通过此模板，管理员可以通过集中管理模型实施和更改许多客户端设置。</span><span class="sxs-lookup"><span data-stu-id="24f07-123">This template enables administrators to implement and change many of the client settings through a centralized administration model.</span></span> <span data-ttu-id="24f07-124">ADM 模板中的一些可用设置是安全设置。</span><span class="sxs-lookup"><span data-stu-id="24f07-124">Some of the settings available in the ADM Template are security settings.</span></span>

<span data-ttu-id="24f07-125">**重要提示** 使用 ADM 模板时，请记住，设置是组策略首选项设置，而不是完全托管的组策略。</span><span class="sxs-lookup"><span data-stu-id="24f07-125">**Important** When using the ADM Template, remember that the settings are Group Policy preference settings and not fully managed Group Policies.</span></span>

 

<span data-ttu-id="24f07-126">有关 ADM 模板的完整说明、特定设置以及在你的环境中成功部署客户端的指南，请参阅中的 App-v ADM 模板白皮书 [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063) 。</span><span class="sxs-lookup"><span data-stu-id="24f07-126">For a full description of the ADM Template, the specific settings, and guidance to successfully deploy clients in your environment, see the App-V ADM Template white paper at [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063).</span></span>

## <span data-ttu-id="24f07-127">删除 OSD 文件类型关联</span><span class="sxs-lookup"><span data-stu-id="24f07-127">Removing OSD File Type Associations</span></span>


<span data-ttu-id="24f07-128">如果你的组织不要求用户直接从 OSD 文件打开应用程序，则可以通过删除客户端上的文件类型关联来增强安全性。</span><span class="sxs-lookup"><span data-stu-id="24f07-128">If your organization does not require users to open applications directly from an OSD file, you can enhance security by removing the file type associations on the client.</span></span> <span data-ttu-id="24f07-129">删除 `HKEY_CURRENT_USERS` 用于 OSD 和 `Softgird.osd.file` 使用注册表编辑器的键。</span><span class="sxs-lookup"><span data-stu-id="24f07-129">Remove the `HKEY_CURRENT_USERS` keys for OSD and `Softgird.osd.file` by using the registry editor.</span></span> <span data-ttu-id="24f07-130">你可以将此过程放入登录脚本或安装后脚本以自动执行这些更改。</span><span class="sxs-lookup"><span data-stu-id="24f07-130">You can put this process into a logon script or into a post-installation script to automate these changes.</span></span>

 

 





