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
# UE-V 1.0 安全注意事项


本主题简要概述了帐户和组、日志文件以及有关 Microsoft 用户体验虚拟化（UE-V）的其他与安全相关的注意事项。 有关详细信息，请访问此处提供的链接。

## UE-V 配置的安全注意事项


**创建设置存储共享时，请将共享访问限制为需要访问的用户。**

由于设置程序包可能包含个人信息，因此应尽可能小心地对其进行保护。 在 "常规" 中，请执行下列操作：

-   将共享限制为仅需要访问的用户。 为在特定共享上具有重定向文件夹的用户创建安全组，并仅将访问权限限制为这些用户。

-   创建共享时，通过在共享名称后放置一个 $ 来隐藏共享。 这将隐藏来自休闲浏览器的共享，并且该共享在 "网上邻居" 中不可见。

-   仅向用户提供所需的最小权限量。 下表中显示了所需的权限。

    1.  为设置存储位置文件夹设置以下共享级（SMB）权限：

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">用户帐户</th>
        <th align="left">推荐的权限</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>所有人</p></td>
        <td align="left"><p>无权限</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V 的安全组</p></td>
        <td align="left"><p>完全控制</p></td>
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



### 使用 Windows Server 2003 或更高版本的服务器托管重定向的文件共享

用户设置程序包文件包含在客户端计算机和存储设置包的服务器之间传输的个人信息。 因此，你应该确保数据在网络上传输时受到保护。

用户设置数据易受以下潜在威胁的影响：在通过网络传输时截获数据;通过网络传输数据时对数据进行篡改;托管数据的服务器的欺骗和欺骗。

Windows Server 2003 和更高版本的多项功能可帮助保护用户数据：

-   **Kerberos** -kerberos 是所有版本的 windows 2000 和 windows Server 2003 及更高版本的标准。 Kerberos 确保网络资源的最高安全级别。 NTLM 仅对客户端进行身份验证;Kerberos 对服务器和客户端进行身份验证。 使用 NTLM 时，客户端不知道服务器是否有效。 如果客户与服务器交换个人文件，这一点尤其重要，漫游配置文件的情况下也是如此。 Kerberos 提供比 NTLM 更高的安全性。 Kerberos 在 Windows NT 版本4.0 或更早版本的操作系统上不可用。

-   **IPsec** -IP 安全协议（IPsec）提供网络级身份验证、数据完整性和加密。 IPsec 可确保以下内容：

    -   在途中，漫游数据可以安全地进行数据修改。

    -   漫游数据从截取、查看或复制中是安全的。

    -   未经身份验证的团体可以安全地访问漫游数据。

-   **SMB 签名**-服务器消息块（SMB）身份验证协议支持消息身份验证，防止活动消息和 "中间人" 攻击。 SMB 签名通过将数字签名放入每个 SMB 来提供此身份验证。 该数字签名随后由客户端和服务器验证。 若要使用 SMB 签名，必须首先在 SMB 客户端和 SMB 服务器上启用它或需要它。 请注意，SMB 签名会对性能产生负面影响。 它不会占用更多的网络带宽，但它会在客户端和服务器端使用更多的 CPU 周期。

### 始终对包含用户数据的卷使用 NTFS 文件系统

对于最安全的配置，请将承载 UE-V 设置文件的服务器配置为使用 NTFS 文件系统。 与 FAT 不同，NTFS 支持随机访问控制列表（Dacl）和系统访问控制列表（Sacl）。 Dacl 和 Sacl 控制哪些人可以对文件执行操作，以及哪些事件将触发对文件执行的操作的日志记录。

### <a href="" id="do-not-rely-on-efs-to-encrypt-users--files-when-transmitted-over-the-network"></a>不要依靠 EFS 在通过网络传输时对用户的文件进行加密

使用加密文件系统（EFS）加密远程服务器上的文件时，加密数据在通过网络传输期间不加密;它仅在存储在磁盘上时才被加密。

如果你的系统包含 Internet 协议安全（IPsec）或 Web 分布式创作和版本控制（WebDAV），则例外。 IPsec 通过 TCP/IP 网络传输时对数据进行加密。 如果在将文件复制或移动到服务器上的 WebDAV 文件夹之前对该文件进行了加密，则它将在传输期间和存储在服务器上时保持加密。

### 加密脱机文件缓存

默认情况下，脱机文件缓存受 Acl 保护在 NTFS 分区上，但对缓存进行加密进一步增强了本地计算机上的安全性。 默认情况下，本地计算机上的缓存未加密，因此从网络缓存的任何加密文件将不会在本地计算机上加密。 这可能会在某些环境中带来安全风险。

启用加密后，将加密脱机文件缓存中的所有文件。 这包括加密现有文件以及稍后添加的文件。 本地计算机上的缓存副本受到影响，但关联的网络副本不受影响。

可以通过以下两种方式之一对缓存进行加密：

1.  通过组策略。 -在组策略编辑器中启用 "**加密脱机文件缓存"** 设置，该设置位于 "计算机 Configuration\\Administrative Templates\\Network\\Offline" 文件中。

2.  手工. -在 Windows 资源管理器的 "命令" 菜单中选择 "工具" 和 "文件夹选项"。 选择 "脱机文件" 选项卡，然后选中 "**加密脱机文件以保护数据**" 复选框。

### 让 UE-V Agent 为每个用户创建文件夹

若要确保 UE-V 能够获得最佳效果，请仅在服务器上创建根目录共享，让 UE-V Agent 为每个用户创建文件夹。 UE-V 将使用相应的安全性创建这些用户文件夹。

此权限配置允许用户为设置存储创建文件夹。 UE-V agent 在用户的上下文中运行时创建并保护 settingspackage 文件夹。 用户接收 settingspackage 文件夹的完全控制。 其他用户不会继承对此文件夹的访问权限。 您无需创建和保护单个用户目录。 这将由在用户上下文中运行的代理自动完成。

**注意**  
在为设置存储共享使用 Windows 服务器时，可以配置其他安全。 UE-V 可以配置为验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。 若要启用其他安全，请使用以下命令：

1.  将名为 "RepositoryOwnerCheckEnabled" 的注册表项的 REG \ _DWORD 注册表项添加到 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` 。

2.  将注册表项值设置为1。

当此配置设置到位时，UE-V agent 将验证本地管理员的组或当前用户是否为 settingspackage 文件夹的所有者。 如果不是，则 UE-V agent 将不允许访问文件夹。



如果必须为用户创建文件夹并确保拥有正确的权限集。

我们强烈建议您不要 precreate 文件夹，而是允许 UE-V agent 为用户创建文件夹。

### <a href="" id="ensure-that-correct-permissions-are-set-when-storing-ue-v-settings-in-a-user-s-home-directory"></a>确保在用户的主目录中存储 UE-V 设置时设置正确的权限

如果将 UE-V 的设置重定向到用户的主目录，请确保针对你的组织正确设置了用户的主目录上的权限。

## 相关主题


[UE-V 1.0 的安全和隐私](security-and-privacy-for-ue-v-10.md)









