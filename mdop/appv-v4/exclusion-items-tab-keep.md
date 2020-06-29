---
title: “排除项”选项卡
description: “排除项”选项卡
author: dansimp
ms.assetid: 864e46dd-3d6e-4a1b-acf4-9dc00548117e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f472fb61c121a1977c3c4ff927bd1ba6f680d86
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802996"
---
# <span data-ttu-id="63ce3-103">“排除项”选项卡</span><span class="sxs-lookup"><span data-stu-id="63ce3-103">Exclusion Items Tab</span></span>


<span data-ttu-id="63ce3-104">"**排除项目**" 选项卡显示应用程序虚拟化 Sequencer 从虚拟文件系统或虚拟注册表中排除的表达式。</span><span class="sxs-lookup"><span data-stu-id="63ce3-104">The **Exclusion Items** tab displays the expressions that the Application Virtualization Sequencer excludes from the virtual file system or virtual registry.</span></span> <span data-ttu-id="63ce3-105">将排除这些表达式，以确保顺序应用程序包可以在应用程序虚拟化桌面客户端上运行。</span><span class="sxs-lookup"><span data-stu-id="63ce3-105">These expressions are excluded to ensure that the sequenced application package can run on Application Virtualization Desktop Clients.</span></span> <span data-ttu-id="63ce3-106">你还可以排除可能不需要在序列中的非标准安装目录。</span><span class="sxs-lookup"><span data-stu-id="63ce3-106">You can also exclude non-standard installation directories that might be unwanted in the sequencing.</span></span>

<span data-ttu-id="63ce3-107">此选项卡包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="63ce3-107">This tab contains the following elements.</span></span>

<a href="" id="exclude-path"></a>**<span data-ttu-id="63ce3-108">排除路径</span><span class="sxs-lookup"><span data-stu-id="63ce3-108">Exclude Path</span></span>**  
<span data-ttu-id="63ce3-109">如果在分析虚拟文件系统项或虚拟注册表项时遇到，则显示 Sequencer 不包括的变量名称。</span><span class="sxs-lookup"><span data-stu-id="63ce3-109">Displays variable names that the Sequencer excludes if encountered while parsing virtual file system items or virtual registry items.</span></span>

<a href="" id="resolves-to"></a>**<span data-ttu-id="63ce3-110">解析为</span><span class="sxs-lookup"><span data-stu-id="63ce3-110">Resolves To</span></span>**  
<span data-ttu-id="63ce3-111">显示对应于 Sequencer 变量的实际路径。</span><span class="sxs-lookup"><span data-stu-id="63ce3-111">Displays the actual paths that correspond to the Sequencer variables.</span></span>

<a href="" id="map-type"></a>**<span data-ttu-id="63ce3-112">地图类型</span><span class="sxs-lookup"><span data-stu-id="63ce3-112">Map Type</span></span>**  
<span data-ttu-id="63ce3-113">显示 Sequencer 适用于分析虚拟文件系统或虚拟注册表中的项的映射规则。</span><span class="sxs-lookup"><span data-stu-id="63ce3-113">Displays mapping rules that the Sequencer applies to parse items in the virtual file system or virtual registry.</span></span> <span data-ttu-id="63ce3-114">可能出现下列值之一：</span><span class="sxs-lookup"><span data-stu-id="63ce3-114">One of the following values can occur:</span></span>

<a href="" id="new"></a>**<span data-ttu-id="63ce3-115">新增</span><span class="sxs-lookup"><span data-stu-id="63ce3-115">New</span></span>**  
<span data-ttu-id="63ce3-116">单击以输入新的排除项。</span><span class="sxs-lookup"><span data-stu-id="63ce3-116">Click to enter a new exclusion item.</span></span>

<a href="" id="edit"></a>**<span data-ttu-id="63ce3-117">编辑</span><span class="sxs-lookup"><span data-stu-id="63ce3-117">Edit</span></span>**  
<span data-ttu-id="63ce3-118">单击以编辑选定的排除项。</span><span class="sxs-lookup"><span data-stu-id="63ce3-118">Click to edit a selected exclusion.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="63ce3-119">删除</span><span class="sxs-lookup"><span data-stu-id="63ce3-119">Delete</span></span>**  
<span data-ttu-id="63ce3-120">单击以删除选定的排除项。</span><span class="sxs-lookup"><span data-stu-id="63ce3-120">Click to remove a selected exclusion.</span></span>

<a href="" id="save-as-default"></a>**<span data-ttu-id="63ce3-121">另存为默认值</span><span class="sxs-lookup"><span data-stu-id="63ce3-121">Save As Default</span></span>**  
<span data-ttu-id="63ce3-122">单击以将当前的排除项目保存为默认值。</span><span class="sxs-lookup"><span data-stu-id="63ce3-122">Click to save the current exclusion items as your default.</span></span>

<a href="" id="restore-defaults"></a>**<span data-ttu-id="63ce3-123">还原默认值</span><span class="sxs-lookup"><span data-stu-id="63ce3-123">Restore Defaults</span></span>**  
<span data-ttu-id="63ce3-124">单击以还原默认分配的排除项目并删除您添加的任何项目。</span><span class="sxs-lookup"><span data-stu-id="63ce3-124">Click to restore default-assigned exclusion items and remove any items you added.</span></span>

<a href="" id="ok"></a>**<span data-ttu-id="63ce3-125">“确定”</span><span class="sxs-lookup"><span data-stu-id="63ce3-125">OK</span></span>**  
<span data-ttu-id="63ce3-126">单击以接受显示的例外。</span><span class="sxs-lookup"><span data-stu-id="63ce3-126">Click to accept the displayed exceptions.</span></span>

<a href="" id="cancel"></a>**<span data-ttu-id="63ce3-127">取消</span><span class="sxs-lookup"><span data-stu-id="63ce3-127">Cancel</span></span>**  
<span data-ttu-id="63ce3-128">单击以取消您所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="63ce3-128">Click to cancel any changes you have made.</span></span>

## <span data-ttu-id="63ce3-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="63ce3-129">Related topics</span></span>


[<span data-ttu-id="63ce3-130">Application Virtualization Sequencer“选项”对话框</span><span class="sxs-lookup"><span data-stu-id="63ce3-130">Application Virtualization Sequencer Options Dialog Box</span></span>](application-virtualization-sequencer-options-dialog-box.md)

[<span data-ttu-id="63ce3-131">“排除项”对话框</span><span class="sxs-lookup"><span data-stu-id="63ce3-131">Exclusion Item Dialog Box</span></span>](exclusion-item-dialog-box.md)

 

 





