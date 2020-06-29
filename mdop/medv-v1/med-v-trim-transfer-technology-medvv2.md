---
title: MED-V 剪裁传输技术
description: MED-V 剪裁传输技术
author: dansimp
ms.assetid: 2744e855-a486-4028-9606-f0084794ec65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa11c8036954070bbff465a6ad78992fdd52f3a2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803918"
---
# <span data-ttu-id="1c4cf-103">MED-V 剪裁传输技术</span><span class="sxs-lookup"><span data-stu-id="1c4cf-103">MED-V Trim Transfer Technology</span></span>


## <a href="" id="bkmk-medvtrimtransfertechnology"></a>


<span data-ttu-id="1c4cf-104">MED-V 高级剪裁传输重复数据消除技术加速了通过 LAN 或 WAN 下载初始和更新的虚拟机映像，从而减少了将 MED-V 工作区虚拟机传输给多个最终用户所需的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-104">The MED-V advanced Trim Transfer de-duplication technology accelerates the download of initial and updated virtual machine images over the LAN or WAN, thereby reducing the network bandwidth needed to transport a MED-V workspace virtual machine to multiple end users.</span></span>

<span data-ttu-id="1c4cf-105">此突破性技术使用现有本地数据构建虚拟机映像，利用在许多情况下，大多数虚拟机（例如，系统和应用程序文件）在最终用户的磁盘上已存在的情况。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-105">This breakthrough technology uses existing local data to build the virtual machine image, leveraging the fact that in many cases, much of the virtual machine (for example, system and application files) already exists on the end user's disk.</span></span> <span data-ttu-id="1c4cf-106">例如，如果将包含 WindowsXP 的虚拟机传送给运行 WindowsXP 的本地副本的客户端，MED-V 将自动从传输中删除多余的 WindowsXP 元素。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-106">For example, if a virtual machine containing WindowsXP is delivered to a client running a local copy of WindowsXP, MED-V will automatically remove the redundant WindowsXP elements from the transfer.</span></span> <span data-ttu-id="1c4cf-107">为了确保有效且功能正常的工作区，MED-V 客户端加密在使用本地数据之前验证其完整性，以确保本地数据块完全按位与所需虚拟机映像中的相同。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-107">To ensure a valid and functional workspace, the MED-V client cryptographically verifies the integrity of local data before it is utilized, guaranteeing that the local blocks of data are absolutely bit-by-bit identical to those in the desired virtual machine image.</span></span> <span data-ttu-id="1c4cf-108">不匹配的块不会被使用。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-108">Blocks that do not match are not used.</span></span>

<span data-ttu-id="1c4cf-109">该过程的带宽高效且透明，并且在后台运行传输，从而利用未使用的网络和 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-109">The process is bandwidth-efficient and transparent, and transfers run in the background, utilizing unused network and CPU resources.</span></span>

<span data-ttu-id="1c4cf-110">当更新到新的映像版本时（例如，当管理员要分发新的应用程序或修补程序时），仅下载已更改（"增量"）的元素，而不是整个虚拟机，这将显著降低所需的网络带宽和传递时间。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-110">When updating to a new image version (for example, when administrators want to distribute a new application or patch), only the elements that have changed ("deltas") are downloaded, and not the entire virtual machine, significantly reducing the required network bandwidth and delivery time.</span></span>

<span data-ttu-id="1c4cf-111">你可以根据主机操作系统，配置在主机上索引哪些文件夹作为剪裁传输协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-111">You can configure which folders are indexed on the host as part of the Trim Transfer protocol, based on the host operating system.</span></span> <span data-ttu-id="1c4cf-112">这些设置在*ClientSettings.xml*文件中配置，可在**Servers\\Configuration Server\\**文件夹中找到。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-112">These settings are configured in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

<span data-ttu-id="1c4cf-113">应用新设置时，必须重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="1c4cf-113">When applying new settings, the service must be restarted.</span></span>

```xml
<HostIndexingXP type="System.String[]"> 
- <ArrayOfString>
<string>%WINDIR%</string> 
<string>%ProgramFiles%\Common Files</string> 
<string>%ProgramFiles%\Internet Explorer</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
<string>%ProgramFiles%\Windows NT</string> 
<string>%ProgramFiles%\Messenger</string> 
<string>%ProgramFiles%\Adobe</string> 
<string>%ProgramFiles%\Outlook Express</string> 
</ArrayOfString> 
</HostIndexingXP> 
- <HostIndexingVista type="System.String[]"> 
- <ArrayOfString> 
<string>%WINDIR%\MSAgent</string> 
<string>%WINDIR%\winsxs</string> 
<string>%WINDIR%\system</string> 
<string>%WINDIR%\system32</string> 
<string>%WINDIR%\Microsoft.NET</string> 
<string>%WINDIR%\SoftwareDistribution</string> 
<string>%WINDIR%\L2Schemas</string> 
<string>%WINDIR%\Cursors</string> 
<string>%WINDIR%\Boot</string> 
<string>%WINDIR%\Help</string> 
<string>%WINDIR%\assembly</string> 
<string>%WINDIR%\inf</string> 
<string>%WINDIR%\fonts</string> 
<string>%WINDIR%\Installer</string> 
<string>%WINDIR%\IME</string> 
<string>%WINDIR%\Resources</string> 
<string>%WINDIR%\servicing</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
</ArrayOfString> 
</HostIndexingVista>
```

 

 





