---
title: 如何针对共享内容存储模式安装 App-V 5.0 Client
description: 如何针对共享内容存储模式安装 App-V 5.0 Client
author: dansimp
ms.assetid: 88f09e6f-19e7-48ea-965a-907052d1a02f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 704ea6c1e4b1ba4670a4e52d754b8e6e5a9fb8f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798450"
---
# <span data-ttu-id="6a961-103">如何针对共享内容存储模式安装 App-V 5.0 Client</span><span class="sxs-lookup"><span data-stu-id="6a961-103">How to Install the App-V 5.0 Client for Shared Content Store Mode</span></span>


<span data-ttu-id="6a961-104">使用以下过程安装 Microsoft Application Virtualization （App-v）5.0 客户端，以便它使用 App-v 5.0 共享内容存储（SCS）模式。</span><span class="sxs-lookup"><span data-stu-id="6a961-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.0 client so that it uses the App-V 5.0 Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="6a961-105">应确保安装了要安装到的计算机上已安装所有必需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="6a961-105">You should ensure that all required prerequisites are installed on the computer you plan to install to.</span></span> <span data-ttu-id="6a961-106">对 app-v [5.0 先决条件](app-v-50-prerequisites.md)使用以下链接。</span><span class="sxs-lookup"><span data-stu-id="6a961-106">Use the following link for a [App-V 5.0 Prerequisites](app-v-50-prerequisites.md).</span></span>

<span data-ttu-id="6a961-107">**注意** 在执行此过程之前，如有必要，请卸载 app-v 5.0 客户端的任何现有版本。</span><span class="sxs-lookup"><span data-stu-id="6a961-107">**Note** Before performing this procedure if necessary uninstall any existing version of the App-V 5.0 client.</span></span>

 

<span data-ttu-id="6a961-108">有关 SCS 模式的详细信息，请参阅[Microsoft app-v 5.0 中的共享内容存储（位于后台）-后台](https://go.microsoft.com/fwlink/?LinkId=316879)（ https://go.microsoft.com/fwlink/?LinkId=316879) 。</span><span class="sxs-lookup"><span data-stu-id="6a961-108">For more information about SCS mode, see [Shared Content Store in Microsoft App-V 5.0 – Behind the Scenes](https://go.microsoft.com/fwlink/?LinkId=316879) (https://go.microsoft.com/fwlink/?LinkId=316879).</span></span>

**<span data-ttu-id="6a961-109">为 SCS 模式安装和配置 app-v 5.0 客户端</span><span class="sxs-lookup"><span data-stu-id="6a961-109">Install and configure the App-V 5.0 client for SCS mode</span></span>**

1.  <span data-ttu-id="6a961-110">将 app-v 5.0 客户端安装文件复制到将在其上安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="6a961-110">Copy the App-V 5.0 client installation files to the computer on which it will be installed.</span></span> <span data-ttu-id="6a961-111">打开命令行，并从保存安装文件的目录中，键入以下选项之一，具体取决于你正在安装的客户端版本：</span><span class="sxs-lookup"><span data-stu-id="6a961-111">Open a command line and from the directory where the installation files are saved type one of the following options depending on the version of the client you are installing:</span></span>

    -   <span data-ttu-id="6a961-112">若要安装 RDS 5.0 客户端类型的 RDS 版本，请执行以下操作： **appv\_client\_setup\_rds.exe/SHAREDCONTENTSTOREMODE = 1/q**</span><span class="sxs-lookup"><span data-stu-id="6a961-112">To install the RDS version of the App-V 5.0 client type: **appv\_client\_setup\_rds.exe /SHAREDCONTENTSTOREMODE=1 /q**</span></span>

    -   <span data-ttu-id="6a961-113">若要安装标准版本的 App-v 5.0 客户端类型，请执行以下操作： **appv\_client\_setup.exe/SHAREDCONTENTSTOREMODE = 1/q**</span><span class="sxs-lookup"><span data-stu-id="6a961-113">To install the standard version of the App-V 5.0 client type: **appv\_client\_setup.exe /SHAREDCONTENTSTOREMODE=1 /q**</span></span>

        <span data-ttu-id="6a961-114">**重要提示** 必须执行静默式安装，否则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="6a961-114">**Important** You must perform a silent installation or the installation will fail.</span></span>

         

2.  <span data-ttu-id="6a961-115">完成安装后，你可以将程序包部署到运行客户端的计算机上，所有程序包内容都将跨网络进行传输。</span><span class="sxs-lookup"><span data-stu-id="6a961-115">After you have completed the installation you can deploy packages to the computer running the client and all package contents will be streamed across the network.</span></span>

    <span data-ttu-id="6a961-116">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="6a961-116">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="6a961-117">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="6a961-117">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="6a961-118">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="6a961-118">Got an App-V issue?</span></span>** <span data-ttu-id="6a961-119">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="6a961-119">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="6a961-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="6a961-120">Related topics</span></span>


[<span data-ttu-id="6a961-121">部署 App-V 5.0 Sequencer 和 Client</span><span class="sxs-lookup"><span data-stu-id="6a961-121">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

 

 





