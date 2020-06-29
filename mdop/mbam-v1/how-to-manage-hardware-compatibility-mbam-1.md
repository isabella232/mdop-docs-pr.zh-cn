---
title: 如何管理硬件兼容性
description: 如何管理硬件兼容性
author: dansimp
ms.assetid: c74b96b9-8161-49bc-b5bb-4838734e7df5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf9e2c5b2b33ea93d9834a81700bd2be8a9b9757
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798182"
---
# <span data-ttu-id="7f33d-103">如何管理硬件兼容性</span><span class="sxs-lookup"><span data-stu-id="7f33d-103">How to Manage Hardware Compatibility</span></span>


<span data-ttu-id="7f33d-104">部署 "允许硬件兼容性检查" 组策略后，Microsoft BitLocker 管理和监视（MBAM）可以收集有关客户端计算机的制造商和型号的信息。</span><span class="sxs-lookup"><span data-stu-id="7f33d-104">Microsoft BitLocker Administration and Monitoring (MBAM) can collect information about the manufacturer and model of client computers after you deploy the Allow Hardware Compatibility Checking Group Policy.</span></span> <span data-ttu-id="7f33d-105">如果配置此策略，则当在客户端计算机上部署 MBAM 客户端时，MBAM 代理会向 MBAM 服务器报告计算机和模型信息。</span><span class="sxs-lookup"><span data-stu-id="7f33d-105">If you configure this policy, the MBAM agent reports the computer make and model information to the MBAM Server when the MBAM Client is deployed on a client computer.</span></span>

<span data-ttu-id="7f33d-106">如果你的组织拥有较旧的计算机硬件或不支持受信任的平台模块（TPM）芯片的计算机，硬件兼容功能将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="7f33d-106">The Hardware Compatibility feature is helpful when your organization has older computer hardware or computers that do not support Trusted Platform Module (TPM) chips.</span></span> <span data-ttu-id="7f33d-107">在这些情况下，你可以使用硬件兼容性功能来确保 BitLocker 加密仅应用于支持它的计算机模型。</span><span class="sxs-lookup"><span data-stu-id="7f33d-107">In these cases, you can use the Hardware Compatibility feature to ensure that BitLocker encryption is applied only to computer models that support it.</span></span> <span data-ttu-id="7f33d-108">如果您的组织中的所有计算机都支持 BitLocker，则无需使用硬件兼容性功能。</span><span class="sxs-lookup"><span data-stu-id="7f33d-108">If all computers in your organization will support BitLocker, you do not have to use the Hardware Compatibility feature.</span></span>

<span data-ttu-id="7f33d-109">**注意** 默认情况下，MBAM 硬件兼容性功能未启用。</span><span class="sxs-lookup"><span data-stu-id="7f33d-109">**Note** By default, MBAM Hardware Compatibility feature is not enabled.</span></span> <span data-ttu-id="7f33d-110">若要启用该功能，请在安装过程中的 "**管理和监视服务器**" 下选择**硬件兼容性**功能。</span><span class="sxs-lookup"><span data-stu-id="7f33d-110">To enable it, select the **Hardware Compatibility** feature under the **Administration and Monitoring Server** feature during setup.</span></span> <span data-ttu-id="7f33d-111">有关如何设置和配置硬件兼容性的详细信息，请参阅[部署 MBAM 1.0 服务器基础结构](deploying-the-mbam-10-server-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="7f33d-111">For more information about how to set up and configure Hardware Compatibility, see [Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md).</span></span>

 

<span data-ttu-id="7f33d-112">硬件兼容性功能的工作方式如下。</span><span class="sxs-lookup"><span data-stu-id="7f33d-112">The Hardware Compatibility feature works in the following way.</span></span>

****

1.  <span data-ttu-id="7f33d-113">MBAM 客户端代理会发现基本计算机信息，例如制造商、型号、BIOS maker、BIOS 版本、TPM 制造商和 TPM 版本，然后将此信息传递给 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="7f33d-113">The MBAM client agent discovers basic computer information such as manufacturer, model, BIOS maker, BIOS version, TPM maker, and TPM version, and then passes this information to the MBAM server.</span></span>

2.  <span data-ttu-id="7f33d-114">MBAM 服务器生成客户端计算机和模型的列表，以使你能够区分可以或不支持 BitLocker 的用户</span><span class="sxs-lookup"><span data-stu-id="7f33d-114">The MBAM server generates a list of client computer makes and models to enable you to differentiate between those that can or cannot support BitLocker</span></span>

3.  <span data-ttu-id="7f33d-115">在企业版中部署的 MBAM 客户端代理会自动更新此列表，其中包含状态为 "**未知**" 的所有新计算机和已发现的模型。</span><span class="sxs-lookup"><span data-stu-id="7f33d-115">The MBAM client agents that are deployed in the enterprise automatically update this list with all new computer makes and models that are discovered with a state of **Unknown**.</span></span> <span data-ttu-id="7f33d-116">然后，管理员可以使用 MBAM 管理网站来更改列表项，以将特定计算机的特定计算机和模型指定为**兼容**或**不兼容**。</span><span class="sxs-lookup"><span data-stu-id="7f33d-116">An administrator can then use the MBAM administration website to change list entries to specify a particular computer make and model as **Compatible** or **Incompatible**.</span></span>

4.  <span data-ttu-id="7f33d-117">在 MBAM 客户端代理开始加密驱动器之前，代理首先验证其正在运行的硬件的 BitLocker 加密兼容性。</span><span class="sxs-lookup"><span data-stu-id="7f33d-117">Before the MBAM client agent begins encrypting a drive, the agent first verifies the BitLocker encryption compatibility of the hardware it is running on.</span></span>

    -   <span data-ttu-id="7f33d-118">如果硬件标记为兼容，则会启动 BitLocker 加密过程。</span><span class="sxs-lookup"><span data-stu-id="7f33d-118">If the hardware is marked as compatible, the BitLocker encryption process starts.</span></span> <span data-ttu-id="7f33d-119">MBAM 还将再次检查计算机的硬件兼容性状态，每次一次。</span><span class="sxs-lookup"><span data-stu-id="7f33d-119">MBAM will also recheck the hardware compatibility status of the computer one time per day.</span></span>

    -   <span data-ttu-id="7f33d-120">如果硬件标记为不兼容，则该代理会记录一个事件，并在合规性报告中传递 "硬件免除" 状态。</span><span class="sxs-lookup"><span data-stu-id="7f33d-120">If the hardware is marked as incompatible, the agent logs an event and passes a “hardware exempted” state as part of compliance reporting.</span></span> <span data-ttu-id="7f33d-121">代理将每隔七天检查一次，以查看状态是否更改为 "兼容"。</span><span class="sxs-lookup"><span data-stu-id="7f33d-121">The agent checks every seven days to see whether the state has changed to “compatible.”</span></span>

    -   <span data-ttu-id="7f33d-122">如果硬件标记为 "未知"，则不会开始 BitLocker 加密过程。</span><span class="sxs-lookup"><span data-stu-id="7f33d-122">If the hardware is marked as unknown, the BitLocker encryption process will not begin.</span></span> <span data-ttu-id="7f33d-123">MBAM 客户端代理将每天一次重新检查计算机的硬件兼容性状态。</span><span class="sxs-lookup"><span data-stu-id="7f33d-123">The MBAM client agent will recheck the hardware compatibility status of the computer one time per day.</span></span>

<span data-ttu-id="7f33d-124">**警告** 如果 MBAM 客户端代理尝试加密不支持 BitLocker 驱动器加密的计算机，则计算机可能会损坏。</span><span class="sxs-lookup"><span data-stu-id="7f33d-124">**Warning** If the MBAM client agent tries to encrypt a computer that does not support BitLocker drive encryption, there is a possibility that the computer will become corrupted.</span></span> <span data-ttu-id="7f33d-125">确保在你的组织拥有不支持 BitLocker 的较旧硬件时正确配置硬件兼容性功能。</span><span class="sxs-lookup"><span data-stu-id="7f33d-125">Ensure that the hardware compatibility feature is correctly configured when your organization has older hardware that does not support BitLocker.</span></span>

 

**<span data-ttu-id="7f33d-126">管理硬件兼容性</span><span class="sxs-lookup"><span data-stu-id="7f33d-126">To manage hardware compatibility</span></span>**

1.  <span data-ttu-id="7f33d-127">打开 web 浏览器并导航到 Microsoft BitLocker 管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="7f33d-127">Open a web browser and navigate to the Microsoft BitLocker Administration and Monitoring website.</span></span> <span data-ttu-id="7f33d-128">在左侧菜单栏中选择 "**硬件**"。</span><span class="sxs-lookup"><span data-stu-id="7f33d-128">Select **Hardware** in the left menu bar.</span></span>

2.  <span data-ttu-id="7f33d-129">在右窗格中，单击 "**高级搜索**"，然后筛选以显示**功能**状态为 "**未知**" 的所有计算机模型的列表。</span><span class="sxs-lookup"><span data-stu-id="7f33d-129">On the right pane, click **Advanced Search**, and then filter to display a list of all computer models that have a **Capability** status of **Unknown**.</span></span> <span data-ttu-id="7f33d-130">将显示与搜索条件匹配的计算机模型的列表。</span><span class="sxs-lookup"><span data-stu-id="7f33d-130">A list of computer models matching the search criteria is displayed.</span></span> <span data-ttu-id="7f33d-131">管理员可以从该页面添加、编辑或删除新的计算机类型。</span><span class="sxs-lookup"><span data-stu-id="7f33d-131">Administrators can add, edit, or remove new computer types from this page.</span></span>

3.  <span data-ttu-id="7f33d-132">检查每个未知硬件配置以确定配置是否应设置为**兼容**或**不兼容**。</span><span class="sxs-lookup"><span data-stu-id="7f33d-132">Review each unknown hardware configuration to determine whether the configuration should be set to **Compatible** or **Incompatible**.</span></span>

4.  <span data-ttu-id="7f33d-133">选择一个或多个行，然后单击 "**设置兼容**性" 或 "**设置不兼容**" 以针对所选计算机模型设置 BitLocker 兼容性。</span><span class="sxs-lookup"><span data-stu-id="7f33d-133">Select one or more rows, and then click either **Set Compatible** or **Set Incompatible** to set the BitLocker compatibility, as appropriate, for the selected computer models.</span></span> <span data-ttu-id="7f33d-134">如果设置为 "**兼容**"，则 BitLocker 会尝试在与支持的模型匹配的计算机上强制实施驱动器加密策略。</span><span class="sxs-lookup"><span data-stu-id="7f33d-134">If set to **Compatible**, BitLocker tries to enforce drive encryption policy on computers that match the supported model.</span></span> <span data-ttu-id="7f33d-135">如果设置为**不兼容**，则 BitLocker 将不会在这些计算机上强制执行驱动器加密策略。</span><span class="sxs-lookup"><span data-stu-id="7f33d-135">If set to **Incompatible**, BitLocker will not enforce drive encryption policy on those computers.</span></span>

    <span data-ttu-id="7f33d-136">**注意** 将计算机模型设置为兼容后，MBAM 客户可能需要超过24小时才能在匹配该硬件模型的计算机上开始 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="7f33d-136">**Note** After you set a computer model as compatible, it can take more than twenty-four hours for the MBAM Client to begin BitLocker encryption on the computers matching that hardware model.</span></span>

     

5.  <span data-ttu-id="7f33d-137">管理员应定期监视硬件兼容性列表以查看由 MBAM 代理发现的新模型，然后将其兼容性设置更新为**兼容**或**不兼容**的相应设置。</span><span class="sxs-lookup"><span data-stu-id="7f33d-137">Administrators should regularly monitor the hardware compatibility list to review new models that are discovered by the MBAM agent, and then update their compatibility setting to **Compatible** or **Incompatible** as appropriate.</span></span>

## <span data-ttu-id="7f33d-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f33d-138">Related topics</span></span>


[<span data-ttu-id="7f33d-139">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="7f33d-139">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





