---
title: App-V 5.0 SP1 中的新增功能
description: App-V 5.0 SP1 中的新增功能
author: dansimp
ms.assetid: e97c2dbb-7b40-46a0-8137-9ee4fc2bd071
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2542d0cc5a544d26b3279b24063cf3ef428b9f39
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798240"
---
# <span data-ttu-id="0197a-103">App-V 5.0 SP1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="0197a-103">What's new in App-V 5.0 SP1</span></span>


<span data-ttu-id="0197a-104">本部分适用于已熟悉 app-v 的用户，想要了解 app-v 5.0 SP1 中的更改。</span><span class="sxs-lookup"><span data-stu-id="0197a-104">This section is for users who are already familiar with App-V and want to know what has changed in App-V 5.0 SP1.</span></span> <span data-ttu-id="0197a-105">如果你还不熟悉 App-v，应首先阅读适用[于 app-v 5.0 的规划](planning-for-app-v-50-rc.md)。</span><span class="sxs-lookup"><span data-stu-id="0197a-105">If you are not already familiar with App-V, you should start by reading [Planning for App-V 5.0](planning-for-app-v-50-rc.md).</span></span>

## <span data-ttu-id="0197a-106">标准功能的更改</span><span class="sxs-lookup"><span data-stu-id="0197a-106">Changes in Standard Functionality</span></span>


<span data-ttu-id="0197a-107">以下各节包含有关 App-v 5.0 SP1 的标准功能更改的信息。</span><span class="sxs-lookup"><span data-stu-id="0197a-107">The following sections contain information about the changes in standard functionality for App-V 5.0 SP1.</span></span>

### <span data-ttu-id="0197a-108">对受支持语言的更改</span><span class="sxs-lookup"><span data-stu-id="0197a-108">Changes to Supported Languages</span></span>

<span data-ttu-id="0197a-109">有关详细信息，请参阅[关于 App-V 5.0 SP1](about-app-v-50-sp1.md)。</span><span class="sxs-lookup"><span data-stu-id="0197a-109">For more information, see [About App-V 5.0 SP1](about-app-v-50-sp1.md).</span></span>

<span data-ttu-id="0197a-110">以下列表包含有关新语言包的详细信息：</span><span class="sxs-lookup"><span data-stu-id="0197a-110">The following list contains more information about the new Language Packs:</span></span>

-   <span data-ttu-id="0197a-111">App-v 5.0 SP1 语言包已捆绑到所有 App-v 5.0 组件的**appv\_xxx\_setup.exe**安装程序中。</span><span class="sxs-lookup"><span data-stu-id="0197a-111">The App-V 5.0SP1 language packs are bundled into the **appv\_xxx\_setup.exe** installer for all the App-V 5.0 Components.</span></span>

-   <span data-ttu-id="0197a-112">运行安装程序时，它将根据在目标计算机上运行的关联操作系统的区域设置自动安装最合适的语言包。</span><span class="sxs-lookup"><span data-stu-id="0197a-112">When you run the installer it will automatically install the most appropriate language pack based on the locale of the associated operating system running on the target computer.</span></span>

-   <span data-ttu-id="0197a-113">如果需要其他语言包，则必须通过运行以下命令从安装程序提取这些语言包： `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”` 。</span><span class="sxs-lookup"><span data-stu-id="0197a-113">If additional language packs are required, you must extract these language packs from the installer by running the following command: `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”`.</span></span> <span data-ttu-id="0197a-114">运行此操作后，安装程序的内容将解压缩到指定位置。</span><span class="sxs-lookup"><span data-stu-id="0197a-114">After this has been run, the contents of the installer are extracted to the specified location.</span></span>

-   <span data-ttu-id="0197a-115">必须通过应用相应语言包的 Windows 安装文件来安装所需的语言包。</span><span class="sxs-lookup"><span data-stu-id="0197a-115">You must install the desired language pack by applying the appropriate Language pack Windows Installation file.</span></span> <span data-ttu-id="0197a-116">例如， **appv\_hib\_LP\_jmmb\_x86.msi**或**appv\_hib\_LP\_jmmb\_x64.msi**，其中**hib**指的是组件， **jmmb**指的是区域设置。</span><span class="sxs-lookup"><span data-stu-id="0197a-116">For example, **appv\_hib\_LP\_jmmb\_x86.msi** or **appv\_hib\_LP\_jmmb\_x64.msi**, where **hib** refers to the component and **jmmb** refers to the locale.</span></span>

## <span data-ttu-id="0197a-117">Microsoft Office2010 增强版支持</span><span class="sxs-lookup"><span data-stu-id="0197a-117">Enhanced Support for Microsoft Office2010</span></span>


<span data-ttu-id="0197a-118">**适用于应用程序虚拟化的 Microsoft Office 2010 排序包 5.0** -通过 microsoft Office2010 的虚拟化版本帮助用户提供一致的体验。</span><span class="sxs-lookup"><span data-stu-id="0197a-118">**Microsoft Office 2010 Sequencing Kit for Application Virtualization 5.0** – helps provide users with a consistent experience using a virtualized version of Microsoft Office2010.</span></span> <span data-ttu-id="0197a-119">**应用程序虚拟化5.0 的 Microsoft office 2010 排序工具包**与适用于 App-v 的**Microsoft Office 2010 部署工具包**结合使用，并且还提供所需的 Microsoft Office2010 授权服务。</span><span class="sxs-lookup"><span data-stu-id="0197a-119">The **Microsoft Office 2010 Sequencing Kit for Application Virtualization 5.0** is used in conjunction with the **Microsoft Office 2010 Deployment Kit for App-V** and also provides the required Microsoft Office2010 licensing service.</span></span>






## <span data-ttu-id="0197a-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="0197a-120">Related topics</span></span>


[<span data-ttu-id="0197a-121">关于 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="0197a-121">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





