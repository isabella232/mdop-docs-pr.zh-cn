---
title: 如何使用命令行配置 App-V Client 注册表设置
description: 如何使用命令行配置 App-V Client 注册表设置
author: dansimp
ms.assetid: 3e3d873f-13d2-402f-97b4-f62d0c399171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c424f39c8209ca641f6073838ebcb8726acc9e25
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801600"
---
# <span data-ttu-id="423e2-103">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="423e2-103">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>


<span data-ttu-id="423e2-104">在使用命令行在安装过程中部署和配置应用程序虚拟化（App-v）客户端之后，可能需要更改一个或多个客户端配置设置。</span><span class="sxs-lookup"><span data-stu-id="423e2-104">After the Application Virtualization (App-V) Client has been deployed and configured during the installation by using the command line, it might be necessary to change one or more client configuration settings.</span></span> <span data-ttu-id="423e2-105">这可以通过使用以下方法之一编辑相应的注册表项来实现：</span><span class="sxs-lookup"><span data-stu-id="423e2-105">This is accomplished by editing the appropriate registry keys, using one of the following methods:</span></span>

-   <span data-ttu-id="423e2-106">直接使用注册表编辑器</span><span class="sxs-lookup"><span data-stu-id="423e2-106">Using the Registry Editor directly</span></span>

-   <span data-ttu-id="423e2-107">使用 .reg 文件</span><span class="sxs-lookup"><span data-stu-id="423e2-107">Using a .reg file</span></span>

-   <span data-ttu-id="423e2-108">使用脚本语言（如 VBScript 或 Windows PowerShell）</span><span class="sxs-lookup"><span data-stu-id="423e2-108">Using a scripting language such as VBScript or Windows PowerShell</span></span>

<span data-ttu-id="423e2-109">还有一个您可以使用的 ADM 模板。</span><span class="sxs-lookup"><span data-stu-id="423e2-109">There is also an ADM template that you can use.</span></span> <span data-ttu-id="423e2-110">有关 ADM 模板的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=121835> 。</span><span class="sxs-lookup"><span data-stu-id="423e2-110">For more information about the ADM template, see <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

<span data-ttu-id="423e2-111">**小心** 编辑注册表时使用小心，因为错误可能会使计算机处于无法使用的状态。</span><span class="sxs-lookup"><span data-stu-id="423e2-111">**Caution** Use care when you edit the registry because errors can leave the computer in an unusable state.</span></span> <span data-ttu-id="423e2-112">请务必遵循与注册表编辑相关的标准业务做法。</span><span class="sxs-lookup"><span data-stu-id="423e2-112">Be sure to follow your standard business practices that relate to registry edits.</span></span> <span data-ttu-id="423e2-113">在将测试环境中的所有建议的更改部署到生产计算机之前，对它们进行全面测试。</span><span class="sxs-lookup"><span data-stu-id="423e2-113">Thoroughly test all proposed changes in a test environment before you deploy them to production computers.</span></span>

 

## <span data-ttu-id="423e2-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="423e2-114">In This Section</span></span>


<span data-ttu-id="423e2-115">**重要提示** 在64位计算机上，以下部分中介绍的键和值将在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client. 下。</span><span class="sxs-lookup"><span data-stu-id="423e2-115">**Important** On a 64-bit computer, the keys and values described in the following sections will be under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client.</span></span>

 

<a href="" id="how-to-reset-the-filesystem-cache"></a>[<span data-ttu-id="423e2-116">如何重置 FileSystem 缓存</span><span class="sxs-lookup"><span data-stu-id="423e2-116">How to Reset the FileSystem Cache</span></span>](how-to-reset-the-filesystem-cache.md)  
<span data-ttu-id="423e2-117">提供重置文件系统缓存所需的信息。</span><span class="sxs-lookup"><span data-stu-id="423e2-117">Provides the information that is required to reset the FileSystem cache.</span></span>

<a href="" id="how-to-change-the-size-of-the-filesystem-cache"></a>[<span data-ttu-id="423e2-118">如何更改 FileSystem 缓存的大小</span><span class="sxs-lookup"><span data-stu-id="423e2-118">How to Change the Size of the FileSystem Cache</span></span>](how-to-change-the-size-of-the-filesystem-cache.md)  
<span data-ttu-id="423e2-119">介绍如何更改缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="423e2-119">Explains how you can change the size of the cache.</span></span>

<a href="" id="how-to-use-the-cache-space-management-feature"></a>[<span data-ttu-id="423e2-120">如何使用缓存空间管理功能</span><span class="sxs-lookup"><span data-stu-id="423e2-120">How to Use the Cache Space Management Feature</span></span>](how-to-use-the-cache-space-management-feature.md)  
<span data-ttu-id="423e2-121">介绍如何配置缓存空间管理功能。</span><span class="sxs-lookup"><span data-stu-id="423e2-121">Describes how you can configure the cache space management feature.</span></span>

<a href="" id="how-to-configure-the-client-log-file"></a>[<span data-ttu-id="423e2-122">如何配置客户端日志文件</span><span class="sxs-lookup"><span data-stu-id="423e2-122">How to Configure the Client Log File</span></span>](how-to-configure-the-client-log-file.md)  
<span data-ttu-id="423e2-123">介绍控制客户端日志文件的各种注册表项值以及如何更改它们。</span><span class="sxs-lookup"><span data-stu-id="423e2-123">Describes the various registry key values that control the client log file and how you can change them.</span></span>

<a href="" id="how-to-configure-user-permissions"></a>[<span data-ttu-id="423e2-124">如何配置用户权限</span><span class="sxs-lookup"><span data-stu-id="423e2-124">How to Configure User Permissions</span></span>](how-to-configure-user-permissions.md)  
<span data-ttu-id="423e2-125">标识控制用户权限的注册表项，并提供有关如何更改某些权限的示例。</span><span class="sxs-lookup"><span data-stu-id="423e2-125">Identifies the registry key that controls the user permissions and gives examples of how you can change some permissions.</span></span>

<a href="" id="how-to-configure-the-client-for-application-package-retrieval"></a>[<span data-ttu-id="423e2-126">如何配置客户端以进行应用程序包检索</span><span class="sxs-lookup"><span data-stu-id="423e2-126">How to Configure the Client for Application Package Retrieval</span></span>](how-to-configure-the-client-for-application-package-retrieval.md)  
<span data-ttu-id="423e2-127">介绍如何配置客户端以检索不同源中的程序包内容、图标和文件类型关联，并提供了正确路径格式的几个示例。</span><span class="sxs-lookup"><span data-stu-id="423e2-127">Explains how to configure the client to retrieve package content, icons, and file type associations from different sources, and provides several examples of the correct path format.</span></span>

<a href="" id="how-to-configure-the-client-for-disconnected-operation-mode"></a>[<span data-ttu-id="423e2-128">如何为断开连接操作模式配置客户端</span><span class="sxs-lookup"><span data-stu-id="423e2-128">How to Configure the Client for Disconnected Operation Mode</span></span>](how-to-configure-the-client-for-disconnected-operation-mode.md)  
<span data-ttu-id="423e2-129">提供有关如何配置与断开连接的操作模式关联的各种设置的信息。</span><span class="sxs-lookup"><span data-stu-id="423e2-129">Provides information about how to configure the various settings associated with disconnected operations mode.</span></span>

<a href="" id="how-to-configure-shortcut-and-file-type-association-behavior"></a>[<span data-ttu-id="423e2-130">如何配置快捷方式和文件类型关联行为</span><span class="sxs-lookup"><span data-stu-id="423e2-130">How to Configure Shortcut and File Type Association Behavior</span></span>](how-to-configure-shortcut-and-file-type-association-behavior-46-only.md)  
<span data-ttu-id="423e2-131">介绍用于控制应用程序-V 客户端中的快捷方式和文件类型关联的注册表项值，并提供有关如何配置它们的详细信息。</span><span class="sxs-lookup"><span data-stu-id="423e2-131">Describes the registry key values that control shortcuts and file type associations in the App-V client, and provides details on how to configure them.</span></span>

## <span data-ttu-id="423e2-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="423e2-132">Related topics</span></span>


[<span data-ttu-id="423e2-133">Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="423e2-133">Application Virtualization Client</span></span>](application-virtualization-client.md)

 

 





