---
title: 为 UE-V 1.0 部署设置存储位置
description: 为 UE-V 1.0 部署设置存储位置
author: dansimp
ms.assetid: b187d44d-649b-487e-98d3-a61ee2be8c2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c179be0882bc6a0efc0f11f21fc231f03b63b0fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804008"
---
# <span data-ttu-id="1ca57-103">为 UE-V 1.0 部署设置存储位置</span><span class="sxs-lookup"><span data-stu-id="1ca57-103">Deploying the Settings Storage Location for UE-V 1.0</span></span>


<span data-ttu-id="1ca57-104">Microsoft 用户体验虚拟化（UE-V）部署需要设置存储位置，其中的用户设置存储在设置包文件中。</span><span class="sxs-lookup"><span data-stu-id="1ca57-104">Microsoft User Experience Virtualization (UE-V) deployment requires a settings storage location where the user settings are stored in a settings package file.</span></span> <span data-ttu-id="1ca57-105">可通过以下两种方式之一配置设置存储位置：</span><span class="sxs-lookup"><span data-stu-id="1ca57-105">The settings storage location can be configured in one of the following two ways:</span></span>

-   <span data-ttu-id="1ca57-106">**Active directory 主目录**-如果在 Active directory 中为用户定义了主目录，则 ue-v agent 将使用此位置存储设置位置程序包。</span><span class="sxs-lookup"><span data-stu-id="1ca57-106">**Active Directory home directory** – if a home directory is defined for the user in Active Directory, the UE-V agent will use this location to store settings location packages.</span></span> <span data-ttu-id="1ca57-107">UE-V agent 会在主目录的根目录下动态创建特定于用户的存储文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ca57-107">The UE-V agent dynamically creates the user-specific storage folder below the root of the home directory.</span></span> <span data-ttu-id="1ca57-108">如果未定义设置存储位置，则代理仅使用 Active Directory 的主目录。</span><span class="sxs-lookup"><span data-stu-id="1ca57-108">The agent only uses the home directory of the Active Directory if a settings storage location is not defined.</span></span>

-   <span data-ttu-id="1ca57-109">**创建设置存储共享**-设置存储共享是可由 ue-v 用户访问的标准网络共享。</span><span class="sxs-lookup"><span data-stu-id="1ca57-109">**Create a settings storage share** – the settings storage share is a standard network share that is accessible by UE-V users.</span></span>

## <span data-ttu-id="1ca57-110">部署 UE-V 设置存储共享</span><span class="sxs-lookup"><span data-stu-id="1ca57-110">Deploy a UE-V settings storage share</span></span>


<span data-ttu-id="1ca57-111">创建设置存储共享时，应仅对需要访问权限的用户限制访问权限。</span><span class="sxs-lookup"><span data-stu-id="1ca57-111">When you create the settings storage share, you should limit access only to users that need access.</span></span> <span data-ttu-id="1ca57-112">下表中显示了必要的权限。</span><span class="sxs-lookup"><span data-stu-id="1ca57-112">The necessary permissions are shown in the tables below.</span></span>

**<span data-ttu-id="1ca57-113">部署 UE-V 网络共享</span><span class="sxs-lookup"><span data-stu-id="1ca57-113">To deploy the UE-V network share</span></span>**

1.  <span data-ttu-id="1ca57-114">为 UE-V 用户创建新的安全组。</span><span class="sxs-lookup"><span data-stu-id="1ca57-114">Create a new security group for UE-V users.</span></span>

2.  <span data-ttu-id="1ca57-115">在集中放置的计算机上创建将存储 UE-V 设置程序包的新文件夹，然后向 UE-V 用户授予对该文件夹的组权限。</span><span class="sxs-lookup"><span data-stu-id="1ca57-115">Create a new folder on the centrally located computer that will store the UE-V settings packages, and then grant the UE-V users with group permissions to the folder.</span></span> <span data-ttu-id="1ca57-116">支持 UE-V 的管理员将需要此共享文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="1ca57-116">The administrator supporting UE-V will need permissions to this shared folder.</span></span>

3.  <span data-ttu-id="1ca57-117">为设置存储位置文件夹设置以下共享级（SMB）权限：</span><span class="sxs-lookup"><span data-stu-id="1ca57-117">Set the following share-level (SMB) permissions for the setting storage location folder:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="1ca57-118">用户帐户</span><span class="sxs-lookup"><span data-stu-id="1ca57-118">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="1ca57-119">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="1ca57-119">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1ca57-120">所有人</span><span class="sxs-lookup"><span data-stu-id="1ca57-120">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1ca57-121">无权限</span><span class="sxs-lookup"><span data-stu-id="1ca57-121">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1ca57-122">UE-V 用户的安全组</span><span class="sxs-lookup"><span data-stu-id="1ca57-122">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1ca57-123">完全控制</span><span class="sxs-lookup"><span data-stu-id="1ca57-123">Full Control</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="1ca57-124">为设置存储位置文件夹设置以下 NTFS 权限：</span><span class="sxs-lookup"><span data-stu-id="1ca57-124">Set the following NTFS permissions for the settings storage location folder:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="1ca57-125">用户帐户</span><span class="sxs-lookup"><span data-stu-id="1ca57-125">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="1ca57-126">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="1ca57-126">Recommended permissions</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="1ca57-127">文件夹</span><span class="sxs-lookup"><span data-stu-id="1ca57-127">Folder</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1ca57-128">创建者/所有者</span><span class="sxs-lookup"><span data-stu-id="1ca57-128">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1ca57-129">完全控制</span><span class="sxs-lookup"><span data-stu-id="1ca57-129">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1ca57-130">仅子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="1ca57-130">Subfolders and Files Only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1ca57-131">UE-V 用户的安全组</span><span class="sxs-lookup"><span data-stu-id="1ca57-131">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1ca57-132">列出文件夹/读取数据、创建文件夹/附加数据</span><span class="sxs-lookup"><span data-stu-id="1ca57-132">List Folder/Read Data, Create Folders/Append Data</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1ca57-133">仅此文件夹</span><span class="sxs-lookup"><span data-stu-id="1ca57-133">This Folder Only</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

5.  <span data-ttu-id="1ca57-134">单击 **"确定"** 关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="1ca57-134">Click **OK** to close the dialog boxes.</span></span>

<span data-ttu-id="1ca57-135">此权限配置允许用户为设置存储创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ca57-135">This permission configuration allows users to create folders for settings storage.</span></span> <span data-ttu-id="1ca57-136">UE-V agent `settingspackage` 在用户的上下文中运行时创建并保护文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ca57-136">The UE-V agent creates and secures a `settingspackage` folder while running in the context of the user.</span></span> <span data-ttu-id="1ca57-137">用户接收其文件夹的 "完全控制" `settingspackage` 。</span><span class="sxs-lookup"><span data-stu-id="1ca57-137">The user receives full control to their `settingspackage` folder.</span></span> <span data-ttu-id="1ca57-138">其他用户不会继承对此文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1ca57-138">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="1ca57-139">无需创建和保护单个用户目录，因为这将由在用户上下文中运行的代理自动完成。</span><span class="sxs-lookup"><span data-stu-id="1ca57-139">You do not need to create and secure individual user directories, because this will be done automatically by the agent that runs in the context of the user.</span></span>

<span data-ttu-id="1ca57-140">**注意** 在为设置存储共享使用 Windows 服务器时，可以配置其他安全。</span><span class="sxs-lookup"><span data-stu-id="1ca57-140">**Note** Additional security can be configured when a Windows server is utilized for the settings storage share.</span></span> <span data-ttu-id="1ca57-141">UE-V 可以配置为验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。</span><span class="sxs-lookup"><span data-stu-id="1ca57-141">UE-V can be configured to verify that either the local administrator's group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="1ca57-142">若要启用其他安全，请完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="1ca57-142">To enable additional security complete the following:</span></span>

1.  <span data-ttu-id="1ca57-143">将名为 "RepositoryOwnerCheckEnabled" 的**REG \ _DWORD**注册表项添加到**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration.**</span><span class="sxs-lookup"><span data-stu-id="1ca57-143">Add a **REG\_DWORD** registry key named "RepositoryOwnerCheckEnabled" to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration.**</span></span>

2.  <span data-ttu-id="1ca57-144">将注册表项值设置为1。</span><span class="sxs-lookup"><span data-stu-id="1ca57-144">Set registry key value to 1.</span></span>

 

## <span data-ttu-id="1ca57-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ca57-145">Related topics</span></span>


[<span data-ttu-id="1ca57-146">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="1ca57-146">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="1ca57-147">UE-V 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="1ca57-147">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

<span data-ttu-id="1ca57-148">部署用于用户体验虚拟化设置模板和设置程序包的中心存储[安装 Ue-v 生成器](installing-the-ue-v-generator.md)</span><span class="sxs-lookup"><span data-stu-id="1ca57-148">Deploy the Central Storage for User Experience Virtualization Settings Templates and Settings Packages [Installing the UE-V Generator](installing-the-ue-v-generator.md)</span></span>

[<span data-ttu-id="1ca57-149">部署 UE-V 代理</span><span class="sxs-lookup"><span data-stu-id="1ca57-149">Deploying the UE-V Agent</span></span>](deploying-the-ue-v-agent.md)

 

 





