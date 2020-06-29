---
title: 规划 Sequencer 安全
description: 规划 Sequencer 安全
author: dansimp
ms.assetid: 8043cb02-476d-4c28-a850-903a8ac5b2d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf1e85e24d93d373add38b5efe51ceb40faae24e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798866"
---
# <span data-ttu-id="8ab8d-103">规划 Sequencer 安全</span><span class="sxs-lookup"><span data-stu-id="8ab8d-103">Planning for Sequencer Security</span></span>


<span data-ttu-id="8ab8d-104">配置应用程序虚拟化（app-v）时尽可能早地合并推荐实施做法，以使 Sequencer 实现正常运行并更安全。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-104">Incorporate recommended implementation practices as early as possible when configuring Application Virtualization (App-V) so that your Sequencer implementation is functional and more secure.</span></span> <span data-ttu-id="8ab8d-105">如果你已配置了排序器，请使用以下最佳做法指南来重新访问你的设计决策，并从安全角度分析这些决策。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-105">If you have already configured the Sequencer, use the following best-practice guidelines to revisit your design decisions and analyze them from a security perspective.</span></span>

**<span data-ttu-id="8ab8d-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="8ab8d-106">Important</span></span>**  
<span data-ttu-id="8ab8d-107">App-v Sequencer 将收集和部署运行 Sequencer 的计算机上记录的所有应用程序信息。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-107">The App-V Sequencer collects and deploys all application information recorded on the computer running the sequencer.</span></span> <span data-ttu-id="8ab8d-108">你应该确保访问运行 Sequencer 的计算机的所有用户都具有管理凭据。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-108">You should ensure that all users accessing the computer running the Sequencer have administrative credentials.</span></span> <span data-ttu-id="8ab8d-109">具有用户帐户凭据的用户不应具有控制程序包内容和程序包文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-109">Users with user account credentials should not have access to control package contents and package files.</span></span> <span data-ttu-id="8ab8d-110">如果你正在运行远程桌面服务（以前称为终端服务）的计算机上进行排序，请确保它是专用于序列化的计算机，并且在排序期间没有与用户帐户凭据连接的用户。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-110">If you are sequencing on a computer running Remote Desktop Services (formerly Terminal Services), make sure it is a computer that is dedicated to sequencing and that users with user account credentials are not connected to it during sequencing.</span></span>



## <span data-ttu-id="8ab8d-111">排序器安全最佳做法</span><span class="sxs-lookup"><span data-stu-id="8ab8d-111">Sequencer Security Best Practices</span></span>


<span data-ttu-id="8ab8d-112">在实现和使用 Application Virtualization （App-v） Sequencer 时，请考虑以下方案和相关的最佳做法：</span><span class="sxs-lookup"><span data-stu-id="8ab8d-112">Consider the following scenarios and the associated best practices when implementing and using the Application Virtualization (App-V) Sequencer:</span></span>

-   <span data-ttu-id="8ab8d-113">**在运行 sequencer 的计算机上进行病毒扫描**-建议扫描运行 sequencer 的计算机以查找病毒，然后在排序过程中禁用运行 sequencer 的计算机上的所有防病毒和恶意软件检测软件。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-113">**Virus scanning on the computer running the Sequencer**—It is recommended that you scan the computer running the Sequencer for viruses and then disable all antivirus and malware detection software on the computer running the Sequencer during the sequencing process.</span></span> <span data-ttu-id="8ab8d-114">这将加快排序过程，并防止防病毒软件组件和反恶意软件组件干扰排序过程。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-114">This will speed the sequencing process and prevent the antivirus and anti-malware software components from interfering with the sequencing process.</span></span> <span data-ttu-id="8ab8d-115">接下来在未运行 Sequencer 的计算机上安装序列化程序包，并且在成功安装后，扫描该计算机以查找病毒。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-115">Next install the sequenced package on a computer not running the Sequencer, and after successful installation, scan that computer for viruses.</span></span> <span data-ttu-id="8ab8d-116">如果发现病毒，则应联系软件制造商，通知他们受感染的源文件，并在没有病毒的情况下请求更新的安装源。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-116">If viruses are found, the manufacturer of the software should be contacted to inform them of the infected source files and request an updated installation source without viruses.</span></span> <span data-ttu-id="8ab8d-117">或者，可以在安装阶段后对 Sequencer 进行扫描，如果发现了病毒，请按照上述说明联系软件制造商。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-117">Optionally, the Sequencer could be scanned after the installation phase and if a virus is found, the software manufacturer should be contacted as mentioned above.</span></span>

    **<span data-ttu-id="8ab8d-118">注意</span><span class="sxs-lookup"><span data-stu-id="8ab8d-118">Note</span></span>**  
    <span data-ttu-id="8ab8d-119">如果在应用程序中检测到病毒，则不应将应用程序部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-119">If a virus is detected in an application, the application should not be deployed to target computers.</span></span>



-   <span data-ttu-id="8ab8d-120">**捕获 ntfs 文件上的访问控制列表（acl）**-app-v Sequencer 捕获在产品安装期间监视的文件的 NTFS 文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-120">**Capturing access control lists (ACLs) on NTFS files**—The App-V Sequencer captures NTFS file system permissions for the files that are monitored during the installation of the product.</span></span> <span data-ttu-id="8ab8d-121">此功能使你能够更准确地复制应用程序的预期行为，就像它是在本地安装且未虚拟化。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-121">This capability allows you to more accurately replicate the intended behavior of the application, as if it were installed locally and not virtualized.</span></span> <span data-ttu-id="8ab8d-122">在某些情况下，应用程序可能会存储用户不打算在应用程序文件中访问的信息。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-122">In some scenarios, an application might store information that users were not intended to access within the application files.</span></span> <span data-ttu-id="8ab8d-123">例如，应用程序可以将凭据信息存储在应用程序内的文件中。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-123">For example, an application could store credentials information in a file inside of the application.</span></span> <span data-ttu-id="8ab8d-124">如果在程序包上未强制使用 Acl，则用户有可能查看并在应用程序外部使用此信息。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-124">If ACLs are not enforced on the package, a user could potentially view and then use this information outside of the application.</span></span>

    **<span data-ttu-id="8ab8d-125">注意</span><span class="sxs-lookup"><span data-stu-id="8ab8d-125">Note</span></span>**  
    <span data-ttu-id="8ab8d-126">不应序列化存储未加密的特定于安全的信息（如密码等）的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-126">You should not sequence applications that store unencrypted security-specific information, such as passwords, and so on.</span></span>



~~~
During the installation phase, you can modify the default permissions of the files if necessary. After completion of the sequencing process, but before saving the package, you can choose whether to enforce security descriptors that were captured during the installation of the application. By default, App-V will enforce the security descriptors specified during the installation of the application. If you turn off security descriptor enforcement, you should test the application to ensure the removal of associated Access Control Lists (ACL) will not cause the application to perform unexpectedly.
~~~

-   <span data-ttu-id="8ab8d-127">**Sequencer 不捕获注册表 acl**，尽管 sequencer 会在序列化的安装阶段捕获 NTFS 文件系统 acl，但不会捕获注册表的 acl。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-127">**Sequencer doesn’t capture registry ACLs**—Although the Sequencer captures the NTFS file system ACLs during the installation phase of sequencing, it does not capture the ACLs for the registry.</span></span> <span data-ttu-id="8ab8d-128">用户将对虚拟应用程序（服务除外）的所有注册表项具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-128">Users will have full access to all registry keys for virtual applications except for services.</span></span> <span data-ttu-id="8ab8d-129">但是，如果用户修改了虚拟应用程序的注册表，则该更改将存储在特定的应用商店（**uservol _sftfs \ _v1**）中，并且不会影响其他用户。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-129">However, if a user modifies the registry of a virtual application, the change will be stored in a specific store (**uservol\_sftfs\_v1.pkg**) and will not affect other users.</span></span>

-   <span data-ttu-id="8ab8d-130">**应用程序服务**-V 为属于虚拟化应用程序的应用程序服务提供支持。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-130">**Application services**—App-V provides support for application services that are part of a virtualized application.</span></span> <span data-ttu-id="8ab8d-131">但是，在虚拟环境中，其运行的安全上下文将受到限制。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-131">However, in the virtual environment, the security context that they will run as is limited.</span></span> <span data-ttu-id="8ab8d-132">虚拟环境中唯一支持的安全上下文是本地系统、本地服务和网络服务。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-132">The only security contexts supported in a virtual environment are Local System, Local Service, and Network Service.</span></span> <span data-ttu-id="8ab8d-133">在排序期间，如果为除支持的三个应用程序服务指定了安全上下文，则会在虚拟环境中应用本地系统安全上下文。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-133">During sequencing, if a security context is specified for an application service other than the three supported, the Local System security context will be applied in the virtual environment.</span></span> <span data-ttu-id="8ab8d-134">如果将应用程序服务配置为使用本地服务或网络服务，它将在虚拟环境中生效。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-134">If the application service is configured to use either Local Service or Network Service, it will be honored in the virtual environment.</span></span> <span data-ttu-id="8ab8d-135">在排序过程中，可以使用这三种安全上下文来配置服务帐户。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-135">Configuring the service account can be done during the sequencing process using these three security contexts.</span></span>

-   <span data-ttu-id="8ab8d-136">**保留的安全信息**-当排序应用程序时，你可以作为用户安装应用程序，也可以开发自动方法来在监视时安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-136">**Persisted security information**—When sequencing applications, you can install the application as a user would or you can develop an automated method for installing the application while being monitored.</span></span> <span data-ttu-id="8ab8d-137">未从程序包中排除的所有内容将作为该程序包的一部分捕获，因此应用程序将具有在虚拟化环境中运行所需的资源。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-137">Everything that is not being excluded from the package will be captured as part of that package so that the application will have the necessary assets to run in a virtualized environment.</span></span> <span data-ttu-id="8ab8d-138">某些应用程序在安装期间存储敏感的安全信息（如密码）;如果保持不受保护，则其他用户可以访问此安全信息，这些用户有权访问程序包。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-138">Some applications store sensitive security information (such as passwords) during the installation; if persisted unprotected, this security information could be accessed by other users with access to the package.</span></span> <span data-ttu-id="8ab8d-139">在安装过程中，如果应用程序安装要求输入密码或其他安全敏感信息，请查看文档以确保它不会保留（安装后删除），或者，如果已保留，则它将受到保护（已加密）。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-139">During installation, if an application installation asks for a password or other security-sensitive information, check with the documentation to ensure that it is either not persisted (removed after installation) or, if persisted, that it is protected (encrypted).</span></span>

-   <span data-ttu-id="8ab8d-140">**保护虚拟应用程序包**的安全-始终将虚拟应用程序包保存在网络上的安全位置，以防止程序包被篡改或损坏。</span><span class="sxs-lookup"><span data-stu-id="8ab8d-140">**Securing virtual application packages**—Always save virtual application packages in a secure location on the network to protect the package from being tampered with or corrupted.</span></span>

## <span data-ttu-id="8ab8d-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="8ab8d-141">Related topics</span></span>


[<span data-ttu-id="8ab8d-142">规划安全和保护</span><span class="sxs-lookup"><span data-stu-id="8ab8d-142">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)









