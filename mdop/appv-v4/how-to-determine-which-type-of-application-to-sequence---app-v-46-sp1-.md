---
title: 如何确定要序列化的应用程序类型（App-v 4.6 SP1）
description: 如何确定要序列化的应用程序类型（App-v 4.6 SP1）
author: dansimp
ms.assetid: 936abee2-98f1-45fb-9f0d-786e1d7464b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 001f6afa36ca28eb1b8e0cc2ccc161cef4194d24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801436"
---
# <span data-ttu-id="31822-103">如何确定要序列化的应用程序类型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="31822-103">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>


<span data-ttu-id="31822-104">你可以使用 Microsoft Application Virtualization （App-v） Sequencer 对三种基本类型的应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="31822-104">You can sequence three basic types of applications by using Microsoft Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="31822-105">确定序列的应用程序类型</span><span class="sxs-lookup"><span data-stu-id="31822-105">To determine which type of application to sequence</span></span>


<span data-ttu-id="31822-106">使用下表确定应序列化的应用程序类型，并获取有关如何对应用程序进行排序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="31822-106">Use the following table to determine which type of application you should sequence and to obtain more information about how to sequence the application.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="31822-107">应用程序类型</span><span class="sxs-lookup"><span data-stu-id="31822-107">Application Type</span></span></th>
<th align="left"><span data-ttu-id="31822-108">描述</span><span class="sxs-lookup"><span data-stu-id="31822-108">Description</span></span></th>
<th align="left"><span data-ttu-id="31822-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="31822-109">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31822-110">Standard</span><span class="sxs-lookup"><span data-stu-id="31822-110">Standard</span></span></p></td>
<td align="left"><p><span data-ttu-id="31822-111">选择此选项可创建包含应用程序或应用程序套件的程序包。</span><span class="sxs-lookup"><span data-stu-id="31822-111">Select this option to create a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="31822-112">对于你打算序列化的大多数应用程序，你应选择此选项。</span><span class="sxs-lookup"><span data-stu-id="31822-112">You should select this option for most applications that you plan to sequence.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-standard-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Standard Application (App-V 4.6 SP1)](how-to-sequence-a-new-standard-application--app-v-46-sp1-.md)"><span data-ttu-id="31822-113">如何对新的标准应用程序进行排序 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="31822-113">How to Sequence a New Standard Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31822-114">加载项或插件</span><span class="sxs-lookup"><span data-stu-id="31822-114">Add-on or Plug-in</span></span></p></td>
<td align="left"><p><span data-ttu-id="31822-115">选择此选项可创建扩展标准应用程序（例如 Microsoft Excel 插件）的功能的程序包。</span><span class="sxs-lookup"><span data-stu-id="31822-115">Select this option to create a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="31822-116">此外，你可以对本机安装的应用程序使用插件，或者对使用动态套件合成链接的其他程序包使用插件。</span><span class="sxs-lookup"><span data-stu-id="31822-116">Additionally, you can use plug-ins for natively installed applications, or another package that is linked by using Dynamic Suite Composition.</span></span> <span data-ttu-id="31822-117">有关动态套件合成的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用动态套件合成 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="31822-117">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)](how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md)"><span data-ttu-id="31822-118">如何对新的加载项或插件应用程序进行排序 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="31822-118">How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31822-119">中间件</span><span class="sxs-lookup"><span data-stu-id="31822-119">Middleware</span></span></p></td>
<td align="left"><p><span data-ttu-id="31822-120">选择此选项可创建标准应用程序（例如 Microsoft .NET Framework）所需的程序包。</span><span class="sxs-lookup"><span data-stu-id="31822-120">Select this option to create a package that is required by a standard application, for example, the Microsoft .NET Framework.</span></span> <span data-ttu-id="31822-121">中间件程序包用于通过使用动态套件合成链接到其他程序包。</span><span class="sxs-lookup"><span data-stu-id="31822-121">Middleware packages are used for linking to other packages by using Dynamic Suite Composition.</span></span> <span data-ttu-id="31822-122">有关动态套件合成的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用动态套件合成 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="31822-122">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Middleware Application (App-V 4.6 SP1)](how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md)"><span data-ttu-id="31822-123">如何对新的中间件应用程序进行排序 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="31822-123">How to Sequence a New Middleware Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="31822-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="31822-124">Related topics</span></span>


[<span data-ttu-id="31822-125">Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="31822-125">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





