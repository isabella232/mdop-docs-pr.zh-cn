---
title: 修改 AGPM 服务
description: 修改 AGPM 服务
author: dansimp
ms.assetid: 3239d088-bb86-4ec4-bc56-dbe8f1c710f5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: be39b170ef4cdc14c0f447bb6bd09a4ea92c82fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802640"
---
# <span data-ttu-id="6945c-103">修改 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="6945c-103">Modify the AGPM Service</span></span>


<span data-ttu-id="6945c-104">AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对域的存档和生产环境中的组策略对象（Gpo）的访问。</span><span class="sxs-lookup"><span data-stu-id="6945c-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy Objects (GPOs) in the archive and production environment of the domain.</span></span> <span data-ttu-id="6945c-105">如果此服务已停止或禁用，则 AGPM 客户端无法通过服务器执行操作。</span><span class="sxs-lookup"><span data-stu-id="6945c-105">If this service is stopped or disabled, AGPM Clients cannot perform operations through the server.</span></span> <span data-ttu-id="6945c-106">你可以修改存档路径、AGPM 服务帐户和 AGPM 服务侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="6945c-106">You can modify the archive path, the AGPM Service Account, and the port on which the AGPM Service listens.</span></span>

<span data-ttu-id="6945c-107">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="6945c-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="6945c-108">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="6945c-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

<span data-ttu-id="6945c-109">一个用户帐户，该帐户是域管理员组的成员，并且有权访问 AGPM 服务器（安装了 Microsoft 高级组策略管理-服务器的计算机），需要完成此过程。</span><span class="sxs-lookup"><span data-stu-id="6945c-109">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span> <span data-ttu-id="6945c-110">此外，必须提供 AGPM 服务帐户的凭据才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="6945c-110">Additionally, you must provide credentials for the AGPM Service Account to complete this procedure.</span></span>

**<span data-ttu-id="6945c-111">修改 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="6945c-111">To modify the AGPM Service</span></span>**

1.  <span data-ttu-id="6945c-112">在安装了 Microsoft 高级组策略管理-服务器的计算机上，单击 "**开始**"、 **"控制面板**"、"**程序**" 和 "**程序和功能**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-112">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, **Control Panel**, **Programs**, and **Programs and Features**.</span></span>

2.  <span data-ttu-id="6945c-113">右键单击 " **Microsoft 高级组策略管理-服务器**"，然后单击 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-113">Right-click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="6945c-114">单击 "**下一步**"，然后单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-114">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="6945c-115">按照说明配置 AGPM 服务：</span><span class="sxs-lookup"><span data-stu-id="6945c-115">Follow the instructions to configure the AGPM Service:</span></span>

    1.  <span data-ttu-id="6945c-116">在 "**存档路径**" 对话框中，输入存档相对于 AGPM 服务器的新位置，或确认当前存档路径，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-116">In the **Archive Path** dialog box, enter a new location for the archive relative to the AGPM Server, or confirm the current archive path, and then click **Next**.</span></span>

        <span data-ttu-id="6945c-117">**重要提示** 存档路径可以指向 AGPM 服务器或其他位置上的文件夹，但位置应该有足够的空间来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="6945c-117">**Important** The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

         

    2.  <span data-ttu-id="6945c-118">在 " **Agpm 服务帐户**" 对话框中，输入要在其下运行 AGPM 服务的服务帐户的凭据，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-118">In the **AGPM Service Account** dialog box, enter credentials for a service account under which the AGPM Service will run, and click **Next**.</span></span>

        <span data-ttu-id="6945c-119">**重要提示** 修改安装会清除 AGPM 服务帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="6945c-119">**Important** Modifying the installation clears the credentials for the AGPM Service Account.</span></span> <span data-ttu-id="6945c-120">您必须重新输入凭据，但它们不需要与原始安装期间使用的凭据相匹配。</span><span class="sxs-lookup"><span data-stu-id="6945c-120">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

        <span data-ttu-id="6945c-121">AGPM 服务帐户必须对它将管理的 Gpo 具有完全访问权限，并将其授予 **"以服务形式登录**" 权限。</span><span class="sxs-lookup"><span data-stu-id="6945c-121">The AGPM Service Account must have full access to the GPOs that it will manage and will be granted **Log On As A Service** permission.</span></span> <span data-ttu-id="6945c-122">如果你将在单个域上管理 Gpo，则可以将主域控制器的本地系统帐户设置为 AGPM 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="6945c-122">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

        <span data-ttu-id="6945c-123">如果你将在多个域上管理 Gpo，或者如果成员服务器是 AGPM 服务器，你应将其他帐户配置为 AGPM 服务帐户，因为一个域控制器的本地系统帐户无法访问其他域上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="6945c-123">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

         

    3.  <span data-ttu-id="6945c-124">在 "**存档所有者**" 对话框中，输入 AGPM 管理员（完全控制）或 agpm 管理员组的用户名，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-124">In the **Archive Owner** dialog box, enter the user name of an AGPM Administrator (Full Control) or group of AGPM Administrators, and click **Next**.</span></span>

        <span data-ttu-id="6945c-125">**注意** 修改安装会清除存档所有者的凭据。</span><span class="sxs-lookup"><span data-stu-id="6945c-125">**Note** Modifying the installation clears the credentials for the Archive Owner.</span></span> <span data-ttu-id="6945c-126">您必须重新输入凭据，但它们不需要与原始安装期间使用的凭据相匹配。</span><span class="sxs-lookup"><span data-stu-id="6945c-126">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

         

    4.  <span data-ttu-id="6945c-127">在 "**端口配置**" 对话框中，键入 AGPM 服务应在其上侦听或确认当前所选端口的新端口，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-127">In the **Port Configuration** dialog box, type a new port on which the AGPM Service should listen or confirm the port currently selected, and click **Next**.</span></span>

        <span data-ttu-id="6945c-128">**注意** 默认情况下，AGPM 服务在端口4600上侦听。</span><span class="sxs-lookup"><span data-stu-id="6945c-128">**Note** By default, the AGPM Service listens on port 4600.</span></span>

        <span data-ttu-id="6945c-129">如果手动配置了端口例外或具有配置端口例外的规则，则可以清除 "**将端口例外添加到防火墙**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6945c-129">If you manually configure port exceptions or have rules configuring port exceptions, you can clear the **Add port exception to firewall** check box.</span></span>

         

5.  <span data-ttu-id="6945c-130">单击 "**更改**"，完成安装后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="6945c-130">Click **Change**, and when the installation is complete click **Finish**.</span></span>

6.  <span data-ttu-id="6945c-131">如果您更改了 AGPM 服务侦听的端口，请在每个组策略管理员的 AGPM 服务器连接中修改该端口。</span><span class="sxs-lookup"><span data-stu-id="6945c-131">If you have changed the port on which the AGPM Service listens, modify the port in the AGPM Server connection for each Group Policy administrator.</span></span> <span data-ttu-id="6945c-132">（有关详细信息，请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm40.md)。）</span><span class="sxs-lookup"><span data-stu-id="6945c-132">(For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).)</span></span>

7.  <span data-ttu-id="6945c-133">对应该应用配置更改的每个 AGPM 服务器重复此操作。</span><span class="sxs-lookup"><span data-stu-id="6945c-133">Repeat for each AGPM Server to which the configuration changes should be applied.</span></span>

### <span data-ttu-id="6945c-134">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="6945c-134">Additional references</span></span>

-   [<span data-ttu-id="6945c-135">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="6945c-135">Managing the AGPM Service</span></span>](managing-the-agpm-service-agpm40.md)

 

 





