---
title: 如何重置 TPM 锁定
description: 如何重置 TPM 锁定
author: dansimp
ms.assetid: 20719ab2-18ae-4d3b-989a-539341909816
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6453473ec09c2033346c7e464c08dbfdfe046d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803691"
---
# <span data-ttu-id="30990-103">如何重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="30990-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="30990-104">Microsoft BitLocker 管理和监视（MBAM）的加密驱动器恢复功能包括数据捕获和存储以及管理受信任的平台模块（TPM）所需的工具的可用性。</span><span class="sxs-lookup"><span data-stu-id="30990-104">The Encrypted Drive Recovery feature of Microsoft BitLocker Administration and Monitoring (MBAM) encompasses both the capture and storage of data and the availability for tools that are needed to manage the Trusted Platform Module (TPM).</span></span> <span data-ttu-id="30990-105">本主题介绍了如何在 "管理和监视" 网站中访问集中的密钥恢复数据系统，该系统可以在提供计算机 ID 和关联的用户标识符时提供 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="30990-105">This topic covers how to access the centralized Key Recovery data system in the Administration and Monitoring website, which can provide a TPM owner password file when a computer ID and associated user identifier are supplied.</span></span>

<span data-ttu-id="30990-106">如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。</span><span class="sxs-lookup"><span data-stu-id="30990-106">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="30990-107">用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。</span><span class="sxs-lookup"><span data-stu-id="30990-107">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span>

<span data-ttu-id="30990-108">只有当 MBAM 拥有 TPM 时，才能重置 TPM 锁定。</span><span class="sxs-lookup"><span data-stu-id="30990-108">You can reset a TPM lockout only if MBAM owns the TPM.</span></span>

**<span data-ttu-id="30990-109">重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="30990-109">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="30990-110">打开 web 浏览器并导航到 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="30990-110">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="30990-111">在左侧导航窗格中，选择 "**管理 tpm** " 以打开 "**管理 tpm** " 页面。</span><span class="sxs-lookup"><span data-stu-id="30990-111">In the left navigation pane, select **Manage TPM** to open the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="30990-112">输入计算机和计算机名的完全限定的域名，并输入用户的 Windows 登录域和用户的用户名以检索 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="30990-112">Enter the fully qualified domain name for the computer and the computer name, and enter the user’s Windows logon domain and the user’s user name to retrieve the TPM owner password file.</span></span>

4.  <span data-ttu-id="30990-113">从 "**请求 TPM 所有者密码文件**" 列表的原因中，选择请求的原因，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="30990-113">From the **Reason for requesting TPM owner password file** list, select a reason for the request, and click **Submit**.</span></span>

    <span data-ttu-id="30990-114">MBAM 返回以下值之一：</span><span class="sxs-lookup"><span data-stu-id="30990-114">MBAM returns one of the following:</span></span>

    -   <span data-ttu-id="30990-115">如果找不到匹配的 TPM 所有者密码文件，则出现错误消息</span><span class="sxs-lookup"><span data-stu-id="30990-115">An error message, if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="30990-116">已提交计算机的 TPM 所有者密码文件</span><span class="sxs-lookup"><span data-stu-id="30990-116">The TPM owner password file for the submitted computer</span></span>

    **<span data-ttu-id="30990-117">注意</span><span class="sxs-lookup"><span data-stu-id="30990-117">Note</span></span>**  
    <span data-ttu-id="30990-118">如果您是高级帮助台用户，则不需要 "用户域" 和 "用户 ID" 字段。</span><span class="sxs-lookup"><span data-stu-id="30990-118">If you are an Advanced Helpdesk user, the user domain and user ID fields are not required.</span></span>



~~~
After the TPM owner password is retrieved, the owner password is displayed.
~~~

5. <span data-ttu-id="30990-119">若要将密码保存到 tpm 文件，请单击 "**保存**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="30990-119">To save the password to a .tpm file, click the **Save** button.</span></span>

   <span data-ttu-id="30990-120">用户将运行 TPM 管理控制台，选择 "**重置 tpm 锁定**" 选项，并提供 tpm 所有者密码文件以重置 tpm 锁定。</span><span class="sxs-lookup"><span data-stu-id="30990-120">The user will run the TPM management console, select the **Reset TPM lockout** option, and provide the TPM owner password file to reset the TPM lockout.</span></span>

   **<span data-ttu-id="30990-121">重要提示</span><span class="sxs-lookup"><span data-stu-id="30990-121">Important</span></span>**  
   <span data-ttu-id="30990-122">技术支持管理员不应将 TPM 哈希值或 TPM 所有者密码文件授予最终用户。</span><span class="sxs-lookup"><span data-stu-id="30990-122">Help Desk administrators should not give the TPM hash value or TPM owner password file to end users.</span></span> <span data-ttu-id="30990-123">TPM 信息不会更改，因此如果向最终用户提供该文件，则可能会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="30990-123">The TPM information does not change, so it could pose a security risk if the file is given to end users.</span></span>



## <span data-ttu-id="30990-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="30990-124">Related topics</span></span>


[<span data-ttu-id="30990-125">使用 MBAM 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="30990-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)









