---
title: “选择包加速器”页
description: “选择包加速器”页
author: dansimp
ms.assetid: 865c2702-4dfd-41ae-8cfc-3514d5f41f76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5723f8244563539c27a3fa915c1a680905e61e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798802"
---
# <span data-ttu-id="97ac6-103">“选择包加速器”页</span><span class="sxs-lookup"><span data-stu-id="97ac6-103">Select Package Accelerator Page</span></span>


<span data-ttu-id="97ac6-104">使用 "**选择包加速器**" 页面选择将用于创建新虚拟应用程序包的程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="97ac6-104">Use the **Select Package Accelerator** page to select the Package Accelerator that will be used to create the new virtual application package.</span></span> <span data-ttu-id="97ac6-105">必须将程序包加速器复制到运行 App-v Sequencer 的计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="97ac6-105">You must copy the Package Accelerator to a folder on the computer running the App-V Sequencer.</span></span> <span data-ttu-id="97ac6-106">有关详细信息，请参阅[关于 app-v 程序包加速器（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="97ac6-106">For more information, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span>

<span data-ttu-id="97ac6-107">仅从您信任的发布者运行程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="97ac6-107">Only run Package Accelerators from publishers that you trust.</span></span> <span data-ttu-id="97ac6-108">程序包加速器通常包含数字签名。</span><span class="sxs-lookup"><span data-stu-id="97ac6-108">Package Accelerators usually include a digital signature.</span></span> <span data-ttu-id="97ac6-109">数字签名是一种电子安全标记，可帮助指示软件的发布者，以及在转换最初签名后程序包是否已被篡改。</span><span class="sxs-lookup"><span data-stu-id="97ac6-109">A digital signature is an electronic security mark that can help indicate the publisher of the software, and whether the package has been tampered with after the transform was originally signed.</span></span> <span data-ttu-id="97ac6-110">如果你使用的转换已由 publisher 进行了数字签名，并且发布者已使用证书颁发机构验证了其身份，则可以更有把握地确保该转换来自特定的发布者且未被更改。</span><span class="sxs-lookup"><span data-stu-id="97ac6-110">If you use a transform that has been digitally signed by a publisher and the publisher has verified its identity with a certification authority, you can be more confident that the transform comes from that specific publisher and has not been altered.</span></span>

<span data-ttu-id="97ac6-111">如果以下任何条件成立，则 App-v 排序器将通知你：</span><span class="sxs-lookup"><span data-stu-id="97ac6-111">The App-V Sequencer notifies you if any of the following conditions are true:</span></span>

-   <span data-ttu-id="97ac6-112">所选转换尚未进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="97ac6-112">The selected transform has not been digitally signed.</span></span>

-   <span data-ttu-id="97ac6-113">所选转换已由尚未使用证书颁发机构验证其身份的发布者进行签名。</span><span class="sxs-lookup"><span data-stu-id="97ac6-113">The selected transform is signed by a publisher that has not verified its identity with a certification authority.</span></span>

-   <span data-ttu-id="97ac6-114">所选转换在经过数字签名和释放后已被更改。</span><span class="sxs-lookup"><span data-stu-id="97ac6-114">The selected transform has been altered after it was digitally signed and released.</span></span>

<span data-ttu-id="97ac6-115">如果在使用包加速器时显示这些消息中的任何消息，请访问程序包加速器 publisher 的网站，获取经过数字签名的转换版本。</span><span class="sxs-lookup"><span data-stu-id="97ac6-115">If any of these messages are displayed when using a Package Accelerators, visit the Package Accelerators publisher’s website to get a digitally signed version of the transform.</span></span>

<span data-ttu-id="97ac6-116">此页面包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="97ac6-116">This page contains the following elements:</span></span>

<a href="" id="browse"></a>**<span data-ttu-id="97ac6-117">浏览</span><span class="sxs-lookup"><span data-stu-id="97ac6-117">Browse</span></span>**  
<span data-ttu-id="97ac6-118">单击 "**浏览**" 以指定将用于创建虚拟应用程序包的程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="97ac6-118">Click **Browse** to specify the Package Accelerator that you will use to create the virtual application package.</span></span> <span data-ttu-id="97ac6-119">保存在运行 Sequencer 的计算机上本地指定的包加速器。</span><span class="sxs-lookup"><span data-stu-id="97ac6-119">Save the Package Accelerator you specified locally on the computer that is running the Sequencer.</span></span>

## <span data-ttu-id="97ac6-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="97ac6-120">Related topics</span></span>


[<span data-ttu-id="97ac6-121">Sequencer 向导 - 包加速器 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="97ac6-121">Sequencer Wizard - Package Accelerator (AppV 4.6 SP1)</span></span>](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





