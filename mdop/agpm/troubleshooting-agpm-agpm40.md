---
title: AGPM 疑难解答
description: AGPM 疑难解答
author: dansimp
ms.assetid: bedcd817-beb2-47bf-aebd-e3923c4fd06f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b44612cb9e3737a8d8f3109f76b0c9325d183383
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802503"
---
# <span data-ttu-id="40f34-103">AGPM 疑难解答</span><span class="sxs-lookup"><span data-stu-id="40f34-103">Troubleshooting AGPM</span></span>


<span data-ttu-id="40f34-104">本部分列出了使用高级组策略管理（AGPM）管理组策略对象（Gpo）时可能遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="40f34-104">This section lists common issues that you may encounter when you use Advanced Group Policy Management (AGPM) to manage Group Policy Objects (GPOs).</span></span> <span data-ttu-id="40f34-105">若要诊断此处未列出的问题，则对于 AGPM 管理员（完全控制）使用日志记录和跟踪可能很有帮助。</span><span class="sxs-lookup"><span data-stu-id="40f34-105">To diagnose issues not listed here, it may be helpful for an AGPM Administrator (Full Control) to use logging and tracing.</span></span> <span data-ttu-id="40f34-106">有关详细信息，请参阅[配置日志记录和跟踪](configure-logging-and-tracing-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-106">For more information, see [Configure Logging and Tracing](configure-logging-and-tracing-agpm40.md).</span></span>

**<span data-ttu-id="40f34-107">注意</span><span class="sxs-lookup"><span data-stu-id="40f34-107">Note</span></span>**  
-   <span data-ttu-id="40f34-108">有关回退到较早版本的 GPO （如果存在问题）的信息，请参阅回退[到较早版本的 gpo](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-108">For information about rolling back to an earlier version of a GPO if there are problems, see [Roll Back to an Earlier Version of a GPO](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md).</span></span>

-   <span data-ttu-id="40f34-109">有关如何通过从备份还原完整存档来从灾难中恢复的信息，请参阅[从备份还原存档](restore-the-archive-from-a-backup-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-109">For information about how to recover from a disaster by restoring the complete archive from a backup, see [Restore the Archive from a Backup](restore-the-archive-from-a-backup-agpm40.md).</span></span>

 

## <span data-ttu-id="40f34-110">你遇到了哪些问题？</span><span class="sxs-lookup"><span data-stu-id="40f34-110">What problems are you having?</span></span>


-   [<span data-ttu-id="40f34-111">我无法访问存档</span><span class="sxs-lookup"><span data-stu-id="40f34-111">I am unable to access an archive</span></span>](#bkmk-access-an-archive)

-   [<span data-ttu-id="40f34-112">GPO 状态因不同组策略管理员而异</span><span class="sxs-lookup"><span data-stu-id="40f34-112">The GPO state varies for different Group Policy administrators</span></span>](#bkmk-state-varies)

-   [<span data-ttu-id="40f34-113">我无法修改 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="40f34-113">I am unable to modify the AGPM Server connection</span></span>](#bkmk-modify-archive-location)

-   [<span data-ttu-id="40f34-114">我无法更改默认模板或查看、创建、编辑、重命名、部署或删除 Gpo</span><span class="sxs-lookup"><span data-stu-id="40f34-114">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>](#bkmk-perform-task)

-   [<span data-ttu-id="40f34-115">我无法使用特定的 GPO 名称</span><span class="sxs-lookup"><span data-stu-id="40f34-115">I am unable to use a particular GPO name</span></span>](#bkmk-use-particular-name)

-   [<span data-ttu-id="40f34-116">我没有收到 AGPM 电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="40f34-116">I am not receiving AGPM e-mail notifications</span></span>](#bkmk-email)

-   [<span data-ttu-id="40f34-117">我无法为 AGPM 服务使用端口4600</span><span class="sxs-lookup"><span data-stu-id="40f34-117">I cannot use port 4600 for the AGPM Service</span></span>](#bkmk-port)

-   [<span data-ttu-id="40f34-118">AGPM 服务将不会启动</span><span class="sxs-lookup"><span data-stu-id="40f34-118">The AGPM Service will not start</span></span>](#bkmk-not-start)

-   [<span data-ttu-id="40f34-119">组策略软件安装无法安装软件</span><span class="sxs-lookup"><span data-stu-id="40f34-119">Group Policy Software Installation fails to install software</span></span>](#bkmk-software-installation)

-   [<span data-ttu-id="40f34-120">将存档还原到新的 AGPM 服务器时出错</span><span class="sxs-lookup"><span data-stu-id="40f34-120">An error occurred when I restored the archive to a new AGPM Server</span></span>](#bkmk-error-on-restore)

### <a href="" id="bkmk-access-an-archive"></a><span data-ttu-id="40f34-121">我无法访问存档</span><span class="sxs-lookup"><span data-stu-id="40f34-121">I am unable to access an archive</span></span>

-   <span data-ttu-id="40f34-122">**原因**：你没有为存档选择正确的服务器和端口。</span><span class="sxs-lookup"><span data-stu-id="40f34-122">**Cause**: You have not selected the correct server and port for the archive.</span></span>

-   <span data-ttu-id="40f34-123">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="40f34-123">**Solution**:</span></span>

    -   <span data-ttu-id="40f34-124">如果你是 AGPM 管理员：请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-124">If you are an AGPM Administrator: See [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

    -   <span data-ttu-id="40f34-125">如果您不是 AGPM 管理员：从 AGPM 管理员请求 AGPM 服务器的连接详细信息。</span><span class="sxs-lookup"><span data-stu-id="40f34-125">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="40f34-126">请参阅[配置 AGPM 服务器连接](configure-an-agpm-server-connection-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-126">See [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

-   <span data-ttu-id="40f34-127">**原因**： AGPM 服务未运行。</span><span class="sxs-lookup"><span data-stu-id="40f34-127">**Cause**: The AGPM Service is not running.</span></span>

-   <span data-ttu-id="40f34-128">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="40f34-128">**Solution**:</span></span>

    -   <span data-ttu-id="40f34-129">如果您是 AGPM 管理员：启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="40f34-129">If you are an AGPM Administrator: Start the AGPM Service.</span></span> <span data-ttu-id="40f34-130">有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-130">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

    -   <span data-ttu-id="40f34-131">如果您不是 AGPM 管理员：请与 AGPM 管理员联系以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="40f34-131">If you are not an AGPM Administrator: Contact an AGPM Administrator for assistance.</span></span>

### <a href="" id="bkmk-state-varies"></a><span data-ttu-id="40f34-132">GPO 状态因不同组策略管理员而异</span><span class="sxs-lookup"><span data-stu-id="40f34-132">The GPO state varies for different Group Policy administrators</span></span>

-   <span data-ttu-id="40f34-133">**原因**：不同的组策略管理员为同一存档选择了不同的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="40f34-133">**Cause**: Different Group Policy administrators have selected different AGPM Servers for the same archive.</span></span>

-   <span data-ttu-id="40f34-134">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="40f34-134">**Solution**:</span></span>

    -   <span data-ttu-id="40f34-135">如果你是 AGPM 管理员：请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-135">If you are an AGPM Administrator: See [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

    -   <span data-ttu-id="40f34-136">如果您不是 AGPM 管理员：从 AGPM 管理员请求 AGPM 服务器的连接详细信息。</span><span class="sxs-lookup"><span data-stu-id="40f34-136">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="40f34-137">请参阅[配置 AGPM 服务器连接](configure-an-agpm-server-connection-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-137">See [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

### <a href="" id="bkmk-modify-archive-location"></a><span data-ttu-id="40f34-138">我无法修改 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="40f34-138">I am unable to modify the AGPM Server connection</span></span>

-   <span data-ttu-id="40f34-139">**原因**：如果 " **agpm 服务器**" 选项卡上的设置不可用，则已使用管理模板对 agpm 服务器进行集中配置。</span><span class="sxs-lookup"><span data-stu-id="40f34-139">**Cause**: If the settings on the **AGPM Server** tab are unavailable, the AGPM Server has been centrally configured using an Administrative template.</span></span>

-   <span data-ttu-id="40f34-140">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="40f34-140">**Solution**:</span></span>

    -   <span data-ttu-id="40f34-141">如果您是 AGPM 管理员：如果 " **Agpm 服务器**" 选项卡上的设置不可用，请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-141">If you are an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

    -   <span data-ttu-id="40f34-142">如果您不是 AGPM 管理员：如果 " **Agpm 服务器**" 选项卡上的设置不可用，则不需要修改 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="40f34-142">If you are not an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, you do not need to modify the AGPM Server.</span></span>

### <a href="" id="bkmk-perform-task"></a><span data-ttu-id="40f34-143">我无法更改默认模板或查看、创建、编辑、重命名、部署或删除 Gpo</span><span class="sxs-lookup"><span data-stu-id="40f34-143">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>

-   <span data-ttu-id="40f34-144">**原因**：尚未向你分配执行任务所需权限的角色。</span><span class="sxs-lookup"><span data-stu-id="40f34-144">**Cause**: You have not been assigned a role with the permissions required to perform the task or tasks.</span></span>

-   <span data-ttu-id="40f34-145">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="40f34-145">**Solution**:</span></span>

    -   <span data-ttu-id="40f34-146">如果你是 AGPM 管理员：请参阅[委派域级别对存档的访问权限](delegate-domain-level-access-to-the-archive-agpm40.md)并[委派对存档中的单个 GPO 的访问权限](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-146">If you are an AGPM Administrator: See [Delegate Domain-Level Access to the Archive](delegate-domain-level-access-to-the-archive-agpm40.md) and [Delegate Access to an Individual GPO in the Archive](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md).</span></span> <span data-ttu-id="40f34-147">AGPM 权限将从域级联到当前存档中的所有 Gpo。</span><span class="sxs-lookup"><span data-stu-id="40f34-147">AGPM permissions will cascade from the domain to all GPOs currently in the archive.</span></span> <span data-ttu-id="40f34-148">有关哪些角色可以执行任务以及执行任务需要哪些权限的详细信息，请参阅该任务的帮助。</span><span class="sxs-lookup"><span data-stu-id="40f34-148">For details about which roles can perform a task and which permissions are necessary to perform a task, refer to the help for that task.</span></span>

    -   <span data-ttu-id="40f34-149">如果您不是 AGPM 管理员，并且您需要其他角色或权限：请与 AGPM 管理员联系以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="40f34-149">If you are not an AGPM Administrator and you require additional roles or permissions: Contact an AGPM Administrator for assistance.</span></span> <span data-ttu-id="40f34-150">请注意，如果你是编辑器，则可以开始创建 GPO、部署 GPO 或从域生产环境中删除 GPO 的过程，但审批者或 AGPM 管理员必须批准你的请求。</span><span class="sxs-lookup"><span data-stu-id="40f34-150">Be aware that if you are an Editor, you can begin the process of creating a GPO, deploying a GPO, or deleting a GPO from the production environment of the domain, but an Approver or AGPM Administrator must approve your request.</span></span>

### <a href="" id="bkmk-use-particular-name"></a><span data-ttu-id="40f34-151">我无法使用特定的 GPO 名称</span><span class="sxs-lookup"><span data-stu-id="40f34-151">I am unable to use a particular GPO name</span></span>

-   <span data-ttu-id="40f34-152">**原因**：该 gpo 名称已在使用或你无权列出该 gpo。</span><span class="sxs-lookup"><span data-stu-id="40f34-152">**Cause**: Either the GPO name is already in use or you lack permission to list the GPO.</span></span>

-   <span data-ttu-id="40f34-153">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="40f34-153">**Solution**:</span></span>

    -   <span data-ttu-id="40f34-154">如果 GPO 名称显示在 "**受控**"、"不**受控制**" 或 "**挂起**" 选项卡上，请选择其他名称。</span><span class="sxs-lookup"><span data-stu-id="40f34-154">If the GPO name appears on the **Controlled**, **Uncontrolled**, or **Pending** tab, choose another name.</span></span> <span data-ttu-id="40f34-155">如果部署的 GPO 已重命名但尚未重新部署，则它将在域生产环境中的旧名称下显示。</span><span class="sxs-lookup"><span data-stu-id="40f34-155">If a GPO that was deployed is renamed but not yet redeployed, it will be displayed under its old name in the production environment of the domain.</span></span> <span data-ttu-id="40f34-156">因此，仍在使用旧名称。</span><span class="sxs-lookup"><span data-stu-id="40f34-156">Therefore, the old name is still being used.</span></span> <span data-ttu-id="40f34-157">重新部署 GPO 以在生产环境中更新其名称，并释放该名称以供另一个 GPO 使用。</span><span class="sxs-lookup"><span data-stu-id="40f34-157">Redeploy the GPO to update its name in the production environment and release that name for use by another GPO.</span></span>

    -   <span data-ttu-id="40f34-158">如果 GPO 名称未显示在 "**受控**"、"不**受控制**" 或 "**挂起**" 选项卡上，则您可能无权列出该 gpo。</span><span class="sxs-lookup"><span data-stu-id="40f34-158">If the GPO name does not appear on the **Controlled**, **Uncontrolled**, or **Pending** tab, you may lack permission to list the GPO.</span></span> <span data-ttu-id="40f34-159">若要请求权限，请与 AGPM 管理员联系。</span><span class="sxs-lookup"><span data-stu-id="40f34-159">To request permission, contact an AGPM Administrator.</span></span>

### <a href="" id="bkmk-email"></a><span data-ttu-id="40f34-160">我没有收到 AGPM 电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="40f34-160">I am not receiving AGPM e-mail notifications</span></span>

-   <span data-ttu-id="40f34-161">**原因**：未提供有效的 SMTP 电子邮件服务器和电子邮件地址，或者没有执行生成电子邮件通知的操作。</span><span class="sxs-lookup"><span data-stu-id="40f34-161">**Cause**: A valid SMTP e-mail server and e-mail address has not been provided, or no action has been taken that generates an e-mail notification.</span></span>

-   <span data-ttu-id="40f34-162">**解决方案**：</span><span class="sxs-lookup"><span data-stu-id="40f34-162">**Solution**:</span></span>

    -   <span data-ttu-id="40f34-163">如果你是 AGPM 管理员：有关要通过 AGPM 发送的待执行操作的电子邮件通知，AGPM 管理员必须为 "**域委派**" 选项卡上的审批者提供有效的 SMTP 电子邮件服务器和电子邮件地址。有关详细信息，请参阅[配置电子邮件通知](configure-e-mail-notification-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-163">If you are an AGPM Administrator: For e-mail notifications about pending actions to be sent by AGPM, an AGPM Administrator must provide a valid SMTP e-mail server and e-mail addresses for Approvers on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm40.md).</span></span>

    -   <span data-ttu-id="40f34-164">仅当缺少创建、部署或删除 GPO 所需权限的编辑器、审阅者或其他组策略管理员提交这些操作之一的请求时，才会生成电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="40f34-164">E-mail notifications are generated only when an Editor, Reviewer, or other Group Policy administrator who lacks the permission necessary to create, deploy, or delete a GPO submits a request for one of those actions to occur.</span></span> <span data-ttu-id="40f34-165">没有自动通知或拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="40f34-165">There is no automatic notification of approval or rejection of a request.</span></span>

### <a href="" id="bkmk-port"></a><span data-ttu-id="40f34-166">我无法为 AGPM 服务使用端口4600</span><span class="sxs-lookup"><span data-stu-id="40f34-166">I cannot use port 4600 for the AGPM Service</span></span>

-   <span data-ttu-id="40f34-167">**原因**：默认情况下，AGPM 服务侦听的端口是端口4600。</span><span class="sxs-lookup"><span data-stu-id="40f34-167">**Cause**: By default, the port on which the AGPM Service listens is port 4600.</span></span>

-   <span data-ttu-id="40f34-168">**解决方案**：如果对于 agpm 服务，端口4600不可用，请修改 agpm 服务器上的端口配置以使用另一个端口，然后在 agpm 服务器连接中更新 Agpm 客户端的端口。</span><span class="sxs-lookup"><span data-stu-id="40f34-168">**Solution**: If port 4600 is not available for the AGPM Service, modify the port configuration on the AGPM Server to use another port and then update the port in the AGPM Server connection for AGPM Clients.</span></span> <span data-ttu-id="40f34-169">有关详细信息，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-169">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

### <a href="" id="bkmk-not-start"></a><span data-ttu-id="40f34-170">AGPM 服务将不会启动</span><span class="sxs-lookup"><span data-stu-id="40f34-170">The AGPM Service will not start</span></span>

-   <span data-ttu-id="40f34-171">**原因**：您在 "**管理工具**和**服务**" 下的操作系统中修改了 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="40f34-171">**Cause**: You have modified settings for the AGPM Service in the operating system under **Administrative Tools** and **Services**.</span></span>

-   <span data-ttu-id="40f34-172">**解决方案**：在 "控制面板" 的 "**程序和功能**" 下修改**Microsoft 高级组策略管理-服务器**的设置。</span><span class="sxs-lookup"><span data-stu-id="40f34-172">**Solution**: Modify the settings for **Microsoft Advanced Group Policy Management - Server** under **Programs and Features** in Control Panel.</span></span> <span data-ttu-id="40f34-173">有关详细信息，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-173">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

### <a href="" id="bkmk-software-installation"></a><span data-ttu-id="40f34-174">组策略软件安装无法安装软件</span><span class="sxs-lookup"><span data-stu-id="40f34-174">Group Policy Software Installation fails to install software</span></span>

-   <span data-ttu-id="40f34-175">**原因**： AGPM 保留组策略软件安装程序包的完整性。</span><span class="sxs-lookup"><span data-stu-id="40f34-175">**Cause**: AGPM preserves the integrity of Group Policy Software Installation packages.</span></span> <span data-ttu-id="40f34-176">尽管 Gpo 的编辑是脱机编辑的，但除了缓存的客户端信息外，程序包之间的链接也会保留。</span><span class="sxs-lookup"><span data-stu-id="40f34-176">Although GPOs are edited offline, links between packages in addition to cached client information are preserved.</span></span> <span data-ttu-id="40f34-177">这是设计使然。</span><span class="sxs-lookup"><span data-stu-id="40f34-177">This is by design.</span></span>

-   <span data-ttu-id="40f34-178">**解决方案**：使用 AGPM 脱机编辑 GPO 时，请将另一个 GPO 中的程序包的任意组策略软件安装升级配置为引用部署的 gpo，而不是签出的副本。</span><span class="sxs-lookup"><span data-stu-id="40f34-178">**Solution**: When you edit a GPO offline with AGPM, configure any Group Policy Software Installation upgrade of a package in another GPO to reference the deployed GPO, not the checked-out copy.</span></span> <span data-ttu-id="40f34-179">编辑器必须具有已部署 GPO 的**读取**权限。</span><span class="sxs-lookup"><span data-stu-id="40f34-179">The Editor must have **Read** permission for the deployed GPO.</span></span>

### <a href="" id="bkmk-error-on-restore"></a><span data-ttu-id="40f34-180">将存档还原到新的 AGPM 服务器时出错</span><span class="sxs-lookup"><span data-stu-id="40f34-180">An error occurred when I restored the archive to a new AGPM Server</span></span>

-   <span data-ttu-id="40f34-181">**原因**：出于安全考虑，如果将存档移动到另一台计算机，加密保护在 "**域委派**" 选项卡上输入的密码将导致密码失败。</span><span class="sxs-lookup"><span data-stu-id="40f34-181">**Cause**: For security reasons, the encryption protecting the password entered on the **Domain Delegation** tab causes the password to fail if the archive is moved to another computer.</span></span>

-   <span data-ttu-id="40f34-182">**解决方案**：重新输入并确认 "**域委派**" 选项卡上的密码。有关详细信息，请参阅[配置电子邮件通知](configure-e-mail-notification-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="40f34-182">**Solution**: Re-enter and confirm the password on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm40.md).</span></span>

 

 





