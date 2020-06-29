---
title: 如何恢复已损坏的驱动器
description: 如何恢复已损坏的驱动器
author: dansimp
ms.assetid: b0457a00-f72e-4ad8-ab3b-7701851ca87e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5bbd4c2a1f5ef3fde78a9f72c1f77ccb0cdea377
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803255"
---
# <span data-ttu-id="0cf51-103">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="0cf51-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="0cf51-104">若要恢复受 BitLocker 保护的损坏的驱动器，Microsoft BitLocker 管理和监视（MBAM）技术支持用户将需要创建恢复密钥包文件。</span><span class="sxs-lookup"><span data-stu-id="0cf51-104">To recover a corrupted drive protected by BitLocker, a Microsoft BitLocker Administration and Monitoring (MBAM) Help Desk user will need to create a recovery key package file.</span></span> <span data-ttu-id="0cf51-105">然后，可以将此程序包文件复制到包含损坏的驱动器的计算机，然后用于恢复驱动器。</span><span class="sxs-lookup"><span data-stu-id="0cf51-105">This package file can then be copied to the computer that contains the corrupted drive, and then used to recover the drive.</span></span> <span data-ttu-id="0cf51-106">对于执行此操作所需的步骤，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="0cf51-106">Use the following procedure for the steps needed to do this.</span></span>

<span data-ttu-id="0cf51-107">**重要提示** 为了避免潜在的数据丢失，强烈建议你阅读 "manage-bde" 帮助并清楚了解如何使用该命令，然后再完成以下说明。</span><span class="sxs-lookup"><span data-stu-id="0cf51-107">**Important** To avoid a potential loss of data, it is strongly recommended that you read the “repair-bde” help and clearly understand how to use the command before completing the following instructions.</span></span>

 

**<span data-ttu-id="0cf51-108">恢复损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="0cf51-108">To recover a corrupted drive</span></span>**

1.  <span data-ttu-id="0cf51-109">若要创建恢复已损坏的驱动器所需的恢复密钥包，请启动 web 浏览器并打开 MBAM 管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="0cf51-109">To create the recovery key package necessary to recover a corrupted drive, start a web browser and open the MBAM Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="0cf51-110">从左侧导航窗格中选择 "**驱动器恢复**"。</span><span class="sxs-lookup"><span data-stu-id="0cf51-110">Select **Drive Recovery** from the left navigation pane.</span></span> <span data-ttu-id="0cf51-111">输入用户的域名、用户名、解锁驱动器的原因以及用户的恢复密码 ID。</span><span class="sxs-lookup"><span data-stu-id="0cf51-111">Enter the user’s domain name, user name, reason for unlocking the drive, and the user’s recovery password ID.</span></span>

    <span data-ttu-id="0cf51-112">**注意** 如果您是技术支持管理员角色的成员，则无需输入用户的域名或用户名。</span><span class="sxs-lookup"><span data-stu-id="0cf51-112">**Note** If you are a member of the Help Desk Administrators role, you do not have to enter the user’s domain name or user name.</span></span>

     

3.  <span data-ttu-id="0cf51-113">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="0cf51-113">Click **Submit**.</span></span> <span data-ttu-id="0cf51-114">将显示恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="0cf51-114">The recovery key will be displayed.</span></span>

4.  <span data-ttu-id="0cf51-115">单击 "**保存**"，然后选择 "**恢复密钥包**"。</span><span class="sxs-lookup"><span data-stu-id="0cf51-115">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="0cf51-116">将在你的计算机上创建恢复密钥包。</span><span class="sxs-lookup"><span data-stu-id="0cf51-116">The recovery key package will be created on your computer.</span></span>

5.  <span data-ttu-id="0cf51-117">将恢复密钥包复制到包含损坏的驱动器的计算机。</span><span class="sxs-lookup"><span data-stu-id="0cf51-117">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

6.  <span data-ttu-id="0cf51-118">打开提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="0cf51-118">Open an elevated command prompt.</span></span> <span data-ttu-id="0cf51-119">若要执行此操作，请单击 "**开始**"，然后 `cmd` 在 "**搜索程序和文件" 框**中键入。</span><span class="sxs-lookup"><span data-stu-id="0cf51-119">To do this, click **Start** and type `cmd` in the **Search programs and files box**.</span></span> <span data-ttu-id="0cf51-120">右键单击**cmd.exe** ，然后选择 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="0cf51-120">Right-click **cmd.exe** and select **Run as Administrator**.</span></span>

7.  <span data-ttu-id="0cf51-121">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="0cf51-121">At the command prompt, type the following:</span></span>

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="0cf51-122">**注意** &lt;将固定驱动器替换 &gt; 为具有等于或大于损坏的驱动器上的数据的可用硬盘空间。</span><span class="sxs-lookup"><span data-stu-id="0cf51-122">**Note** Replace &lt;fixed drive&gt; with an available hard disk drive that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="0cf51-123">已损坏的驱动器上的数据将恢复并移动到指定的硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="0cf51-123">Data on the corrupted drive is recovered and moved to the specified hard disk drive.</span></span>

     

## <span data-ttu-id="0cf51-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="0cf51-124">Related topics</span></span>


[<span data-ttu-id="0cf51-125">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="0cf51-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





