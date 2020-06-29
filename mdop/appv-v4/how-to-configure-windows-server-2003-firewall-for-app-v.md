---
title: 如何为 App-V 配置 Windows Server 2003 防火墙
description: 如何为 App-V 配置 Windows Server 2003 防火墙
author: dansimp
ms.assetid: 2c0e80f8-41e9-4164-ac83-b23b132b489a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af75479504b454851ee2efc7ca2638d2daf45053
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801532"
---
# <span data-ttu-id="e0dd2-103">如何为 App-V 配置 Windows Server 2003 防火墙</span><span class="sxs-lookup"><span data-stu-id="e0dd2-103">How to Configure Windows Server 2003 Firewall for App-V</span></span>


<span data-ttu-id="e0dd2-104">使用以下过程配置 app-v 的 WindowsServer 2003 防火墙。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-104">Use the following procedure to configure the WindowsServer 2003 firewall for App-V.</span></span>

**<span data-ttu-id="e0dd2-105">要为 App-v 配置 WindowsServer 2003 防火墙</span><span class="sxs-lookup"><span data-stu-id="e0dd2-105">To configure WindowsServer 2003 firewall for App-V</span></span>**

1.  <span data-ttu-id="e0dd2-106">在 "**控制面板**" 中，打开 " **Windows 防火墙**"。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-106">In **Control Panel**, open the **Windows Firewall**.</span></span>

    <span data-ttu-id="e0dd2-107">**注意** 如果在执行此步骤之前，服务器尚未配置为运行防火墙服务，系统将提示你启动防火墙服务。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-107">**Note** If the server has not been configured to run the firewall service before this step, you will be prompted to start the firewall service.</span></span>

     

2.  <span data-ttu-id="e0dd2-108">如果 .ICO 和 OSD 文件是通过 SMB 发布的，请确保已启用 "**例外**" 选项卡上的 "**文件和打印机共享**"。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-108">If ICO and OSD files are published through SMB, ensure that **File and Printer Sharing** is enabled on the **Exceptions** tab.</span></span>

    <span data-ttu-id="e0dd2-109">**注意** 如果通过管理服务器上的 HTTP/HTTPS 发布 .ICO 和 OSD 文件，可能需要为 HTTP 或 HTTPS 添加例外。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-109">**Note** If ICO and OSD files are published through HTTP/HTTPS on the Management Server, you might need to add an exception for HTTP or HTTPS.</span></span> <span data-ttu-id="e0dd2-110">如果托管 .ICO 和 OSD 文件的 IIS 服务器托管在独立于管理服务器的计算机上，则需要将例外添加到该计算机。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-110">If the IIS server hosting the ICO and OSD files is hosted on a computer separate from the Management Server, you need to add the exception to that computer.</span></span> <span data-ttu-id="e0dd2-111">为了最大程度地提高性能，建议你将 .ICO 和 OSD 文件托管在不同服务器上的管理服务器。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-111">To maximize performance, it is recommended that you host the ICO and OSD files on a separate server from the Management Server.</span></span>

     

3.  <span data-ttu-id="e0dd2-112">为 `sghwdsptr.exe` 管理服务器服务可执行文件添加程序例外。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-112">Add a program exception for `sghwdsptr.exe`, which is the Management Server service executable.</span></span> <span data-ttu-id="e0dd2-113">此可执行文件的默认路径为 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-113">The default path to this executable is `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin`.</span></span>

    <span data-ttu-id="e0dd2-114">**注意** 如果管理服务器使用 RTSP 进行通信，则你还必须添加的程序例外 `sghwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-114">**Note** If the Management Server uses RTSP for communication, you must also add a program exception for `sghwsvr.exe`.</span></span>

    <span data-ttu-id="e0dd2-115">对于 RTSPS 通信，app-v 流服务器需要程序异常 `sglwdsptr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-115">The App-V Streaming Server requires a program exception `sglwdsptr.exe` for RTSPS communication.</span></span> <span data-ttu-id="e0dd2-116">使用 RTSP 进行通信的 app-v 流式处理服务器还需要程序例外 `sglwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-116">The App-V Streaming Server that uses RTSP for communication also requires a program exception for `sglwsvr.exe`.</span></span>

     

4.  <span data-ttu-id="e0dd2-117">确保为每个异常配置正确的范围。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-117">Ensure that the proper scope is configured for each exception.</span></span> <span data-ttu-id="e0dd2-118">若要降低风险，请删除任何计算机，严格限制服务器将响应的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e0dd2-118">To reduce risk, remove any computer and strictly limit the IP addresses to which the server will respond.</span></span>

## <span data-ttu-id="e0dd2-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="e0dd2-119">Related topics</span></span>


[<span data-ttu-id="e0dd2-120">如何为 App-V 配置 Windows Server 2008 防火墙</span><span class="sxs-lookup"><span data-stu-id="e0dd2-120">How to Configure Windows Server 2008 Firewall for App-V</span></span>](how-to-configure-windows-server-2008-firewall-for-app-v.md)

 

 





