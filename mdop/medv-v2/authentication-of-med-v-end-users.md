---
title: MED-V 最终用户的身份验证
description: MED-V 最终用户的身份验证
author: dansimp
ms.assetid: aaf96eb6-91d1-4f4d-9854-5fc73c7ae7ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14c1e95a94f2da76b6b6c5ebd9d4cf14dcf839a7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803658"
---
# <span data-ttu-id="3bebb-103">MED-V 最终用户的身份验证</span><span class="sxs-lookup"><span data-stu-id="3bebb-103">Authentication of MED-V End Users</span></span>


<span data-ttu-id="3bebb-104">Microsoft 企业桌面虚拟化（MED-V）2.0 最终用户的身份验证是非常重要的安全问题。</span><span class="sxs-lookup"><span data-stu-id="3bebb-104">The authentication of Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 end users is a very important security issue.</span></span> <span data-ttu-id="3bebb-105">在此上下文中，身份验证指验证 MED-V 最终用户的身份。</span><span class="sxs-lookup"><span data-stu-id="3bebb-105">In this context, authentication refers to verifying the identity of the MED-V end user.</span></span>

<span data-ttu-id="3bebb-106">下一节提供了有关在 MED-V 中最终用户身份验证的信息和指南。</span><span class="sxs-lookup"><span data-stu-id="3bebb-106">The following section provides information and guidance about end-user authentication in MED-V.</span></span>

## <span data-ttu-id="3bebb-107">MED-V 中的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="3bebb-107">User Authentication in MED-V</span></span>


<span data-ttu-id="3bebb-108">MED-V 中的身份验证通常出现在两个级别上：当用户首次访问 MED-V 和每次更改其密码时。</span><span class="sxs-lookup"><span data-stu-id="3bebb-108">Authentication in MED-V generally occurs at two levels: when a user first accesses MED-V and every time that they change their password.</span></span>

<span data-ttu-id="3bebb-109">根据你配置身份验证的 MED-V 设置的方式，通常会在某一点提示最终用户输入其密码，即启动 MED-V 时首次启动或首次尝试打开已发布的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bebb-109">Depending on how you have configured MED-V settings for authentication, the end user is typically prompted at some point to enter their password, either the first time MED-V is started or the first time that they try to open a published application.</span></span>

<span data-ttu-id="3bebb-110">最终用户身份验证有多个方面可供你控制，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="3bebb-110">There are several aspects of end-user authentication that you can control, including the following:</span></span>

<span data-ttu-id="3bebb-111">最终用户输入的凭据是否存储在凭据管理器中</span><span class="sxs-lookup"><span data-stu-id="3bebb-111">Whether the credentials the end user enters are stored in Credential Manager</span></span>

<span data-ttu-id="3bebb-112">最终用户的显示方式，提供了输入和保存密码的选项</span><span class="sxs-lookup"><span data-stu-id="3bebb-112">In what manner the end user is presented with the option of entering and saving their password</span></span>

<span data-ttu-id="3bebb-113">根据贵公司用于管理最终用户身份验证的首选过程，你可以指定特定的 MED-V 工作区是否进行凭据缓存。</span><span class="sxs-lookup"><span data-stu-id="3bebb-113">Depending on your company’s preferred process for managing end-user authentication, you can specify whether credential caching occurs for a particular MED-V workspace.</span></span> <span data-ttu-id="3bebb-114">缓存最终用户的凭据非常有用，因为它们只会提示一次用于其密码。</span><span class="sxs-lookup"><span data-stu-id="3bebb-114">Caching the credentials of an end user is helpful because they are only prompted one time for their password.</span></span> <span data-ttu-id="3bebb-115">如果最终用户每次启动新的 MED-V 会话时都不允许保存其密码，则他们必须再次输入它。</span><span class="sxs-lookup"><span data-stu-id="3bebb-115">If the end user is not allowed to save their password or they decide not to, every time that they start a new MED-V session, they must enter it again.</span></span> <span data-ttu-id="3bebb-116">例如，如果将 MED-V 配置为当最终用户登录到主机但禁用身份验证时启动，则仅在登录期间提示最终用户一次。</span><span class="sxs-lookup"><span data-stu-id="3bebb-116">For example, if MED-V is configured to start when the end user logs on to the host but Authentication is disabled, the end user is only prompted one time during logon.</span></span> <span data-ttu-id="3bebb-117">在这种情况下，凭据将有效，直到最终用户从主持人注销。</span><span class="sxs-lookup"><span data-stu-id="3bebb-117">In this case, credentials are valid until the end user logs off from the host.</span></span>

<span data-ttu-id="3bebb-118">如果需要，您可以使用 "凭据管理器" 删除任何存储的最终用户凭据。</span><span class="sxs-lookup"><span data-stu-id="3bebb-118">If it is necessary, you can use Credential Manager to remove any stored end-user credentials.</span></span>

<span data-ttu-id="3bebb-119">默认情况下，凭据存储已禁用，但你可以通过以下方法之一更改此设置：</span><span class="sxs-lookup"><span data-stu-id="3bebb-119">By default, credential storing is disabled, but you can change this setting through one of the following methods:</span></span>

<span data-ttu-id="3bebb-120">**创建 med-v 工作区程序包时**。</span><span class="sxs-lookup"><span data-stu-id="3bebb-120">**While you are creating the MED-V workspace package**.</span></span> <span data-ttu-id="3bebb-121">有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="3bebb-121">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

<span data-ttu-id="3bebb-122">**部署 med-v 工作区后**。</span><span class="sxs-lookup"><span data-stu-id="3bebb-122">**After you have deployed the MED-V workspace**.</span></span> <span data-ttu-id="3bebb-123">编辑 MED-V cmdlet 参数 UxCredentialCacheEnabled 以设置终端服务注册表项。</span><span class="sxs-lookup"><span data-stu-id="3bebb-123">Edit the MED-V cmdlet parameter UxCredentialCacheEnabled to set the Terminal Services registry key.</span></span> <span data-ttu-id="3bebb-124">有关详细信息，请参阅 Windows PowerShell 帮助。</span><span class="sxs-lookup"><span data-stu-id="3bebb-124">For more information, see Windows PowerShell Help.</span></span>

<span data-ttu-id="3bebb-125">在 MED-V 工作区部署之后，你可以通过修改名为 DisablePasswordSaving 的终端服务策略来设置最终用户身份验证的首选项。</span><span class="sxs-lookup"><span data-stu-id="3bebb-125">After MED-V workspace deployment, you can set your preference for end-user authentication by modifying the Terminal Services policy named DisablePasswordSaving.</span></span> <span data-ttu-id="3bebb-126">DisablePasswordSaving 控制是否在 RDP 客户端对话框窗口中显示 "密码保存" 复选框，以及是否显示 MED-V 凭据提示。</span><span class="sxs-lookup"><span data-stu-id="3bebb-126">DisablePasswordSaving controls whether the password saving check box appears on the RDP client dialog window and whether the MED-V credential prompt is displayed.</span></span>

<span data-ttu-id="3bebb-127">以下是名为 DisablePasswordSaving 的终端服务策略的策略路径。</span><span class="sxs-lookup"><span data-stu-id="3bebb-127">Following is the policy path for the Terminal Services policy named DisablePasswordSaving.</span></span>

**<span data-ttu-id="3bebb-128">Regedit.exe</span><span class="sxs-lookup"><span data-stu-id="3bebb-128">Regedit:</span></span>**

<span data-ttu-id="3bebb-129">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Virtual Machine\\Policies\\DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="3bebb-129">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Virtual Machine\\Policies\\DisablePasswordSaving</span></span>

**<span data-ttu-id="3bebb-130">注意</span><span class="sxs-lookup"><span data-stu-id="3bebb-130">Note</span></span>**  
<span data-ttu-id="3bebb-131">对 DisablePasswordSaving 所做的更改仅会影响到虚拟机的 RDP 提示。</span><span class="sxs-lookup"><span data-stu-id="3bebb-131">The changes that you make to DisablePasswordSaving only affect the RDP prompt to a virtual machine.</span></span>



<span data-ttu-id="3bebb-132">下表列出了可用于配置凭据存储和不同配置的效果的不同方法：</span><span class="sxs-lookup"><span data-stu-id="3bebb-132">The following table lists the different ways you can configure your settings for credential storing and the effects of the different configurations:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3bebb-133">值</span><span class="sxs-lookup"><span data-stu-id="3bebb-133">Value</span></span></th>
<th align="left"><span data-ttu-id="3bebb-134">配置</span><span class="sxs-lookup"><span data-stu-id="3bebb-134">Configuration</span></span></th>
<th align="left"><span data-ttu-id="3bebb-135">结果</span><span class="sxs-lookup"><span data-stu-id="3bebb-135">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bebb-136">DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="3bebb-136">DisablePasswordSaving</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3bebb-137">禁用</span><span class="sxs-lookup"><span data-stu-id="3bebb-137">Disabled</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3bebb-138">将显示 "MED-V" 提示，并清除 "接受" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3bebb-138">The MED-V prompt is presented and a check box to accept is available and cleared.</span></span> <span data-ttu-id="3bebb-139">如果最终用户选中该复选框，则将缓存凭据以供以后使用。</span><span class="sxs-lookup"><span data-stu-id="3bebb-139">If the end user selects the check box, credentials are cached for subsequent use.</span></span> <span data-ttu-id="3bebb-140">最终用户还具有仅在密码过期时收到提示的好处。</span><span class="sxs-lookup"><span data-stu-id="3bebb-140">The end user also has the benefit of only being prompted when the password expires.</span></span></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3bebb-141">如果最终用户未选中此复选框，则会显示远程桌面连接（RDC）客户端提示，而不是 MED-V 提示，并且清除 "接受" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3bebb-141">If the end user does not select the check box, the Remote Desktop Connection (RDC) Client prompt is presented instead of the MED-V prompt, and the check box to accept is cleared.</span></span> <span data-ttu-id="3bebb-142">如果最终用户选中该复选框，则将存储 RDC 客户端凭据以供以后使用。</span><span class="sxs-lookup"><span data-stu-id="3bebb-142">If the end user selects the check box, the RDC Client credential is stored for later use.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="3bebb-143">重要提示</span><span class="sxs-lookup"><span data-stu-id="3bebb-143">Important</span></span></strong><br/><p><span data-ttu-id="3bebb-144">当最终用户输入凭据时，RDC 不会验证凭据。</span><span class="sxs-lookup"><span data-stu-id="3bebb-144">RDC does not validate credentials when the end user enters them.</span></span> <span data-ttu-id="3bebb-145">如果最终用户通过 RDC 提示缓存凭据，则可能会有可能存储凭据错误的风险。</span><span class="sxs-lookup"><span data-stu-id="3bebb-145">If the end user caches the credentials through the RDC prompt, there is a risk that incorrect credentials might be stored.</span></span> <span data-ttu-id="3bebb-146">在这种情况下，必须在 Windows 凭据管理器中删除不正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="3bebb-146">In this case, the incorrect credentials must be deleted in the Windows Credential Manager.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bebb-147">DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="3bebb-147">DisablePasswordSaving</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="3bebb-148">启用</span><span class="sxs-lookup"><span data-stu-id="3bebb-148">Enabled</span></span></strong></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="3bebb-149">注意</span><span class="sxs-lookup"><span data-stu-id="3bebb-149">Note</span></span></strong><br/><p><span data-ttu-id="3bebb-150">此配置更安全，因为它不允许缓存最终用户凭据。</span><span class="sxs-lookup"><span data-stu-id="3bebb-150">This configuration is more secure because it does not allow end user credentials to be cached.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="3bebb-151">默认情况下，MED-V 安装会在来宾中设置一个注册表项，以取消 "密码过期" 提示。</span><span class="sxs-lookup"><span data-stu-id="3bebb-151">By default, the MED-V installation sets a registry key in the guest to suppress the "password about to expire" prompt.</span></span> <span data-ttu-id="3bebb-152">最终用户仅提示在主机上更改密码。</span><span class="sxs-lookup"><span data-stu-id="3bebb-152">The end user is only prompted for a password change on the host.</span></span> <span data-ttu-id="3bebb-153">在主机上更新的凭据将传递给来宾。</span><span class="sxs-lookup"><span data-stu-id="3bebb-153">Credentials that are updated on the host are passed to the guest.</span></span>

**<span data-ttu-id="3bebb-154">注意</span><span class="sxs-lookup"><span data-stu-id="3bebb-154">Caution</span></span>**  
<span data-ttu-id="3bebb-155">如果你在你的环境中使用组策略，请知道它可以替代注册表项，从而导致来自来宾的密码提示再次出现。</span><span class="sxs-lookup"><span data-stu-id="3bebb-155">If you use Group Policy in your environment, know that it can override the registry key causing the password prompts from the guest to reappear.</span></span>



### <span data-ttu-id="3bebb-156">身份验证的安全问题</span><span class="sxs-lookup"><span data-stu-id="3bebb-156">Security Concerns with Authentication</span></span>

<span data-ttu-id="3bebb-157">即使缓存最终用户的凭据可提供最佳用户体验，你也必须了解所涉及的风险。</span><span class="sxs-lookup"><span data-stu-id="3bebb-157">Even though caching the end user’s credentials provides the best user experience, you must be aware of the risks involved.</span></span>

<span data-ttu-id="3bebb-158">启用凭据缓存后，最终用户的域凭据将以一种可还原的格式存储在 Windows 凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="3bebb-158">When credential caching is enabled, the end user’s domain credential is stored in a reversible format within the Windows Credential Manager.</span></span> <span data-ttu-id="3bebb-159">因此，攻击者可以编写作为系统级进程或最终用户进程运行的工具，并检索最终用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="3bebb-159">As a result, an attacker could write a tool that runs as either a system level process or an end user process and that retrieves the end user's credentials.</span></span> <span data-ttu-id="3bebb-160">您只能通过将 DisablePasswordSaving 设置为 "**启用**" 来减少此风险。</span><span class="sxs-lookup"><span data-stu-id="3bebb-160">You can only lessen this risk by setting DisablePasswordSaving to **Enabled**.</span></span>

<span data-ttu-id="3bebb-161">如果禁用了 MED-V 身份验证，但 "终端服务" 策略设置处于启用状态，则存在同样的问题。</span><span class="sxs-lookup"><span data-stu-id="3bebb-161">This same concern exists when MED-V authentication is disabled but the Terminal Services policy setting is enabled.</span></span>

## <span data-ttu-id="3bebb-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="3bebb-162">Related topics</span></span>


[<span data-ttu-id="3bebb-163">MED-V 操作的安全最佳方案</span><span class="sxs-lookup"><span data-stu-id="3bebb-163">Security Best Practices for MED-V Operations</span></span>](security-best-practices-for-med-v-operations.md)









