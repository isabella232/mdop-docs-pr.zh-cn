---
title: Application Virtualization Client 中的用户访问权限
description: Application Virtualization Client 中的用户访问权限
author: dansimp
ms.assetid: 7459374c-810c-45e3-b205-fdd1f8514f80
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083faffb48aa58a0ee0c81b58fae307e53548b8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798707"
---
# <span data-ttu-id="a1864-103">Application Virtualization Client 中的用户访问权限</span><span class="sxs-lookup"><span data-stu-id="a1864-103">User Access Permissions in Application Virtualization Client</span></span>


<span data-ttu-id="a1864-104">在 "**属性**" 对话框的 "**权限**" 选项卡上，右键单击应用程序虚拟化客户端管理控制台中的 "**应用程序虚拟化**" 节点可访问该选项卡，管理员可以授予用户使用各种客户端功能的权限。</span><span class="sxs-lookup"><span data-stu-id="a1864-104">On the **Permissions** tab on the **Properties** dialog box, accessible by right-clicking the **Application Virtualization** node in the Application Virtualization Client Management Console, administrators can grant users permissions to use the various client functions.</span></span>

<span data-ttu-id="a1864-105">**注意** 在更改用户权限之前，请确保任何权限更改均与组织授予用户权限的指南一致。</span><span class="sxs-lookup"><span data-stu-id="a1864-105">**Note** Before changing users permissions, ensure that any permissions changes are consistent with the organization's guidelines for granting user permissions.</span></span>

 

<span data-ttu-id="a1864-106">下表列出并介绍了可授予用户的权限。</span><span class="sxs-lookup"><span data-stu-id="a1864-106">The following table lists and describes the permissions that can be granted to users.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a1864-107">权限名称</span><span class="sxs-lookup"><span data-stu-id="a1864-107">Permission Name</span></span></th>
<th align="left"><span data-ttu-id="a1864-108">描述</span><span class="sxs-lookup"><span data-stu-id="a1864-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-109">添加应用程序</span><span class="sxs-lookup"><span data-stu-id="a1864-109">Add applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-110">通过使用 sfttray.exe、sftmime.exe 或 MMC 将新的 OSD 文件传递到客户端来注册新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1864-110">Register new applications by passing a new OSD file to the client by using sfttray.exe, sftmime.exe or the MMC.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-111">更改文件系统缓存大小</span><span class="sxs-lookup"><span data-stu-id="a1864-111">Change file system cache size</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-112">增加文件系统缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="a1864-112">Increase the size of the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-113">更改文件系统驱动器</span><span class="sxs-lookup"><span data-stu-id="a1864-113">Change file system drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-114">为文件系统选择不同的首选驱动器号。</span><span class="sxs-lookup"><span data-stu-id="a1864-114">Select a different preferred drive letter for the file system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-115">更改日志设置</span><span class="sxs-lookup"><span data-stu-id="a1864-115">Change log settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-116">更改客户端日志文件的日志级别或日志路径。</span><span class="sxs-lookup"><span data-stu-id="a1864-116">Change the log level or the log path for the client log file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-117">更改 OSD 文件</span><span class="sxs-lookup"><span data-stu-id="a1864-117">Change OSD files</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-118">修改已注册应用程序的 OSD 文件并将其传递到客户端。</span><span class="sxs-lookup"><span data-stu-id="a1864-118">Modify OSD files for registered applications and pass them into the client.</span></span> <span data-ttu-id="a1864-119">这不会影响发布刷新。</span><span class="sxs-lookup"><span data-stu-id="a1864-119">This does not affect publishing refresh.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-120">清除应用程序设置</span><span class="sxs-lookup"><span data-stu-id="a1864-120">Clear application settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-121">删除当前用户的文件类型、快捷方式和任何配置。</span><span class="sxs-lookup"><span data-stu-id="a1864-121">Delete file types, shortcuts and any configurations for the current user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-122">删除应用程序</span><span class="sxs-lookup"><span data-stu-id="a1864-122">Delete applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-123">从文件系统中删除对应用程序的所有引用以及计算机上所有用户的 OSD 缓存。</span><span class="sxs-lookup"><span data-stu-id="a1864-123">Remove all references to an application from the file system and OSD cache for all users on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-124">将应用程序导入到缓存中</span><span class="sxs-lookup"><span data-stu-id="a1864-124">Import applications into the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-125">将应用程序数据从指定的 SFT 文件直接加载到文件系统缓存中。</span><span class="sxs-lookup"><span data-stu-id="a1864-125">Load application data directly from a specified SFT file into the file system cache.</span></span> <span data-ttu-id="a1864-126">这将影响所有用户。</span><span class="sxs-lookup"><span data-stu-id="a1864-126">This affects all users.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-127">将应用程序加载到缓存中</span><span class="sxs-lookup"><span data-stu-id="a1864-127">Load applications into the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-128">从已配置的源开始对应用程序的 SFT 文件的加载，例如 App-v 流式处理服务器。</span><span class="sxs-lookup"><span data-stu-id="a1864-128">Start a load of the SFT file for an application from the configured source, such as an App-V Streaming Server.</span></span> <span data-ttu-id="a1864-129">这将为计算机上的所有用户加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1864-129">This loads the application for all users on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-130">在缓存中锁定和取消锁定应用程序</span><span class="sxs-lookup"><span data-stu-id="a1864-130">Lock and unlock applications in the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-131">阻止或允许从文件系统缓存中卸载应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1864-131">Prevent or allow applications from being unloaded from the file system cache.</span></span> <span data-ttu-id="a1864-132">这会影响计算机上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="a1864-132">This affects all users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-133">管理文件类型关联</span><span class="sxs-lookup"><span data-stu-id="a1864-133">Manage file type associations</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-134">仅添加、修改或删除当前用户的文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="a1864-134">Add, modify, or delete file type associations for the current user only.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-135">管理发布刷新设置</span><span class="sxs-lookup"><span data-stu-id="a1864-135">Manage publishing refresh settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-136">更改用于控制计算机上所有用户的发布刷新计时的设置。</span><span class="sxs-lookup"><span data-stu-id="a1864-136">Change settings that control the timing of publishing refreshes for all users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-137">管理发布服务器</span><span class="sxs-lookup"><span data-stu-id="a1864-137">Manage publishing servers</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-138">为计算机上的所有用户添加、修改或删除发布服务器。</span><span class="sxs-lookup"><span data-stu-id="a1864-138">Add, modify, or delete publishing servers for all users on the computer.</span></span> <span data-ttu-id="a1864-139">此权限隐式包含管理发布刷新设置的权限。</span><span class="sxs-lookup"><span data-stu-id="a1864-139">This permission implicitly includes permission to manage publishing refresh settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-140">发布快捷方式</span><span class="sxs-lookup"><span data-stu-id="a1864-140">Publish shortcuts</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-141">创建新的注册应用程序快捷方式。</span><span class="sxs-lookup"><span data-stu-id="a1864-141">Create new shortcuts to registered applications.</span></span> <span data-ttu-id="a1864-142">用户还必须具有在本地文件系统中创建文件的权限。</span><span class="sxs-lookup"><span data-stu-id="a1864-142">The user must also have permission to create files in the local file system.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-143">修复应用程序</span><span class="sxs-lookup"><span data-stu-id="a1864-143">Repair applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-144">删除当前用户的特定于应用程序的配置，而不删除快捷方式或文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="a1864-144">Remove application specific configurations for the current user without removing shortcuts or file type associations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-145">启动发布刷新</span><span class="sxs-lookup"><span data-stu-id="a1864-145">Start a publishing refresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-146">为当前用户启动计划外的发布刷新。</span><span class="sxs-lookup"><span data-stu-id="a1864-146">Start an unscheduled publishing refresh for the current user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-147">切换脱机模式</span><span class="sxs-lookup"><span data-stu-id="a1864-147">Toggle offline mode</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-148">为所有用户将整个客户端从联机模式更改为脱机模式。</span><span class="sxs-lookup"><span data-stu-id="a1864-148">Change the entire client from online to offline mode for all users.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a1864-149">从缓存卸载应用程序</span><span class="sxs-lookup"><span data-stu-id="a1864-149">Unload applications from the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-150">为所有用户清除文件系统缓存中的应用程序数据，而不删除特定于用户的设置、快捷方式或文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="a1864-150">Clear application data from the file system cache for all users without removing user-specific settings, shortcuts, or file type associations.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a1864-151">查看所有应用程序</span><span class="sxs-lookup"><span data-stu-id="a1864-151">View all applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="a1864-152">允许用户查看计算机上注册的所有用户的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1864-152">Allow the user to see the virtual applications for all users registered on the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a1864-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="a1864-153">Related topics</span></span>


[<span data-ttu-id="a1864-154">如何更改用户访问权限</span><span class="sxs-lookup"><span data-stu-id="a1864-154">How to Change User Access Permissions</span></span>](how-to-change-user-access-permissions.md)

 

 





