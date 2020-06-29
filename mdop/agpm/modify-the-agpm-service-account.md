---
title: 修改 AGPM 服务帐户
description: 修改 AGPM 服务帐户
author: dansimp
ms.assetid: 0d8d8c7b-f299-4fee-8414-406492156942
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0672ceed2fba17060e17d2ffcfa264da458b9897
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802651"
---
# <span data-ttu-id="0678a-103">修改 AGPM 服务帐户</span><span class="sxs-lookup"><span data-stu-id="0678a-103">Modify the AGPM Service Account</span></span>


<span data-ttu-id="0678a-104">AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对存档和生产环境中的组策略对象（Gpo）的访问。</span><span class="sxs-lookup"><span data-stu-id="0678a-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="0678a-105">如果此服务已停止或禁用，则 AGPM 客户端无法通过服务器执行操作。</span><span class="sxs-lookup"><span data-stu-id="0678a-105">If this service is stopped or disabled, AGPM clients cannot perform operations through the server.</span></span>

<span data-ttu-id="0678a-106">存档路径和 AGPM 服务帐户是在安装 AGPM 服务器期间配置的，可在以后通过 AGPM 服务器上的 "**添加或删除程序**" 更改。</span><span class="sxs-lookup"><span data-stu-id="0678a-106">The archive path and AGPM Service Account are configured during the installation of AGPM Server and can be changed afterward through **Add or Remove Programs** on the AGPM Server.</span></span>

<span data-ttu-id="0678a-107">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="0678a-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="0678a-108">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="0678a-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

<span data-ttu-id="0678a-109">一个用户帐户，该帐户是域管理员组的成员，并且有权访问 AGPM 服务器（安装了 Microsoft 高级组策略管理-服务器的计算机），需要完成此过程。</span><span class="sxs-lookup"><span data-stu-id="0678a-109">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span>

<span data-ttu-id="0678a-110">**重要提示** AGPM 服务帐户必须对它将管理的 Gpo 具有完全访问权限，并将其授予 **"以服务形式登录**" 权限。</span><span class="sxs-lookup"><span data-stu-id="0678a-110">**Important** The AGPM Service Account must have full access to the GPOs that it will manage and will be granted **Log On As A Service** permission.</span></span> <span data-ttu-id="0678a-111">如果你将在单个域上管理 Gpo，则可以将主域控制器的本地系统帐户设置为 AGPM 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="0678a-111">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

<span data-ttu-id="0678a-112">如果你将在多个域上管理 Gpo，或者如果成员服务器是 AGPM 服务器，你应将其他帐户配置为 AGPM 服务帐户，因为一个域控制器的本地系统帐户无法访问其他域上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="0678a-112">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

 

**<span data-ttu-id="0678a-113">修改 AGPM 服务帐户</span><span class="sxs-lookup"><span data-stu-id="0678a-113">To modify the AGPM Service Account</span></span>**

1.  <span data-ttu-id="0678a-114">在安装了 Microsoft 高级组策略管理-服务器的计算机上，单击 "**开始**"，单击 "**控制面板**"，然后单击 "**添加或删除程序**"。</span><span class="sxs-lookup"><span data-stu-id="0678a-114">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, click **Control Panel**, click **Add or Remove Programs**.</span></span>

2.  <span data-ttu-id="0678a-115">单击 " **Microsoft 高级组策略管理-服务器**"，然后单击 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="0678a-115">Click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="0678a-116">单击 "**下一步**"，然后单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="0678a-116">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="0678a-117">按照屏幕上的说明配置 AGPM 服务的设置：</span><span class="sxs-lookup"><span data-stu-id="0678a-117">Follow the instructions on screen to configure settings for the AGPM Service:</span></span>

    1.  <span data-ttu-id="0678a-118">对于存档路径，请确认或更改相对于 AGPM 服务器的存档位置。</span><span class="sxs-lookup"><span data-stu-id="0678a-118">For the archive path, confirm or change the location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="0678a-119">存档路径可以指向 AGPM 服务器或其他位置上的文件夹，但位置应该有足够的空间来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="0678a-119">The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

    2.  <span data-ttu-id="0678a-120">为 AGPM 服务帐户输入新的凭据。</span><span class="sxs-lookup"><span data-stu-id="0678a-120">Enter new credentials for the AGPM Service Account.</span></span>

    3.  <span data-ttu-id="0678a-121">对于存档所有者，请输入 AGPM 管理员的凭据（"完全控制"）。</span><span class="sxs-lookup"><span data-stu-id="0678a-121">For the archive owner, enter the credentials of an AGPM Administrator (Full Control).</span></span>

5.  <span data-ttu-id="0678a-122">单击 "**更改**"，完成安装后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="0678a-122">Click **Change**, and when the installation is complete click **Finish**.</span></span>

### <span data-ttu-id="0678a-123">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="0678a-123">Additional references</span></span>

-   [<span data-ttu-id="0678a-124">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="0678a-124">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





