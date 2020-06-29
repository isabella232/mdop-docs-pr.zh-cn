---
title: “选择包加速器”（了解详细信息）页
description: “选择包加速器”（了解详细信息）页
author: dansimp
ms.assetid: 2db51514-8695-4b5e-b3e5-1e96e3ee4cc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51df0f8eb16816bacf681b1acaf4c911ee9da55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798803"
---
# <span data-ttu-id="25d59-103">“选择包加速器”（了解详细信息）页</span><span class="sxs-lookup"><span data-stu-id="25d59-103">Select Package Accelerator (Learn More) Page</span></span>


<span data-ttu-id="25d59-104">仅从您信任的发布者运行程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="25d59-104">Only run Package Accelerators from publishers that you trust.</span></span> <span data-ttu-id="25d59-105">程序包加速器通常包含数字签名。</span><span class="sxs-lookup"><span data-stu-id="25d59-105">Package Accelerators usually include a digital signature.</span></span> <span data-ttu-id="25d59-106">数字签名是一个电子安全标记，可帮助指示软件的发行者，并且程序包在转换最初签名后未被篡改。</span><span class="sxs-lookup"><span data-stu-id="25d59-106">A digital signature is an electronic security mark that can help indicate the publisher of the software, and that the package has not been tampered with after the transform was originally signed.</span></span> <span data-ttu-id="25d59-107">如果你使用的转换已由 publisher 进行了数字签名，并且发布者已使用证书颁发机构验证了其身份，则可以更有把握地确保该转换来自特定的发布者且未被更改。</span><span class="sxs-lookup"><span data-stu-id="25d59-107">If you use a transform that has been digitally signed by a publisher and the publisher has verified its identity with a certification authority, you can be more confident that the transform comes from that specific publisher and has not been altered.</span></span>

<span data-ttu-id="25d59-108">排序器将通知你以下任何条件为 true：</span><span class="sxs-lookup"><span data-stu-id="25d59-108">The sequencer notifies you if any of the following conditions are true:</span></span>

-   <span data-ttu-id="25d59-109">所选转换尚未进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="25d59-109">The selected transform has not been digitally signed.</span></span>

-   <span data-ttu-id="25d59-110">所选转换已由尚未使用证书颁发机构验证其身份的发布者进行签名。</span><span class="sxs-lookup"><span data-stu-id="25d59-110">The selected transform is signed by a publisher that has not verified its identity with a certification authority.</span></span>

-   <span data-ttu-id="25d59-111">所选转换在经过数字签名和释放后已被更改。</span><span class="sxs-lookup"><span data-stu-id="25d59-111">The selected transform has been altered after it was digitally signed and released.</span></span>

<span data-ttu-id="25d59-112">如果在使用包加速器时显示这些消息中的任何消息，请访问程序包加速器发布者的网站，获取经过数字签名的转换版本。</span><span class="sxs-lookup"><span data-stu-id="25d59-112">If any of these messages are displayed when using a Package Accelerator, visit the Package Accelerators publisher’s website to get a digitally signed version of the transform.</span></span>

## <span data-ttu-id="25d59-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="25d59-113">Related topics</span></span>


[<span data-ttu-id="25d59-114">Sequencer 向导 - 包加速器 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="25d59-114">Sequencer Wizard - Package Accelerator (AppV 4.6 SP1)</span></span>](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





