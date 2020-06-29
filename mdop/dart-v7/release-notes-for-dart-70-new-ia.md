---
title: DaRT 7.0 发行说明
description: DaRT 7.0 发行说明
author: dansimp
ms.assetid: fad227d0-5c22-4efd-9187-0e5922f7250b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5114acfe5a46a2c78f722a2bb6394c0dbef55dd4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803233"
---
# <span data-ttu-id="1ad94-103">DaRT 7.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="1ad94-103">Release Notes for DaRT 7.0</span></span>


**<span data-ttu-id="1ad94-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="1ad94-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="1ad94-105">安装 Microsoft 诊断和恢复工具集（DaRT）7之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="1ad94-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT)7.</span></span>

## <span data-ttu-id="1ad94-106">关于 Microsoft 诊断和恢复工具集7。0</span><span class="sxs-lookup"><span data-stu-id="1ad94-106">About Microsoft Diagnostics and Recovery Toolset 7.0</span></span>


<span data-ttu-id="1ad94-107">这些发行说明包含成功安装 DaRT7 所需的信息，其中包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="1ad94-107">These release notes contain information that is required to successfully install DaRT7 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="1ad94-108">如果这些发行说明和其他 DaRT 平台文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="1ad94-108">If there is a difference between these release notes and other DaRT platform documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="1ad94-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="1ad94-109">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="1ad94-110">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="1ad94-110">About the Product Documentation</span></span>


<span data-ttu-id="1ad94-111">Microsoft 诊断和恢复工具集（DaRT）7的文档随产品和连接网站一起分发。</span><span class="sxs-lookup"><span data-stu-id="1ad94-111">Documentation for Microsoft Diagnostics and Recovery Toolset (DaRT)7 is distributed with the product and on the Connect site.</span></span>

<span data-ttu-id="1ad94-112">有关如何使用 DaRT7 中的工具的详细帮助，请参阅 "**诊断和恢复工具集**" 菜单上的可用帮助文件。</span><span class="sxs-lookup"><span data-stu-id="1ad94-112">For detailed help about how to use the tools in DaRT7, see the Help file available on the **Diagnostics and Recovery Toolset** menu.</span></span>

## <span data-ttu-id="1ad94-113">提供反馈</span><span class="sxs-lookup"><span data-stu-id="1ad94-113">Providing feedback</span></span>


<span data-ttu-id="1ad94-114">我们对 DaRT7 的反馈感兴趣。</span><span class="sxs-lookup"><span data-stu-id="1ad94-114">We are interested in your feedback on DaRT7.</span></span> <span data-ttu-id="1ad94-115">您可以向 dart7feedback@microsoft.com 发送反馈。</span><span class="sxs-lookup"><span data-stu-id="1ad94-115">You can send your feedback to dart7feedback@microsoft.com.</span></span> <span data-ttu-id="1ad94-116">此电子邮件地址不是支持频道，但你的反馈将帮助我们为这些工具计划将来的更改，以使其在将来更有用。</span><span class="sxs-lookup"><span data-stu-id="1ad94-116">This email address is not a support channel, but your feedback will help us to plan future changes for these tools to make them more useful to you in the future.</span></span>

## <span data-ttu-id="1ad94-117">防范安全漏洞和病毒</span><span class="sxs-lookup"><span data-stu-id="1ad94-117">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="1ad94-118">为了帮助防范安全漏洞和病毒，我们建议你为正在安装的任何新软件安装最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="1ad94-118">To help protect against security vulnerabilities and viruses, we recommend that you install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="1ad94-119">有关详细信息，请参阅[Microsoft Security](https://go.microsoft.com/fwlink/?LinkId=3482) （ https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="1ad94-119">For more information, see [Microsoft Security](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="1ad94-120">DaRT 7.0 的已知问题</span><span class="sxs-lookup"><span data-stu-id="1ad94-120">Known Issues with DaRT 7.0</span></span>


### <span data-ttu-id="1ad94-121">如果独立系统 Sweeper 处于打开状态，则无法启动 SFC 扫描</span><span class="sxs-lookup"><span data-stu-id="1ad94-121">SFC Scan cannot start if Standalone System Sweeper is open</span></span>

<span data-ttu-id="1ad94-122">如果独立系统 Sweeper 正在运行，则无法启动或运行 SFC 扫描，因为这两个工具之间存在资源冲突。</span><span class="sxs-lookup"><span data-stu-id="1ad94-122">If the Standalone System Sweeper is running, SFC Scan cannot start or run because of a resource conflict between the two tools.</span></span>

<span data-ttu-id="1ad94-123">**解决方法：** 在尝试打开或运行 "SFC 扫描" 工具之前，请关闭独立系统 Sweeper。</span><span class="sxs-lookup"><span data-stu-id="1ad94-123">**Workaround:** Close the Standalone System Sweeper before you try to open or run the SFC Scan tool.</span></span>

### <span data-ttu-id="1ad94-124">Unicode 字符可能不会显示在文件名中</span><span class="sxs-lookup"><span data-stu-id="1ad94-124">Unicode characters may not be displayed in file names</span></span>

<span data-ttu-id="1ad94-125">如果删除文件名中包含 Unicode 字符的文件并尝试使用 "文件还原" 工具还原文件，则不会找到该文件。</span><span class="sxs-lookup"><span data-stu-id="1ad94-125">If you delete a file that has Unicode characters in its file name and try to restore the file by using the File Restore tool, the file is not found.</span></span> <span data-ttu-id="1ad94-126">仅当你使用的语言不是用于创建恢复映像的 Windows DVD 语言之外的字符时，才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1ad94-126">This only occurs when you use characters from a language other than the language of the Windows DVD that was used to create the recovery image.</span></span>

<span data-ttu-id="1ad94-127">**解决方法：** 请确保 DaRT 使用的语言与尝试从中还原文件的操作系统所使用的语言相匹配。</span><span class="sxs-lookup"><span data-stu-id="1ad94-127">**Workaround:** Make sure that the language that is used by DaRT matches the language that is used by the operating system from which it is trying to restore files.</span></span>

### <span data-ttu-id="1ad94-128">DaRT 命令行安装可能会悄悄地失败</span><span class="sxs-lookup"><span data-stu-id="1ad94-128">DaRT command-line installation may fail silently</span></span>

<span data-ttu-id="1ad94-129">如果使用安静模式选项运行，则 DaRT 命令行安装将失败，除非使用提升的管理员权限运行。</span><span class="sxs-lookup"><span data-stu-id="1ad94-129">DaRT command-line installation fails silently if run with the quiet mode option unless it is run by using elevated administrator permissions.</span></span>

<span data-ttu-id="1ad94-130">**解决方法：** 使用提升的管理员权限运行命令行安装。</span><span class="sxs-lookup"><span data-stu-id="1ad94-130">**Workaround:** Run the command-line installation by using elevated administrator permissions.</span></span> <span data-ttu-id="1ad94-131">DaRT 安装支持命令行安装的典型 Windows 安装程序选项。</span><span class="sxs-lookup"><span data-stu-id="1ad94-131">DaRT installation supports the typical Windows Installer options for command-line installation.</span></span> <span data-ttu-id="1ad94-132">有关多个可用开关的详细信息，请参阅 Windows Installer 的[命令行选项](https://go.microsoft.com/fwlink/?LinkId=160689)。</span><span class="sxs-lookup"><span data-stu-id="1ad94-132">Please see [Command-Line Options](https://go.microsoft.com/fwlink/?LinkId=160689) for Windows Installer for more information about the several available switches.</span></span>

### <span data-ttu-id="1ad94-133">文件搜索无法将文件夹移动到不同的卷</span><span class="sxs-lookup"><span data-stu-id="1ad94-133">File Search cannot move a folder to a different volume</span></span>

<span data-ttu-id="1ad94-134">文件搜索应用程序不支持在卷之间移动文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ad94-134">Moving folders between volumes is not supported by the File Search application.</span></span> <span data-ttu-id="1ad94-135">如果你尝试在 "文件搜索" 中将文件夹移动到另一个卷，则会返回以下错误： "写入文件\* &lt; 文件名 &gt; \*时出错。</span><span class="sxs-lookup"><span data-stu-id="1ad94-135">If you try to move a folder to a different volume in File Search, the following error is returned: "An error occurred while writing the file *&lt;filename&gt;*.</span></span> <span data-ttu-id="1ad94-136">请确保驱动器有足够的空间，并且目标路径可访问。</span><span class="sxs-lookup"><span data-stu-id="1ad94-136">Make sure that the drive has sufficient space and the destination path is accessible."</span></span>

<span data-ttu-id="1ad94-137">**解决方法：** 使用资源管理器将文件夹移动到不同的卷。</span><span class="sxs-lookup"><span data-stu-id="1ad94-137">**Workaround:** Use the Explorer to move a folder to a different volume.</span></span>

### <span data-ttu-id="1ad94-138">在重新映射驱动器号的计算机上，某些数据可能不可用</span><span class="sxs-lookup"><span data-stu-id="1ad94-138">Some data may not be available on computers where the drive letters are remapped</span></span>

<span data-ttu-id="1ad94-139">此问题可能会在启用了 BitLocker 的计算机和多重引导计算机上发生。</span><span class="sxs-lookup"><span data-stu-id="1ad94-139">This problem can occur on BitLocker-enabled computers and multiboot computers.</span></span> <span data-ttu-id="1ad94-140">出现这种情况是因为脱机注册表中的某些信息具有硬编码的驱动器号，并且 DaRT 对相同的卷使用不同的字母。</span><span class="sxs-lookup"><span data-stu-id="1ad94-140">This occurs because some information in the offline registry has hard-coded drive letters, and DaRT uses different letters for the same volumes.</span></span> <span data-ttu-id="1ad94-141">典型效果包括无法访问注册表编辑器中的某些本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1ad94-141">The typical effects include not having access to certain local user accounts in Registry Editor.</span></span> <span data-ttu-id="1ad94-142">此外，某些工具可能无法获取依赖于解析文件路径的属性。</span><span class="sxs-lookup"><span data-stu-id="1ad94-142">Additionally, some tools may be unable to obtain properties that rely on resolving file paths.</span></span>

<span data-ttu-id="1ad94-143">**解决方法：** 在 DaRT 启动时使用该选项重新映射驱动器号。</span><span class="sxs-lookup"><span data-stu-id="1ad94-143">**Workaround:** Use the option to remap the drive letters as DaRT starts.</span></span> <span data-ttu-id="1ad94-144">这通常会将典型的驱动器号与预期的相符。</span><span class="sxs-lookup"><span data-stu-id="1ad94-144">This usually aligns the typical drive letters to what is expected.</span></span>

### <span data-ttu-id="1ad94-145">修补程序卸载可能不会卸载某些更新</span><span class="sxs-lookup"><span data-stu-id="1ad94-145">Hotfix Uninstall might not uninstall certain updates</span></span>

<span data-ttu-id="1ad94-146">无法卸载某些更新和服务包，因为它们被标记为 "不可安装"，或者因为它们需要从 Windows 7 内部卸载。</span><span class="sxs-lookup"><span data-stu-id="1ad94-146">Some updates and service packs cannot be uninstalled because they are marked as un-installable or because they need to be uninstalled from within Windows 7.</span></span> <span data-ttu-id="1ad94-147">在这些情况下，修复程序卸载工具可能会指示这些更新尚未卸载，即使它们尚未安装。</span><span class="sxs-lookup"><span data-stu-id="1ad94-147">In these instances, the Hotfix Uninstall tool may indicate that these updates have been uninstalled even though they have not been.</span></span>

<span data-ttu-id="1ad94-148">**解决方法：** 从 Windows 7 卸载这些有问题的更新。</span><span class="sxs-lookup"><span data-stu-id="1ad94-148">**Workaround:** Uninstall these problematic updates from Windows 7.</span></span>

### <span data-ttu-id="1ad94-149">磁盘擦除：无法删除具有跨区卷、带区卷或镜像卷的磁盘</span><span class="sxs-lookup"><span data-stu-id="1ad94-149">Disk Wipe: Disks with spanned volumes, striped volumes, or mirrored volumes cannot be deleted</span></span>

<span data-ttu-id="1ad94-150">磁盘擦除不支持删除跨一个或多个卷的跨区、镜像或带区的磁盘。</span><span class="sxs-lookup"><span data-stu-id="1ad94-150">Disk Wipe does not support deleting disks that are spanned, mirrored, or striped across one or more volumes.</span></span>

<span data-ttu-id="1ad94-151">**解决方法：** 单独选择并删除卷中的每个磁盘。</span><span class="sxs-lookup"><span data-stu-id="1ad94-151">**Workaround:** Select and delete each disk in the volume separately.</span></span>

## <span data-ttu-id="1ad94-152">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="1ad94-152">Release Notes Copyright Information</span></span>


<span data-ttu-id="1ad94-153">本文档 "按现状" 提供。</span><span class="sxs-lookup"><span data-stu-id="1ad94-153">This document is provided “as-is”.</span></span> <span data-ttu-id="1ad94-154">本文档中表示的信息和视图（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="1ad94-154">Information and views expressed in this document, including URL and other Internet website references, may change without notice.</span></span> <span data-ttu-id="1ad94-155">使用本文档的风险由你自己承担。</span><span class="sxs-lookup"><span data-stu-id="1ad94-155">You bear the risk of using it.</span></span>

<span data-ttu-id="1ad94-156">此处描述的一些示例仅供说明，并且是虚构的。</span><span class="sxs-lookup"><span data-stu-id="1ad94-156">Some examples depicted herein are provided for illustration only and are fictitious.</span></span><span data-ttu-id="1ad94-157">不打算或应该推断出真正的关联或连接。</span><span class="sxs-lookup"><span data-stu-id="1ad94-157">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="1ad94-158">本文档未向你提供针对任何 Microsoft 产品的任何知识产权的任何法律权限。</span><span class="sxs-lookup"><span data-stu-id="1ad94-158">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="1ad94-159">本文档是 Microsoft 的机密和专有文档。</span><span class="sxs-lookup"><span data-stu-id="1ad94-159">This document is confidential and proprietary to Microsoft.</span></span> <span data-ttu-id="1ad94-160">它是公开的，并且只能依照保密协议使用。</span><span class="sxs-lookup"><span data-stu-id="1ad94-160">It is disclosed and can be used only pursuant to a nondisclosure agreement.</span></span>



<span data-ttu-id="1ad94-161">Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer 和 Windows Vista 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="1ad94-161">Microsoft, Active Directory, ActiveSync, MS-DOS, Windows, WindowsServer, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="1ad94-162">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="1ad94-162">All other trademarks are property of their respective owners.</span></span>

## <span data-ttu-id="1ad94-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ad94-163">Related topics</span></span>


[<span data-ttu-id="1ad94-164">关于 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="1ad94-164">About DaRT 7.0</span></span>](about-dart-70-new-ia.md)

 

 





