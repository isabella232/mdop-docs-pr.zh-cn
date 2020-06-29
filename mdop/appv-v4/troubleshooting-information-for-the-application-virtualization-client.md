---
title: Application Virtualization Client 的故障排除信息
description: Application Virtualization Client 的故障排除信息
author: dansimp
ms.assetid: 260a8dad-847f-4ec0-b7dd-6e6bc52017ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2ab332f5f3b7f8cdc40f6d35e8712d55028a60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798722"
---
# <span data-ttu-id="3ecf7-103">Application Virtualization Client 的故障排除信息</span><span class="sxs-lookup"><span data-stu-id="3ecf7-103">Troubleshooting Information for the Application Virtualization Client</span></span>


<span data-ttu-id="3ecf7-104">本主题包含可用于解决应用程序虚拟化（app-v）客户端上的各种问题的信息。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-104">This topic includes information that you can use to troubleshoot various issues on the Application Virtualization (App-V) Client.</span></span>

## <span data-ttu-id="3ecf7-105">发布刷新速度非常慢</span><span class="sxs-lookup"><span data-stu-id="3ecf7-105">Publishing Refresh Is Very Slow</span></span>


<span data-ttu-id="3ecf7-106">如果在特定计算机上发布的刷新时间比预期长得多，并且客户端配置为使用**IconSourceRoot**设置，请确定**IconSourceRoot**是否包含无效的 URL。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-106">If publishing refresh on a specific computer takes much longer than expected and if the client is configured to use the **IconSourceRoot** setting, determine whether **IconSourceRoot** contains a nonvalid URL.</span></span> <span data-ttu-id="3ecf7-107">无效 URL 将在发布刷新期间产生很长的延迟。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-107">A nonvalid URL will cause very long delays during publishing refresh.</span></span>

## <span data-ttu-id="3ecf7-108">用户无法连接到服务器并转到断开连接的操作模式</span><span class="sxs-lookup"><span data-stu-id="3ecf7-108">Users Cannot Connect to the Server and Go into Disconnected Operations Mode</span></span>


<span data-ttu-id="3ecf7-109">当你使用配置了 RTSPS 协议的 app-v 管理服务器时，如果用户无法连接，并且它们进入断开连接的操作模式，请确定服务器上正在使用的证书是否有效。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-109">When you are using an App-V Management Server configured with the RTSPS protocol, if the users are unable to connect and they go into disconnected operations mode, determine whether the certificate that is being used on the server is valid.</span></span> <span data-ttu-id="3ecf7-110">无效证书将阻止用户连接，并将导致用户进入断开连接的操作模式。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-110">A nonvalid certificate will prevent users from connecting and will cause them to go into disconnected operations mode.</span></span>

## <a href="" id="users-experience-slow-performance-when-applications-are-not-fully-cached-"></a><span data-ttu-id="3ecf7-111">应用程序不完全缓存时用户遇到性能较慢的情况</span><span class="sxs-lookup"><span data-stu-id="3ecf7-111">Users Experience Slow Performance When Applications Are Not Fully Cached</span></span>


<span data-ttu-id="3ecf7-112">当应用程序不完全缓存时，用户在启动或使用该应用程序时偶尔会遇到暂时的缓慢或间歇性性能。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-112">When applications are not fully cached, users might occasionally experience temporary slow or intermittent performance when they start or use the application.</span></span> <span data-ttu-id="3ecf7-113">可能出现这种情况的可能原因，例如，当 App-v 客户端正在自动加载应用程序的过程中时，或者正在处理不连续的请求时。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-113">There are several possible reasons this can occur—for example, when the App-V Client is in the process of auto-loading an application or when an Out Of Sequence request is being processed.</span></span> <span data-ttu-id="3ecf7-114">当应用程序完全缓存时，这些问题将不再出现。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-114">When the applications are fully cached, these problems will no longer occur.</span></span>

## <a href="" id="error-displayed-after-an-update-is-removed-"></a><span data-ttu-id="3ecf7-115">删除更新后显示的错误</span><span class="sxs-lookup"><span data-stu-id="3ecf7-115">Error Displayed After an Update Is Removed</span></span>


<span data-ttu-id="3ecf7-116">必须使用正确的 Windows Installer 3.1 命令格式从 App-v 客户端中删除更新，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ecf7-116">You must use the correct Windows Installer 3.1 command format to remove an update from the App-V Client, as follows:</span></span>

`Msiexec /I {F82584A0-D706-4D2D-9BC1-7E6D8BE3BB0F} MSIPATCHREMOVE={BE3DD018-9A1F-40FD-9538-C0A995CBD254} /qb /l*v "Uninstall.log"`

<span data-ttu-id="3ecf7-117">使用较旧的命令格式 `msiexec /package <GUID> /uninstall <GUID>` 将导致错误 6003 "应用程序虚拟化客户端无法启动"。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-117">Using the older command format `msiexec /package <GUID> /uninstall <GUID>` will cause error 6003 "Application Virtualization client could not be started".</span></span>

## <span data-ttu-id="3ecf7-118">尝试启动应用程序时出现错误代码 0A-0000E01E</span><span class="sxs-lookup"><span data-stu-id="3ecf7-118">Error Code 0A-0000E01E Occurs When You Try to Start an Application</span></span>


<span data-ttu-id="3ecf7-119">错误代码 0A-0000E01E 表示序列化的应用程序包可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-119">Error code 0A-0000E01E indicates that the sequenced application package might be corrupt.</span></span> <span data-ttu-id="3ecf7-120">解决方案是 resequence 软件包。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-120">The solution is to resequence the package.</span></span>

## <span data-ttu-id="3ecf7-121">用户无法访问在问答：驱动器上创建的文件</span><span class="sxs-lookup"><span data-stu-id="3ecf7-121">Users Cannot Access Files They Have Created on the Q: Drive</span></span>


<span data-ttu-id="3ecf7-122">如果用户将文件保存到**Q：** 驱动器，则无法检索它们，因为它们对驱动器没有读取权限。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-122">If users save files to the **Q:** drive, they cannot retrieve them because they do not have read rights to the drive.</span></span> <span data-ttu-id="3ecf7-123">用户不应将文件保存到**Q：** 驱动器。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-123">Users should not save files to the **Q:** drive.</span></span>

## <span data-ttu-id="3ecf7-124">用户收到1D1 错误</span><span class="sxs-lookup"><span data-stu-id="3ecf7-124">User Is Prompted with a 1D1 Error</span></span>


<span data-ttu-id="3ecf7-125">当打开的软件描述符（OSD）文件中错误地设置了文件流 URL 时，App-v 客户端将返回一个1d1 错误，而不是 "找不到文件" 错误。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-125">When the file streaming URL is incorrectly set in the Open Software Descriptor (OSD) file, the App-V Client returns a 1d1 error instead of a “file not found” error.</span></span> <span data-ttu-id="3ecf7-126">此错误表示应用程序启动失败，用户已强制进入断开连接操作模式。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-126">This error indicates that the application start failed and the user has been forced into disconnected operations mode.</span></span> <span data-ttu-id="3ecf7-127">更正文件流 URL。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-127">Correct the file streaming URL.</span></span>

## <span data-ttu-id="3ecf7-128">与某些应用程序相关联的错误图标</span><span class="sxs-lookup"><span data-stu-id="3ecf7-128">Incorrect Icons Associated with Some Applications</span></span>


<span data-ttu-id="3ecf7-129">当要在发布操作中使用图标时，App-v 客户端首先确定它是否已有图标的缓存副本，方法是查看其原始源路径与给定于发布操作的图标路径相匹配的项目的图标缓存。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-129">When an icon is to be used in a publishing operation, the App-V Client first determines whether it already has a cached copy of the icon, by looking in the icon cache for an item whose original source path matches the path of the icon given to the publishing operation.</span></span> <span data-ttu-id="3ecf7-130">如果 App-v 客户端找到匹配项，它将使用已缓存的图标;否则，它会将新图标下载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-130">If the App-V Client finds a match, it will use the already-cached icon; otherwise, it will download the new icon into the cache.</span></span> <span data-ttu-id="3ecf7-131">如果图标的路径是暂存目录，或者它为新图标或程序包重用，则缓存中的查找可能会从上一个操作中选择错误的图标。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-131">If the path to the icon is a scratch directory or if it gets reused for new icons or packages, the lookup in the cache might pick the wrong icon from a previous operation.</span></span>

## <span data-ttu-id="3ecf7-132">启动应用程序时，系统会提示用户提供凭据</span><span class="sxs-lookup"><span data-stu-id="3ecf7-132">Users Are Prompted for Credentials When Starting an Application</span></span>


<span data-ttu-id="3ecf7-133">如果用户尝试启动一个系统管理员限制访问的虚拟应用程序，系统可能会提示用户输入凭据。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-133">If a user attempts to start a virtual application to which the system administrator has restricted access, the user might be prompted to enter credentials.</span></span> <span data-ttu-id="3ecf7-134">用户应键入有权启动该应用程序的帐户的用户名和密码，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-134">The user should type the user name and password for an account that has permission to launch the application and then press ENTER.</span></span>

## <span data-ttu-id="3ecf7-135">将 App-v 客户端升级到版本4.5 后，发布刷新失败</span><span class="sxs-lookup"><span data-stu-id="3ecf7-135">Publishing Refresh Fails After Upgrading the App-V Client to Version 4.5</span></span>


<span data-ttu-id="3ecf7-136">如果用户数据目录以前放置在非标准位置（%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*用户名*%）中，则在计算机上没有管理员权限的用户将发现在升级 app-v 客户端后发布刷新失败。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-136">If the user data directory was previously placed in a non-standard location (%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*username*%), users who do not have administrator privileges on the computer will find that publishing refresh fails after the App-V Client is upgraded.</span></span> <span data-ttu-id="3ecf7-137">在升级期间，App-v 客户端全局数据目录及其所有子目录仅使用管理员的受限访问权限进行配置。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-137">During the upgrade, the App-V Client global data directory and all its subdirectories are configured with restricted access rights for administrators only.</span></span> <span data-ttu-id="3ecf7-138">在升级之前更改用户数据目录以使其不是全局数据目录的子目录，可以避免此问题。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-138">You can avoid this problem by changing the user data directory before upgrading so that it is not a subdirectory of the global data directory.</span></span>

## <span data-ttu-id="3ecf7-139">安装失败后需要重启</span><span class="sxs-lookup"><span data-stu-id="3ecf7-139">Reboot Required After Install Failure</span></span>


<span data-ttu-id="3ecf7-140">如果客户端安装因任何原因而失败，并且如果随后尝试安装客户端也失败，请检查 Windows Installer 日志以查看它是否显示错误 "sftplay 失败，错误 = 1072"。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-140">If the client install fails for any reason and if subsequent attempts to install the client also fail, check the Windows Installer log to see whether it shows an error “sftplay failed, error=1072”.</span></span> <span data-ttu-id="3ecf7-141">如果是这样，请重新启动计算机，然后再次尝试安装客户端。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-141">If so, restart the computer before trying to install the client again.</span></span>

## <span data-ttu-id="3ecf7-142">修复损坏的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="3ecf7-142">Repairing a Corrupted Virtual Application</span></span>


<span data-ttu-id="3ecf7-143">如果由于任何原因，使用 Windows 安装程序包（MSI）文件安装的虚拟应用程序包损坏，请重新安装程序包。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-143">If for any reason a virtual application package installed using a Windows Installer Package (MSI) file becomes corrupted, reinstall the package.</span></span> <span data-ttu-id="3ecf7-144">Windows 安装程序中提供的修复功能不会更新用户卷。</span><span class="sxs-lookup"><span data-stu-id="3ecf7-144">The Repair function available in the Windows Installer will not update the user volumes.</span></span>

## <span data-ttu-id="3ecf7-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="3ecf7-145">Related topics</span></span>


[<span data-ttu-id="3ecf7-146">Application Virtualization Client 参考</span><span class="sxs-lookup"><span data-stu-id="3ecf7-146">Application Virtualization Client Reference</span></span>](application-virtualization-client-reference.md)

 

 





