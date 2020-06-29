---
title: UE-V 2.x 的安全注意事项
description: UE-V 2.x 的安全注意事项
author: dansimp
ms.assetid: 9d5c3cae-9fcb-4dea-bd67-741b3dea63be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8e24e9e37de11053663bb90974fabf2ff369aeca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803613"
---
# <span data-ttu-id="d2444-103">UE-V 2.x 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="d2444-103">Security Considerations for UE-V 2.x</span></span>


<span data-ttu-id="d2444-104">本主题简要概述了帐户和组、日志文件，以及有关 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 的其他与安全相关的注意事项。</span><span class="sxs-lookup"><span data-stu-id="d2444-104">This topic contains a brief overview of accounts and groups, log files, and other security-related considerations for Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1.</span></span> <span data-ttu-id="d2444-105">有关详细信息，请访问此处提供的链接。</span><span class="sxs-lookup"><span data-stu-id="d2444-105">For more information, follow the links that are provided here.</span></span>

## <span data-ttu-id="d2444-106">UE-V 配置的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="d2444-106">Security considerations for UE-V configuration</span></span>


<span data-ttu-id="d2444-107">**重要提示** 创建设置存储共享时，请将共享访问限制为需要访问的用户。</span><span class="sxs-lookup"><span data-stu-id="d2444-107">**Important** When you create the settings storage share, limit the share access to users who require access.</span></span>

 

<span data-ttu-id="d2444-108">由于设置程序包可能包含个人信息，因此应尽可能小心地对其进行保护。</span><span class="sxs-lookup"><span data-stu-id="d2444-108">Because settings packages might contain personal information, you should take care to protect them as well as possible.</span></span> <span data-ttu-id="d2444-109">在 "常规" 中，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d2444-109">In general, do the following:</span></span>

-   <span data-ttu-id="d2444-110">将共享限制为仅需要访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="d2444-110">Restrict the share to only those users who require access.</span></span> <span data-ttu-id="d2444-111">为在特定共享上具有重定向文件夹的用户创建安全组，并将访问权限仅限于这些用户。</span><span class="sxs-lookup"><span data-stu-id="d2444-111">Create a security group for users who have redirected folders on a particular share and limit access to only those users.</span></span>

-   <span data-ttu-id="d2444-112">创建共享时，通过在共享名称后放置一个 $ 来隐藏共享。</span><span class="sxs-lookup"><span data-stu-id="d2444-112">When you create the share, hide the share by putting a $ after the share name.</span></span> <span data-ttu-id="d2444-113">此添加操作会隐藏来自休闲浏览器的共享，并且共享在 "网上邻居" 中不可见。</span><span class="sxs-lookup"><span data-stu-id="d2444-113">This addition hides the share from casual browsers, and the share is not visible in My Network Places.</span></span>

-   <span data-ttu-id="d2444-114">仅向用户提供他们必须拥有的最少量权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-114">Only give users the minimum amount of permissions that they must have.</span></span> <span data-ttu-id="d2444-115">下表显示了所需的权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-115">The following tables show the required permissions.</span></span>

    1.  <span data-ttu-id="d2444-116">为 "设置存储位置" 文件夹设置以下共享级别的 SMB 权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-116">Set the following share-level SMB permissions for the setting storage location folder.</span></span>

        | <span data-ttu-id="d2444-117">用户帐户</span><span class="sxs-lookup"><span data-stu-id="d2444-117">User account</span></span> | <span data-ttu-id="d2444-118">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="d2444-118">Recommended permissions</span></span> |
        | - | - |
        | <span data-ttu-id="d2444-119">所有人</span><span class="sxs-lookup"><span data-stu-id="d2444-119">Everyone</span></span> | <span data-ttu-id="d2444-120">无权限</span><span class="sxs-lookup"><span data-stu-id="d2444-120">No permissions</span></span> |
        |<span data-ttu-id="d2444-121">UE-V 的安全组</span><span class="sxs-lookup"><span data-stu-id="d2444-121">Security group of UE-V</span></span> | <span data-ttu-id="d2444-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="d2444-122">Full control</span></span> |

    2.  <span data-ttu-id="d2444-123">为 "设置存储位置" 文件夹设置以下 NTFS 文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-123">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

        | <span data-ttu-id="d2444-124">用户帐户</span><span class="sxs-lookup"><span data-stu-id="d2444-124">User account</span></span> | <span data-ttu-id="d2444-125">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="d2444-125">Recommended permissions</span></span> | <span data-ttu-id="d2444-126">文件夹</span><span class="sxs-lookup"><span data-stu-id="d2444-126">Folder</span></span> |
        | - | - | - |
        | <span data-ttu-id="d2444-127">创建者/所有者</span><span class="sxs-lookup"><span data-stu-id="d2444-127">Creator/Owner</span></span> | <span data-ttu-id="d2444-128">完全控制</span><span class="sxs-lookup"><span data-stu-id="d2444-128">Full control</span></span> | <span data-ttu-id="d2444-129">仅子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="d2444-129">Subfolders and files only</span></span>|
        | <span data-ttu-id="d2444-130">域管理员</span><span class="sxs-lookup"><span data-stu-id="d2444-130">Domain Admins</span></span> | <span data-ttu-id="d2444-131">完全控制</span><span class="sxs-lookup"><span data-stu-id="d2444-131">Full control</span></span> | <span data-ttu-id="d2444-132">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="d2444-132">This folder, subfolders, and files</span></span> |
        | <span data-ttu-id="d2444-133">UE-V 用户的安全组</span><span class="sxs-lookup"><span data-stu-id="d2444-133">Security group of UE-V users</span></span> | <span data-ttu-id="d2444-134">列出文件夹/读取数据、创建文件夹/附加数据</span><span class="sxs-lookup"><span data-stu-id="d2444-134">List folder/read data, create folders/append data</span></span> | <span data-ttu-id="d2444-135">仅此文件夹</span><span class="sxs-lookup"><span data-stu-id="d2444-135">This folder only</span></span> |
        | <span data-ttu-id="d2444-136">所有人</span><span class="sxs-lookup"><span data-stu-id="d2444-136">Everyone</span></span> | <span data-ttu-id="d2444-137">删除所有权限</span><span class="sxs-lookup"><span data-stu-id="d2444-137">Remove all permissions</span></span> | <span data-ttu-id="d2444-138">无权限</span><span class="sxs-lookup"><span data-stu-id="d2444-138">No permissions</span></span> |

    3.  <span data-ttu-id="d2444-139">为设置模板目录文件夹设置以下共享级别的 SMB 权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-139">Set the following share-level SMB permissions for the settings template catalog folder.</span></span>

        | <span data-ttu-id="d2444-140">用户帐户</span><span class="sxs-lookup"><span data-stu-id="d2444-140">User account</span></span> | <span data-ttu-id="d2444-141">推荐权限</span><span class="sxs-lookup"><span data-stu-id="d2444-141">Recommend permissions</span></span> |
        | - | - |
        | <span data-ttu-id="d2444-142">所有人</span><span class="sxs-lookup"><span data-stu-id="d2444-142">Everyone</span></span> | <span data-ttu-id="d2444-143">无权限</span><span class="sxs-lookup"><span data-stu-id="d2444-143">No permissions</span></span> |
        | <span data-ttu-id="d2444-144">域计算机</span><span class="sxs-lookup"><span data-stu-id="d2444-144">Domain computers</span></span> | <span data-ttu-id="d2444-145">读取权限级别</span><span class="sxs-lookup"><span data-stu-id="d2444-145">Read permission Levels</span></span> |
        | <span data-ttu-id="d2444-146">管理员</span><span class="sxs-lookup"><span data-stu-id="d2444-146">Administrators</span></span> | <span data-ttu-id="d2444-147">读/写权限级别</span><span class="sxs-lookup"><span data-stu-id="d2444-147">Read/write permission levels</span></span> |
         
    4.  <span data-ttu-id="d2444-148">为设置模板目录文件夹设置以下 NTFS 权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-148">Set the following NTFS permissions for the settings template catalog folder.</span></span>

        | <span data-ttu-id="d2444-149">用户帐户</span><span class="sxs-lookup"><span data-stu-id="d2444-149">User account</span></span> | <span data-ttu-id="d2444-150">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="d2444-150">Recommended permissions</span></span> | <span data-ttu-id="d2444-151">应用于</span><span class="sxs-lookup"><span data-stu-id="d2444-151">Apply to</span></span> |
        | - | - | - |
        | <span data-ttu-id="d2444-152">创建者/所有者</span><span class="sxs-lookup"><span data-stu-id="d2444-152">Creator/Owner</span></span> | <span data-ttu-id="d2444-153">完全控制</span><span class="sxs-lookup"><span data-stu-id="d2444-153">Full control</span></span> | <span data-ttu-id="d2444-154">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="d2444-154">This folder, subfolders, and files</span></span> |
        | <span data-ttu-id="d2444-155">域计算机</span><span class="sxs-lookup"><span data-stu-id="d2444-155">Domain Computers</span></span> | <span data-ttu-id="d2444-156">列出文件夹内容和读取权限</span><span class="sxs-lookup"><span data-stu-id="d2444-156">List folder contents and Read permissions</span></span> | <span data-ttu-id="d2444-157">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="d2444-157">This folder, subfolders, and files</span></span>|
        | <span data-ttu-id="d2444-158">所有人</span><span class="sxs-lookup"><span data-stu-id="d2444-158">Everyone</span></span>| <span data-ttu-id="d2444-159">无权限</span><span class="sxs-lookup"><span data-stu-id="d2444-159">No permissions</span></span>| <span data-ttu-id="d2444-160">无权限</span><span class="sxs-lookup"><span data-stu-id="d2444-160">No permissions</span></span>|
        | <span data-ttu-id="d2444-161">管理员</span><span class="sxs-lookup"><span data-stu-id="d2444-161">Administrators</span></span>| <span data-ttu-id="d2444-162">完全控制</span><span class="sxs-lookup"><span data-stu-id="d2444-162">Full Control</span></span>| <span data-ttu-id="d2444-163">此文件夹、子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="d2444-163">This folder, subfolders, and files</span></span>|

### <span data-ttu-id="d2444-164">在 WindowsServer2003 中使用 WindowsServer 来托管重定向的文件共享</span><span class="sxs-lookup"><span data-stu-id="d2444-164">Use WindowsServer as of WindowsServer2003 to host redirected file shares</span></span>

<span data-ttu-id="d2444-165">用户设置程序包文件包含在客户端计算机和存储设置包的服务器之间传输的个人信息。</span><span class="sxs-lookup"><span data-stu-id="d2444-165">User settings package files contain personal information that is transferred between the client computer and the server that stores the settings packages.</span></span> <span data-ttu-id="d2444-166">由于此过程，你应确保数据在通过网络传输时受到保护。</span><span class="sxs-lookup"><span data-stu-id="d2444-166">Because of this process, you should ensure that the data is protected while it travels over the network.</span></span>

<span data-ttu-id="d2444-167">用户设置数据易受以下潜在威胁的影响：在通过网络传输数据时对数据进行篡改，篡改通过网络传递的数据，以及托管数据的服务器的欺骗。</span><span class="sxs-lookup"><span data-stu-id="d2444-167">User settings data is vulnerable to these potential threats: interception of the data as it passes over the network, tampering with the data as it passes over the network, and spoofing of the server that hosts the data.</span></span>

<span data-ttu-id="d2444-168">在 Windows Server2003 中，Windows Server 操作系统的多项功能可帮助保护用户数据：</span><span class="sxs-lookup"><span data-stu-id="d2444-168">As of Windows Server2003, several features of the Windows Server operating system can help secure user data:</span></span>

-   <span data-ttu-id="d2444-169">**Kerberos** -kerberos 是所有版本的 Microsoft Windows2000Server 和 WindowsServer 的标准，从 WindowsServer2003 开始。</span><span class="sxs-lookup"><span data-stu-id="d2444-169">**Kerberos** - Kerberos is standard on all versions of Microsoft Windows2000Server and WindowsServer beginning with WindowsServer2003.</span></span> <span data-ttu-id="d2444-170">Kerberos 确保网络资源的最高安全级别。</span><span class="sxs-lookup"><span data-stu-id="d2444-170">Kerberos ensures the highest level of security to network resources.</span></span> <span data-ttu-id="d2444-171">NTLM 仅对客户端进行身份验证;Kerberos 对服务器和客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d2444-171">NTLM authenticates the client only; Kerberos authenticates the server and the client.</span></span> <span data-ttu-id="d2444-172">使用 NTLM 时，客户端不知道服务器是否有效。</span><span class="sxs-lookup"><span data-stu-id="d2444-172">When NTLM is used, the client does not know whether the server is valid.</span></span> <span data-ttu-id="d2444-173">如果客户与服务器交换个人文件（漫游用户配置文件的情况相同），则此差异尤其重要。</span><span class="sxs-lookup"><span data-stu-id="d2444-173">This difference is particularly important if the client exchanges personal files with the server, as is the case with Roaming User Profiles.</span></span> <span data-ttu-id="d2444-174">Kerberos 提供比 NTLM 更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="d2444-174">Kerberos provides better security than NTLM.</span></span> <span data-ttu-id="d2444-175">Kerberos 在 Microsoft WindowsNTServer 4.0 或更早版本的操作系统上不可用。</span><span class="sxs-lookup"><span data-stu-id="d2444-175">Kerberos is not available on the Microsoft WindowsNTServer 4.0 or earlier operating systems.</span></span>

-   <span data-ttu-id="d2444-176">**IPsec** -IP 安全协议（IPsec）提供网络级身份验证、数据完整性和加密。</span><span class="sxs-lookup"><span data-stu-id="d2444-176">**IPsec** - The IP Security Protocol (IPsec) provides network-level authentication, data integrity, and encryption.</span></span> <span data-ttu-id="d2444-177">IPsec 可确保以下内容：</span><span class="sxs-lookup"><span data-stu-id="d2444-177">IPsec ensures the following:</span></span>

    -   <span data-ttu-id="d2444-178">在数据是途中，漫游数据可以安全地进行数据修改。</span><span class="sxs-lookup"><span data-stu-id="d2444-178">Roamed data is safe from data modification while data is en route.</span></span>

    -   <span data-ttu-id="d2444-179">漫游数据从截取、查看或复制中是安全的。</span><span class="sxs-lookup"><span data-stu-id="d2444-179">Roamed data is safe from interception, viewing, or copying.</span></span>

    -   <span data-ttu-id="d2444-180">未经身份验证的方可以安全地访问漫游数据。</span><span class="sxs-lookup"><span data-stu-id="d2444-180">Roamed data is safe from access by unauthenticated parties.</span></span>

-   <span data-ttu-id="d2444-181">**SMB 签名**-服务器消息块（SMB）身份验证协议支持消息身份验证，从而阻止活动消息和 "中间人" 攻击。</span><span class="sxs-lookup"><span data-stu-id="d2444-181">**SMB Signing** - The Server Message Block (SMB) authentication protocol supports message authentication, which prevents active message and "man-in-the-middle" attacks.</span></span> <span data-ttu-id="d2444-182">SMB 签名通过将数字签名放入每个 SMB 来提供此身份验证。</span><span class="sxs-lookup"><span data-stu-id="d2444-182">SMB signing provides this authentication by placing a digital signature into each SMB.</span></span> <span data-ttu-id="d2444-183">该数字签名随后由客户端和服务器验证。</span><span class="sxs-lookup"><span data-stu-id="d2444-183">The digital signature is then verified by both the client and the server.</span></span> <span data-ttu-id="d2444-184">为了使用 SMB 签名，必须首先启用它，或者必须在 SMB 客户端和 SMB 服务器上都需要它。</span><span class="sxs-lookup"><span data-stu-id="d2444-184">In order to use SMB signing, you must first either enable it, or you must require it on both the SMB client and the SMB server.</span></span> <span data-ttu-id="d2444-185">请注意，SMB 签名会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="d2444-185">Note that the SMB signing imposes a performance penalty.</span></span> <span data-ttu-id="d2444-186">它不会占用更多的网络带宽，但它会在客户端和服务器端使用更多的 CPU 周期。</span><span class="sxs-lookup"><span data-stu-id="d2444-186">It does not consume any more network bandwidth, but it uses more CPU cycles on the client and server side.</span></span>

### <span data-ttu-id="d2444-187">始终对保留用户数据的卷使用 NTFS 文件系统</span><span class="sxs-lookup"><span data-stu-id="d2444-187">Always use the NTFS file system for volumes that hold user data</span></span>

<span data-ttu-id="d2444-188">对于最安全的配置，请将承载 UE-V 设置文件的服务器配置为使用 NTFS 文件系统。</span><span class="sxs-lookup"><span data-stu-id="d2444-188">For the most secure configuration, configure servers that host the UE-V settings files to use the NTFS file system.</span></span> <span data-ttu-id="d2444-189">与 FAT 文件系统不同，NTFS 支持随机访问控制列表（Dacl）和系统访问控制列表（Sacl）。</span><span class="sxs-lookup"><span data-stu-id="d2444-189">Unlike the FAT file system, NTFS supports Discretionary access control lists (DACLs) and system access control lists (SACLs).</span></span> <span data-ttu-id="d2444-190">Dacl 和 Sacl 控制哪些人可以对文件执行操作，以及哪些事件会触发对文件执行的操作的日志记录。</span><span class="sxs-lookup"><span data-stu-id="d2444-190">DACLs and SACLs control who can perform operations on a file and what events trigger the logging of actions that is performed on a file.</span></span>

### <span data-ttu-id="d2444-191">不要依靠 EFS 在通过网络传输用户文件时对其进行加密</span><span class="sxs-lookup"><span data-stu-id="d2444-191">Do not rely on EFS to encrypt user files when they are transmitted over the network</span></span>

<span data-ttu-id="d2444-192">使用加密文件系统（EFS）加密远程服务器上的文件时，加密数据在通过网络传输期间不加密;它仅在存储在磁盘上时才会被加密。</span><span class="sxs-lookup"><span data-stu-id="d2444-192">When you use the Encrypting File System (EFS) to encrypt files on a remote server, the encrypted data is not encrypted during transit over the network; it only becomes encrypted when it is stored on disk.</span></span>

<span data-ttu-id="d2444-193">当您的系统包含网际协议安全性（IPsec）或 Web 分布式创作和版本控制（WebDAV）时，此加密过程不适用。</span><span class="sxs-lookup"><span data-stu-id="d2444-193">This encryption process does not apply when your system includes Internet Protocol security (IPsec) or Web Distributed Authoring and Versioning (WebDAV).</span></span> <span data-ttu-id="d2444-194">IPsec 通过 TCP/IP 网络传输时对数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="d2444-194">IPsec encrypts data while it is transported over a TCP/IP network.</span></span> <span data-ttu-id="d2444-195">如果在将文件复制或移动到服务器上的 WebDAV 文件夹之前对其进行了加密，则该文件在传输期间和存储在服务器上时保持加密。</span><span class="sxs-lookup"><span data-stu-id="d2444-195">If the file is encrypted before it is copied or moved to a WebDAV folder on a server, it remains encrypted during the transmission and while it is stored on the server.</span></span>

### <span data-ttu-id="d2444-196">让 UE-V Agent 为每个用户创建文件夹</span><span class="sxs-lookup"><span data-stu-id="d2444-196">Let the UE-V Agent create folders for each user</span></span>

<span data-ttu-id="d2444-197">若要确保 UE-V 能够获得最佳效果，请仅在服务器上创建根目录共享，让 UE-V Agent 为每个用户创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2444-197">To ensure that UE-V works optimally, create only the root share on the server, and let the UE-V Agent create the folders for each user.</span></span> <span data-ttu-id="d2444-198">UE-V 使用相应的安全性创建这些用户文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2444-198">UE-V creates these user folders with the appropriate security.</span></span>

<span data-ttu-id="d2444-199">此权限配置使用户能够创建用于设置存储的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2444-199">This permission configuration enables users to create folders for settings storage.</span></span> <span data-ttu-id="d2444-200">UE-V Agent 在设置程序包文件夹的上下文中运行时创建并保护它。</span><span class="sxs-lookup"><span data-stu-id="d2444-200">The UE-V Agent creates and secures a settings package folder while it runs in the context of the user.</span></span> <span data-ttu-id="d2444-201">用户接收对其设置包文件夹的完全控制。</span><span class="sxs-lookup"><span data-stu-id="d2444-201">Users receive full control to their settings package folder.</span></span> <span data-ttu-id="d2444-202">其他用户不会继承对此文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-202">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="d2444-203">您不必创建和保护单个用户目录。</span><span class="sxs-lookup"><span data-stu-id="d2444-203">You do not have to create and secure individual user directories.</span></span> <span data-ttu-id="d2444-204">在用户上下文中运行的代理会自动执行。</span><span class="sxs-lookup"><span data-stu-id="d2444-204">The agent that runs in the context of the user does it automatically.</span></span>

<span data-ttu-id="d2444-205">**注意** 在将 Windows 服务器用于设置存储共享时，可以配置其他安全。</span><span class="sxs-lookup"><span data-stu-id="d2444-205">**Note** Additional security can be configured when a Windows Server is used for the settings storage share.</span></span> <span data-ttu-id="d2444-206">UE-V 可以配置为验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。</span><span class="sxs-lookup"><span data-stu-id="d2444-206">UE-V can be configured to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="d2444-207">若要启用其他安全，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="d2444-207">To enable additional security, use the following command:</span></span>

1.  <span data-ttu-id="d2444-208">将 REG \ _DWORD 注册表项 RepositoryOwnerCheckEnabled 添加到 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="d2444-208">Add the REG\_DWORD registry key RepositoryOwnerCheckEnabled to `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="d2444-209">将注册表项值设置为*1*。</span><span class="sxs-lookup"><span data-stu-id="d2444-209">Set the registry key value to *1*.</span></span>

<span data-ttu-id="d2444-210">当此配置设置到位时，UE-V Agent 将验证本地管理员组或当前用户是否为设置程序包文件夹的所有者。</span><span class="sxs-lookup"><span data-stu-id="d2444-210">When this configuration setting is in place, the UE-V Agent verifies that the local Administrators group or current user is the owner of the settings package folder.</span></span> <span data-ttu-id="d2444-211">如果不是，则 UE-V Agent 不会授予对文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-211">If not, then the UE-V Agent does not grant access to the folder.</span></span>

 

<span data-ttu-id="d2444-212">如果必须为用户创建文件夹，请确保您具有正确的权限集。</span><span class="sxs-lookup"><span data-stu-id="d2444-212">If you must create folders for the users, ensure that you have the correct permissions set.</span></span>

<span data-ttu-id="d2444-213">我们强烈建议您不要预创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2444-213">We strongly recommend that you do not pre-create folders.</span></span> <span data-ttu-id="d2444-214">而是让 UE-V Agent 为用户创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2444-214">Instead, let the UE-V Agent create the folder for the user.</span></span>

### <span data-ttu-id="d2444-215">确保在主目录或自定义目录中存储 UE-V 2 设置的正确权限</span><span class="sxs-lookup"><span data-stu-id="d2444-215">Ensure correct permissions to store UE-V 2 settings in a home directory or custom directory</span></span>

<span data-ttu-id="d2444-216">如果你将 UE-V 的设置重定向到用户的主目录或自定义 Active Directory （AD）目录，请确保针对你的组织正确设置目录的权限。</span><span class="sxs-lookup"><span data-stu-id="d2444-216">If you redirect UE-V settings to a user’s home directory or a custom Active Directory (AD) directory, ensure that the permissions on the directory are set appropriately for your organization.</span></span>






## <span data-ttu-id="d2444-217">相关主题</span><span class="sxs-lookup"><span data-stu-id="d2444-217">Related topics</span></span>


[<span data-ttu-id="d2444-218">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="d2444-218">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





