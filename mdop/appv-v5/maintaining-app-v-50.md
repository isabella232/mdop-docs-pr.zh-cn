---
title: 维护 App-V 5.0
description: 维护 App-V 5.0
author: dansimp
ms.assetid: 66851ec3-c674-493b-ad6d-db8fcbf1956c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3445bfe00ba7703a66fa3da2f9d7089990dd3854
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798340"
---
# <span data-ttu-id="fc143-103">维护 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="fc143-103">Maintaining App-V 5.0</span></span>


<span data-ttu-id="fc143-104">完成所有必要的计划，然后部署 app-v 5.0 之后，你可以使用以下信息维护 App-v 5.0 基础结构。</span><span class="sxs-lookup"><span data-stu-id="fc143-104">After you have completed all the necessary planning, and then deployment of App-V 5.0, you can use the following information to maintain the App-V 5.0 infrastructure.</span></span>

## <a href="" id="move-the-app-v-5-0-server-"></a><span data-ttu-id="fc143-105">移动 app-v 5.0 服务器</span><span class="sxs-lookup"><span data-stu-id="fc143-105">Move the App-V 5.0 Server</span></span>


<span data-ttu-id="fc143-106">App-v 5.0 服务器连接到 app-v 5.0 数据库。</span><span class="sxs-lookup"><span data-stu-id="fc143-106">The App-V 5.0 server connects to the App-V 5.0 database.</span></span> <span data-ttu-id="fc143-107">因此，你可以将管理组件安装到网络上的任何计算机，然后将其连接到 app-v 5.0 数据库。</span><span class="sxs-lookup"><span data-stu-id="fc143-107">Therefore you can install the management component to any computer on the network and then connect it to the App-V 5.0 database.</span></span>

[<span data-ttu-id="fc143-108">如何将 App-V Server 移动到另一台计算机</span><span class="sxs-lookup"><span data-stu-id="fc143-108">How to Move the App-V Server to Another Computer</span></span>](how-to-move-the-app-v-server-to-another-computer.md)

## <a href="" id="determine-if-an-app-v-5-0-application-is-running-virtualized-"></a><span data-ttu-id="fc143-109">确定 App-v 5.0 应用程序是否运行虚拟化</span><span class="sxs-lookup"><span data-stu-id="fc143-109">Determine if an App-V 5.0 Application is Running Virtualized</span></span>


<span data-ttu-id="fc143-110">希望确定应用程序是否使用 App-v 5.0 或更高版本运行的独立软件供应商（ISV）应在默认命名空间中打开名为\*\*AppVVirtual 的 &lt; &gt; \*\*命名对象。</span><span class="sxs-lookup"><span data-stu-id="fc143-110">Independent software vendors (ISV) who want to determine if an application is running virtualized with App-V 5.0 or above, should open a named object called **AppVVirtual-&lt;PID&gt;** in the default namespace.</span></span> <span data-ttu-id="fc143-111">例如，Windows API **GetCurrentProcessId （）** 可用于获取当前进程的 ID （例如4052），然后，如果可以使用**OpenEvent （）** 在默认命名空间中成功打开名为**AppVVirtual-4052**的命名事件对象，则应用程序是虚拟的。</span><span class="sxs-lookup"><span data-stu-id="fc143-111">For example, Windows API **GetCurrentProcessId()** can be used to obtain the current process's ID, for example 4052, and then if a named Event object called **AppVVirtual-4052** can be successfully opened using **OpenEvent()** in the default namespace for read access, then the application is virtual.</span></span> <span data-ttu-id="fc143-112">如果**OpenEvent （）** 调用失败，则应用程序不是虚拟的。</span><span class="sxs-lookup"><span data-stu-id="fc143-112">If the **OpenEvent()** call fails, the application is not virtual.</span></span>

<span data-ttu-id="fc143-113">此外，要使用 app-v 5.0 和更高版本在特定 API 上显式虚拟化或不虚拟化调用的 ISV 用户可以使用在 AppEntSubsystems32.dll 模块中实现的**VirtualizeCurrentThread （）** 和**CurrentThreadIsVirtualized （）** 函数。</span><span class="sxs-lookup"><span data-stu-id="fc143-113">Additionally, ISV’s who want to explicitly virtualize or not virtualize calls on specific API’s with App-V 5.0 and above, can use the **VirtualizeCurrentThread()** and **CurrentThreadIsVirtualized()** functions implemented in the AppEntSubsystems32.dll module.</span></span> <span data-ttu-id="fc143-114">这些方法提供了一种在下游组件上进行提示的方法，即不应虚拟化调用。</span><span class="sxs-lookup"><span data-stu-id="fc143-114">These provide a way of hinting at a downstream component that the call should or should not be virtualized.</span></span>






## <span data-ttu-id="fc143-115">用于维护 App-v 5.0 的其他资源</span><span class="sxs-lookup"><span data-stu-id="fc143-115">Other resources for maintaining App-V 5.0</span></span>


[<span data-ttu-id="fc143-116">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="fc143-116">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





