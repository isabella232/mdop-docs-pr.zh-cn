---
title: 为 UE-V 1.0 部署设置模板目录
description: 为 UE-V 1.0 部署设置模板目录
author: dansimp
ms.assetid: 0e6ab5ef-8eeb-40b4-be7b-a841bd83be96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f342daa958607a077fa5eb2a27ec705c8d99e67f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804007"
---
# <span data-ttu-id="0dd42-103">为 UE-V 1.0 部署设置模板目录</span><span class="sxs-lookup"><span data-stu-id="0dd42-103">Deploying the Settings Template Catalog for UE-V 1.0</span></span>


<span data-ttu-id="0dd42-104">自定义设置位置模板可以存储在 Microsoft 用户体验虚拟化（UE-V）计算机或服务器消息块（SMB）网络共享上的文件夹路径中。</span><span class="sxs-lookup"><span data-stu-id="0dd42-104">Custom settings location templates can be stored on a folder path on Microsoft User Experience Virtualization (UE-V) computers or on a Server Message Block (SMB) network share.</span></span> <span data-ttu-id="0dd42-105">计算机上的计划任务从该位置检查新的或更新的模板。</span><span class="sxs-lookup"><span data-stu-id="0dd42-105">A scheduled task on the computer checks for new or updated templates from this location.</span></span> <span data-ttu-id="0dd42-106">该任务每天检查此位置一次，并根据此文件夹中的模板更新其同步行为。</span><span class="sxs-lookup"><span data-stu-id="0dd42-106">The task checks this location once each day and updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="0dd42-107">自上次检查以来在此文件夹中添加或更新的模板由 UE-V agent 注册。</span><span class="sxs-lookup"><span data-stu-id="0dd42-107">Templates that are added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="0dd42-108">从该文件夹中删除的 UE-V agent deregisters 模板。</span><span class="sxs-lookup"><span data-stu-id="0dd42-108">The UE-V agent deregisters templates that were removed from this folder.</span></span> <span data-ttu-id="0dd42-109">计划任务作为系统运行。</span><span class="sxs-lookup"><span data-stu-id="0dd42-109">The scheduled task runs as SYSTEM.</span></span> <span data-ttu-id="0dd42-110">至少，网络共享必须为 "域计算机" 组授予权限。</span><span class="sxs-lookup"><span data-stu-id="0dd42-110">At a minimum, the network share must grant permissions for the Domain Computers group.</span></span> <span data-ttu-id="0dd42-111">此外，将网络共享文件夹的访问权限授予将管理存储的模板的管理员。</span><span class="sxs-lookup"><span data-stu-id="0dd42-111">In addition, grant access permissions for the network share folder to administrators who will manage the stored templates.</span></span> <span data-ttu-id="0dd42-112">有关自定义设置位置模板的详细信息，请参阅[规划 ue-v 1.0 的自定义模板部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd42-112">For more information about custom setting location templates, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

**<span data-ttu-id="0dd42-113">配置 UE-V 的设置模板目录</span><span class="sxs-lookup"><span data-stu-id="0dd42-113">To configure the settings template catalog for UE-V</span></span>**

1.  <span data-ttu-id="0dd42-114">在将存储 UE-V 设置模板目录的计算机上创建一个新文件夹。</span><span class="sxs-lookup"><span data-stu-id="0dd42-114">Create a new folder on the computer that will store the UE-V settings template catalog.</span></span>

2.  <span data-ttu-id="0dd42-115">为设置模板目录文件夹设置以下共享级别（SMB）权限。</span><span class="sxs-lookup"><span data-stu-id="0dd42-115">Set the following share-level (SMB) permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="0dd42-116">用户帐户</span><span class="sxs-lookup"><span data-stu-id="0dd42-116">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="0dd42-117">推荐权限</span><span class="sxs-lookup"><span data-stu-id="0dd42-117">Recommend permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0dd42-118">所有人</span><span class="sxs-lookup"><span data-stu-id="0dd42-118">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-119">无权限</span><span class="sxs-lookup"><span data-stu-id="0dd42-119">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="0dd42-120">域计算机</span><span class="sxs-lookup"><span data-stu-id="0dd42-120">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-121">读取权限级别</span><span class="sxs-lookup"><span data-stu-id="0dd42-121">Read Permission Levels</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0dd42-122">管理员</span><span class="sxs-lookup"><span data-stu-id="0dd42-122">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-123">读/写权限级别</span><span class="sxs-lookup"><span data-stu-id="0dd42-123">Read/Write Permission Levels</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

3.  <span data-ttu-id="0dd42-124">为设置模板目录文件夹设置以下 NTFS 权限。</span><span class="sxs-lookup"><span data-stu-id="0dd42-124">Set the following NTFS permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="0dd42-125">用户帐户</span><span class="sxs-lookup"><span data-stu-id="0dd42-125">User Account</span></span></th>
    <th align="left"><span data-ttu-id="0dd42-126">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="0dd42-126">Recommended Permissions</span></span></th>
    <th align="left"><span data-ttu-id="0dd42-127">应用于</span><span class="sxs-lookup"><span data-stu-id="0dd42-127">Apply To</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0dd42-128">创建者/所有者</span><span class="sxs-lookup"><span data-stu-id="0dd42-128">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-129">完全控制</span><span class="sxs-lookup"><span data-stu-id="0dd42-129">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-130">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="0dd42-130">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="0dd42-131">域计算机</span><span class="sxs-lookup"><span data-stu-id="0dd42-131">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-132">列出文件夹内容和阅读</span><span class="sxs-lookup"><span data-stu-id="0dd42-132">List Folder Contents and Read</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-133">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="0dd42-133">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0dd42-134">所有人</span><span class="sxs-lookup"><span data-stu-id="0dd42-134">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-135">无权限</span><span class="sxs-lookup"><span data-stu-id="0dd42-135">No Permissions</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-136">无权限</span><span class="sxs-lookup"><span data-stu-id="0dd42-136">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="0dd42-137">管理员</span><span class="sxs-lookup"><span data-stu-id="0dd42-137">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-138">完全控制</span><span class="sxs-lookup"><span data-stu-id="0dd42-138">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0dd42-139">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="0dd42-139">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="0dd42-140">单击 **"确定"** 关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="0dd42-140">Click **OK** to close the dialog boxes.</span></span>

## <span data-ttu-id="0dd42-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="0dd42-141">Related topics</span></span>


[<span data-ttu-id="0dd42-142">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="0dd42-142">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="0dd42-143">规划 UE-V 1.0 的自定义模板部署</span><span class="sxs-lookup"><span data-stu-id="0dd42-143">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

 

 





