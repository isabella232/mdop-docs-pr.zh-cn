---
title: DaRT 7.0 的安全注意事项
description: DaRT 7.0 的安全注意事项
author: dansimp
ms.assetid: 52ad7e6c-c169-4ba4-aa76-56335a585eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739c0319195aeb26e38d55ffe01d14b623de7f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803227"
---
# <span data-ttu-id="05b65-103">DaRT 7.0 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="05b65-103">Security Considerations for DaRT 7.0</span></span>


<span data-ttu-id="05b65-104">Microsoft 诊断和恢复工具集（DaRT）7包含允许管理员远程运行 DaRT 工具以解决最终用户计算机上的问题的功能。</span><span class="sxs-lookup"><span data-stu-id="05b65-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes functionality that lets an administrator run the DaRT tools remotely to resolve problems on an end-user computer.</span></span> <span data-ttu-id="05b65-105">在早期版本的 DaRT 中，技术支持技术人员或管理员必须使用包含 DaRT 恢复映像的 CD 或 DVD，才能在最终用户计算机上启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="05b65-105">In earlier releases of DaRT, a help desk technician or administrator had to physically be at an end-user computer and boot into DaRT by using the CD or DVD that included the DaRT recovery image.</span></span> <span data-ttu-id="05b65-106">现在，技术支持技术人员或管理员可以远程执行相同的过程。</span><span class="sxs-lookup"><span data-stu-id="05b65-106">Now, the help desk technician or administrator can perform the same procedures remotely.</span></span>

<span data-ttu-id="05b65-107">此外，在 DaRT7 中，除了刻录 CD 或 DVD，你现在可以将国际标准化组织（ISO）映像保存到 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="05b65-107">Also in DaRT7, in addition to burning a CD or DVD, you are now able to save the International Organization for Standardization (ISO) image to a USB flash drive.</span></span> <span data-ttu-id="05b65-108">你还可以将 ISO 映像放在网络上，或将其内容包含在计算机硬盘上的恢复分区。</span><span class="sxs-lookup"><span data-stu-id="05b65-108">You can also put the ISO image on a network or include its contents as a recovery partition on a computer hard disk.</span></span>

<span data-ttu-id="05b65-109">DaRT7 中的**远程连接**功能允许最终用户使用这些新部署方法之一访问 DaRT。</span><span class="sxs-lookup"><span data-stu-id="05b65-109">The **Remote Connection** feature in DaRT7 lets end users access DaRT by using one of these new deployment methods.</span></span> <span data-ttu-id="05b65-110">因此，他们可以更轻松地启动 DaRT 和访问 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="05b65-110">Therefore, they can more easily start DaRT and access the DaRT tools.</span></span>

<span data-ttu-id="05b65-111">DaRT7 中的新功能在您的企业中使用 DaRT 的方式提供了更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="05b65-111">The new functionalities in DaRT7 provide much more flexibility in how you use DaRT in your enterprise.</span></span> <span data-ttu-id="05b65-112">但是，他们还会创建自己的一组必须解决的安全问题。</span><span class="sxs-lookup"><span data-stu-id="05b65-112">However, they also create their own set of security issues that must be addressed.</span></span> <span data-ttu-id="05b65-113">我们建议你在配置 DaRT 时考虑以下安全提示。</span><span class="sxs-lookup"><span data-stu-id="05b65-113">We recommend that you consider the following security tips when you configure DaRT.</span></span>

## <span data-ttu-id="05b65-114">创建 DaRT 恢复映像时帮助保持安全</span><span class="sxs-lookup"><span data-stu-id="05b65-114">To help maintain security when you create the DaRT recovery image</span></span>


<span data-ttu-id="05b65-115">创建 DaRT 恢复映像时，可以选择要包含的工具。</span><span class="sxs-lookup"><span data-stu-id="05b65-115">When you are creating the DaRT recovery image, you can select the tools that you want to include.</span></span> <span data-ttu-id="05b65-116">出于安全原因，你可能希望限制最终用户对更强大的 DaRT 工具（如磁盘擦除和 Locksmith）的访问。</span><span class="sxs-lookup"><span data-stu-id="05b65-116">For security reasons, you might want to restrict end-user access to the more powerful DaRT tools, such as Disk Wipe and Locksmith.</span></span> <span data-ttu-id="05b65-117">在 DaRT7 中，你可以在配置期间禁用某些工具，并且当最终用户启动远程连接功能时仍将它们提供给帮助台代理。</span><span class="sxs-lookup"><span data-stu-id="05b65-117">In DaRT7, you can disable certain tools during configuration and still make them available to helpdesk agents when the end user starts the Remote Connection feature.</span></span>

<span data-ttu-id="05b65-118">您甚至可以配置 DaRT 映像，以便用于启动远程连接会话的选项是最终用户可用的唯一工具。</span><span class="sxs-lookup"><span data-stu-id="05b65-118">You can even configure the DaRT image so that the option to start a remote connection session is the only tool available to an end user.</span></span>

<span data-ttu-id="05b65-119">**重要提示** 建立远程连接后，你包含在恢复映像中的所有工具（包括最终用户不可用的工具）将对在最终用户计算机上工作的帮助台工程师可用。</span><span class="sxs-lookup"><span data-stu-id="05b65-119">**Important** After the remote connection is established, all the tools that you included in the recovery image, including those unavailable to the end user, will become available to the helpdesk agent working on the end–user computer.</span></span>

 

<span data-ttu-id="05b65-120">有关在 DaRT 恢复映像中包括工具在内的详细信息，请参阅[如何使用 Dart 恢复映像向导创建恢复映像](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="05b65-120">For more information about including tools in the DaRT recovery image, see [How to Use the DaRT Recovery Image Wizard to Create the Recovery Image](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md).</span></span>

## <span data-ttu-id="05b65-121">通过加密 DaRT 恢复映像来帮助维护安全性</span><span class="sxs-lookup"><span data-stu-id="05b65-121">To help maintain security by encrypting the DaRT recovery image</span></span>


<span data-ttu-id="05b65-122">如果你使用 DaRT7 中新增的一个部署选项（例如，保存到 USB 闪存驱动器或创建远程分区或恢复分区），则可以在 ISO 上包括公司的首选驱动器加密方法。</span><span class="sxs-lookup"><span data-stu-id="05b65-122">If you use one of the deployment options new in DaRT7, for example, saving to a USB flash drive or creating a remote partition or a recovery partition, you can include your company’s preferred method of drive encryption on the ISO.</span></span> <span data-ttu-id="05b65-123">这将帮助确保最终用户不能使用 DaRT 的功能来获得恢复映像的访问权限。</span><span class="sxs-lookup"><span data-stu-id="05b65-123">This will help make sure that an end user cannot use the functionality of DaRT should they gain access to the recovery image.</span></span> <span data-ttu-id="05b65-124">此外，它还将确保未经授权的用户无法在属于其他人的计算机上启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="05b65-124">And it will also make sure that unauthorized users cannot boot into DaRT on computers that belong to someone else.</span></span>

<span data-ttu-id="05b65-125">应在所有计算机中部署和启用加密方法。</span><span class="sxs-lookup"><span data-stu-id="05b65-125">Your encryption method should be deployed and enabled in all computers.</span></span>

<span data-ttu-id="05b65-126">**注意** DaRT7 支持 BitLocker 本身。</span><span class="sxs-lookup"><span data-stu-id="05b65-126">**Note** DaRT7 supports BitLocker natively.</span></span>

 

## <span data-ttu-id="05b65-127">在远程连接期间帮助保持两台计算机的安全</span><span class="sxs-lookup"><span data-stu-id="05b65-127">To help maintain security between two computers during Remote Connection</span></span>


<span data-ttu-id="05b65-128">默认情况下，已建立**远程连接**会话的两台计算机之间的通信可能不会加密。</span><span class="sxs-lookup"><span data-stu-id="05b65-128">By default, the communication between two computers that have established a **Remote Connection** session may not be encrypted.</span></span> <span data-ttu-id="05b65-129">因此，为了帮助维护两台计算机之间的安全，我们建议两台计算机都是同一网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="05b65-129">Therefore, to help maintain security between the two computers, we recommend that both computers are a part of the same network.</span></span>

## <span data-ttu-id="05b65-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="05b65-130">Related topics</span></span>


[<span data-ttu-id="05b65-131">DaRT 7.0 的操作</span><span class="sxs-lookup"><span data-stu-id="05b65-131">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)

 

 





