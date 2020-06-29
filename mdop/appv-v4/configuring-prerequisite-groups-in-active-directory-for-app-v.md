---
title: 在 Active Directory 中为 App-V 配置必备组
description: 在 Active Directory 中为 App-V 配置必备组
author: dansimp
ms.assetid: 0010d534-46c0-44a3-b5c1-621b4d5e2c31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa1ab6393dee20203b715311d4e1dfdc4c22c679
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803053"
---
# <span data-ttu-id="6aa8b-103">在 Active Directory 中为 App-V 配置必备组</span><span class="sxs-lookup"><span data-stu-id="6aa8b-103">Configuring Prerequisite Groups in Active Directory for App-V</span></span>


<span data-ttu-id="6aa8b-104">在安装 Microsoft Application Virtualization （App-v）管理服务器之前，必须在 Active Directory 中创建以下对象。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-104">Before you install the Microsoft Application Virtualization (App-V) Management Server, you must create the following objects in Active Directory.</span></span> <span data-ttu-id="6aa8b-105">App-v 使用 Active Directory 组控制对应用程序和管理功能的访问。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-105">App-V uses Active Directory groups to control access to applications and administrative functions.</span></span> <span data-ttu-id="6aa8b-106">在服务器安装过程中以及发布应用程序时，您将使用这些组。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-106">You will use these groups during the server installation process and when publishing applications.</span></span>

## <span data-ttu-id="6aa8b-107">在 Active Directory 中为应用程序虚拟化配置必备项组</span><span class="sxs-lookup"><span data-stu-id="6aa8b-107">Configuring Prerequisite Groups in Active Directory for Application Virtualization</span></span>


<span data-ttu-id="6aa8b-108">下表列出了安装 app-v 所需的 Active Directory 组。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-108">This table lists the Active Directory groups that are required for installing App-V.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa8b-109">对象</span><span class="sxs-lookup"><span data-stu-id="6aa8b-109">Object</span></span></th>
<th align="left"><span data-ttu-id="6aa8b-110">说明</span><span class="sxs-lookup"><span data-stu-id="6aa8b-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa8b-111">组织单位（OU）</span><span class="sxs-lookup"><span data-stu-id="6aa8b-111">Organizational Unit (OU)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa8b-112">在 Active Directory 中为 App-v 所需的特定组创建一个 OU。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-112">Create an OU in Active Directory for the specific groups required for App-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa8b-113">App-v 管理组</span><span class="sxs-lookup"><span data-stu-id="6aa8b-113">App-V Administrative Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa8b-114">在安装 app-v 管理服务器的过程中，必须选择一个 Active Directory 组以用作 App-v 管理员组，以便控制对管理控制台的管理访问。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-114">During installation of the App-V Management Server, you must select an Active Directory group to use as the App-V Administrators group to control administrative access to the Management Console.</span></span> <span data-ttu-id="6aa8b-115">为 App-v 管理员创建安全组，并将需要使用管理控制台的每位用户添加到该组。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-115">Create a security group for App-V administrators, and add to this group every user who needs to use the Management Console.</span></span> <span data-ttu-id="6aa8b-116">您不能直接从 App-v 管理服务器安装程序创建此组。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-116">You cannot create this group directly from the App-V Management Server installer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa8b-117">App-v Users 组</span><span class="sxs-lookup"><span data-stu-id="6aa8b-117">App-V Users Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa8b-118">App-v 要求访问 App-v 函数的每个用户帐户都是与单个组相关联的提供程序策略的成员，用于通用平台访问。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-118">App-V requires that every User account that accesses App-V functions be a member of a provider policy associated with a single group for general platform access.</span></span> <span data-ttu-id="6aa8b-119">使用现有组;例如，如果所有用户都具有对 App-v 的访问权限，或者创建新组，则为域用户。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-119">Use an existing group; for example, Domain Users, if all users are to have access to App-V, or create a new group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa8b-120">应用程序组</span><span class="sxs-lookup"><span data-stu-id="6aa8b-120">Application Groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa8b-121">App-v 将使用单个应用程序与 Active Directory 组相关联的权限。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-121">App-V associates the right to use an individual application with an Active Directory group.</span></span> <span data-ttu-id="6aa8b-122">为每个应用程序创建一个 Active Directory 组，并根据需要向这些组分配用户，以控制用户对应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6aa8b-122">Create an Active Directory group for each application, and assign users to these groups as needed to control user access to the applications.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6aa8b-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="6aa8b-123">Related topics</span></span>


[<span data-ttu-id="6aa8b-124">Application Virtualization 部署要求</span><span class="sxs-lookup"><span data-stu-id="6aa8b-124">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

[<span data-ttu-id="6aa8b-125">如何为 App-V Management Server 配置 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="6aa8b-125">How to Configure Windows Server 2008 for App-V Management Servers</span></span>](how-to-configure-windows-server-2008-for-app-v-management-servers.md)

 

 





