---
title: 如何更改部署属性
description: 如何更改部署属性
author: dansimp
ms.assetid: 0a214a7a-cc83-4d04-89f9-5727153be918
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfb42962d41159479db61da9c3beb3771ef35502
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801667"
---
# <span data-ttu-id="274e8-103">如何更改部署属性</span><span class="sxs-lookup"><span data-stu-id="274e8-103">How to Change Deployment Properties</span></span>


<span data-ttu-id="274e8-104">你可以使用以下过程更改你要对其进行排序的应用程序的 "**部署**" 选项卡信息，包括应用程序虚拟化服务器 URL、虚拟化应用程序所需的操作系统以及要安装的虚拟应用程序的输出选项。</span><span class="sxs-lookup"><span data-stu-id="274e8-104">You can use the following procedures to change the **Deployment** tab information for an application you are sequencing, including the Application Virtualization server URL, the operating systems required by the virtualized applications, and the output options for the virtual application to be installed.</span></span>

**<span data-ttu-id="274e8-105">更改服务器 URL</span><span class="sxs-lookup"><span data-stu-id="274e8-105">To change the server URL</span></span>**

1.  <span data-ttu-id="274e8-106">从下拉列表框中选择 "流协议"。</span><span class="sxs-lookup"><span data-stu-id="274e8-106">Select the streaming protocol from the drop-down list box.</span></span>

2.  <span data-ttu-id="274e8-107">输入虚拟应用程序服务器或服务器组负载平衡器的主机名。</span><span class="sxs-lookup"><span data-stu-id="274e8-107">Enter the host name of the virtual application server or the server group's load balancer.</span></span> <span data-ttu-id="274e8-108">您可以使用实际的主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="274e8-108">You can use the actual host name or IP address.</span></span>

3.  <span data-ttu-id="274e8-109">指定虚拟应用程序服务器或负载平衡器将在其上侦听针对流应用的应用程序虚拟化桌面客户端请求的端口号。</span><span class="sxs-lookup"><span data-stu-id="274e8-109">Specify the port number on which the virtual application server or load balancer will listen for an Application Virtualization Desktop Client request for the streamed application.</span></span>

4.  <span data-ttu-id="274e8-110">指定存储软件包的虚拟应用程序服务器上的相对路径。</span><span class="sxs-lookup"><span data-stu-id="274e8-110">Specify the relative path on the virtual application server where the software package is stored.</span></span>

**<span data-ttu-id="274e8-111">更改应用程序操作系统要求</span><span class="sxs-lookup"><span data-stu-id="274e8-111">To change the application operating systems requirements</span></span>**

1.  <span data-ttu-id="274e8-112">若要添加所需操作系统，请在 "**可用**" 列表中选择它，然后单击指向**所选**操作系统列表控件的箭头按钮。</span><span class="sxs-lookup"><span data-stu-id="274e8-112">To add the required operating system(s), select it in the **Available** list and click the arrow button pointing to the **Selected** operating systems list control.</span></span>

2.  <span data-ttu-id="274e8-113">若要删除操作系统，请在**所选**列表控件中选择它，然后单击指向**可用**操作系统列表控件的箭头按钮。</span><span class="sxs-lookup"><span data-stu-id="274e8-113">To remove an operating system, select it in the **Selected** list control, and click the arrow button pointing to the **Available** operating systems list control.</span></span>

**<span data-ttu-id="274e8-114">更改应用程序输出选项</span><span class="sxs-lookup"><span data-stu-id="274e8-114">To change the application output options</span></span>**

1.  <span data-ttu-id="274e8-115">从 "**压缩算法**" 下拉列表中，选择要在流式处理应用程序时使用的压缩方法。</span><span class="sxs-lookup"><span data-stu-id="274e8-115">From the **Compression Algorithm** drop-down list, select the compression method to use when streaming the application.</span></span>

2.  <span data-ttu-id="274e8-116">选中 "**强制执行安全描述符**" 复选框，以确保打包应用程序的安全描述符在部署时生效。</span><span class="sxs-lookup"><span data-stu-id="274e8-116">Select the **Enforce Security Descriptors** check box to ensure security descriptors of the packaged applications are enforced when deployed.</span></span>

3.  <span data-ttu-id="274e8-117">选择 "**生成差异文件**" 以从以前的已排序版本生成应用程序的差异文件。</span><span class="sxs-lookup"><span data-stu-id="274e8-117">Select **Generate Difference File** to generate a difference file for the application from the previous sequenced version.</span></span>

4.  <span data-ttu-id="274e8-118">选择 "**生成 Microsoft Windows Installer （MSI）程序包**" 以创建一个安装程序包。</span><span class="sxs-lookup"><span data-stu-id="274e8-118">Select **Generate Microsoft Windows Installer (MSI) Package** to create an installer package.</span></span>

## <span data-ttu-id="274e8-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="274e8-119">Related topics</span></span>


[<span data-ttu-id="274e8-120">关于“部署”选项卡</span><span class="sxs-lookup"><span data-stu-id="274e8-120">About the Deployment Tab</span></span>](about-the-deployment-tab.md)

[<span data-ttu-id="274e8-121">Sequencer 控制台</span><span class="sxs-lookup"><span data-stu-id="274e8-121">Sequencer Console</span></span>](sequencer-console.md)

 

 





