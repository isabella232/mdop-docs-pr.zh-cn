---
title: 修改存档路径
description: 修改存档路径
author: dansimp
ms.assetid: 6d90daf9-58db-4166-b5b3-e84bb261164a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1fc6ba2bf415d3d1bc67144d0dec1030c6173026
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802639"
---
# <span data-ttu-id="39465-103">修改存档路径</span><span class="sxs-lookup"><span data-stu-id="39465-103">Modify the Archive Path</span></span>


<span data-ttu-id="39465-104">存档路径是存档相对于 AGPM 服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="39465-104">The archive path is the location of the archive relative to the AGPM Server.</span></span> <span data-ttu-id="39465-105">存档路径可以指向 AGPM 服务器上的文件夹，也可以指向同一林中的另一台服务器上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="39465-105">The archive path can point to a folder on the AGPM Server or on another server in the same forest.</span></span>

<span data-ttu-id="39465-106">存档路径和 AGPM 服务帐户是在安装 AGPM 服务器期间配置的，可在以后通过 AGPM 服务器上的 "**添加或删除程序**" 更改。</span><span class="sxs-lookup"><span data-stu-id="39465-106">The archive path and AGPM Service Account are configured during the installation of AGPM Server and can be changed afterward through **Add or Remove Programs** on the AGPM Server.</span></span>

<span data-ttu-id="39465-107">一个用户帐户，该帐户是域管理员组的成员，并且有权访问 AGPM 服务器（安装了 Microsoft 高级组策略管理-服务器的计算机），需要完成此过程。</span><span class="sxs-lookup"><span data-stu-id="39465-107">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span>

**<span data-ttu-id="39465-108">修改存档路径</span><span class="sxs-lookup"><span data-stu-id="39465-108">To modify the archive path</span></span>**

1.  <span data-ttu-id="39465-109">在安装了 Microsoft 高级组策略管理-服务器的计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**添加或删除程序**"。</span><span class="sxs-lookup"><span data-stu-id="39465-109">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, click **Control Panel**, click **Add or Remove Programs**.</span></span>

2.  <span data-ttu-id="39465-110">单击 " **Microsoft 高级组策略管理-服务器**"，然后单击 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="39465-110">Click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="39465-111">单击 "**下一步**"，然后单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="39465-111">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="39465-112">按照屏幕上的说明配置 AGPM 服务的设置：</span><span class="sxs-lookup"><span data-stu-id="39465-112">Follow the instructions on screen to configure settings for the AGPM Service:</span></span>

    1.  <span data-ttu-id="39465-113">对于存档路径，输入与 AGPM 服务器相关的存档的新位置。</span><span class="sxs-lookup"><span data-stu-id="39465-113">For the archive path, enter a new location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="39465-114">存档路径可以指向 AGPM 服务器或其他位置上的文件夹，但位置应该有足够的空间来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="39465-114">The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

    2.  <span data-ttu-id="39465-115">输入 AGPM 服务帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="39465-115">Enter credentials for the AGPM Service Account.</span></span>

        <span data-ttu-id="39465-116">**重要提示** 修改安装会清除 AGPM 服务帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="39465-116">**Important** Modifying the installation clears the credentials for the AGPM Service Account.</span></span> <span data-ttu-id="39465-117">您必须重新输入凭据，但它们不需要与原始安装期间使用的凭据相匹配。</span><span class="sxs-lookup"><span data-stu-id="39465-117">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

        <span data-ttu-id="39465-118">AGPM 服务帐户必须对它将管理的 Gpo 具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="39465-118">The AGPM Service Account must have full access to the GPOs that it will manage.</span></span> <span data-ttu-id="39465-119">如果你将在单个域上管理 Gpo，则可以将主域控制器的本地系统帐户设置为 AGPM 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="39465-119">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

        <span data-ttu-id="39465-120">如果你将在多个域上管理 Gpo，或者如果成员服务器是 AGPM 服务器，你应将其他帐户配置为 AGPM 服务帐户，因为一个域控制器的本地系统帐户无法访问其他域上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="39465-120">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

         

    3.  <span data-ttu-id="39465-121">对于存档所有者，请输入 AGPM 管理员的凭据（"完全控制"）。</span><span class="sxs-lookup"><span data-stu-id="39465-121">For the archive owner, enter the credentials of an AGPM Administrator (Full Control).</span></span>

5.  <span data-ttu-id="39465-122">单击 "**更改**"，完成安装后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="39465-122">Click **Change**, and when the installation is complete click **Finish**.</span></span>

### <span data-ttu-id="39465-123">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="39465-123">Additional references</span></span>

-   [<span data-ttu-id="39465-124">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="39465-124">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





