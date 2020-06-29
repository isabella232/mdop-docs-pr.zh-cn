---
title: 如何使用技术支持门户
description: 如何使用技术支持门户
author: dansimp
ms.assetid: c27f7737-10c8-4164-9de8-57987292c89c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8813fbe9a7b6980b656ecc673ac4ed618c4cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803946"
---
# <span data-ttu-id="c4cc5-103">如何使用技术支持门户</span><span class="sxs-lookup"><span data-stu-id="c4cc5-103">How to Use the Help Desk Portal</span></span>


<span data-ttu-id="c4cc5-104">MBAM 管理和监视网站（也称为帮助桌面门户）是一种管理界面，用于作为 Microsoft BitLocker 管理和监视（MBAM）服务器基础结构的一部分安装的 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-104">The MBAM Administration and Monitoring website, also referred to as the Help Desk Portal, is an administrative interface to BitLocker drive encryption that is installed as part of the Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure.</span></span> <span data-ttu-id="c4cc5-105">以下部分介绍了如何使用此网站查看报表、恢复最终用户的驱动器以及管理最终用户的 TPMs。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-105">The following sections describe how you can use this website to review reports, recover end users’ drives, and manage end users’ TPMs.</span></span>

## <a href="" id="bkmk-reports"></a><span data-ttu-id="c4cc5-106">报告</span><span class="sxs-lookup"><span data-stu-id="c4cc5-106">Reports</span></span>


<span data-ttu-id="c4cc5-107">MBAM 从 Active Directory 和客户端计算机收集信息，这使你可以运行不同的报告来监视 BitLocker 使用情况和合规性。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-107">MBAM collects information from Active Directory and client computers, which enables you to run different reports to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="c4cc5-108">使用 "管理和监视" 网站的 "**报告**" 部分，你可以生成有关企业合规性、单个计算机和密钥恢复活动的报告。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-108">Using the **Reports** section of the Administration and Monitoring website, you can generate reports on enterprise compliance, individual computers, and key recovery activity.</span></span> <span data-ttu-id="c4cc5-109">有关每个报表的说明，请参阅[了解 MBAM 报表](understanding-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-109">For a description of each report, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

**<span data-ttu-id="c4cc5-110">访问报表</span><span class="sxs-lookup"><span data-stu-id="c4cc5-110">To access reports</span></span>**

1.  <span data-ttu-id="c4cc5-111">打开 web 浏览器并导航到 MBAM 管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-111">Open a web browser and navigate to the MBAM Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="c4cc5-112">在左窗格中选择 "**报表**"。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-112">Select **Reports** in the left pane.</span></span>

3.  <span data-ttu-id="c4cc5-113">从顶部菜单栏中，选择要生成的报表类型。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-113">From the top menu bar, select the report type you want to generate.</span></span> <span data-ttu-id="c4cc5-114">若要保存报表，请单击 "报表" 菜单栏上的 "**导出**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-114">To save reports, click the **Export** button on the Reports menu bar.</span></span>

<span data-ttu-id="c4cc5-115">有关如何运行 MBAM 报表的其他信息，请参阅[如何生成 MBAM 报表](how-to-generate-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-115">For additional information about how to run MBAM reports, see [How to Generate MBAM Reports](how-to-generate-mbam-reports-mbam-2.md).</span></span>

## <a href="" id="bkmk-drirec"></a><span data-ttu-id="c4cc5-116">驱动器恢复</span><span class="sxs-lookup"><span data-stu-id="c4cc5-116">Drive Recovery</span></span>


<span data-ttu-id="c4cc5-117">管理和监视网站的**驱动器恢复**功能允许具有特定管理员角色（例如，技术支持用户）的用户访问已由 MBAM 客户端收集的恢复密钥数据。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-117">The **Drive Recovery** feature of the Administration and Monitoring website allows users with specific administrator roles (for example, Help Desk Users) to access recovery key data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="c4cc5-118">当 BitLocker 进入恢复模式时，此数据可用于访问受 BitLocker 保护的驱动器。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-118">This data can be used to access a BitLocker-protected drive when BitLocker goes into recovery mode.</span></span> <span data-ttu-id="c4cc5-119">有关如何恢复处于恢复模式的驱动器的说明，请参阅[如何在恢复模式下恢复驱动器](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-119">For instructions on how to recover a drive that is in recovery mode, see [How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-2.md).</span></span>

<span data-ttu-id="c4cc5-120">您还可以恢复已被移动或损坏的驱动器：</span><span class="sxs-lookup"><span data-stu-id="c4cc5-120">You can also recover drives that have been moved or that are corrupted:</span></span>

-   [<span data-ttu-id="c4cc5-121">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="c4cc5-121">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

-   [<span data-ttu-id="c4cc5-122">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="c4cc5-122">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

<span data-ttu-id="c4cc5-123">有关如何恢复受 BitLocker 保护的驱动器的其他信息，请参阅[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-123">For additional information about how to recover a BitLocker-protected drive, see [Performing BitLocker Management with MBAM](performing-bitlocker-management-with-mbam-mbam-2.md).</span></span>

## <a href="" id="bkmk-manatpm"></a><span data-ttu-id="c4cc5-124">管理 TPM</span><span class="sxs-lookup"><span data-stu-id="c4cc5-124">Manage TPM</span></span>


<span data-ttu-id="c4cc5-125">管理和监视网站的 "管理 TPM" 功能为用户提供某些管理员角色（例如，"MBAM 帮助台用户"）对 MBAM 客户端收集的 TPM 数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-125">The Manage TPM feature of the Administration and Monitoring website gives users with certain administrator roles (for example, “MBAM Helpdesk Users”) access to TPM data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="c4cc5-126">在 TPM 锁定中，管理员可以使用管理和监视网站检索用于解锁 TPM 的必需密码文件。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-126">In a TPM lockout, an administrator can use the Administration and Monitoring website to retrieve the necessary password file to unlock the TPM.</span></span> <span data-ttu-id="c4cc5-127">有关如何在 TPM 锁定后重置 TPM 的说明，请参阅[如何重置 Tpm 锁定](how-to-reset-a-tpm-lockout-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-127">For instructions on how to reset a TPM after a TPM lockout, see [How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-2.md).</span></span>

## <a href="" id="bkmk-helpdesk"></a> <span data-ttu-id="c4cc5-128">MBAM 技术支持任务</span><span class="sxs-lookup"><span data-stu-id="c4cc5-128">MBAM Help Desk Tasks</span></span>


<span data-ttu-id="c4cc5-129">你可以使用管理和监视网站执行许多管理任务，例如管理受 BitLocker 保护的硬件、恢复驱动器和运行报告。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-129">You can use the Administration and Monitoring website for many administrative tasks, such as managing BitLocker-protected hardware, recovering drives, and running reports.</span></span> <span data-ttu-id="c4cc5-130">默认情况下，管理和监视网站的 URL 是 http:// &lt; *MBAMAdministrationServername* &gt; ，但你可以在安装过程中对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-130">By default, the URL for the Administration and Monitoring website is http://&lt;*MBAMAdministrationServername*&gt;, although you can customize it during the installation process.</span></span>

<span data-ttu-id="c4cc5-131">**注意** 若要访问由管理和监视网站提供的各种功能，您必须拥有与您的用户帐户相关联的相应角色。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-131">**Note** To access the various features offered by the Administration and Monitoring website, you must have the appropriate roles associated with your user account.</span></span> <span data-ttu-id="c4cc5-132">有关了解用户角色的详细信息，请参阅[如何管理 MBAM 管理员角色](how-to-manage-mbam-administrator-roles-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cc5-132">For more information about understanding user roles, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md).</span></span>

 

<span data-ttu-id="c4cc5-133">使用以下链接查找有关可通过使用管理和监视网站执行的任务的信息：</span><span class="sxs-lookup"><span data-stu-id="c4cc5-133">Use the following links to find information about the tasks that you can perform by using the Administration and Monitoring website:</span></span>

-   [<span data-ttu-id="c4cc5-134">如何重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="c4cc5-134">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-2.md)

-   [<span data-ttu-id="c4cc5-135">如何在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="c4cc5-135">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

-   [<span data-ttu-id="c4cc5-136">如何恢复已移动的驱动器</span><span class="sxs-lookup"><span data-stu-id="c4cc5-136">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

-   [<span data-ttu-id="c4cc5-137">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="c4cc5-137">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

-   [<span data-ttu-id="c4cc5-138">如何确定丢失计算机的 BitLocker 加密状态</span><span class="sxs-lookup"><span data-stu-id="c4cc5-138">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

 

 





