---
title: 高级组策略管理疑难解答
description: 高级组策略管理疑难解答
author: dansimp
ms.assetid: f58849cf-6c5b-44d8-b356-0ed7a5b24cee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c22b9a0983b26252ee0d9c8d99b63cd4ab5dc2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801743"
---
# <span data-ttu-id="7d780-103">高级组策略管理疑难解答</span><span class="sxs-lookup"><span data-stu-id="7d780-103">Troubleshooting Advanced Group Policy Management</span></span>


<span data-ttu-id="7d780-104">本部分列出了使用高级组策略管理（AGPM）管理组策略对象（Gpo）时可能遇到的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="7d780-104">This section lists a few common issues you may encounter when using Advanced Group Policy Management (AGPM) to manage Group Policy objects (GPOs).</span></span>

## <span data-ttu-id="7d780-105">你遇到了哪些问题？</span><span class="sxs-lookup"><span data-stu-id="7d780-105">What problems are you having?</span></span>


-   [<span data-ttu-id="7d780-106">我无法访问存档</span><span class="sxs-lookup"><span data-stu-id="7d780-106">I am unable to access an archive</span></span>](#bkmk-access-an-archive)

-   [<span data-ttu-id="7d780-107">GPO 状态因不同组策略管理员而异</span><span class="sxs-lookup"><span data-stu-id="7d780-107">The GPO state varies for different Group Policy administrators</span></span>](#bkmk-state-varies)

-   [<span data-ttu-id="7d780-108">我无法修改 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="7d780-108">I am unable to modify the AGPM Server connection</span></span>](#bkmk-modify-archive-location)

-   [<span data-ttu-id="7d780-109">我无法更改默认模板或查看、创建、编辑、重命名、部署或删除 Gpo</span><span class="sxs-lookup"><span data-stu-id="7d780-109">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>](#bkmk-perform-task)

-   [<span data-ttu-id="7d780-110">我无法使用特定的 GPO 名称</span><span class="sxs-lookup"><span data-stu-id="7d780-110">I am unable to use a particular GPO name</span></span>](#bkmk-use-particular-name)

-   [<span data-ttu-id="7d780-111">我没有收到 AGPM 电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="7d780-111">I am not receiving AGPM e-mail notifications</span></span>](#bkmk-email)

-   [<span data-ttu-id="7d780-112">我无法为 AGPM 服务使用端口4600</span><span class="sxs-lookup"><span data-stu-id="7d780-112">I cannot use port 4600 for the AGPM Service</span></span>](#bkmk-port)

-   [<span data-ttu-id="7d780-113">AGPM 服务将不会启动</span><span class="sxs-lookup"><span data-stu-id="7d780-113">The AGPM Service will not start</span></span>](#bkmk-not-start)

-   [<span data-ttu-id="7d780-114">组策略软件安装无法安装软件</span><span class="sxs-lookup"><span data-stu-id="7d780-114">Group Policy Software Installation fails to install software</span></span>](#bkmk-software-installation)

### <a href="" id="bkmk-access-an-archive"></a><span data-ttu-id="7d780-115">我无法访问存档</span><span class="sxs-lookup"><span data-stu-id="7d780-115">I am unable to access an archive</span></span>

-   <span data-ttu-id="7d780-116">**原因**：你没有为存档选择正确的服务器和端口。</span><span class="sxs-lookup"><span data-stu-id="7d780-116">**Cause**: You have not selected the correct server and port for the archive.</span></span>

-   <span data-ttu-id="7d780-117">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="7d780-117">**Solution**:</span></span>

    -   <span data-ttu-id="7d780-118">如果你是 AGPM 管理员：请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-118">If you are an AGPM Administrator: See [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="7d780-119">如果您不是 AGPM 管理员：从 AGPM 管理员请求 AGPM 服务器的连接详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d780-119">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="7d780-120">请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection-reviewer.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-120">See [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

-   <span data-ttu-id="7d780-121">**原因**：高级组策略管理服务未运行。</span><span class="sxs-lookup"><span data-stu-id="7d780-121">**Cause**: The Advanced Group Policy Management Service is not running.</span></span>

-   <span data-ttu-id="7d780-122">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="7d780-122">**Solution**:</span></span>

    -   <span data-ttu-id="7d780-123">如果您是 AGPM 管理员：启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="7d780-123">If you are an AGPM Administrator: Start the AGPM Service.</span></span> <span data-ttu-id="7d780-124">有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-124">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service.md).</span></span>

    -   <span data-ttu-id="7d780-125">如果您不是 AGPM 管理员：请与 AGPM 管理员联系以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="7d780-125">If you are not an AGPM Administrator: Contact an AGPM Administrator for assistance.</span></span>

### <a href="" id="bkmk-state-varies"></a><span data-ttu-id="7d780-126">GPO 状态因不同组策略管理员而异</span><span class="sxs-lookup"><span data-stu-id="7d780-126">The GPO state varies for different Group Policy administrators</span></span>

-   <span data-ttu-id="7d780-127">**原因**：不同的组策略管理员为同一存档选择了不同的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="7d780-127">**Cause**: Different Group Policy administrators have selected different AGPM Servers for the same archive.</span></span>

-   <span data-ttu-id="7d780-128">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="7d780-128">**Solution**:</span></span>

    -   <span data-ttu-id="7d780-129">如果你是 AGPM 管理员：请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-129">If you are an AGPM Administrator: See [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="7d780-130">如果您不是 AGPM 管理员：从 AGPM 管理员请求 AGPM 服务器的连接详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d780-130">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="7d780-131">请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection-reviewer.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-131">See [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

### <a href="" id="bkmk-modify-archive-location"></a><span data-ttu-id="7d780-132">我无法修改 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="7d780-132">I am unable to modify the AGPM Server connection</span></span>

-   <span data-ttu-id="7d780-133">**原因**：如果 " **agpm 服务器**" 选项卡上的设置不可用，则已使用管理模板对 agpm 服务器进行集中配置。</span><span class="sxs-lookup"><span data-stu-id="7d780-133">**Cause**: If the settings on the **AGPM Server** tab are unavailable, the AGPM Server has been centrally configured using an Administrative template.</span></span>

-   <span data-ttu-id="7d780-134">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="7d780-134">**Solution**:</span></span>

    -   <span data-ttu-id="7d780-135">如果您是 AGPM 管理员：如果 " **Agpm 服务器**" 选项卡上的设置不可用，请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-135">If you are an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="7d780-136">如果您不是 AGPM 管理员：如果 " **Agpm 服务器**" 选项卡上的设置不可用，则不需要修改 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="7d780-136">If you are not an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, you do not need to modify the AGPM Server.</span></span>

### <a href="" id="bkmk-perform-task"></a><span data-ttu-id="7d780-137">我无法更改默认模板或查看、创建、编辑、重命名、部署或删除 Gpo</span><span class="sxs-lookup"><span data-stu-id="7d780-137">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>

-   <span data-ttu-id="7d780-138">**原因**：尚未向你分配执行任务所需权限的角色。</span><span class="sxs-lookup"><span data-stu-id="7d780-138">**Cause**: You have not been assigned a role with the permissions required to perform the task or tasks.</span></span>

-   <span data-ttu-id="7d780-139">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="7d780-139">**Solution**:</span></span>

    -   <span data-ttu-id="7d780-140">如果您是 AGPM 管理员：请参阅[委派域级访问](delegate-domain-level-access.md)和[委派对单个 GPO 的访问权限](delegate-access-to-an-individual-gpo.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-140">If you are an AGPM Administrator: See [Delegate Domain-Level Access](delegate-domain-level-access.md) and [Delegate Access to an Individual GPO](delegate-access-to-an-individual-gpo.md).</span></span> <span data-ttu-id="7d780-141">AGPM 权限将从域级联到当前存档中的所有 Gpo。</span><span class="sxs-lookup"><span data-stu-id="7d780-141">AGPM permissions will cascade from the domain to all GPOs currently in the archive.</span></span> <span data-ttu-id="7d780-142">当新组策略管理员添加到域级别时，其权限必须设置为应用于**此对象和嵌套的对象**。</span><span class="sxs-lookup"><span data-stu-id="7d780-142">As new Group Policy administrators are added at the domain level, their permissions must be set to apply to **This object and nested objects**.</span></span> <span data-ttu-id="7d780-143">有关哪些角色可以执行任务以及执行任务需要哪些权限的详细信息，请参阅该任务的帮助。</span><span class="sxs-lookup"><span data-stu-id="7d780-143">For details about which roles can perform a task and what permissions are necessary to perform a task, refer to the help for that task.</span></span>

    -   <span data-ttu-id="7d780-144">如果您不是 AGPM 管理员，并且您需要其他角色或权限：请与 AGPM 管理员联系以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="7d780-144">If you are not an AGPM Administrator and you require additional roles or permissions: Contact an AGPM Administrator for assistance.</span></span> <span data-ttu-id="7d780-145">请注意，如果你是编辑器，则可以开始创建 GPO、部署 GPO 或从生产环境中删除 GPO 的过程，但审批者或 AGPM 管理员必须批准你的请求。</span><span class="sxs-lookup"><span data-stu-id="7d780-145">Note that if you are an Editor, you can begin the process of creating a GPO, deploying a GPO, or deleting a GPO from the production environment, but an Approver or AGPM Administrator must approve your request.</span></span>

### <a href="" id="bkmk-use-particular-name"></a><span data-ttu-id="7d780-146">我无法使用特定的 GPO 名称</span><span class="sxs-lookup"><span data-stu-id="7d780-146">I am unable to use a particular GPO name</span></span>

-   <span data-ttu-id="7d780-147">**原因**：该 gpo 名称已在使用或你无权列出该 gpo。</span><span class="sxs-lookup"><span data-stu-id="7d780-147">**Cause**: Either the GPO name is already in use or you lack permission to list the GPO.</span></span>

-   <span data-ttu-id="7d780-148">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="7d780-148">**Solution**:</span></span>

    -   <span data-ttu-id="7d780-149">如果 GPO 名称显示在 "**受控**"、"不**受控制**" 或 "**挂起**" 选项卡上，请选择其他名称。</span><span class="sxs-lookup"><span data-stu-id="7d780-149">If the GPO name appears on the **Controlled**, **Uncontrolled**, or **Pending** tab, choose another name.</span></span> <span data-ttu-id="7d780-150">如果已部署的 GPO 已重命名但尚未重新部署，则它将显示在生产环境中的旧名称下，因此旧名称仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="7d780-150">If a GPO that has been deployed is renamed but not yet redeployed, it will be displayed under its old name in the production environment—therefore, the old name is still in use.</span></span> <span data-ttu-id="7d780-151">重新部署 GPO 以在生产环境中更新其名称，并释放该名称以供另一个 GPO 使用。</span><span class="sxs-lookup"><span data-stu-id="7d780-151">Redeploy the GPO to update its name in the production environment and release that name for use by another GPO.</span></span>

    -   <span data-ttu-id="7d780-152">如果 GPO 名称未显示在 "**受控**"、"不**受控制**" 或 "**挂起**" 选项卡上，则您可能无权列出该 gpo。</span><span class="sxs-lookup"><span data-stu-id="7d780-152">If the GPO name does not appear on the **Controlled**, **Uncontrolled**, or **Pending** tab, you may lack permission to list the GPO.</span></span> <span data-ttu-id="7d780-153">若要请求权限，请与 AGPM 管理员联系。</span><span class="sxs-lookup"><span data-stu-id="7d780-153">To request permission, contact an AGPM Administrator.</span></span>

### <a href="" id="bkmk-email"></a><span data-ttu-id="7d780-154">我没有收到 AGPM 电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="7d780-154">I am not receiving AGPM e-mail notifications</span></span>

-   <span data-ttu-id="7d780-155">**原因**：未提供有效的 SMTP 电子邮件服务器和电子邮件地址，或者没有执行生成电子邮件通知的操作。</span><span class="sxs-lookup"><span data-stu-id="7d780-155">**Cause**: A valid SMTP e-mail server and e-mail address has not been provided, or no action has been taken that generates an e-mail notification.</span></span>

-   <span data-ttu-id="7d780-156">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="7d780-156">**Solution**:</span></span>

    -   <span data-ttu-id="7d780-157">如果你是 AGPM 管理员：有关要通过 AGPM 发送的待执行操作的电子邮件通知，AGPM 管理员必须为 "**域委派**" 选项卡上的审批者提供有效的 SMTP 电子邮件服务器和电子邮件地址。有关详细信息，请参阅[配置电子邮件通知](configure-e-mail-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-157">If you are an AGPM Administrator: For e-mail notifications about pending actions to be sent by AGPM, an AGPM Administrator must provide a valid SMTP e-mail server and e-mail addresses for Approvers on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification.md).</span></span>

    -   <span data-ttu-id="7d780-158">仅当缺少创建、部署或删除 GPO 所需权限的编辑器、审阅者或其他组策略管理员提交这些操作之一的请求时，才会生成电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7d780-158">E-mail notifications are generated only when an Editor, Reviewer, or other Group Policy administrator who lacks the permission necessary to create, deploy, or delete a GPO submits a request for one of those actions to occur.</span></span> <span data-ttu-id="7d780-159">没有自动通知或拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="7d780-159">There is no automatic notification of approval or rejection of a request.</span></span>

### <a href="" id="bkmk-port"></a><span data-ttu-id="7d780-160">我无法为 AGPM 服务使用端口4600</span><span class="sxs-lookup"><span data-stu-id="7d780-160">I cannot use port 4600 for the AGPM Service</span></span>

-   <span data-ttu-id="7d780-161">**原因**：默认情况下，AGPM 服务侦听的端口是端口4600。</span><span class="sxs-lookup"><span data-stu-id="7d780-161">**Cause**: By default, the port on which the AGPM Service listens is port 4600.</span></span>

-   <span data-ttu-id="7d780-162">**解决方案**：如果对于 AGPM 服务，端口4600不可用，请修改每个存档索引文件以使用另一个端口，然后为所有组策略管理员更新 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="7d780-162">**Solution**: If port 4600 is not available for the AGPM Service, modify each archive index file to use another port and then update the AGPM Server for all Group Policy administrators.</span></span> <span data-ttu-id="7d780-163">有关详细信息，请参阅[修改 AGPM 服务侦听的端口](modify-the-port-on-which-the-agpm-service-listens.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-163">For more information, see [Modify the Port on Which the AGPM Service Listens](modify-the-port-on-which-the-agpm-service-listens.md).</span></span>

### <a href="" id="bkmk-not-start"></a><span data-ttu-id="7d780-164">AGPM 服务将不会启动</span><span class="sxs-lookup"><span data-stu-id="7d780-164">The AGPM Service will not start</span></span>

-   <span data-ttu-id="7d780-165">**原因**：您在 "**管理工具**和**服务**" 下的操作系统中修改了 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="7d780-165">**Cause**: You have modified settings for the AGPM Service in the operating system under **Administrative Tools** and **Services**.</span></span>

-   <span data-ttu-id="7d780-166">**解决方案**：在 "**添加或删除程序**" 下修改**Microsoft 高级组策略管理-服务器**的设置。</span><span class="sxs-lookup"><span data-stu-id="7d780-166">**Solution**: Modify the settings for **Microsoft Advanced Group Policy Management - Server** under **Add or Remove Programs**.</span></span> <span data-ttu-id="7d780-167">有关详细信息，请参阅[修改 AGPM 服务帐户](modify-the-agpm-service-account.md)。</span><span class="sxs-lookup"><span data-stu-id="7d780-167">For more information, see [Modify the AGPM Service Account](modify-the-agpm-service-account.md).</span></span>

### <a href="" id="bkmk-software-installation"></a><span data-ttu-id="7d780-168">组策略软件安装无法安装软件</span><span class="sxs-lookup"><span data-stu-id="7d780-168">Group Policy Software Installation fails to install software</span></span>

-   <span data-ttu-id="7d780-169">**原因**： AGPM 保留组策略软件安装程序包的完整性。</span><span class="sxs-lookup"><span data-stu-id="7d780-169">**Cause**: AGPM preserves the integrity of Group Policy Software Installation packages.</span></span> <span data-ttu-id="7d780-170">虽然脱机编辑 Gpo，但会保留程序包之间的链接和缓存的客户端信息。</span><span class="sxs-lookup"><span data-stu-id="7d780-170">Although GPOs are edited offline, links between packages as well as cached client information are preserved.</span></span> <span data-ttu-id="7d780-171">这是设计使然。</span><span class="sxs-lookup"><span data-stu-id="7d780-171">This is by design.</span></span>

-   <span data-ttu-id="7d780-172">**解决方案**：使用 AGPM 脱机编辑 GPO 时，请将另一个 GPO 中的程序包的任意组策略软件安装升级配置为引用部署的 gpo，而不是签出的副本。</span><span class="sxs-lookup"><span data-stu-id="7d780-172">**Solution**: When editing a GPO offline with AGPM, configure any Group Policy Software Installation upgrade of a package in another GPO to reference the deployed GPO, not the checked-out copy.</span></span> <span data-ttu-id="7d780-173">编辑器必须具有已部署 GPO 的**读取**权限。</span><span class="sxs-lookup"><span data-stu-id="7d780-173">The Editor must have **Read** permission for the deployed GPO.</span></span>

 

 





