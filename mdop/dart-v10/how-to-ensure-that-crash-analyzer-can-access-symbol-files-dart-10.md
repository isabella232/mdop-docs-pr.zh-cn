---
title: 如何确保故障分析器可以访问符号文件
description: 如何确保故障分析器可以访问符号文件
author: dansimp
ms.assetid: 39e307bd-5d21-4e44-bed6-bf532f580775
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8e0ba2fa777039e1c6ffb91dd997438d8ea50616
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803202"
---
# <span data-ttu-id="16e83-103">如何确保故障分析器可以访问符号文件</span><span class="sxs-lookup"><span data-stu-id="16e83-103">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>


<span data-ttu-id="16e83-104">通常，调试信息存储在与程序分离的符号文件中。</span><span class="sxs-lookup"><span data-stu-id="16e83-104">Typically, debugging information is stored in a symbol file that is separate from the program.</span></span> <span data-ttu-id="16e83-105">调试已停止响应的应用程序时，您必须具有访问符号信息的权限。</span><span class="sxs-lookup"><span data-stu-id="16e83-105">You must have access to the symbol information when you debug an application that has stopped responding.</span></span>

<span data-ttu-id="16e83-106">当运行**崩溃分析器**时，将自动下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="16e83-106">Symbol files are automatically downloaded when you run **Crash Analyzer**.</span></span> <span data-ttu-id="16e83-107">如果计算机没有 Internet 连接或网络要求计算机访问 HTTP 代理服务器，则无法下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="16e83-107">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

**<span data-ttu-id="16e83-108">确保崩溃分析器可以访问符号文件</span><span class="sxs-lookup"><span data-stu-id="16e83-108">To ensure that Crash Analyzer can access symbol files</span></span>**

1.  **<span data-ttu-id="16e83-109">将转储文件复制到另一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="16e83-109">Copy the dump file to another computer.</span></span>** <span data-ttu-id="16e83-110">如果由于缺少 Internet 连接而无法下载符号，请将内存转储文件复制到具有 Internet 连接的计算机上，并在该计算机上运行独立的**故障分析器向导**。</span><span class="sxs-lookup"><span data-stu-id="16e83-110">If the symbols cannot be downloaded because of a lack of an Internet connection, copy the memory dump file to a computer that does have an Internet connection and run the stand-alone **Crash Analyzer Wizard** on that computer.</span></span>

2.  **<span data-ttu-id="16e83-111">从另一台计算机访问符号文件。</span><span class="sxs-lookup"><span data-stu-id="16e83-111">Access the symbol files from another computer.</span></span>** <span data-ttu-id="16e83-112">如果由于缺少 Internet 连接而无法下载符号，则可以从具有 Internet 连接的计算机下载符号，然后将其复制到没有 Internet 连接的计算机上，也可以将网络驱动器映射到本地网络上的符号可用的位置。</span><span class="sxs-lookup"><span data-stu-id="16e83-112">If the symbols cannot be downloaded because of a lack of an Internet connection, you can download the symbols from a computer that does have an Internet connection and then copy them to the computer that does not have an Internet connection, or you can map a network drive to a location where the symbols are available on the local network.</span></span> <span data-ttu-id="16e83-113">如果你在 Windows 恢复环境（WindowsRE）中运行**崩溃分析**程序，你可以在 Microsoft 诊断和恢复工具集（DaRT）10恢复映像上包括符号文件。</span><span class="sxs-lookup"><span data-stu-id="16e83-113">If you run the **Crash Analyzer** in a Windows Recovery Environment (WindowsRE), you can include the symbol files on the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image.</span></span>

3.  **<span data-ttu-id="16e83-114">通过 HTTP 代理服务器访问符号文件。</span><span class="sxs-lookup"><span data-stu-id="16e83-114">Access symbol files through an HTTP proxy server.</span></span>** <span data-ttu-id="16e83-115">如果无法下载符号，因为必须访问 HTTP 代理服务器，请使用以下步骤访问 HTTP 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="16e83-115">If the symbols cannot be downloaded because an HTTP proxy server must be accessed, use the following steps to access an HTTP proxy server.</span></span> <span data-ttu-id="16e83-116">在 DaRT 10 中，**故障分析器向导**在 "**指定符号文件位置**" 对话框页面上提供了一个设置，使用标签**代理服务器（可选，使用 "服务器：端口" 格式）** 标记。</span><span class="sxs-lookup"><span data-stu-id="16e83-116">In DaRT 10, the **Crash Analyzer Wizard** has a setting available on the **Specify Symbol Files Location** dialog page, marked with the label **Proxy server (optional, using the format "server:port")**.</span></span> <span data-ttu-id="16e83-117">可以使用此文本框指定代理服务器。</span><span class="sxs-lookup"><span data-stu-id="16e83-117">You can use this text box to specify a proxy server.</span></span> <span data-ttu-id="16e83-118">在 " \*\* &lt; 主机名 &gt; ： &lt; &gt; 端口\*\*" 窗体中输入代理地址，其中 &lt; **主机名** &gt; 是 DNS 名称或 IP 地址，而 &lt; **端口** &gt; 是 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="16e83-118">Enter the proxy address in the form **&lt;hostname&gt;:&lt;port&gt;**, where the &lt;**hostname**&gt; is a DNS name or IP address, and the &lt;**port**&gt; is a TCP port number.</span></span> <span data-ttu-id="16e83-119">可通过两种模式运行**崩溃分析器**。</span><span class="sxs-lookup"><span data-stu-id="16e83-119">There are two modes in which the **Crash Analyzer** can be run.</span></span> <span data-ttu-id="16e83-120">下面介绍如何在其中每种模式下使用代理设置：</span><span class="sxs-lookup"><span data-stu-id="16e83-120">Following is how you use the proxy setting in each of these modes:</span></span>

    -   <span data-ttu-id="16e83-121">**联机模式：** 在此模式下，如果 "代理服务器" 字段保留为空，向导将使用 "控制面板" 中的 "Internet 选项" 中的代理设置。</span><span class="sxs-lookup"><span data-stu-id="16e83-121">**Online mode:** In this mode, if the proxy server field is left blank, the wizard uses the proxy settings from Internet Options in Control Panel.</span></span> <span data-ttu-id="16e83-122">如果在提供的文本框中输入代理地址，则将使用该地址，并且它将覆盖 "Internet 选项" 中的设置。</span><span class="sxs-lookup"><span data-stu-id="16e83-122">If you enter a proxy address in the text box which is provided, that address will be used, and it will override the setting in the Internet Options.</span></span>

    -   <span data-ttu-id="16e83-123">Windows 恢复环境（WindowsRE）：从 "**诊断和恢复工具集**" 窗口运行**崩溃分析**程序时，没有默认的代理地址。</span><span class="sxs-lookup"><span data-stu-id="16e83-123">Windows Recovery Environment (WindowsRE): When you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window, there is no default proxy address.</span></span> <span data-ttu-id="16e83-124">如果计算机直接连接到 Internet，则不需要代理地址。</span><span class="sxs-lookup"><span data-stu-id="16e83-124">If the computer is directly connected to the Internet, a proxy address is not required.</span></span> <span data-ttu-id="16e83-125">因此，您可以在向导设置中将此字段保留为空。</span><span class="sxs-lookup"><span data-stu-id="16e83-125">Therefore, you can leave this field blank in the wizard setting.</span></span> <span data-ttu-id="16e83-126">如果计算机未直接连接到 Internet，并且它位于具有代理服务器的网络环境中，则必须在向导中将 "代理" 字段设置为 "访问符号存储区"。</span><span class="sxs-lookup"><span data-stu-id="16e83-126">If the computer is not directly connected to the Internet, and it is in a network environment that has a proxy server, you must set the proxy field in the wizard to access the symbol store.</span></span> <span data-ttu-id="16e83-127">可以从网络管理员处获取代理地址。</span><span class="sxs-lookup"><span data-stu-id="16e83-127">The proxy address can be obtained from the network administrator.</span></span> <span data-ttu-id="16e83-128">只有当公用符号存储连接到 Internet 时，设置代理服务器才很重要。</span><span class="sxs-lookup"><span data-stu-id="16e83-128">Setting the proxy server is important only when the public symbol store is connected to the Internet.</span></span> <span data-ttu-id="16e83-129">如果这些符号已在 DaRT 恢复映像上，或者如果它们在本地可用，则不需要设置代理服务器。</span><span class="sxs-lookup"><span data-stu-id="16e83-129">If the symbols are already on the DaRT recovery image, or if they are available locally, setting the proxy server is not required.</span></span>

## <span data-ttu-id="16e83-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="16e83-130">Related topics</span></span>


[<span data-ttu-id="16e83-131">使用故障分析器诊断系统故障</span><span class="sxs-lookup"><span data-stu-id="16e83-131">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[<span data-ttu-id="16e83-132">DaRT 10 的操作</span><span class="sxs-lookup"><span data-stu-id="16e83-132">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





