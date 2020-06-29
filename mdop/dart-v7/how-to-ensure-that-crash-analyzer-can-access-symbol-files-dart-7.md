---
title: 如何确保故障分析器可以访问符号文件
description: 如何确保故障分析器可以访问符号文件
author: dansimp
ms.assetid: 150a2f88-68a5-40eb-8471-e5008488ab6e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db56bb21ad885d1e3aa73bcbd922a7e8bde77080
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803241"
---
# <span data-ttu-id="b4396-103">如何确保故障分析器可以访问符号文件</span><span class="sxs-lookup"><span data-stu-id="b4396-103">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>


<span data-ttu-id="b4396-104">通常，调试信息存储在与可执行文件不同的符号文件中。</span><span class="sxs-lookup"><span data-stu-id="b4396-104">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="b4396-105">当你调试已停止响应的应用程序时（例如，如果该应用程序崩溃），你必须具有访问符号信息的权限。</span><span class="sxs-lookup"><span data-stu-id="b4396-105">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="b4396-106">当运行 Microsoft 诊断和恢复工具集（DaRT）7故障分析器时，将自动下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="b4396-106">Symbol files are automatically downloaded when you run the Microsoft Diagnostics and Recovery Toolset (DaRT)7 Crash Analyzer.</span></span> <span data-ttu-id="b4396-107">如果计算机没有 Internet 连接或网络要求计算机访问 HTTP 代理服务器，则无法下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="b4396-107">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

## <span data-ttu-id="b4396-108">确保访问符号文件</span><span class="sxs-lookup"><span data-stu-id="b4396-108">Ensure access to symbol files</span></span>


<span data-ttu-id="b4396-109">通常，调试信息存储在与可执行文件不同的符号文件中。</span><span class="sxs-lookup"><span data-stu-id="b4396-109">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="b4396-110">当你调试已停止响应的应用程序时（例如，如果该应用程序崩溃），你必须具有访问符号信息的权限。</span><span class="sxs-lookup"><span data-stu-id="b4396-110">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="b4396-111">当运行**崩溃分析器**时，将自动下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="b4396-111">Symbol files are automatically downloaded when you run **Crash Analyzer**.</span></span> <span data-ttu-id="b4396-112">如果计算机没有 Internet 连接或网络要求计算机访问 HTTP 代理服务器，则无法下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="b4396-112">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

<span data-ttu-id="b4396-113">下面是可用于确保对符号文件的访问的选项列表：</span><span class="sxs-lookup"><span data-stu-id="b4396-113">The following is a list of options that are available for guaranteeing access to symbol files:</span></span>

-   **<span data-ttu-id="b4396-114">将转储文件复制到另一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="b4396-114">Copy the dump file to another computer.</span></span>** <span data-ttu-id="b4396-115">如果由于缺少 Internet 连接而无法下载符号，请将故障转储文件复制到具有 Internet 连接的计算机上，并在该计算机上运行独立的**故障分析器向导**。</span><span class="sxs-lookup"><span data-stu-id="b4396-115">If the symbols cannot be downloaded because of a lack of an Internet connection, copy the crash dump file to a computer that does have an Internet connection and run the stand-alone **Crash Analyzer Wizard** on that computer.</span></span>

-   **<span data-ttu-id="b4396-116">从另一台计算机访问符号文件。</span><span class="sxs-lookup"><span data-stu-id="b4396-116">Access the symbol files from another computer.</span></span>** <span data-ttu-id="b4396-117">如果由于缺少 Internet 连接而无法下载符号，则可以从具有 Internet 连接的计算机下载符号，然后将其复制到没有 Internet 连接的计算机上，也可以将网络驱动器映射到本地网络上的符号可用的位置。</span><span class="sxs-lookup"><span data-stu-id="b4396-117">If the symbols cannot be downloaded because of a lack of an Internet connection, you can download the symbols from a computer that does have an Internet connection and then copy them to the computer that does not have an Internet connection, or you can map a network drive to a location where the symbols are available on the local network.</span></span> <span data-ttu-id="b4396-118">如果在 Windows 恢复环境（WindowsRE）中运行**崩溃分析器**，则可以将符号文件包含在 DaRT 恢复映像中。</span><span class="sxs-lookup"><span data-stu-id="b4396-118">If you run the **Crash Analyzer** in a Windows Recovery Environment (WindowsRE), you can include the symbol files on the DaRT recovery image.</span></span> <span data-ttu-id="b4396-119">有关如何创建恢复映像的详细信息，请参阅[创建 DaRT 7.0 恢复映像](creating-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="b4396-119">For more information about how to create a recovery image, see [Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md).</span></span>

-   **<span data-ttu-id="b4396-120">通过 HTTP 代理服务器访问符号文件。</span><span class="sxs-lookup"><span data-stu-id="b4396-120">Access symbol files through an HTTP proxy server.</span></span>** <span data-ttu-id="b4396-121">如果无法下载符号，因为必须访问 HTTP 代理服务器，请使用以下步骤访问 HTTP 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b4396-121">If the symbols cannot be downloaded because an HTTP proxy server must be accessed, use the following steps to access an HTTP proxy server.</span></span> <span data-ttu-id="b4396-122">在 DaRT7 中，**崩溃分析向导**在 "**指定符号文件位置**" 对话框页面上提供了一个设置，使用标签**代理服务器（可选，使用 "server： port" 格式）** 标记。</span><span class="sxs-lookup"><span data-stu-id="b4396-122">In DaRT7, the **Crash Analyzer Wizard** has a setting available on the **Specify Symbol Files Location** dialog page, marked with the label **Proxy server (optional, using the format "server:port")**.</span></span> <span data-ttu-id="b4396-123">可以使用此文本框指定代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b4396-123">You can use this text box to specify a proxy server.</span></span> <span data-ttu-id="b4396-124">在 " \*\* &lt; 主机名 &gt; ： &lt; 端口 &gt; \*\*" 窗体中输入代理地址，其中 &lt; **主机名** &gt; 是 DNS 名称或 IP 地址，而 &lt; **端口** &gt; 是 TCP 端口号，通常为80。</span><span class="sxs-lookup"><span data-stu-id="b4396-124">Enter the proxy address in the form **&lt;hostname&gt;:&lt;port&gt;**, where the &lt;**hostname**&gt; is a DNS name or IP address, and the &lt;**port**&gt; is a TCP port number, usually 80.</span></span> <span data-ttu-id="b4396-125">可通过两种模式运行**崩溃分析器**。</span><span class="sxs-lookup"><span data-stu-id="b4396-125">There are two modes in which the **Crash Analyzer** can be run.</span></span> <span data-ttu-id="b4396-126">下面介绍如何在其中每种模式下使用代理设置：</span><span class="sxs-lookup"><span data-stu-id="b4396-126">Following is how you use the proxy setting in each of these modes:</span></span>

    -   <span data-ttu-id="b4396-127">**联机模式：** 在此模式下，如果 "代理服务器" 字段保留为空，向导将使用 "控制面板" 中的 "Internet 选项" 中的代理设置。</span><span class="sxs-lookup"><span data-stu-id="b4396-127">**Online mode:** In this mode, if the proxy server field is left blank, the wizard uses the proxy settings from Internet Options in Control Panel.</span></span> <span data-ttu-id="b4396-128">如果在提供的文本框中输入代理地址，则将使用该地址，并且它将覆盖 "Internet 选项" 中的设置。</span><span class="sxs-lookup"><span data-stu-id="b4396-128">If you enter a proxy address in the text box which is provided, that address will be used, and it will override the setting in the Internet Options.</span></span>

    -   <span data-ttu-id="b4396-129">**Windows 恢复环境（WindowsRE）：** 从 "**诊断和恢复工具集**" 窗口运行**崩溃分析器**时，没有默认的代理地址。</span><span class="sxs-lookup"><span data-stu-id="b4396-129">**Windows Recovery Environment (WindowsRE):** When you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window, there is no default proxy address.</span></span> <span data-ttu-id="b4396-130">如果计算机直接连接到 Internet，则不需要代理地址。</span><span class="sxs-lookup"><span data-stu-id="b4396-130">If the computer is directly connected to the Internet, a proxy address is not required.</span></span> <span data-ttu-id="b4396-131">因此，您可以在向导设置中将此字段保留为空。</span><span class="sxs-lookup"><span data-stu-id="b4396-131">Therefore, you can leave this field blank in the wizard setting.</span></span> <span data-ttu-id="b4396-132">如果计算机未直接连接到 Internet，并且它位于具有代理服务器的网络环境中，则必须在向导中将 "代理" 字段设置为 "访问符号存储区"。</span><span class="sxs-lookup"><span data-stu-id="b4396-132">If the computer is not directly connected to the Internet, and it is in a network environment that has a proxy server, you must set the proxy field in the wizard to access the symbol store.</span></span> <span data-ttu-id="b4396-133">可以从网络管理员处获取代理地址。</span><span class="sxs-lookup"><span data-stu-id="b4396-133">The proxy address can be obtained from the network administrator.</span></span> <span data-ttu-id="b4396-134">只有当公用符号存储连接到 Internet 时，设置代理服务器才很重要。</span><span class="sxs-lookup"><span data-stu-id="b4396-134">Setting the proxy server is important only when the public symbol store is connected to the Internet.</span></span> <span data-ttu-id="b4396-135">如果这些符号已在 DaRT 恢复映像上，或者如果它们在本地可用，则不需要设置代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b4396-135">If the symbols are already on the DaRT recovery image, or if they are available locally, setting the proxy server is not required.</span></span>

## <span data-ttu-id="b4396-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="b4396-136">Related topics</span></span>


[<span data-ttu-id="b4396-137">使用故障分析器诊断系统故障</span><span class="sxs-lookup"><span data-stu-id="b4396-137">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





