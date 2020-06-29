---
title: 关于“虚拟注册表”选项卡
description: 关于“虚拟注册表”选项卡
author: dansimp
ms.assetid: ca8d837f-8218-4f86-95fd-13a44dccd022
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 77decee4a8e07333b466db0a1bd0513efe859c9a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802399"
---
# <span data-ttu-id="5e48b-103">关于“虚拟注册表”选项卡</span><span class="sxs-lookup"><span data-stu-id="5e48b-103">About the Virtual Registry Tab</span></span>


<span data-ttu-id="5e48b-104">排序期间将创建一个虚拟注册表。</span><span class="sxs-lookup"><span data-stu-id="5e48b-104">A virtual registry is created during sequencing.</span></span> <span data-ttu-id="5e48b-105">"**虚拟注册表**" 选项卡显示顺序应用程序包运行所需的所有注册表项和值。</span><span class="sxs-lookup"><span data-stu-id="5e48b-105">The **Virtual Registry** tab displays all the registry keys and values that are required for a sequenced application package to run.</span></span> <span data-ttu-id="5e48b-106">使用此选项卡添加、编辑和删除注册表项和注册表值。</span><span class="sxs-lookup"><span data-stu-id="5e48b-106">Use this tab to add, edit, and delete registry keys and registry values.</span></span>

<span data-ttu-id="5e48b-107">还可以通过选择 "**替代本地密钥**" 来忽略托管系统的密钥，也可以通过选择 "**使用本地密钥合并**" 来创建虚拟环境中的密钥的合并视图。</span><span class="sxs-lookup"><span data-stu-id="5e48b-107">You can also choose to ignore the hosting system’s keys by selecting **Override Local Key**, or you can create a merged view of the key from within the virtual environment by selecting **Merge with Local Key**.</span></span>

<span data-ttu-id="5e48b-108">对虚拟注册表 "**设置**" 选项卡的更改影响属于特定顺序应用程序包的应用程序，但不会影响在应用程序虚拟化桌面客户端上传输到或本地安装的其他应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="5e48b-108">The changes to the virtual registry **Settings** tab affect applications that are part of the specific sequenced application package, but they do not affect the operation of other applications that are streamed to or locally installed on the Application Virtualization Desktop Client.</span></span>

<span data-ttu-id="5e48b-109">**注意** 更改虚拟注册表项和值时应小心。</span><span class="sxs-lookup"><span data-stu-id="5e48b-109">**Note** Exercise caution when changing virtual registry keys and values.</span></span> <span data-ttu-id="5e48b-110">更改这些注册表项和值可能会导致序列化应用程序包不可操作。</span><span class="sxs-lookup"><span data-stu-id="5e48b-110">Changing these keys and values might render your sequenced application package inoperable.</span></span>

 

<span data-ttu-id="5e48b-111">"**虚拟注册表**" 选项卡的左窗格显示在应用程序排序期间创建的虚拟注册表的完整列表。</span><span class="sxs-lookup"><span data-stu-id="5e48b-111">The left pane of the **Virtual Registry** tab displays the full list of virtual registries created during the sequencing of an application.</span></span>

## <span data-ttu-id="5e48b-112">多</span><span class="sxs-lookup"><span data-stu-id="5e48b-112">Columns</span></span>


<a href="" id="name"></a>**<span data-ttu-id="5e48b-113">名称</span><span class="sxs-lookup"><span data-stu-id="5e48b-113">Name</span></span>**  
<span data-ttu-id="5e48b-114">虚拟注册表中的条目名称。</span><span class="sxs-lookup"><span data-stu-id="5e48b-114">The name for the entry in the virtual registry.</span></span>

<a href="" id="type"></a>**<span data-ttu-id="5e48b-115">类型</span><span class="sxs-lookup"><span data-stu-id="5e48b-115">Type</span></span>**  
<span data-ttu-id="5e48b-116">条目存储其数据的方式。</span><span class="sxs-lookup"><span data-stu-id="5e48b-116">How the entry stores its data.</span></span>

<a href="" id="data"></a>**<span data-ttu-id="5e48b-117">数据</span><span class="sxs-lookup"><span data-stu-id="5e48b-117">Data</span></span>**  
<span data-ttu-id="5e48b-118">由条目存储的值。</span><span class="sxs-lookup"><span data-stu-id="5e48b-118">The value stored by the entry.</span></span>

<a href="" id="attributes"></a>**<span data-ttu-id="5e48b-119">属性</span><span class="sxs-lookup"><span data-stu-id="5e48b-119">Attributes</span></span>**  
<span data-ttu-id="5e48b-120">显示文件属性。</span><span class="sxs-lookup"><span data-stu-id="5e48b-120">Displays the file attributes.</span></span>

## <span data-ttu-id="5e48b-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="5e48b-121">Related topics</span></span>


[<span data-ttu-id="5e48b-122">如何修改虚拟注册表项信息</span><span class="sxs-lookup"><span data-stu-id="5e48b-122">How to Modify Virtual Registry Key Information</span></span>](how-to-modify-virtual-registry-key-information.md)

[<span data-ttu-id="5e48b-123">Sequencer 控制台</span><span class="sxs-lookup"><span data-stu-id="5e48b-123">Sequencer Console</span></span>](sequencer-console.md)

 

 





