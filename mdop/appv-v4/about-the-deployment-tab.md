---
title: 关于“部署”选项卡
description: 关于“部署”选项卡
author: dansimp
ms.assetid: 12891798-baa4-45a5-b845-b9505ab95633
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 147e8b1057c789d97087461a585fa3f365089784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802427"
---
# <span data-ttu-id="4d6c7-103">关于“部署”选项卡</span><span class="sxs-lookup"><span data-stu-id="4d6c7-103">About the Deployment Tab</span></span>


<span data-ttu-id="4d6c7-104">使用应用程序虚拟化 Sequencer 控制台中的 "**部署**" 选项卡更改要序列化的应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-104">Use the **Deployment** tab in the Application Virtualization Sequencer Console to change the information for an application you are about to sequence.</span></span> <span data-ttu-id="4d6c7-105">此选项卡包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-105">This tab contains the following elements.</span></span>

## <span data-ttu-id="4d6c7-106">服务器 URL</span><span class="sxs-lookup"><span data-stu-id="4d6c7-106">Server URL</span></span>


<span data-ttu-id="4d6c7-107">使用**服务器 URL**控件指定虚拟应用程序服务器配置设置。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-107">Use the **Server URL** controls to specify the virtual application server configuration settings.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4d6c7-108">控件</span><span class="sxs-lookup"><span data-stu-id="4d6c7-108">Control</span></span></th>
<th align="left"><span data-ttu-id="4d6c7-109">描述</span><span class="sxs-lookup"><span data-stu-id="4d6c7-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4d6c7-110">协议</span><span class="sxs-lookup"><span data-stu-id="4d6c7-110">Protocol</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-111">使你能够选择将序列化应用程序包从虚拟应用程序服务器流式传输到应用程序虚拟化桌面客户端的协议。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-111">Enables you to select the protocol that will stream the sequenced application package from a virtual application server to an Application Virtualization Desktop Client.</span></span> <span data-ttu-id="4d6c7-112">可使用以下协议：</span><span class="sxs-lookup"><span data-stu-id="4d6c7-112">The following protocols are available:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="4d6c7-113">RTSP </strong> -默认情况下，它指定实时流协议控制支持虚拟化的应用程序的交换。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-113">RTSP</strong>—The default, it specifies that the Real-Time Streaming Protocol controls the exchange of virtualization-enabled applications.</span></span></p></li>
<li><p><strong><span data-ttu-id="4d6c7-114">RTSPS </strong> -指定具有传输层安全性的实时流协议控制序列化应用程序包的交换。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-114">RTSPS</strong>—Specifies that the Real-Time Streaming Protocol with Transport Layer Security controls the exchange of a sequenced application package.</span></span></p></li>
<li><p><strong><span data-ttu-id="4d6c7-115">文件 </strong> -指定序列化的应用程序将从文件共享流出。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-115">File</strong>—Specifies that the sequenced application will be streamed from a file share.</span></span></p></li>
<li><p><strong><span data-ttu-id="4d6c7-116">HTTPS </strong> —指定安全超文本传输协议控制程序包的交换。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-116">HTTPS</strong>—Specifies that Secure Hypertext Transport Protocol controls the exchange of a package.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4d6c7-117">主机</span><span class="sxs-lookup"><span data-stu-id="4d6c7-117">Hostname</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-118">使你能够选择虚拟应用程序服务器或虚拟应用程序服务器组前面的负载平衡器，这些服务器会将软件包传输到应用程序虚拟化桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-118">Enables you to select the virtual application server or the load balancer in front of a group of virtual application servers that will stream the software package to an Application Virtualization Desktop Client.</span></span> <span data-ttu-id="4d6c7-119">必须完成此项才能创建顺序应用程序包，但你可以从默认的% SFT_SOFTGRIDSERVER% 环境变量更改为虚拟应用程序服务器的实际主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-119">You must complete this item to create a sequenced application package, but you can change from the default %SFT_SOFTGRIDSERVER% environment variable to the actual hostname or IP address of a virtual application server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4d6c7-120">注意</span><span class="sxs-lookup"><span data-stu-id="4d6c7-120">Note</span></span></strong><br/><p><span data-ttu-id="4d6c7-121">如果您选择不指定静态主机名或 IP 地址，请在每个应用程序虚拟化桌面客户端上设置一个名为 SFT_SOFTGRIDSERVER 的环境变量。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-121">If you choose not to specify a static hostname or IP address, on each Application Virtualization Desktop Client you must set up an environment variable called SFT_SOFTGRIDSERVER.</span></span> <span data-ttu-id="4d6c7-122">它的值必须是虚拟应用程序服务器或负载平衡器的主机名或 IP 地址，该客户端&#39;s 应用程序源。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-122">Its value must be the hostname or IP address of the virtual application server or load balancer that is this client&#39;s source of applications.</span></span> <span data-ttu-id="4d6c7-123">你应该将此环境变量设置为系统变量，而不是用户变量。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-123">You should make this environment variable a system variable rather than a user variable.</span></span> <span data-ttu-id="4d6c7-124">在分配此变量期间，在此计算机上运行的任何应用程序虚拟化桌面客户端会话必须关闭，然后再打开，以便恢复的会话将知道它的新应用程序源。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-124">Any Application Virtualization Desktop Client session that is running on this computer during your assignment of this variable must be closed and then opened so that the resumed session will be aware of its new application source.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4d6c7-125">端口</span><span class="sxs-lookup"><span data-stu-id="4d6c7-125">Port</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-126">使你能够指定虚拟应用程序服务器或负载平衡器将在其上侦听应用程序虚拟化桌面客户端&#39;程序包请求的端口。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-126">Enables you to specify the port on which the virtual application server or the load balancer will listen for an Application Virtualization Desktop Client&#39;s request for the package.</span></span> <span data-ttu-id="4d6c7-127">创建程序包需要此信息，但你可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-127">This information is required to create a package, but you can change it.</span></span> <span data-ttu-id="4d6c7-128">默认端口为554。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-128">The default port is 554.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4d6c7-129">路径</span><span class="sxs-lookup"><span data-stu-id="4d6c7-129">Path</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-130">使你能够指定存储软件包的虚拟应用服务器上的相对路径，以及将从该程序包传送数据包的位置。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-130">Enables you to specify the relative path on the virtual application server where the software package is stored and from which it will be streamed.</span></span> <span data-ttu-id="4d6c7-131">如果将 SFT 文件存储在内容子目录中，则创建程序包需要此信息;否则，不需要此信息。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-131">This information is required to create a package if the SFT file will be stored in a subdirectory of CONTENT; otherwise, this information is not required.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4d6c7-132">操作系统</span><span class="sxs-lookup"><span data-stu-id="4d6c7-132">Operating Systems</span></span>


<span data-ttu-id="4d6c7-133">使用**操作系统**控件指定应用程序的操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-133">Use the **Operating Systems** controls to specify the application's operating system requirements.</span></span> <span data-ttu-id="4d6c7-134">如果应用程序虚拟化桌面客户端无法支持任何选定的操作系统，应用程序将无法启动。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-134">If an Application Virtualization Desktop Client cannot support any of the selected operating systems, the application will not start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4d6c7-135">控件</span><span class="sxs-lookup"><span data-stu-id="4d6c7-135">Controls</span></span></th>
<th align="left"><span data-ttu-id="4d6c7-136">描述</span><span class="sxs-lookup"><span data-stu-id="4d6c7-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4d6c7-137">可用操作系统</span><span class="sxs-lookup"><span data-stu-id="4d6c7-137">Available Operating Systems</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-138">显示可支持程序包中的应用程序的操作系统列表。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-138">Displays a list of operating systems that can support the applications in the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4d6c7-139">所选操作系统</span><span class="sxs-lookup"><span data-stu-id="4d6c7-139">Selected Operating Systems</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-140">显示支持程序包中的应用程序的选定操作系统的列表。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-140">Displays a list of selected operating systems that support the applications in the package.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4d6c7-141">输出选项</span><span class="sxs-lookup"><span data-stu-id="4d6c7-141">Output Options</span></span>


<span data-ttu-id="4d6c7-142">使用 "**输出" 选项**控件指定要安装的应用程序的输出选项。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-142">Use the **Output Options** controls to specify the output options for the application to be installed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4d6c7-143">控件</span><span class="sxs-lookup"><span data-stu-id="4d6c7-143">Control</span></span></th>
<th align="left"><span data-ttu-id="4d6c7-144">描述</span><span class="sxs-lookup"><span data-stu-id="4d6c7-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4d6c7-145">压缩算法</span><span class="sxs-lookup"><span data-stu-id="4d6c7-145">Compression Algorithm</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-146">用于选择压缩 SFT 文件以通过网络进行流式传输的方法。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-146">Use to select the method for compressing the SFT file for streaming across a network.</span></span> <span data-ttu-id="4d6c7-147">选择下列压缩方法之一：</span><span class="sxs-lookup"><span data-stu-id="4d6c7-147">Select one of the following compression methods:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="4d6c7-148">已压缩 </strong> —指定将 SFT 文件压缩为 <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)"> ZLIB </a> 格式。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-148">Compressed</strong>—Specifies that the SFT file be compressed in the <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)">ZLIB</a> format.</span></span></p></li>
<li><p><strong><span data-ttu-id="4d6c7-149">未压缩 </strong> -默认情况下; 指定不压缩 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-149">Not Compressed</strong>—The default; specifies that the SFT file not be compressed.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4d6c7-150">强制实施安全描述符</span><span class="sxs-lookup"><span data-stu-id="4d6c7-150">Enforce Security Descriptors</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-151">选择以在将程序包部署到客户端后，在其中执行应用程序的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-151">Select to enforce security descriptors of the applications in the package after it is deployed to the client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4d6c7-152">生成 Microsoft Windows Installer （MSI）程序包</span><span class="sxs-lookup"><span data-stu-id="4d6c7-152">Generate Microsoft Windows Installer (MSI) Package</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4d6c7-153">选择以使用 Windows Installer 安装或部署序列化的应用程序包。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-153">Select to install or deploy a sequenced application package with the Windows Installer.</span></span> <span data-ttu-id="4d6c7-154">如果你使用 sequencer 进行了任何更改，则 Windows Installer 文件中将不包含这些更改。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-154">If you have made any changes using the sequencer the changes will not be included with the Windows Installer file.</span></span> <span data-ttu-id="4d6c7-155">将始终使用保存在硬盘上的 sft 文件创建 Windows Installer 文件。</span><span class="sxs-lookup"><span data-stu-id="4d6c7-155">The Windows Installer file will always be created using the .sft file saved on the hard disk.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4d6c7-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d6c7-156">Related topics</span></span>


[<span data-ttu-id="4d6c7-157">如何更改部署属性</span><span class="sxs-lookup"><span data-stu-id="4d6c7-157">How to Change Deployment Properties</span></span>](how-to-change-deployment-properties.md)

[<span data-ttu-id="4d6c7-158">Sequencer 控制台</span><span class="sxs-lookup"><span data-stu-id="4d6c7-158">Sequencer Console</span></span>](sequencer-console.md)









