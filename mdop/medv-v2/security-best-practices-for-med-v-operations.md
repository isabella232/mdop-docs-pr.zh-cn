---
title: MED-V 操作的安全最佳方案
description: MED-V 操作的安全最佳方案
author: dansimp
ms.assetid: 231e2b9a-8b49-42fe-93b5-2ef12fe17bac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4353a15c756dba8cf44f530c2077546e3f9288cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803760"
---
# <span data-ttu-id="72dd3-103">MED-V 操作的安全最佳方案</span><span class="sxs-lookup"><span data-stu-id="72dd3-103">Security Best Practices for MED-V Operations</span></span>


<span data-ttu-id="72dd3-104">作为授权的管理员，您负责保护用户的信息，并在部署 MED-V 工作区期间和之后维护组织的安全。</span><span class="sxs-lookup"><span data-stu-id="72dd3-104">As an authorized administrator, you are responsible to protect the information of the users and maintain security of your organization during and after the deployment of MED-V workspaces.</span></span> <span data-ttu-id="72dd3-105">特别是，请考虑以下问题。</span><span class="sxs-lookup"><span data-stu-id="72dd3-105">In particular, consider the following issues.</span></span>

<span data-ttu-id="72dd3-106">**在 med-v 工作区中自定义 Internet Explorer**。</span><span class="sxs-lookup"><span data-stu-id="72dd3-106">**Customizing Internet Explorer in the MED-V workspace**.</span></span> <span data-ttu-id="72dd3-107">较早版本的 Windows 操作系统和 Internet Explorer 不如当前版本安全。</span><span class="sxs-lookup"><span data-stu-id="72dd3-107">Earlier versions of the Windows operating system and of Internet Explorer are not as secure as current versions.</span></span> <span data-ttu-id="72dd3-108">因此，MED-V 工作区中的 Internet Explorer 配置为阻止浏览和其他可能带来安全风险的活动。</span><span class="sxs-lookup"><span data-stu-id="72dd3-108">Therefore, Internet Explorer in the MED-V workspace is configured to prevent browsing and other activities that can pose security risks.</span></span> <span data-ttu-id="72dd3-109">此外，MED-V 工作区中 Internet Explorer 的 Internet 安全区域设置将设置为最高级别。</span><span class="sxs-lookup"><span data-stu-id="72dd3-109">In addition, the Internet security zone setting for Internet Explorer in the MED-V workspace is set to the highest level.</span></span> <span data-ttu-id="72dd3-110">默认情况下，当你创建 MED-V 工作区程序包时，将在 MED-V 工作区包装器中设置这两个配置。</span><span class="sxs-lookup"><span data-stu-id="72dd3-110">By default, both of these configurations are set in the MED-V Workspace Packager when you create your MED-V workspace package.</span></span>

<span data-ttu-id="72dd3-111">通过使用 Internet Explorer 管理工具包（IEAK）或通过更改 MED-V 工作区包装程序中的默认设置，你可以在 MED-V 工作区中自定义 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="72dd3-111">By using Internet Explorer Administration Kit (IEAK) or by changing the defaults in the MED-V Workspace Packager, you can customize Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="72dd3-112">但是，请注意，如果在 MED-V 工作区中自定义 Internet Explorer 的方式使其不太安全，则可以将组织暴露给较早版本的 Internet Explorer 中提供的安全风险。</span><span class="sxs-lookup"><span data-stu-id="72dd3-112">However, realize that if you customize Internet Explorer in the MED-V workspace in such a way as to make it less secure, you can expose your organization to those security risks that are present in older versions of Internet Explorer.</span></span>

<span data-ttu-id="72dd3-113">从安全角度来看，在 MED-V 工作区中管理 Internet Explorer 的最佳做法如下所示：</span><span class="sxs-lookup"><span data-stu-id="72dd3-113">From a security perspective, best practices for managing Internet Explorer in the MED-V workspace are as follows:</span></span>

-   <span data-ttu-id="72dd3-114">创建 MED-V 工作区程序包时，保留默认设置，以便将 MED-V 工作区中的 Internet Explorer 配置为阻止浏览和其他可能带来安全风险的活动。</span><span class="sxs-lookup"><span data-stu-id="72dd3-114">When creating your MED-V workspace package, leave the defaults set so that Internet Explorer in the MED-V workspace is configured to prevent browsing and other activities that can pose security risks.</span></span>

-   <span data-ttu-id="72dd3-115">创建 MED-V 工作区程序包时，保留默认设置，以便 Internet 安全区域的安全设置保持在最高级别。</span><span class="sxs-lookup"><span data-stu-id="72dd3-115">When creating your MED-V workspace package, leave the defaults set so that the security setting for the Internet security zone remains at the highest level.</span></span>

-   <span data-ttu-id="72dd3-116">配置企业代理或 Internet Explorer 内容顾问以阻止位于公司 intranet 外部的域。</span><span class="sxs-lookup"><span data-stu-id="72dd3-116">Configure your enterprise proxy or Internet Explorer Content Advisor to block domains that are outside your company’s intranet.</span></span>

**<span data-ttu-id="72dd3-117">为共享计算机上的所有用户配置 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="72dd3-117">Configuring a MED-V workspace for all users on a shared computer.</span></span>** <span data-ttu-id="72dd3-118">将 MED-V 工作区配置为可供共享计算机上的所有用户访问时，请注意将来宾虚拟机（VHD）放入一个位置，该位置将向该系统上的所有用户提供读写访问权限。</span><span class="sxs-lookup"><span data-stu-id="72dd3-118">When configuring a MED-V workspace so that it can be accessed by all users on a shared computer, realize that the guest virtual machine (VHD) is put in a location that gives Read and Write access to all users on that system.</span></span>

**<span data-ttu-id="72dd3-119">配置用于加入域的代理帐户。</span><span class="sxs-lookup"><span data-stu-id="72dd3-119">Configuring a proxy account for domain joining.</span></span>** <span data-ttu-id="72dd3-120">配置用于将虚拟机加入域的代理帐户时，必须知道最终用户可以获取代理帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="72dd3-120">When configuring a proxy account for joining virtual machines to the domain, you must know that it is possible for an end user to obtain the proxy account credentials.</span></span> <span data-ttu-id="72dd3-121">因此，必须采取必要的预防措施（如限制帐户用户权限），以防止最终用户使用凭据造成危害。</span><span class="sxs-lookup"><span data-stu-id="72dd3-121">Thus, necessary precautions must be taken, such as limiting account user rights, to prevent an end user from using the credentials for causing harm.</span></span>

**<span data-ttu-id="72dd3-122">Sysprep 配置。</span><span class="sxs-lookup"><span data-stu-id="72dd3-122">Sysprep Configuration.</span></span>** <span data-ttu-id="72dd3-123">尽管 Sysprep.inf 文件在默认情况下已加密，但其内容可由任何已确定的最终用户（可成功登录到虚拟机）进行解密和读取。</span><span class="sxs-lookup"><span data-stu-id="72dd3-123">Although the Sysprep.inf file is encrypted by default, its contents can be decrypted and read by any determined end user who can successfully log on to the virtual machine.</span></span> <span data-ttu-id="72dd3-124">这将引发安全问题，因为除了 Windows 产品密钥之外，Sysprep.inf 文件还可以包含凭据。</span><span class="sxs-lookup"><span data-stu-id="72dd3-124">This raises security concerns because the Sysprep.inf file can contain credentials in addition to a Windows product key.</span></span>

<span data-ttu-id="72dd3-125">你可以通过设置受限帐户将虚拟机加入域并在配置 Sysprep 时指定该帐户的凭据来减少此风险。</span><span class="sxs-lookup"><span data-stu-id="72dd3-125">You can lessen this risk by setting up a limited account for joining virtual machines to the domain and specifying the credentials for that account when configuring Sysprep.</span></span> <span data-ttu-id="72dd3-126">或者，你也可以配置 Sysprep 和首次设置以在**参与**模式下运行，并要求最终用户提供其凭据以将虚拟机加入到域。</span><span class="sxs-lookup"><span data-stu-id="72dd3-126">Alternately, you can also configure Sysprep and first time setup to run in **Attended** mode and require end users to provide their credentials for joining the virtual machine to the domain.</span></span>

<span data-ttu-id="72dd3-127">MED-V 最佳做法是指定在通过远程桌面连接（RDC）客户端通过远程桌面连接（RDC）客户端连接到来宾的帐户下运行 FtsCompletion.exe。</span><span class="sxs-lookup"><span data-stu-id="72dd3-127">A MED-V best practice is to specify that FtsCompletion.exe is run under an account that gives the end user rights to connect to the guest through the Remote Desktop Connection (RDC) Client.</span></span>

**<span data-ttu-id="72dd3-128">最终用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="72dd3-128">End-user authentication.</span></span>** <span data-ttu-id="72dd3-129">启用最终用户凭据的缓存可提供 MED-V 的最佳用户体验，但会带来可能会导致某人获得对最终用户凭据的访问权限的可能性。</span><span class="sxs-lookup"><span data-stu-id="72dd3-129">Enabling the caching of end-user credentials provides the best user experience of MED-V, but creates the potential that someone could gain access to the end user’s credentials.</span></span> <span data-ttu-id="72dd3-130">减少这种风险的唯一方法是在不存储最终用户凭据的**Med-v 工作区包装**上指定。</span><span class="sxs-lookup"><span data-stu-id="72dd3-130">The only way to lessen this risk is by specifying on the **MED-V Workspace Packager** that end-user credentials are not stored.</span></span> <span data-ttu-id="72dd3-131">有关最终用户身份验证的详细信息，请参阅[Med-v 最终用户的身份验证](authentication-of-med-v-end-users.md)。</span><span class="sxs-lookup"><span data-stu-id="72dd3-131">For more information about authentication of end users, see [Authentication of MED-V End Users](authentication-of-med-v-end-users.md).</span></span>

## <span data-ttu-id="72dd3-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="72dd3-132">Related topics</span></span>


[<span data-ttu-id="72dd3-133">操作疑难解答</span><span class="sxs-lookup"><span data-stu-id="72dd3-133">Operations Troubleshooting</span></span>](operations-troubleshooting-medv2.md)

[<span data-ttu-id="72dd3-134">Microsoft 企业版桌面虚拟化2。0</span><span class="sxs-lookup"><span data-stu-id="72dd3-134">Microsoft Enterprise Desktop Virtualization 2.0</span></span>](index.md)

 

 





