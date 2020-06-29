---
title: DaRT 8.0 的安全注意事项
description: DaRT 8.0 的安全注意事项
author: dansimp
ms.assetid: 45ef8164-fee7-41a1-9a36-de4e3264e7a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02d32d926c0def7d33bebd399cd380eed4e8385e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798110"
---
# <span data-ttu-id="7c007-103">DaRT 8.0 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="7c007-103">Security Considerations for DaRT 8.0</span></span>


<span data-ttu-id="7c007-104">本主题包含有关客户和组、日志文件以及有关 Microsoft 诊断和恢复工具集（DaRT）8.0 的其他安全相关注意事项的简要概述。</span><span class="sxs-lookup"><span data-stu-id="7c007-104">This topic contains a brief overview about the accounts and groups, log files, and other security-related considerations for Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0.</span></span> <span data-ttu-id="7c007-105">有关详细信息，请访问本文中的链接。</span><span class="sxs-lookup"><span data-stu-id="7c007-105">For more information, follow the links within this article.</span></span>

## <span data-ttu-id="7c007-106">常规安全注意事项</span><span class="sxs-lookup"><span data-stu-id="7c007-106">General security considerations</span></span>


<span data-ttu-id="7c007-107">**了解安全风险**。</span><span class="sxs-lookup"><span data-stu-id="7c007-107">**Understand the security risks**.</span></span> <span data-ttu-id="7c007-108">DaRT 8.0 包括允许管理员或技术支持人员远程运行 DaRT 工具以解决最终用户计算机上的问题的功能。</span><span class="sxs-lookup"><span data-stu-id="7c007-108">DaRT 8.0 includes functionality that lets an administrator or a help desk worker run the DaRT tools remotely to resolve problems on an end-user computer.</span></span> <span data-ttu-id="7c007-109">此外，你可以将国际标准化组织（ISO）映像保存到 USB 闪存驱动器，或将 ISO 映像放在网络上以将其内容包含在计算机硬盘上的恢复分区中。</span><span class="sxs-lookup"><span data-stu-id="7c007-109">In addition, you can save the International Organization for Standardization (ISO) image to a USB flash drive or put the ISO image on a network to include its contents as a recovery partition on a computer’s hard disk.</span></span> <span data-ttu-id="7c007-110">这些功能提供了灵活性，但还带来了在配置 DaRT 时应考虑的潜在安全风险。</span><span class="sxs-lookup"><span data-stu-id="7c007-110">These capabilities provide flexibility, but also create potential security risks that you should consider when configuring DaRT.</span></span>

<span data-ttu-id="7c007-111">**确保计算机的物理安全**。</span><span class="sxs-lookup"><span data-stu-id="7c007-111">**Physically secure your computers**.</span></span> <span data-ttu-id="7c007-112">当管理员和技术支持工作者不是在其计算机上实际使用时，他们应该锁定其计算机并使用安全的屏幕保护程序。</span><span class="sxs-lookup"><span data-stu-id="7c007-112">When administrators and help desk workers are not physically at their computers, they should lock their computers and use a secured screen saver.</span></span>

<span data-ttu-id="7c007-113">**对所有计算机应用最新的安全更新**。</span><span class="sxs-lookup"><span data-stu-id="7c007-113">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="7c007-114">通过订阅安全通知服务（），随时了解操作系统的新更新 <https://go.microsoft.com/fwlink/?LinkId=28819> 。</span><span class="sxs-lookup"><span data-stu-id="7c007-114">Stay informed about new updates for operating systems by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/?LinkId=28819>).</span></span>

## <span data-ttu-id="7c007-115">限制最终用户访问 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="7c007-115">Limit end-user access to DaRT tools</span></span>


<span data-ttu-id="7c007-116">创建 DaRT 恢复映像时，可以选择要包含的工具。</span><span class="sxs-lookup"><span data-stu-id="7c007-116">When you are creating the DaRT recovery image, you can select the tools that you want to include.</span></span> <span data-ttu-id="7c007-117">出于安全原因，你可能希望限制最终用户对更强大的 DaRT 工具（如磁盘擦除和 Locksmith）的访问。</span><span class="sxs-lookup"><span data-stu-id="7c007-117">For security reasons, you might want to restrict end-user access to the more powerful DaRT tools, such as Disk Wipe and Locksmith.</span></span> <span data-ttu-id="7c007-118">在 DaRT 8.0 中，你可以在配置期间禁用某些工具，并且当最终用户启动远程连接功能时仍将其提供给技术支持人员。</span><span class="sxs-lookup"><span data-stu-id="7c007-118">In DaRT 8.0, you can disable certain tools during configuration and still make them available to help desk workers when the end user starts the Remote Connection feature.</span></span>

<span data-ttu-id="7c007-119">您甚至可以配置 DaRT 映像，以便用于启动远程连接会话的选项是最终用户可用的唯一工具。</span><span class="sxs-lookup"><span data-stu-id="7c007-119">You can even configure the DaRT image so that the option to start a remote connection session is the only tool available to an end user.</span></span>

<span data-ttu-id="7c007-120">**重要提示** 建立远程连接后，在恢复映像中包括的所有工具（包括最终用户不可用的工具）将提供给任何正在使用最终用户计算机的技术支持人员使用。</span><span class="sxs-lookup"><span data-stu-id="7c007-120">**Important** After the remote connection is established, all the tools that you included in the recovery image, including those unavailable to the end user, will become available to any help desk worker who is working on the end–user computer.</span></span>

 

<span data-ttu-id="7c007-121">有关在 DaRT 恢复映像中包括工具在内的详细信息，请参阅[dart 8.0 中的工具概述](overview-of-the-tools-in-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="7c007-121">For more information about including tools in the DaRT recovery image, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span>

## <span data-ttu-id="7c007-122">保护 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="7c007-122">Secure the DaRT recovery image</span></span>


<span data-ttu-id="7c007-123">如果你通过将 DaRT 恢复映像保存到 USB 闪存驱动器或创建远程分区或恢复分区来部署它，你可能希望在 ISO 上包含公司的首选驱动器加密方法。</span><span class="sxs-lookup"><span data-stu-id="7c007-123">If you deploy the DaRT recovery image by saving it to a USB flash drive or by creating a remote partition or a recovery partition, you might want to include your company’s preferred method of drive encryption on the ISO.</span></span> <span data-ttu-id="7c007-124">加密 ISO 有助于确保最终用户无法使用 DaRT 功能（如果他们获取恢复映像的访问权限），并确保未经授权的用户无法在属于其他人的计算机上启动 DaRT。</span><span class="sxs-lookup"><span data-stu-id="7c007-124">Encrypting the ISO helps to ensure that end users cannot use DaRT functionality if they were to gain access to the recovery image, and it ensures that unauthorized users cannot boot into DaRT on computers that belong to someone else.</span></span> <span data-ttu-id="7c007-125">如果使用加密方法，请确保在所有计算机中部署并启用它。</span><span class="sxs-lookup"><span data-stu-id="7c007-125">If you use an encryption method, be sure to deploy and enable it in all computers.</span></span>

<span data-ttu-id="7c007-126">**注意** DaRT 8.0 本身支持 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="7c007-126">**Note** DaRT 8.0 supports BitLocker natively.</span></span>

 

<span data-ttu-id="7c007-127">若要包括驱动器加密，请在创建恢复映像时添加加密解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="7c007-127">To include drive encryption, add the encryption solution files when you create the recovery image.</span></span> <span data-ttu-id="7c007-128">您的加密解决方案必须能够在 WinPE 上运行。</span><span class="sxs-lookup"><span data-stu-id="7c007-128">Your encryption solution must be able to run on WinPE.</span></span> <span data-ttu-id="7c007-129">然后，从 ISO 启动的最终用户可以访问该加密解决方案并取消阻止驱动器。</span><span class="sxs-lookup"><span data-stu-id="7c007-129">End users who boot from the ISO are then able to access that encryption solution and unblock the drive.</span></span>

## <span data-ttu-id="7c007-130">使用远程连接时维护两台计算机之间的安全性</span><span class="sxs-lookup"><span data-stu-id="7c007-130">Maintain security between two computers when you use Remote Connection</span></span>


<span data-ttu-id="7c007-131">默认情况下，已建立**远程连接**会话的两台计算机之间的通信可能不会加密。</span><span class="sxs-lookup"><span data-stu-id="7c007-131">By default, the communication between two computers that have established a **Remote Connection** session may not be encrypted.</span></span> <span data-ttu-id="7c007-132">因此，为了帮助维护两台计算机之间的安全，我们建议两台计算机都是同一网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="7c007-132">Therefore, to help maintain security between the two computers, we recommend that both computers are a part of the same network.</span></span>

## <span data-ttu-id="7c007-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="7c007-133">Related topics</span></span>


[<span data-ttu-id="7c007-134">DaRT 8.0 的安全和隐私</span><span class="sxs-lookup"><span data-stu-id="7c007-134">Security and Privacy for DaRT 8.0</span></span>](security-and-privacy-for-dart-80-dart-8.md)

 

 





