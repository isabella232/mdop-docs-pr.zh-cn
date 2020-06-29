---
title: 独立传递方案概述
description: 独立传递方案概述
author: dansimp
ms.assetid: b109f309-f3c1-43af-996f-2a9b138dd171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f29b1c8d1c9ae97f7a21498369647f31f552839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798745"
---
# <span data-ttu-id="7fd5f-103">独立传递方案概述</span><span class="sxs-lookup"><span data-stu-id="7fd5f-103">Stand-Alone Delivery Scenario Overview</span></span>


<span data-ttu-id="7fd5f-104">独立交付方案是适用于低带宽连接或无连接的环境的理想应用虚拟化解决方案，它限制了应用程序虚拟化桌面客户端从集中式服务器流出应用程序的能力。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-104">The stand-alone delivery scenario is an ideal application virtualization solution for environments where either low bandwidth connectivity or no connectivity limits the ability of the Application Virtualization Desktop Client to stream applications from centralized servers.</span></span> <span data-ttu-id="7fd5f-105">在这些环境中，用户通常使用 Windows Installer 文件远程工作和设备所有者安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-105">In these environments, users often work remotely and device owners install applications by using Windows Installer files.</span></span>

<span data-ttu-id="7fd5f-106">你可以使用应用程序虚拟化 Sequencer 创建包含 Windows Installer 文件的序列化应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-106">You can use the Application Virtualization Sequencer to create sequenced applications that include Windows Installer files.</span></span> <span data-ttu-id="7fd5f-107">这些程序包包括虚拟化应用程序、发布信息以及在客户端系统上安装程序包所需的安装程序例程。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-107">These packages include the virtualized applications, publication information, and the necessary installer routines for installing the packages on the client systems.</span></span> <span data-ttu-id="7fd5f-108">安装程序将虚拟应用程序包添加到 Microsoft Application Virtualization 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-108">The installer adds the virtual application package to the Microsoft Application Virtualization Desktop Client.</span></span> <span data-ttu-id="7fd5f-109">发布信息配置为从本地位置加载应用程序，而不是通过 WAN 流出它们。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-109">The publication information is configured to load applications from a local location rather than stream them across a WAN.</span></span> <span data-ttu-id="7fd5f-110">用户可以暂时连接到网络以检索 Windows 安装程序文件，也可以从 DVD 运行它们。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-110">Users can temporarily connect to a network to retrieve the Windows Installer files or can run them from a DVD.</span></span>

<span data-ttu-id="7fd5f-111">独立交付方案为用户提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="7fd5f-111">The stand-alone delivery scenario provides users the following benefits:</span></span>

-   <span data-ttu-id="7fd5f-112">简单的部署操作。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-112">Simple deployment operation.</span></span>

-   <span data-ttu-id="7fd5f-113">在运行时不需要网络和服务器。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-113">Network and servers not needed at runtime.</span></span>

-   <span data-ttu-id="7fd5f-114">应用程序预缓存并供所有用户使用。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-114">Applications pre-cached and available to all users.</span></span>

<span data-ttu-id="7fd5f-115">独立交付方案具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="7fd5f-115">The stand-alone delivery scenario has the following limitations:</span></span>

-   <span data-ttu-id="7fd5f-116">内置的自动报告不可用;报表必须通过外部报表工具生成。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-116">Built-in, automated reporting is unavailable; reports must be generated with external reporting tools.</span></span>

-   <span data-ttu-id="7fd5f-117">应用程序必须手动发送到客户端，就像原始的 Windows 安装程序文件一样。</span><span class="sxs-lookup"><span data-stu-id="7fd5f-117">Applications must be delivered to the client manually like the original Windows Installer files.</span></span>

## <span data-ttu-id="7fd5f-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="7fd5f-118">Related topics</span></span>


[<span data-ttu-id="7fd5f-119">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="7fd5f-119">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="7fd5f-120">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="7fd5f-120">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

 

 





