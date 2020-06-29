---
title: 如何恢复已损坏的驱动器
description: 如何恢复已损坏的驱动器
author: dansimp
ms.assetid: 715491ae-69c0-4fae-ad3f-3bd19a0db2f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 545ff5c7e6bea29d5f89cce1cf18212b7d0e2870
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798172"
---
# <span data-ttu-id="50920-103">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="50920-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="50920-104">若要恢复受 BitLocker 保护的损坏的驱动器，Microsoft BitLocker 管理和监视（MBAM）技术支持用户必须创建恢复密钥包文件。</span><span class="sxs-lookup"><span data-stu-id="50920-104">To recover a corrupted drive that has been protected by BitLocker, a Microsoft BitLocker Administration and Monitoring (MBAM) help desk user must create a recovery key package file.</span></span> <span data-ttu-id="50920-105">此程序包文件可以复制到包含损坏的驱动器的计算机，然后用于恢复驱动器。</span><span class="sxs-lookup"><span data-stu-id="50920-105">This package file can be copied to the computer that contains the corrupted drive and then used to recover the drive.</span></span> <span data-ttu-id="50920-106">若要实现此目的，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="50920-106">To accomplish this, use the following procedure.</span></span>

**<span data-ttu-id="50920-107">恢复损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="50920-107">To Recover a Corrupted Drive</span></span>**

1.  <span data-ttu-id="50920-108">打开 MBAM 管理网站。</span><span class="sxs-lookup"><span data-stu-id="50920-108">Open the MBAM administration website.</span></span>

2.  <span data-ttu-id="50920-109">从导航窗格中选择 "**驱动器恢复**"。</span><span class="sxs-lookup"><span data-stu-id="50920-109">Select **Drive Recovery** from the navigation pane.</span></span> <span data-ttu-id="50920-110">输入用户的域名和用户名、解锁驱动器的原因以及用户的恢复密码 ID。</span><span class="sxs-lookup"><span data-stu-id="50920-110">Enter the user’s domain name and user name, the reason for unlocking the drive, and the user’s recovery password ID.</span></span>

    <span data-ttu-id="50920-111">**注意** 如果您是技术支持管理员角色的成员，则无需输入用户的域名或用户名。</span><span class="sxs-lookup"><span data-stu-id="50920-111">**Note** If you are a member of the Help Desk Administrators role, you do not have to enter the user’s domain name or user name.</span></span>

     

3.  <span data-ttu-id="50920-112">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="50920-112">Click **Submit**.</span></span> <span data-ttu-id="50920-113">将显示恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="50920-113">The recovery key will be displayed.</span></span>

4.  <span data-ttu-id="50920-114">单击 "**保存**"，然后选择 "**恢复密钥包**"。</span><span class="sxs-lookup"><span data-stu-id="50920-114">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="50920-115">将在你的计算机上创建恢复密钥包。</span><span class="sxs-lookup"><span data-stu-id="50920-115">The recovery key package will be created on your computer.</span></span>

5.  <span data-ttu-id="50920-116">将恢复密钥包复制到包含损坏的驱动器的计算机。</span><span class="sxs-lookup"><span data-stu-id="50920-116">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

6.  <span data-ttu-id="50920-117">打开提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="50920-117">Open an elevated command prompt.</span></span> <span data-ttu-id="50920-118">若要执行此操作，请单击 "**开始**"，然后 `cmd` 在 "**搜索程序和文件**" 框中键入。</span><span class="sxs-lookup"><span data-stu-id="50920-118">To do this, click **Start** and type `cmd` in the **Search programs and files** box.</span></span> <span data-ttu-id="50920-119">在 "搜索结果" 列表中，右键单击**cmd.exe** ，然后选择 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="50920-119">In the search results list, right-click **cmd.exe** and select **Run as Administrator**.</span></span>

7.  <span data-ttu-id="50920-120">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="50920-120">At the command prompt, type the following:</span></span>

    `repair-bde <fixed drive> <corrupted drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="50920-121">**注意** 对于该 &lt; 命令中的固定驱动器 &gt; ，请指定一个可用的存储设备，该设备的可用空间等于或大于损坏的驱动器上的数据。</span><span class="sxs-lookup"><span data-stu-id="50920-121">**Note** For the &lt;fixed drive&gt; in the command, specify an available storage device that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="50920-122">已损坏的驱动器上的数据将恢复并移动到指定的固定驱动器。</span><span class="sxs-lookup"><span data-stu-id="50920-122">Data on the corrupted drive is recovered and moved to the specified fixed drive.</span></span>

     

## <span data-ttu-id="50920-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="50920-123">Related topics</span></span>


[<span data-ttu-id="50920-124">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="50920-124">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





