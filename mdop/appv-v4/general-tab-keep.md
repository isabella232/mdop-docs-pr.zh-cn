---
title: “常规”选项卡
description: “常规”选项卡
author: dansimp
ms.assetid: aeefae39-60cd-4ad4-9575-c07d7e2b1e59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 327635422030b713aeadbc5de0007685b69e1c2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802975"
---
# <span data-ttu-id="da072-103">“常规”选项卡</span><span class="sxs-lookup"><span data-stu-id="da072-103">General Tab</span></span>


<span data-ttu-id="da072-104">使用 "**常规**" 选项卡配置 Microsoft Application Virtualization （App-v） Sequencer 的选项。</span><span class="sxs-lookup"><span data-stu-id="da072-104">Use the **General** tab to configure options for Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<a href="" id="scratch-directory"></a>**<span data-ttu-id="da072-105">暂存目录</span><span class="sxs-lookup"><span data-stu-id="da072-105">Scratch Directory</span></span>**  
<span data-ttu-id="da072-106">指定 Sequencer 将在排序期间临时保存所生成文件的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="da072-106">Specifies the path to the location where the Sequencer will temporarily save files generated during sequencing.</span></span> <span data-ttu-id="da072-107">默认路径是 C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Scratch。</span><span class="sxs-lookup"><span data-stu-id="da072-107">The default path is C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Scratch.</span></span> <span data-ttu-id="da072-108">若要指定新路径，请单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="da072-108">To specify a new path, click **Browse**.</span></span>

<a href="" id="log-directory"></a>**<span data-ttu-id="da072-109">日志目录</span><span class="sxs-lookup"><span data-stu-id="da072-109">Log Directory</span></span>**  
<span data-ttu-id="da072-110">指定 Sequencer 将在其中保存日志文件的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="da072-110">Specifies the path to the directory where the Sequencer will save log files.</span></span> <span data-ttu-id="da072-111">默认路径是 C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Logs。</span><span class="sxs-lookup"><span data-stu-id="da072-111">The default path is C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Logs.</span></span> <span data-ttu-id="da072-112">若要指定新路径，请单击 "**浏览**"</span><span class="sxs-lookup"><span data-stu-id="da072-112">To specify a new path, click **Browse**</span></span>

<a href="" id="allow-use-of-msi-installer"></a>**<span data-ttu-id="da072-113">允许使用 MSI 安装程序</span><span class="sxs-lookup"><span data-stu-id="da072-113">Allow Use of MSI Installer</span></span>**  
<span data-ttu-id="da072-114">选择此选项可允许在 Sequencer 和应用程序安装程序之间进行交互。</span><span class="sxs-lookup"><span data-stu-id="da072-114">Select this option to allow interaction between the Sequencer and the application installer.</span></span> <span data-ttu-id="da072-115">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="da072-115">This option is selected by default.</span></span>

<a href="" id="allow-virtualization-of-events"></a>**<span data-ttu-id="da072-116">允许虚拟化事件</span><span class="sxs-lookup"><span data-stu-id="da072-116">Allow Virtualization of Events</span></span>**  
<span data-ttu-id="da072-117">选择此选项可允许应用程序的低级别操作系统活动在 App-v 桌面客户端上运行序列化应用程序包时进行虚拟化。</span><span class="sxs-lookup"><span data-stu-id="da072-117">Select this option to allow low-level operating system activities of the application to be virtualized when a sequenced application package is run on App-V Desktop Clients.</span></span> <span data-ttu-id="da072-118">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="da072-118">This option is selected by default.</span></span>

<a href="" id="allow-virtualization-of-services"></a>**<span data-ttu-id="da072-119">允许虚拟化服务</span><span class="sxs-lookup"><span data-stu-id="da072-119">Allow Virtualization of Services</span></span>**  
<span data-ttu-id="da072-120">选择此选项可允许应用程序在应用程序在 App-v 桌面客户端上运行时虚拟化所需的服务。</span><span class="sxs-lookup"><span data-stu-id="da072-120">Select this option to allow services required by the application to be virtualized when the application is run on App-V Desktop Clients.</span></span> <span data-ttu-id="da072-121">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="da072-121">This option is selected by default.</span></span>

<a href="" id="append-package-version-to-filename"></a>**<span data-ttu-id="da072-122">将程序包版本附加到文件名</span><span class="sxs-lookup"><span data-stu-id="da072-122">Append Package Version to Filename</span></span>**  
<span data-ttu-id="da072-123">选择此选项可将序列化应用程序包的版本号自动追加到文件名。</span><span class="sxs-lookup"><span data-stu-id="da072-123">Select this option to automatically append the sequenced application package version number to the file name.</span></span> <span data-ttu-id="da072-124">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="da072-124">This option is selected by default.</span></span>

<a href="" id="ok"></a>**<span data-ttu-id="da072-125">“确定”</span><span class="sxs-lookup"><span data-stu-id="da072-125">OK</span></span>**  
<span data-ttu-id="da072-126">保存更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="da072-126">Saves changes and closes the dialog box.</span></span>

<a href="" id="cancel"></a>**<span data-ttu-id="da072-127">取消</span><span class="sxs-lookup"><span data-stu-id="da072-127">Cancel</span></span>**  
<span data-ttu-id="da072-128">退出对话框，但不保存任何更改。</span><span class="sxs-lookup"><span data-stu-id="da072-128">Exits the dialog box without saving any changes.</span></span>

<a href="" id="apply"></a>**<span data-ttu-id="da072-129">“应用”</span><span class="sxs-lookup"><span data-stu-id="da072-129">Apply</span></span>**  
<span data-ttu-id="da072-130">保存所做的更改并保留在对话框中。</span><span class="sxs-lookup"><span data-stu-id="da072-130">Saves the changes and remains in the dialog box.</span></span>

## <span data-ttu-id="da072-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="da072-131">Related topics</span></span>


[<span data-ttu-id="da072-132">Application Virtualization Sequencer“选项”对话框</span><span class="sxs-lookup"><span data-stu-id="da072-132">Application Virtualization Sequencer Options Dialog Box</span></span>](application-virtualization-sequencer-options-dialog-box.md)

 

 





