---
title: 监视 MED-V 工作区部署
description: 监视 MED-V 工作区部署
author: dansimp
ms.assetid: 5de0cb06-b8a9-48a5-b8b3-836954295765
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ec4c7c85326e7945aa3d61b7f96872afe24fe37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804123"
---
# <span data-ttu-id="e970b-103">监视 MED-V 工作区部署</span><span class="sxs-lookup"><span data-stu-id="e970b-103">Monitoring MED-V Workspace Deployments</span></span>


<span data-ttu-id="e970b-104">通过 Microsoft 企业桌面虚拟化（MED-V）2.0 中的 "监视" 功能，你可以在单个 MED-V 工作区上运行查询，以确定在部署 MED-V 工作区后是否在整个企业中首次设置成功。</span><span class="sxs-lookup"><span data-stu-id="e970b-104">The monitoring feature in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 lets you run queries on individual MED-V workspaces to determine whether first time setup succeeded throughout your enterprise after the MED-V workspaces are deployed.</span></span> <span data-ttu-id="e970b-105">监视首次设置是否成功是很重要的，因为在首次成功完成设置之前，MED-V 不处于可用状态。</span><span class="sxs-lookup"><span data-stu-id="e970b-105">Monitoring the success of first time setup is important because MED-V is not in a usable state until first time setup has been completed successfully.</span></span>

<span data-ttu-id="e970b-106">本部分提供的信息和说明可帮助你在首次设置成功时进行监视。</span><span class="sxs-lookup"><span data-stu-id="e970b-106">This section provides information and instruction to assist you in monitoring the success or failure of first time setup.</span></span>

## <span data-ttu-id="e970b-107">监视 MED-V 工作区部署</span><span class="sxs-lookup"><span data-stu-id="e970b-107">To monitor MED-V workspace deployments</span></span>


<span data-ttu-id="e970b-108">监视功能包含一个耦合的进程内 Windows 管理规范（WMI）提供程序，你可以使用 WMI 查询语言查询该提供程序，以便在 MED-V 工作区中针对所有最终用户首次设置状态。</span><span class="sxs-lookup"><span data-stu-id="e970b-108">The monitoring feature consists of a coupled in-process Windows Management Instrumentation (WMI) provider that you can query using WMI Query Language to discover the status of first time setup for all end users on a MED-V workspace.</span></span>

<span data-ttu-id="e970b-109">WMI 提供程序是使用 Microsoft .Net Framework 3.5 中的 WMI 提供程序扩展框架实现的。</span><span class="sxs-lookup"><span data-stu-id="e970b-109">The WMI provider is implemented by using the WMI Provider Extension framework from the Microsoft .Net Framework 3.5.</span></span> <span data-ttu-id="e970b-110">WMI 提供程序在 LocalService 的上下文中执行，并在 \\ProgramData. 下安全地存储首次设置状态。</span><span class="sxs-lookup"><span data-stu-id="e970b-110">The WMI provider executes in the context of LocalService and stores the first time setup state securely under \\ProgramData.</span></span>

<span data-ttu-id="e970b-111">WMI 提供程序在**root\\microsoft\\medv**命名空间中实现并实现类**FTS \ _Status**，该类将公开该方法**SetFtsState**。</span><span class="sxs-lookup"><span data-stu-id="e970b-111">The WMI provider is implemented in the **root\\microsoft\\medv** namespace and implements the class **FTS\_Status**, which exposes the method **SetFtsState**.</span></span> <span data-ttu-id="e970b-112">MED-V 使用**SetFtsState**设置首次设置状态。</span><span class="sxs-lookup"><span data-stu-id="e970b-112">MED-V uses **SetFtsState** to set the first time setup state.</span></span>

<span data-ttu-id="e970b-113">此类包含以下属性。</span><span class="sxs-lookup"><span data-stu-id="e970b-113">The class contains the following properties.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e970b-114">属性</span><span class="sxs-lookup"><span data-stu-id="e970b-114">Property</span></span></th>
<th align="left"><span data-ttu-id="e970b-115">描述</span><span class="sxs-lookup"><span data-stu-id="e970b-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e970b-116">计算机</span><span class="sxs-lookup"><span data-stu-id="e970b-116">Machine</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="e970b-117">"只读" </strong> 属性，包含首次设置时预配的来宾虚拟机的名称。</span><span class="sxs-lookup"><span data-stu-id="e970b-117">Read Only</strong> property that contains the name of the guest virtual machine provisioned by first time setup.</span></span> <span data-ttu-id="e970b-118">此项包含来宾在首次设置失败时所拥有的名称。</span><span class="sxs-lookup"><span data-stu-id="e970b-118">This key contains the name that the guest would have had on first time setup failure.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e970b-119">StatusCode</span><span class="sxs-lookup"><span data-stu-id="e970b-119">StatusCode</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="e970b-120">只读 </strong> 属性，如果首次设置成功，则该属性包含零。</span><span class="sxs-lookup"><span data-stu-id="e970b-120">Read Only</strong> property that contains zero if first time setup succeeded.</span></span> <span data-ttu-id="e970b-121">返回的任何其他值等于所记录错误的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="e970b-121">Any other value returned equals the event ID for the error that is logged.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e970b-122">时间</span><span class="sxs-lookup"><span data-stu-id="e970b-122">Time</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e970b-123">首次设置完成时的 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="e970b-123">The UTC time that first time setup completed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e970b-124">用户</span><span class="sxs-lookup"><span data-stu-id="e970b-124">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e970b-125">首次运行设置的用户。</span><span class="sxs-lookup"><span data-stu-id="e970b-125">The user for which first time setup was run.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e970b-126">以下代码显示了托管对象格式（MOF）文件，该文件定义了**FTS \ _Status**类。</span><span class="sxs-lookup"><span data-stu-id="e970b-126">The following code shows the Managed Object Format (MOF) file that defines the **FTS\_Status** class.</span></span>

``` syntax
[dynamic: ToInstance, provider("MedvWmi, Version=2.0.258.0, Culture=neutral, PublicKeyToken=14986c3f172d1c2c")]
class FTS_Status
{
[read, key] string User;
[read] string Machine;
[read] sint32 StatusCode;
[read] datetime Time;
[static, implemented] void SetFtsState([in] sint32 statusCode, [in] string machine);
};
```

<span data-ttu-id="e970b-127">由于主要关注的问题很可能是首次未成功完成的 MED-V 工作区，因此你可以编写查询以仅返回首次设置失败的查询，例如：</span><span class="sxs-lookup"><span data-stu-id="e970b-127">Because your main concern is most likely those MED-V workspaces for which first time setup was not completed successfully, you can write your query to only return those that failed first time setup, for example:</span></span>

``` syntax
Select * from FTS_Status where StatusCode != 0
```

<span data-ttu-id="e970b-128">在这种情况下，监视功能将返回第一次失败设置失败的那些 MED-V 工作区的列表，您可以使用该列表执行相应的操作来解决该故障。</span><span class="sxs-lookup"><span data-stu-id="e970b-128">In this case, the monitoring feature returns a list of those MED-V workspaces that failed first time setup, which you can use to take the appropriate actions to resolve the failure.</span></span>

## <span data-ttu-id="e970b-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="e970b-129">Related topics</span></span>


[<span data-ttu-id="e970b-130">监视 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="e970b-130">Monitor MED-V Workspaces</span></span>](monitor-med-v-workspaces.md)

[<span data-ttu-id="e970b-131">如何验证首次安装设置</span><span class="sxs-lookup"><span data-stu-id="e970b-131">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

 

 





