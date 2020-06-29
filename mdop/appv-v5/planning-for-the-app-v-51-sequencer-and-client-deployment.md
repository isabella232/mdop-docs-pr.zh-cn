---
title: 计划 App-V 5.1 Sequencer 和 Client 部署
description: 计划 App-V 5.1 Sequencer 和 Client 部署
author: dansimp
ms.assetid: d92f8773-fa7d-4926-978a-433978f91202
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 31a0296814b16ba1c776dca522423fc7b6b6ed96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798301"
---
# <span data-ttu-id="d7e6f-103">计划 App-V 5.1 Sequencer 和 Client 部署</span><span class="sxs-lookup"><span data-stu-id="d7e6f-103">Planning for the App-V 5.1 Sequencer and Client Deployment</span></span>


<span data-ttu-id="d7e6f-104">在开始使用 Microsoft Application Virtualization （App-v）5.1 之前，必须安装 app-v 5.1 sequencer、app-v 5.1 客户端以及可选的 App-v 5.1 共享内容存储。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-104">Before you can start to use Microsoft Application Virtualization (App-V) 5.1, you must install the App-V 5.1 sequencer, the App-V 5.1 client, and optionally the App-V 5.1 shared content store.</span></span> <span data-ttu-id="d7e6f-105">以下各节将介绍这些安装的规划。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-105">The following sections address planning for these installations.</span></span>

## <span data-ttu-id="d7e6f-106">规划 app-v 5.1 sequencer 部署</span><span class="sxs-lookup"><span data-stu-id="d7e6f-106">Planning for App-V 5.1 sequencer deployment</span></span>


<span data-ttu-id="d7e6f-107">App-v 5.1 使用名为 "先后顺序" 的进程创建虚拟化的应用程序和应用程序包。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-107">App-V 5.1 uses a process called sequencing to create virtualized applications and application packages.</span></span> <span data-ttu-id="d7e6f-108">排序需要使用运行 app-v 5.1 sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-108">Sequencing requires the use of a computer that runs the App-V 5.1 sequencer.</span></span>

<span data-ttu-id="d7e6f-109">**注意** 有关 app-v 5.1 sequencer 的新功能的信息，请参阅[关于 app-V 5.1](about-app-v-51.md)的**sequencer 改进**部分。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-109">**Note** For information about the new functionality of App-V 5.1 sequencer, see the **Sequencer Improvements** section of [About App-V 5.1](about-app-v-51.md).</span></span>

 

<span data-ttu-id="d7e6f-110">运行 app-v 5.1 sequencer 的计算机必须满足最低系统要求。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-110">The computer that runs the App-V 5.1 sequencer must meet the minimum system requirements.</span></span> <span data-ttu-id="d7e6f-111">有关这些要求的列表，请参阅[App-V 5.1 支持的配置](app-v-51-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-111">For a list of these requirements, see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="d7e6f-112">理想情况下，应在作为虚拟机运行的计算机上安装 sequencer。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-112">Ideally, you should install the sequencer on a computer running as a virtual machine.</span></span> <span data-ttu-id="d7e6f-113">这使你能够更轻松地将运行 sequencer 的计算机还原为 "干净" 状态，然后再对其他应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-113">This enables you to more easily revert the computer running the sequencer to a “clean” state before sequencing another application.</span></span> <span data-ttu-id="d7e6f-114">使用虚拟机安装 sequencer 时，应执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d7e6f-114">When you install the sequencer using a virtual machine, you should perform the following steps:</span></span>

1.  <span data-ttu-id="d7e6f-115">安装所有关联的 sequencer 先决条件。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-115">Install all associated sequencer prerequisites.</span></span>

2.  <span data-ttu-id="d7e6f-116">安装 sequencer。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-116">Install the sequencer.</span></span>

3.  <span data-ttu-id="d7e6f-117">获取环境的 "快照"。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-117">Take a “snapshot” of the environment.</span></span>

<span data-ttu-id="d7e6f-118">**重要提示** 您应让您的公司安全小组查看和批准排序过程计划。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-118">**Important** You should have your corporate security team review and approve the sequencing process plan.</span></span> <span data-ttu-id="d7e6f-119">出于安全考虑，应将 sequencer 操作保留在与生产环境分开的实验中。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-119">For security reasons, you should keep the sequencer operations in a lab that is separate from the production environment.</span></span> <span data-ttu-id="d7e6f-120">根据您的业务要求，分色排列可以简单，也可以在必要时全面。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-120">The separation arrangement can be as simple or as comprehensive as necessary, based on your business requirements.</span></span> <span data-ttu-id="d7e6f-121">排序计算机必须能够连接到企业网络才能将完成的程序包复制到生产服务器。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-121">The sequencing computers must be able to connect to the corporate network to copy finished packages to the production servers.</span></span> <span data-ttu-id="d7e6f-122">但是，由于先后顺序计算机通常在没有防病毒保护的情况下运行，因此它们不能在未受保护的企业网络上。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-122">However, because the sequencing computers are typically operated without antivirus protection, they must not be on the corporate network unprotected.</span></span> <span data-ttu-id="d7e6f-123">例如，你可能能够在防火墙后或在隔离的网段上操作。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-123">For example, you might be able to operate behind a firewall or on an isolated network segment.</span></span> <span data-ttu-id="d7e6f-124">你还可以使用配置为共享隔离虚拟网络的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-124">You might also be able to use virtual machines that are configured to share an isolated virtual network.</span></span> <span data-ttu-id="d7e6f-125">按照您的公司安全策略来安全地解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-125">Follow your corporate security policies to safely address these concerns.</span></span>

 

## <span data-ttu-id="d7e6f-126">规划 app-v 5.1 客户端部署</span><span class="sxs-lookup"><span data-stu-id="d7e6f-126">Planning for App-V 5.1 client deployment</span></span>


<span data-ttu-id="d7e6f-127">若要在目标计算机上运行虚拟化程序包，必须在目标计算机上安装 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-127">To run virtualized packages on target computers, you must install the App-V 5.1 client on the target computers.</span></span> <span data-ttu-id="d7e6f-128">App-v 5.1 客户端是在目标计算机上运行虚拟化应用程序的组件。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-128">The App-V 5.1 client is the component that runs a virtualized application on a target computer.</span></span> <span data-ttu-id="d7e6f-129">客户端使用户能够与图标和特定文件类型交互，以启动虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-129">The client enables users to interact with icons and specific file types to start virtualized applications.</span></span> <span data-ttu-id="d7e6f-130">客户端还有助于从管理服务器获取应用程序内容，并在客户端启动应用程序之前缓存内容。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-130">The client also helps obtain application content from the management server and caches the content before the client starts the application.</span></span> <span data-ttu-id="d7e6f-131">有两种不同的客户端类型：远程桌面服务的客户端，用于远程桌面会话主机（RD 会话主机）服务器系统和 App-v 5.1 客户端，该客户端用于所有其他计算机。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-131">There are two different client types: the client for Remote Desktop Services, which is used on Remote Desktop Session Host (RD Session Host) server systems and the App-V 5.1 client, which is used for all other computers.</span></span>

<span data-ttu-id="d7e6f-132">App-v 5.1 客户端应使用安装程序命令行或在安装完成后使用 PowerShell 脚本进行配置。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-132">The App-V 5.1 client should be configured by using either the installer command line or by using a PowerShell script after the installation has been completed.</span></span>

<span data-ttu-id="d7e6f-133">必须仔细定义这些设置，以便加速 app-v 5.1 客户端软件的部署。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-133">The settings must be defined carefully in advance in order to expedite the deployment of the App-V 5.1 client software.</span></span> <span data-ttu-id="d7e6f-134">当您的计算机位于不同的办公室，并且客户端必须配置为使用不同的源位置时，这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-134">This is especially important when you have computers in different offices where the clients must be configured to use different source locations.</span></span>

<span data-ttu-id="d7e6f-135">您还必须确定部署客户端软件的方式。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-135">You must also determine how you will deploy the client software.</span></span> <span data-ttu-id="d7e6f-136">虽然可以在每台计算机上手动部署客户端，但大多数组织希望通过自动化过程部署客户端。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-136">Although it is possible to deploy the client manually on each computer, most organizations prefer to deploy the client through an automated process.</span></span> <span data-ttu-id="d7e6f-137">较大的组织可能具有可操作的电子软件分发（ESD）系统，这是一个理想的客户端部署系统。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-137">A larger organization might have an operational Electronic Software Distribution (ESD) system, which is an ideal client deployment system.</span></span> <span data-ttu-id="d7e6f-138">如果不存在 ESD 系统，则可以使用组织的标准安装软件的方法。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-138">If no ESD system exists, you can use your organization’s standard method of installing software.</span></span> <span data-ttu-id="d7e6f-139">可能的方法包括组策略或各种脚本技术。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-139">Possible methods include Group Policy or various scripting techniques.</span></span> <span data-ttu-id="d7e6f-140">此部署过程可能很复杂，具体取决于客户端计算机的数量和不同位置。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-140">Depending on the quantity and disparate locations of your client computers, this deployment process can be complex.</span></span> <span data-ttu-id="d7e6f-141">你必须使用结构化方法来确保所有计算机都使用正确的配置来安装客户端。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-141">You must use a structured approach to ensure that all computers get the client installed with the correct configuration.</span></span>

<span data-ttu-id="d7e6f-142">有关客户端最低要求的列表，请参阅[App-V 5.1 先决条件](app-v-51-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-142">For a list of the client minimum requirements see [App-V 5.1 Prerequisites](app-v-51-prerequisites.md).</span></span>

## <a href="" id="bkmk-client-coexist"></a><span data-ttu-id="d7e6f-143">规划 app-v 客户端共存</span><span class="sxs-lookup"><span data-stu-id="d7e6f-143">Planning for App-V client coexistence</span></span>


<span data-ttu-id="d7e6f-144">你可以使用 app-v 4.6 客户端并排部署 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-144">You can deploy the App-V 5.1 client side by side with the App-V 4.6 client.</span></span> <span data-ttu-id="d7e6f-145">客户端共存要求你通过使用部署配置文件或用户配置文件来添加或发布虚拟化的应用程序，因为这些配置文件中的某些设置必须配置，才能使 app-v 5.1 与 App-v 4.6 客户端一起正常工作。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-145">Client coexistence requires that you add or publish virtualized applications by using either a deployment configuration file or a user configuration file, because there are certain settings in these configuration files that must be configured in order for App-V 5.1 to function with App-V4.6 clients.</span></span> <span data-ttu-id="d7e6f-146">使用客户端或服务器升级程序包时，程序包必须重新提交配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-146">When a package is upgraded by using either the client or the server, the package must resubmit the configuration file.</span></span> <span data-ttu-id="d7e6f-147">对于具有相应配置文件的任何程序包，这是正确的，因此它不特定于客户端共存。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-147">This is true for any package that has a corresponding configuration file, so it is not specific to client coexistence.</span></span> <span data-ttu-id="d7e6f-148">但是，如果在程序包升级期间未提交配置文件，则程序包状态在共存方案中将不会按预期运行。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-148">However, if you do not submit the configuration file during the package upgrade, then the package state will not function as expected in coexistence scenarios.</span></span>

<span data-ttu-id="d7e6f-149">App-v 5.1 动态配置文件为特定用户自定义程序包。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-149">App-V 5.1 dynamic configuration files customize a package for a specific user.</span></span> <span data-ttu-id="d7e6f-150">必须先创建动态用户配置（.xml）文件或动态部署配置文件，然后才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-150">You must create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use them.</span></span> <span data-ttu-id="d7e6f-151">若要创建文件，它需要高级手动操作。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-151">To create the file it requires an advanced manual operation.</span></span>

<span data-ttu-id="d7e6f-152">使用动态用户配置文件时，不会使用清单文件中的扩展的任何 App-v 5.1 信息。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-152">When a dynamic user configuration file is used, none of the App-V 5.1 information for the extension in the manifest file is used.</span></span> <span data-ttu-id="d7e6f-153">这意味着，动态用户配置文件必须包含特定于清单文件中的 app-v 5.1 的扩展的所有内容，以及要进行的更改，例如删除和更新。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-153">This means that the dynamic user configuration file must include everything for the extension that is specific to App-V 5.1 in the manifest file, as well as the changes that you want to make, such as, deletions and updates.</span></span> <span data-ttu-id="d7e6f-154">有关如何创建自定义配置文件的详细信息，请参阅[如何使用 app-v 5.1 管理控制台创建自定义配置文件](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-154">For more information about how to create a custom configuration file, see [How to Create a Custom Configuration File by Using the App-V 5.1 Management Console](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md).</span></span>

## <a href="" id="bkmk-plan-for-scs"></a><span data-ttu-id="d7e6f-155">规划 app-v 5.1 共享内容存储（SCS）</span><span class="sxs-lookup"><span data-stu-id="d7e6f-155">Planning for the App-V 5.1 Shared Content Store (SCS)</span></span>


<span data-ttu-id="d7e6f-156">App-v 5.1 共享的内容存储模式允许运行应用-V 5.1 客户端的计算机运行虚拟化的应用程序，并且不会在运行 App-v 5.1 客户端的计算机上保存任何程序包内容。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-156">The App-V 5.1 shared content store mode allows the computer running the App-V 5.1 client to run virtualized applications and none of the package contents is saved on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="d7e6f-157">仅当客户端请求时，才会将虚拟应用程序流式传输到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-157">Virtual applications are streamed to target computers only when requested by the client.</span></span>

<span data-ttu-id="d7e6f-158">下表显示了使用 app-v 5.1 共享内容存储的一些优点：</span><span class="sxs-lookup"><span data-stu-id="d7e6f-158">The following list displays some of the benefits of using the App-V 5.1 shared content store:</span></span>

-   <span data-ttu-id="d7e6f-159">减少应用到应用和多用户应用程序冲突，因此降低了回归测试的需求</span><span class="sxs-lookup"><span data-stu-id="d7e6f-159">Reduced app-to-app and multi-user application conflicts and hence a reduced need for regression testing</span></span>

-   <span data-ttu-id="d7e6f-160">通过降低部署风险加快应用程序部署</span><span class="sxs-lookup"><span data-stu-id="d7e6f-160">Accelerated application deployment by reduction of deployment risk</span></span>

-   <span data-ttu-id="d7e6f-161">简化的配置文件管理</span><span class="sxs-lookup"><span data-stu-id="d7e6f-161">Simplified profile management</span></span>






## <a href="" id="other-resources-for-the-app-v-5-1-deployment-"></a><span data-ttu-id="d7e6f-162">适用于 app-v 5.1 部署的其他资源</span><span class="sxs-lookup"><span data-stu-id="d7e6f-162">Other resources for the App-V 5.1 deployment</span></span>


[<span data-ttu-id="d7e6f-163">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="d7e6f-163">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

## <span data-ttu-id="d7e6f-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7e6f-164">Related topics</span></span>


[<span data-ttu-id="d7e6f-165">如何安装 Sequencer</span><span class="sxs-lookup"><span data-stu-id="d7e6f-165">How to Install the Sequencer</span></span>](how-to-install-the-sequencer-51beta-gb18030.md)

[<span data-ttu-id="d7e6f-166">如何部署 App-V Client</span><span class="sxs-lookup"><span data-stu-id="d7e6f-166">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-51gb18030.md)

[<span data-ttu-id="d7e6f-167">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="d7e6f-167">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

[<span data-ttu-id="d7e6f-168">如何针对共享内容存储模式安装 App-V 5.1 Client</span><span class="sxs-lookup"><span data-stu-id="d7e6f-168">How to Install the App-V 5.1 Client for Shared Content Store Mode</span></span>](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

 

 





