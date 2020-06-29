---
title: AGPM 4.0 中的新增功能
description: AGPM 4.0 中的新增功能
author: dansimp
ms.assetid: 31775f7f-a59c-4e64-a875-0adc9f5bc835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 82b4445a7d22fb7c1ef4f42d896f11908a22f2f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802483"
---
# <span data-ttu-id="216cf-103">AGPM 4.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="216cf-103">What's New in AGPM 4.0</span></span>


<span data-ttu-id="216cf-104">Microsoft 高级组策略管理（AGPM）4.0 包含新功能，可让你搜索组策略对象（Gpo）、筛选所显示的 Gpo 列表、将 GPO 导出和导入到其他林，以及在运行 Windows7 和 Windows Server2008R2 的计算机上安装 AGPM。</span><span class="sxs-lookup"><span data-stu-id="216cf-104">Microsoft Advanced Group Policy Management (AGPM)4.0 includes new features that let you search for Group Policy Objects (GPOs), filter the list of GPOs displayed, export and import a GPO to a different forest, and install AGPM on computers running Windows7 and Windows Server2008R2.</span></span>

## <span data-ttu-id="216cf-105">搜索和筛选 Gpo</span><span class="sxs-lookup"><span data-stu-id="216cf-105">Search and filter GPOs</span></span>


<span data-ttu-id="216cf-106">在 AGPM 4.0 中，你可以在 Gpo 列表中搜索特定属性，以筛选所显示的 Gpo 列表。</span><span class="sxs-lookup"><span data-stu-id="216cf-106">In AGPM 4.0, you can search the list of GPOs for specific attributes to filter the list of GPOs displayed.</span></span> <span data-ttu-id="216cf-107">例如，您可以搜索具有特定名称、状态或注释的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="216cf-107">For example, you can search for GPOs with a particular name, state, or comment.</span></span> <span data-ttu-id="216cf-108">你还可以搜索特定组策略管理员或特定日期上次更改的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="216cf-108">You can also search for GPOs that were last changed by a particular Group Policy administrator or on a particular date.</span></span>

<span data-ttu-id="216cf-109">你可以使用 format *GPO 属性1：搜索文本 1 GPO 属性2：搜索文本 2 ...*，其中 gpo 属性是 AGPM 中 gpo 列表中的任意列标题。</span><span class="sxs-lookup"><span data-stu-id="216cf-109">You can create a complex search string by using the format *GPO attribute 1: search text 1 GPO attribute 2: search text 2…*, where a GPO attribute is any column heading in the list of GPOs in AGPM.</span></span> <span data-ttu-id="216cf-110">例如，若要搜索名称中包含已签入并由用户 Editor03 最后更改的文本 "MyGPO" 的所有 Gpo，请在 "搜索" 框中键入以下内容：**名称： MyGPO 状态：\*\*\*\*"** 已**更改者： Editor03**"。</span><span class="sxs-lookup"><span data-stu-id="216cf-110">For example, to search for all GPOs with names including the text "MyGPO" that are checked in and were last changed by the user Editor03, you would type the following in the Search box: **name: MyGPO state:\*\*\*\*checked in\*\*\*\*changed by: Editor03**.</span></span> <span data-ttu-id="216cf-111">搜索返回部分匹配，以便你可以输入 GPO 名称或用户名的一部分，并查看其名称中包含该文本的所有 Gpo 的列表。</span><span class="sxs-lookup"><span data-stu-id="216cf-111">The search returns partial matches so that you can enter part of a GPO name or user name and view a list of all GPOs that include that text in their name.</span></span>

<span data-ttu-id="216cf-112">此外，你可以使用在 Windows 中搜索时可用的相同特殊条件搜索在特定日期或日期范围内更改的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="216cf-112">Additionally, you can use the same special terms available when you search in Windows to search for GPOs changed on a specific date or range of dates.</span></span> <span data-ttu-id="216cf-113">例如，**更改日期：\*\*\*\*lastmonth**或**更改日期：\*\*\*\*thisweek**。</span><span class="sxs-lookup"><span data-stu-id="216cf-113">For example, **change date:\*\*\*\*lastmonth** or **change date:\*\*\*\*thisweek**.</span></span>

## <span data-ttu-id="216cf-114">将 Gpo 导出并导入到不同的林</span><span class="sxs-lookup"><span data-stu-id="216cf-114">Export and import GPOs to different forests</span></span>


<span data-ttu-id="216cf-115">使用 AGPM 4.0，您可以将一个目录林中的域的受控 GPO 复制到第二个林中的域。</span><span class="sxs-lookup"><span data-stu-id="216cf-115">Using AGPM 4.0, you can copy a controlled GPO from a domain in one forest to a domain in a second forest.</span></span> <span data-ttu-id="216cf-116">例如，你可以通过使用 AGPM 将 GPO 从一个林中的域导出到 CAB 文件，将该 CAB 文件复制到一个 USB 驱动器，将 USB 驱动器插入第二个林中的域中的计算机，然后将该 GPO 导入到第二个林中的域中的 AGPM 中。</span><span class="sxs-lookup"><span data-stu-id="216cf-116">For example, you can export a GPO from a domain in one forest to a CAB file by using AGPM, copy that CAB file to a USB drive, plug the USB drive into a computer in a domain in a second forest, and import the GPO into AGPM in a domain in the second forest.</span></span> <span data-ttu-id="216cf-117">你可以将 GPO 作为新的受控 GPO 导入，或将其导入以替换已签出的现有 GPO 的设置。</span><span class="sxs-lookup"><span data-stu-id="216cf-117">You can either import the GPO as a new controlled GPO, or import it to replace the settings of an existing GPO that is checked out.</span></span>

## <span data-ttu-id="216cf-118">Windows Server 2008 R2 和 Windows 7 支持</span><span class="sxs-lookup"><span data-stu-id="216cf-118">Support for Windows Server 2008 R2 and Windows 7</span></span>


<span data-ttu-id="216cf-119">AGPM 4.0 支持 Windows Server2008R2 和 Windows7，但仍支持 Windows Server2008 和 WindowsVista® Service Pack1 （SP1）。</span><span class="sxs-lookup"><span data-stu-id="216cf-119">AGPM 4.0 supports Windows Server2008R2 and Windows7, yet still supports Windows Server2008 and WindowsVista® with Service Pack1 (SP1).</span></span> <span data-ttu-id="216cf-120">但是，混合环境中存在限制，包括更新的旧操作系统，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="216cf-120">However, there are limitations in a mixed environment that includes both the newer and older operating systems, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="216cf-121">在其上运行 AGPM 服务器4.0 的操作系统</span><span class="sxs-lookup"><span data-stu-id="216cf-121">Operating system on which AGPM Server 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="216cf-122">在其上运行 AGPM 客户端4.0 的操作系统</span><span class="sxs-lookup"><span data-stu-id="216cf-122">Operating system on which AGPM Client 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="216cf-123">AGPM 4.0 支持的状态</span><span class="sxs-lookup"><span data-stu-id="216cf-123">Status of AGPM 4.0 support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="216cf-124">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="216cf-124">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-125">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="216cf-125">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-126">支持</span><span class="sxs-lookup"><span data-stu-id="216cf-126">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="216cf-127">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="216cf-127">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-128">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="216cf-128">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-129">受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="216cf-129">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="216cf-130">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="216cf-130">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-131">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="216cf-131">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-132">不支持</span><span class="sxs-lookup"><span data-stu-id="216cf-132">Unsupported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="216cf-133">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="216cf-133">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-134">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="216cf-134">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="216cf-135">受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="216cf-135">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





