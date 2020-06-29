---
title: App-V 4.6 SP3 发行说明
description: App-V 4.6 SP3 发行说明
author: dansimp
ms.assetid: 206fadeb-59cc-47b4-836f-191ab1c27ff8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: dd0b82c5e12cbe161066a7f4a4e0932cb92cca42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802359"
---
# <span data-ttu-id="ce5d0-103">App-V 4.6 SP3 发行说明</span><span class="sxs-lookup"><span data-stu-id="ce5d0-103">App-V 4.6 SP3 Release Notes</span></span>


<span data-ttu-id="ce5d0-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="ce5d0-105">在安装 Microsoft Application Virtualization （app-v）管理系统之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-105">Read these Release Notes thoroughly before you install the Microsoft Application Virtualization (App-V) Management System.</span></span> <span data-ttu-id="ce5d0-106">这些发行说明包含的信息可帮助你成功安装应用程序虚拟化（app-v） 4.6 SP3。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-106">These Release Notes contain information that helps you successfully install Application Virtualization (App-V)4.6 SP3.</span></span> <span data-ttu-id="ce5d0-107">本文档包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="ce5d0-108">如果这些发行说明和其他 App-v 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-108">If there is a difference between these Release Notes and other App-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="ce5d0-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="ce5d0-110">防范安全漏洞和病毒</span><span class="sxs-lookup"><span data-stu-id="ce5d0-110">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="ce5d0-111">若要帮助防范安全漏洞和病毒，请务必为正在安装的任何新软件安装最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-111">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="ce5d0-112">有关详细信息，请参阅[Microsoft 安全网站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-112">For more information, see the [Microsoft Security website](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="ce5d0-113">应用程序虚拟化 4.6 SP3 的已知问题</span><span class="sxs-lookup"><span data-stu-id="ce5d0-113">Known Issues with Application Virtualization4.6 SP3</span></span>


<span data-ttu-id="ce5d0-114">本部分提供有关 Microsoft Application Virtualization （app-v） 4.6 SP3 问题的最新信息。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-114">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.6SP3.</span></span> <span data-ttu-id="ce5d0-115">这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-115">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="ce5d0-116">如果可能，这些问题将在以后的版本中解决。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-116">When it is possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="ce5d0-117">无法在虚拟环境中使用 Microsoft Windows 8.1 上的 Internet Explorer11 打开超链接</span><span class="sxs-lookup"><span data-stu-id="ce5d0-117">Unable to open hyperlinks using Internet Explorer11 on Microsoft Windows 8.1 within the Virtual Environment</span></span>

<span data-ttu-id="ce5d0-118">在使用 Internet Explorer 11 的 Windows 8.1 上尝试从虚拟环境中打开超链接将失败。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-118">Attempting to open hyperlinks from within a virtual environment will fail on Windows 8.1 using Internet Explorer 11.</span></span> <span data-ttu-id="ce5d0-119">这是因为 Internet Explorer 11 现在附带了默认启用的增强保护模式（EPM），这将导致 App-v 无法访问所需的注册表项、文件和通信端口对象。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-119">This is because Internet Explorer 11 now ships with the Enhanced Protection Mode (EPM) enabled by default and this causes App-V to be unable to access required registry keys, files and communication port objects.</span></span>

<span data-ttu-id="ce5d0-120">解决方法：打开 App-v 程序包之前，在 Internet Explorer11 中禁用 EPM。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-120">WORKAROUND: Disable EPM in Internet Explorer11 before opening an App-V package.</span></span> <span data-ttu-id="ce5d0-121">这将允许你从虚拟环境中打开 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="ce5d0-121">This will allow you to open Internet Explorer from within the virtual environment.</span></span>

## <span data-ttu-id="ce5d0-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="ce5d0-122">Related topics</span></span>


[<span data-ttu-id="ce5d0-123">关于 Microsoft Application Virtualization 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="ce5d0-123">About Microsoft Application Virtualization 4.6 SP3</span></span>](about-microsoft-application-virtualization-46-sp3.md)

 

 





