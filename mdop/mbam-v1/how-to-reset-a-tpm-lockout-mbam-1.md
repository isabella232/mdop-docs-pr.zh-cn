---
title: 如何重置 TPM 锁定
description: 如何重置 TPM 锁定
author: dansimp
ms.assetid: 91ec6666-1ae2-4e76-9459-ad65c405f639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde77a12e97d050777dac15d4106124ec111b3cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798166"
---
# <span data-ttu-id="f19f6-103">如何重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="f19f6-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="f19f6-104">Microsoft BitLocker 管理和监视（MBAM）的加密驱动器恢复功能包括数据捕获和存储以及管理受信任的平台模块（TPM）所需的工具的可用性。</span><span class="sxs-lookup"><span data-stu-id="f19f6-104">The Encrypted Drive Recovery feature of Microsoft BitLocker Administration and Monitoring (MBAM) encompasses both the capture and storage of data and the availability for tools that are required to manage the Trusted Platform Module (TPM).</span></span> <span data-ttu-id="f19f6-105">本主题介绍了如何在 "位 _admmon \ _tlanextref 管理" 网站中访问集中的密钥恢复数据系统。</span><span class="sxs-lookup"><span data-stu-id="f19f6-105">This topic covers how to access the centralized Key Recovery data system in the bit\_admmon\_tlanextref administration website.</span></span> <span data-ttu-id="f19f6-106">密钥恢复数据系统可以在提供计算机标识和关联的用户标识符时提供 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="f19f6-106">The Key Recovery data system can provide a TPM owner password file when the computer identity and the associated user identifier are supplied.</span></span>

<span data-ttu-id="f19f6-107">如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。</span><span class="sxs-lookup"><span data-stu-id="f19f6-107">A TPM lockout can occur if a user enters an incorrect PIN too many times.</span></span> <span data-ttu-id="f19f6-108">在 TPM 锁定之前，用户可以输入不正确的 PIN 的次数基于计算机制造商的规范。</span><span class="sxs-lookup"><span data-stu-id="f19f6-108">The number of times that a user can enter an incorrect PIN before the TPM lockout is based on the computer manufacturer's specification.</span></span>

**<span data-ttu-id="f19f6-109">重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="f19f6-109">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="f19f6-110">打开 MBAM 管理网站。</span><span class="sxs-lookup"><span data-stu-id="f19f6-110">Open the MBAM administration website.</span></span>

2.  <span data-ttu-id="f19f6-111">在导航窗格中，选择 "**管理 TPM**"。</span><span class="sxs-lookup"><span data-stu-id="f19f6-111">In the navigation pane, select **Manage TPM**.</span></span> <span data-ttu-id="f19f6-112">这将打开 "**管理 TPM** " 页面。</span><span class="sxs-lookup"><span data-stu-id="f19f6-112">This opens the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="f19f6-113">输入计算机和计算机名称的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="f19f6-113">Enter the fully qualified domain name (FQDN) for the computer and the computer name.</span></span> <span data-ttu-id="f19f6-114">输入用户的 Windows 登录域和用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="f19f6-114">Enter the user’s Windows Logon domain and the user’s user name.</span></span> <span data-ttu-id="f19f6-115">在 "**请求 TPM 所有者密码文件**" 下拉菜单的原因中，选择一个预定义选项。</span><span class="sxs-lookup"><span data-stu-id="f19f6-115">Select one of the predefined options in the **Reason for requesting TPM owner password file** drop-down menu.</span></span> <span data-ttu-id="f19f6-116">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="f19f6-116">Click **Submit**.</span></span>

4.  <span data-ttu-id="f19f6-117">MBAM 将返回下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="f19f6-117">MBAM will return one of the following:</span></span>

    -   <span data-ttu-id="f19f6-118">找不到匹配的 TPM 所有者密码文件时出现的错误消息</span><span class="sxs-lookup"><span data-stu-id="f19f6-118">An error message if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="f19f6-119">已提交计算机的 TPM 所有者密码文件</span><span class="sxs-lookup"><span data-stu-id="f19f6-119">The TPM owner password file for the submitted computer</span></span>

    <span data-ttu-id="f19f6-120">**注意** 如果您是高级帮助台用户，则不需要 "用户域" 和 "用户 ID" 字段。</span><span class="sxs-lookup"><span data-stu-id="f19f6-120">**Note** If you are an Advanced Helpdesk User, the user domain and user ID fields are not required.</span></span>

     

5.  <span data-ttu-id="f19f6-121">检索时，将显示所有者密码。</span><span class="sxs-lookup"><span data-stu-id="f19f6-121">Upon retrieval, the owner password is displayed.</span></span> <span data-ttu-id="f19f6-122">若要将此密码保存到 tpm 文件，请单击 "**保存**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f19f6-122">To save this password to a .tpm file, click the **Save** button.</span></span>

6.  <span data-ttu-id="f19f6-123">用户将运行 TPM 管理控制台并选择 "**重置 tpm 锁定**" 选项，并提供 tpm 所有者密码文件以重置 tpm 锁定。</span><span class="sxs-lookup"><span data-stu-id="f19f6-123">The user will run the TPM management console and select the **Reset TPM lockout** option and provide the TPM owner password file to reset the TPM lockout.</span></span>

## <span data-ttu-id="f19f6-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="f19f6-124">Related topics</span></span>


[<span data-ttu-id="f19f6-125">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="f19f6-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





