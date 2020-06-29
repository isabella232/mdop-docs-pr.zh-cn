---
title: UE-V 1.0 安全注意事项
description: UE-V 1.0 安全注意事项
author: dansimp
ms.assetid: c5cdf9ff-dc96-4491-98e9-0eada898ffe0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b503028ae327f92759fe0f64f33fe0cffc62b05c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803480"
---
# <span data-ttu-id="44ff9-103">UE-V 1.0 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="44ff9-103">UE-V 1.0 Security Considerations</span></span>


<span data-ttu-id="44ff9-104">本主题简要概述了帐户和组、日志文件以及有关 Microsoft 用户体验虚拟化（UE-V）的其他与安全相关的注意事项。</span><span class="sxs-lookup"><span data-stu-id="44ff9-104">This topic contains a brief overview of accounts and groups, log files, and other security-related considerations for Microsoft User Experience Virtualization (UE-V).</span></span> <span data-ttu-id="44ff9-105">有关详细信息，请访问此处提供的链接。</span><span class="sxs-lookup"><span data-stu-id="44ff9-105">For more information, follow the links that are provided here.</span></span>

## <span data-ttu-id="44ff9-106">UE-V 配置的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="44ff9-106">Security considerations for UE-V configuration</span></span>


**<span data-ttu-id="44ff9-107">创建设置存储共享时，请将共享访问限制为需要访问的用户。</span><span class="sxs-lookup"><span data-stu-id="44ff9-107">When you create the settings storage share, limit the share access to users that need access.</span></span>**

<span data-ttu-id="44ff9-108">由于设置程序包可能包含个人信息，因此应尽可能小心地对其进行保护。</span><span class="sxs-lookup"><span data-stu-id="44ff9-108">Because settings packages may contain personal information, you should take care to protect them as well as possible.</span></span> <span data-ttu-id="44ff9-109">在 "常规" 中，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="44ff9-109">In general, do the following:</span></span>

-   <span data-ttu-id="44ff9-110">将共享限制为仅需要访问的用户。</span><span class="sxs-lookup"><span data-stu-id="44ff9-110">Restrict the share to only the users that need access.</span></span> <span data-ttu-id="44ff9-111">为在特定共享上具有重定向文件夹的用户创建安全组，并仅将访问权限限制为这些用户。</span><span class="sxs-lookup"><span data-stu-id="44ff9-111">Create a security group for users that have redirected folders on a particular share, and limit access to only those users.</span></span>

-   <span data-ttu-id="44ff9-112">创建共享时，通过在共享名称后放置一个 $ 来隐藏共享。</span><span class="sxs-lookup"><span data-stu-id="44ff9-112">When you create the share, hide the share by putting a $ after the share name.</span></span> <span data-ttu-id="44ff9-113">这将隐藏来自休闲浏览器的共享，并且该共享在 "网上邻居" 中不可见。</span><span class="sxs-lookup"><span data-stu-id="44ff9-113">This will hide the share from casual browsers, and the share will not be visible in My Network Places.</span></span>

-   <span data-ttu-id="44ff9-114">仅向用户提供所需的最小权限量。</span><span class="sxs-lookup"><span data-stu-id="44ff9-114">Only give users the minimum amount of permissions needed.</span></span> <span data-ttu-id="44ff9-115">下表中显示了所需的权限。</span><span class="sxs-lookup"><span data-stu-id="44ff9-115">The permissions needed are shown in the tables below.</span></span>

    1.  <span data-ttu-id="44ff9-116">为设置存储位置文件夹设置以下共享级（SMB）权限：</span><span class="sxs-lookup"><span data-stu-id="44ff9-116">Set the following share-level (SMB) permissions for the setting storage location folder:</span></span>

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><span data-ttu-id="44ff9-117">用户帐户</span><span class="sxs-lookup"><span data-stu-id="44ff9-117">User account</span></span></th>
        <th align="left"><span data-ttu-id="44ff9-118">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="44ff9-118">Recommended permissions</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="44ff9-119">所有人</span><span class="sxs-lookup"><span data-stu-id="44ff9-119">Everyone</span></span></p></td>
        <td align="left"><p><span data-ttu-id="44ff9-120">无权限</span><span class="sxs-lookup"><span data-stu-id="44ff9-120">No Permissions</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="44ff9-121">UE-V 的安全组</span><span class="sxs-lookup"><span data-stu-id="44ff9-121">Security group of UE-V</span></span></p></td>
        <td align="left"><p><span data-ttu-id="44ff9-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="44ff9-122">Full Control</span></span></p></td>
        </tr>
        </tbody>
        </table>



~~~
2.  Set the following NTFS permissions for the settings storage location folder:

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommended permissions</th>
    <th align="left">Folder</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Creator/Owner</p></td>
    <td align="left"><p>No Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Admins</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Security group of UE-V users</p></td>
    <td align="left"><p>List Folder/Read Data, Create Folders/Append Data</p></td>
    <td align="left"><p>This Folder Only</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>Remove all Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    </tbody>
    </table>



3.  Set the following share-level (SMB) permissions for the settings template catalog folder.

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommend permissions</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Computers</p></td>
    <td align="left"><p>Read Permission Levels</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Administrators</p></td>
    <td align="left"><p>Read/Write Permission Levels</p></td>
    </tr>
    </tbody>
    </table>



4.  Set the following NTFS permissions for the settings template catalog folder.

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommended permissions</th>
    <th align="left">Apply to</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Creator/Owner</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Computers</p></td>
    <td align="left"><p>List Folder Contents and Read</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>No Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Administrators</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    </tbody>
    </table>
~~~



### <span data-ttu-id="44ff9-123">使用 Windows Server 2003 或更高版本的服务器托管重定向的文件共享</span><span class="sxs-lookup"><span data-stu-id="44ff9-123">Use Windows Server 2003 or later servers to host redirected file shares</span></span>

<span data-ttu-id="44ff9-124">用户设置程序包文件包含在客户端计算机和存储设置包的服务器之间传输的个人信息。</span><span class="sxs-lookup"><span data-stu-id="44ff9-124">User settings package files contain personal information that is transferred between the client computer and the server that stores the settings packages.</span></span> <span data-ttu-id="44ff9-125">因此，你应该确保数据在网络上传输时受到保护。</span><span class="sxs-lookup"><span data-stu-id="44ff9-125">Because of this, you should ensure that the data is protected while it travels over the network.</span></span>

<span data-ttu-id="44ff9-126">用户设置数据易受以下潜在威胁的影响：在通过网络传输时截获数据;通过网络传输数据时对数据进行篡改;托管数据的服务器的欺骗和欺骗。</span><span class="sxs-lookup"><span data-stu-id="44ff9-126">User settings data is vulnerable to these potential threats: interception of the data as it passes over the network; tampering with the data as it passes over the network; and spoofing of the server that hosts the data.</span></span>

<span data-ttu-id="44ff9-127">Windows Server 2003 和更高版本的多项功能可帮助保护用户数据：</span><span class="sxs-lookup"><span data-stu-id="44ff9-127">Several features of Windows Server 2003 and above can help to secure user data:</span></span>

-   <span data-ttu-id="44ff9-128">**Kerberos** -kerberos 是所有版本的 windows 2000 和 windows Server 2003 及更高版本的标准。</span><span class="sxs-lookup"><span data-stu-id="44ff9-128">**Kerberos** - Kerberos is standard on all versions of Windows 2000 and Windows Server 2003 and later.</span></span> <span data-ttu-id="44ff9-129">Kerberos 确保网络资源的最高安全级别。</span><span class="sxs-lookup"><span data-stu-id="44ff9-129">Kerberos ensures the highest level of security to network resources.</span></span> <span data-ttu-id="44ff9-130">NTLM 仅对客户端进行身份验证;Kerberos 对服务器和客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="44ff9-130">NTLM authenticates the client only; Kerberos authenticates the server and the client.</span></span> <span data-ttu-id="44ff9-131">使用 NTLM 时，客户端不知道服务器是否有效。</span><span class="sxs-lookup"><span data-stu-id="44ff9-131">When NTLM is used, the client does not know whether the server is valid.</span></span> <span data-ttu-id="44ff9-132">如果客户与服务器交换个人文件，这一点尤其重要，漫游配置文件的情况下也是如此。</span><span class="sxs-lookup"><span data-stu-id="44ff9-132">This is particularly important if the client is exchanging personal files with the server, as is the case with Roaming Profiles.</span></span> <span data-ttu-id="44ff9-133">Kerberos 提供比 NTLM 更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="44ff9-133">Kerberos provides better security than NTLM.</span></span> <span data-ttu-id="44ff9-134">Kerberos 在 Windows NT 版本4.0 或更早版本的操作系统上不可用。</span><span class="sxs-lookup"><span data-stu-id="44ff9-134">Kerberos is not available on Windows NT version 4.0 or earlier operating systems.</span></span>

-   <span data-ttu-id="44ff9-135">**IPsec** -IP 安全协议（IPsec）提供网络级身份验证、数据完整性和加密。</span><span class="sxs-lookup"><span data-stu-id="44ff9-135">**IPsec** - The IP Security Protocol (IPsec) provides network-level authentication, data integrity, and encryption.</span></span> <span data-ttu-id="44ff9-136">IPsec 可确保以下内容：</span><span class="sxs-lookup"><span data-stu-id="44ff9-136">IPsec ensures the following:</span></span>

    -   <span data-ttu-id="44ff9-137">在途中，漫游数据可以安全地进行数据修改。</span><span class="sxs-lookup"><span data-stu-id="44ff9-137">Roamed data is safe from data modification while en route.</span></span>

    -   <span data-ttu-id="44ff9-138">漫游数据从截取、查看或复制中是安全的。</span><span class="sxs-lookup"><span data-stu-id="44ff9-138">Roamed data is safe from interception, viewing, or copying.</span></span>

    -   <span data-ttu-id="44ff9-139">未经身份验证的团体可以安全地访问漫游数据。</span><span class="sxs-lookup"><span data-stu-id="44ff9-139">Roamed data is safe from being accessed by unauthenticated parties.</span></span>

-   <span data-ttu-id="44ff9-140">**SMB 签名**-服务器消息块（SMB）身份验证协议支持消息身份验证，防止活动消息和 "中间人" 攻击。</span><span class="sxs-lookup"><span data-stu-id="44ff9-140">**SMB Signing** - The Server Message Block (SMB) authentication protocol supports message authentication which prevents active message and "man-in-the-middle" attacks.</span></span> <span data-ttu-id="44ff9-141">SMB 签名通过将数字签名放入每个 SMB 来提供此身份验证。</span><span class="sxs-lookup"><span data-stu-id="44ff9-141">SMB signing provides this authentication by placing a digital signature into each SMB.</span></span> <span data-ttu-id="44ff9-142">该数字签名随后由客户端和服务器验证。</span><span class="sxs-lookup"><span data-stu-id="44ff9-142">The digital signature is then verified by both the client and the server.</span></span> <span data-ttu-id="44ff9-143">若要使用 SMB 签名，必须首先在 SMB 客户端和 SMB 服务器上启用它或需要它。</span><span class="sxs-lookup"><span data-stu-id="44ff9-143">In order to use SMB signing, you must first either enable it or require it on both the SMB client and the SMB server.</span></span> <span data-ttu-id="44ff9-144">请注意，SMB 签名会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="44ff9-144">Note that the SMB signing imposes a performance penalty.</span></span> <span data-ttu-id="44ff9-145">它不会占用更多的网络带宽，但它会在客户端和服务器端使用更多的 CPU 周期。</span><span class="sxs-lookup"><span data-stu-id="44ff9-145">It does not consume any more network bandwidth, but it uses more CPU cycles on the client and server side.</span></span>

### <span data-ttu-id="44ff9-146">始终对包含用户数据的卷使用 NTFS 文件系统</span><span class="sxs-lookup"><span data-stu-id="44ff9-146">Always use the NTFS File system for volumes holding users data</span></span>

<span data-ttu-id="44ff9-147">对于最安全的配置，请将承载 UE-V 设置文件的服务器配置为使用 NTFS 文件系统。</span><span class="sxs-lookup"><span data-stu-id="44ff9-147">For the most secure configuration, configure servers that host the UE-V settings files to use the NTFS File System.</span></span> <span data-ttu-id="44ff9-148">与 FAT 不同，NTFS 支持随机访问控制列表（Dacl）和系统访问控制列表（Sacl）。</span><span class="sxs-lookup"><span data-stu-id="44ff9-148">Unlike FAT, NTFS supports Discretionary access control lists (DACLs) and system access control lists (SACLs).</span></span> <span data-ttu-id="44ff9-149">Dacl 和 Sacl 控制哪些人可以对文件执行操作，以及哪些事件将触发对文件执行的操作的日志记录。</span><span class="sxs-lookup"><span data-stu-id="44ff9-149">DACLs and SACLs control who can perform operations on a file and what events will trigger the logging of actions performed on a file.</span></span>

### <a href="" id="do-not-rely-on-efs-to-encrypt-users--files-when-transmitted-over-the-network"></a><span data-ttu-id="44ff9-150">不要依靠 EFS 在通过网络传输时对用户的文件进行加密</span><span class="sxs-lookup"><span data-stu-id="44ff9-150">Do not rely on EFS to encrypt users’ files when transmitted over the network</span></span>

<span data-ttu-id="44ff9-151">使用加密文件系统（EFS）加密远程服务器上的文件时，加密数据在通过网络传输期间不加密;它仅在存储在磁盘上时才被加密。</span><span class="sxs-lookup"><span data-stu-id="44ff9-151">When you use Encrypting File System (EFS) to encrypt files on a remote server, the encrypted data is not encrypted during transit over the network; It only becomes encrypted when stored on disk.</span></span>

<span data-ttu-id="44ff9-152">如果你的系统包含 Internet 协议安全（IPsec）或 Web 分布式创作和版本控制（WebDAV），则例外。</span><span class="sxs-lookup"><span data-stu-id="44ff9-152">The exceptions to this are when your system includes Internet Protocol security (IPsec) or Web Distributed Authoring and Versioning (WebDAV).</span></span> <span data-ttu-id="44ff9-153">IPsec 通过 TCP/IP 网络传输时对数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="44ff9-153">IPsec encrypts data while it is transported over a TCP/IP network.</span></span> <span data-ttu-id="44ff9-154">如果在将文件复制或移动到服务器上的 WebDAV 文件夹之前对该文件进行了加密，则它将在传输期间和存储在服务器上时保持加密。</span><span class="sxs-lookup"><span data-stu-id="44ff9-154">If the file is encrypted before being copied or moved to a WebDAV folder on a server, it will remain encrypted during the transmission and while it is stored on the server.</span></span>

### <span data-ttu-id="44ff9-155">加密脱机文件缓存</span><span class="sxs-lookup"><span data-stu-id="44ff9-155">Encrypt the Offline Files cache</span></span>

<span data-ttu-id="44ff9-156">默认情况下，脱机文件缓存受 Acl 保护在 NTFS 分区上，但对缓存进行加密进一步增强了本地计算机上的安全性。</span><span class="sxs-lookup"><span data-stu-id="44ff9-156">By default, the Offline Files cache is protected on NTFS partitions by ACLs, but encrypting the cache further enhances security on a local computer.</span></span> <span data-ttu-id="44ff9-157">默认情况下，本地计算机上的缓存未加密，因此从网络缓存的任何加密文件将不会在本地计算机上加密。</span><span class="sxs-lookup"><span data-stu-id="44ff9-157">By default, the cache on the local computer is not encrypted, so any encrypted files cached from the network will not be encrypted on the local computer.</span></span> <span data-ttu-id="44ff9-158">这可能会在某些环境中带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="44ff9-158">This may pose a security risk in some environments.</span></span>

<span data-ttu-id="44ff9-159">启用加密后，将加密脱机文件缓存中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="44ff9-159">When encryption is enabled, all files in the Offline Files cache are encrypted.</span></span> <span data-ttu-id="44ff9-160">这包括加密现有文件以及稍后添加的文件。</span><span class="sxs-lookup"><span data-stu-id="44ff9-160">This includes encrypting existing files as well as files that are added later.</span></span> <span data-ttu-id="44ff9-161">本地计算机上的缓存副本受到影响，但关联的网络副本不受影响。</span><span class="sxs-lookup"><span data-stu-id="44ff9-161">The cached copy on the local computer is affected, but the associated network copy is not.</span></span>

<span data-ttu-id="44ff9-162">可以通过以下两种方式之一对缓存进行加密：</span><span class="sxs-lookup"><span data-stu-id="44ff9-162">The cache can be encrypted in one of two ways:</span></span>

1.  <span data-ttu-id="44ff9-163">通过组策略。</span><span class="sxs-lookup"><span data-stu-id="44ff9-163">Via Group Policy.</span></span> <span data-ttu-id="44ff9-164">-在组策略编辑器中启用 "**加密脱机文件缓存"** 设置，该设置位于 "计算机 Configuration\\Administrative Templates\\Network\\Offline" 文件中。</span><span class="sxs-lookup"><span data-stu-id="44ff9-164">- Enable the **Encrypt the Offline Files Cache** setting, located at Computer Configuration\\Administrative Templates\\Network\\Offline Files, in the Group Policy editor.</span></span>

2.  <span data-ttu-id="44ff9-165">手工.</span><span class="sxs-lookup"><span data-stu-id="44ff9-165">Manually.</span></span> <span data-ttu-id="44ff9-166">-在 Windows 资源管理器的 "命令" 菜单中选择 "工具" 和 "文件夹选项"。</span><span class="sxs-lookup"><span data-stu-id="44ff9-166">- Select Tools and then Folder Options in the command menu of Windows Explorer.</span></span> <span data-ttu-id="44ff9-167">选择 "脱机文件" 选项卡，然后选中 "**加密脱机文件以保护数据**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="44ff9-167">Select the Offline Files tab, and then select the **Encrypt offline files to secure data** check box.</span></span>

### <span data-ttu-id="44ff9-168">让 UE-V Agent 为每个用户创建文件夹</span><span class="sxs-lookup"><span data-stu-id="44ff9-168">Let the UE-V Agent create folders for each user</span></span>

<span data-ttu-id="44ff9-169">若要确保 UE-V 能够获得最佳效果，请仅在服务器上创建根目录共享，让 UE-V Agent 为每个用户创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="44ff9-169">To ensure that UE-V works optimally, create only the root share on the server, and let the UE-V Agent create the folders for each user.</span></span> <span data-ttu-id="44ff9-170">UE-V 将使用相应的安全性创建这些用户文件夹。</span><span class="sxs-lookup"><span data-stu-id="44ff9-170">UE-V will create these user folders with the appropriate security.</span></span>

<span data-ttu-id="44ff9-171">此权限配置允许用户为设置存储创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="44ff9-171">This permission configuration allows users to create folders for settings storage.</span></span> <span data-ttu-id="44ff9-172">UE-V agent 在用户的上下文中运行时创建并保护 settingspackage 文件夹。</span><span class="sxs-lookup"><span data-stu-id="44ff9-172">The UE-V agent creates and secures a settingspackage folder while running in the context of the user.</span></span> <span data-ttu-id="44ff9-173">用户接收 settingspackage 文件夹的完全控制。</span><span class="sxs-lookup"><span data-stu-id="44ff9-173">The user receives full control to their settingspackage folder.</span></span> <span data-ttu-id="44ff9-174">其他用户不会继承对此文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="44ff9-174">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="44ff9-175">您无需创建和保护单个用户目录。</span><span class="sxs-lookup"><span data-stu-id="44ff9-175">You do not need to create and secure individual user directories.</span></span> <span data-ttu-id="44ff9-176">这将由在用户上下文中运行的代理自动完成。</span><span class="sxs-lookup"><span data-stu-id="44ff9-176">This will be done automatically by the agent that runs in the context of the user.</span></span>

**<span data-ttu-id="44ff9-177">注意</span><span class="sxs-lookup"><span data-stu-id="44ff9-177">Note</span></span>**  
<span data-ttu-id="44ff9-178">在为设置存储共享使用 Windows 服务器时，可以配置其他安全。</span><span class="sxs-lookup"><span data-stu-id="44ff9-178">Additional security can be configured when a Windows server is utilized for the settings storage share.</span></span> <span data-ttu-id="44ff9-179">UE-V 可以配置为验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。</span><span class="sxs-lookup"><span data-stu-id="44ff9-179">UE-V can be configured to verify that either the local administrator's group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="44ff9-180">若要启用其他安全，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="44ff9-180">To enable additional security use the following command:</span></span>

1.  <span data-ttu-id="44ff9-181">将名为 "RepositoryOwnerCheckEnabled" 的注册表项的 REG \ _DWORD 注册表项添加到 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="44ff9-181">Add a REG\_DWORD registry key named "RepositoryOwnerCheckEnabled" to `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="44ff9-182">将注册表项值设置为1。</span><span class="sxs-lookup"><span data-stu-id="44ff9-182">Set registry key value to 1.</span></span>

<span data-ttu-id="44ff9-183">当此配置设置到位时，UE-V agent 将验证本地管理员的组或当前用户是否为 settingspackage 文件夹的所有者。</span><span class="sxs-lookup"><span data-stu-id="44ff9-183">When this configuration setting is in place, the UE-V agent verifies that the local administrator’s group or current user is the owner of the settingspackage folder.</span></span> <span data-ttu-id="44ff9-184">如果不是，则 UE-V agent 将不允许访问文件夹。</span><span class="sxs-lookup"><span data-stu-id="44ff9-184">If not, then the UE-V agent will not allow access to the folder.</span></span>



<span data-ttu-id="44ff9-185">如果必须为用户创建文件夹并确保拥有正确的权限集。</span><span class="sxs-lookup"><span data-stu-id="44ff9-185">If you must create folders for the users and ensure that you have the correct permissions set.</span></span>

<span data-ttu-id="44ff9-186">我们强烈建议您不要 precreate 文件夹，而是允许 UE-V agent 为用户创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="44ff9-186">We strongly recommend that you do not precreate folders and that instead, you allow the UE-V agent to create the folder for the user.</span></span>

### <a href="" id="ensure-that-correct-permissions-are-set-when-storing-ue-v-settings-in-a-user-s-home-directory"></a><span data-ttu-id="44ff9-187">确保在用户的主目录中存储 UE-V 设置时设置正确的权限</span><span class="sxs-lookup"><span data-stu-id="44ff9-187">Ensure that correct permissions are set when storing UE-V settings in a user’s home directory</span></span>

<span data-ttu-id="44ff9-188">如果将 UE-V 的设置重定向到用户的主目录，请确保针对你的组织正确设置了用户的主目录上的权限。</span><span class="sxs-lookup"><span data-stu-id="44ff9-188">If you redirect UE-V settings to a user’s home directory, be sure that the permissions on the user's home directory are set appropriately for your organization.</span></span>

## <span data-ttu-id="44ff9-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="44ff9-189">Related topics</span></span>


[<span data-ttu-id="44ff9-190">UE-V 1.0 的安全和隐私</span><span class="sxs-lookup"><span data-stu-id="44ff9-190">Security and Privacy for UE-V 1.0</span></span>](security-and-privacy-for-ue-v-10.md)









