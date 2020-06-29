---
title: 如何使用 PowerShell 命令执行 DaRT 任务
description: 如何使用 PowerShell 命令执行 DaRT 任务
author: dansimp
ms.assetid: f5a5c5f9-d667-4c85-9e82-7baf0b2aec6e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fdf167ca81281da4e04dae10e34bad6122ec05aa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803200"
---
# <span data-ttu-id="4b19b-103">如何使用 PowerShell 命令执行 DaRT 任务</span><span class="sxs-lookup"><span data-stu-id="4b19b-103">How to Perform DaRT Tasks by Using PowerShell Commands</span></span>


<span data-ttu-id="4b19b-104">Microsoft 诊断和恢复工具集（DaRT）10提供以下列出的一组 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b19b-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 10 provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4b19b-105">管理员可以使用这些 PowerShell cmdlet 从命令提示符而不是从 DaRT 恢复映像向导执行各种 DaRT 10 服务器任务。</span><span class="sxs-lookup"><span data-stu-id="4b19b-105">Administrators can use these PowerShell cmdlets to perform various DaRT 10 server tasks from the command prompt rather than from the DaRT Recovery Image wizard.</span></span>

## <span data-ttu-id="4b19b-106">使用 PowerShell 命令管理 DaRT</span><span class="sxs-lookup"><span data-stu-id="4b19b-106">To administer DaRT by using PowerShell commands</span></span>


<span data-ttu-id="4b19b-107">使用此处介绍的 PowerShell cmdlet 管理 DaRT。</span><span class="sxs-lookup"><span data-stu-id="4b19b-107">Use the PowerShell cmdlets described here to administer DaRT.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b19b-108">名称</span><span class="sxs-lookup"><span data-stu-id="4b19b-108">Name</span></span></th>
<th align="left"><span data-ttu-id="4b19b-109">描述</span><span class="sxs-lookup"><span data-stu-id="4b19b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b19b-110">Copy-DartImage</span><span class="sxs-lookup"><span data-stu-id="4b19b-110">Copy-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b19b-111">将 ISO 刻录到 CD、DVD 或 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="4b19b-111">Burns an ISO to a CD, DVD, or USB drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b19b-112">Export-DartImage</span><span class="sxs-lookup"><span data-stu-id="4b19b-112">Export-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b19b-113">允许将包含 DaRT 映像的源 WIM 文件转换为 ISO 文件。</span><span class="sxs-lookup"><span data-stu-id="4b19b-113">Allows the source WIM file, which contains a DaRT image, to be converted into an ISO file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b19b-114">新-DartConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b19b-114">New-DartConfiguration</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b19b-115">创建将 DaRT 工具集应用于 Windows 映像所需的 DaRT 配置对象。</span><span class="sxs-lookup"><span data-stu-id="4b19b-115">Creates a DaRT configuration object that is needed to apply a DaRT toolset to a Windows Image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b19b-116">Set-DartImage</span><span class="sxs-lookup"><span data-stu-id="4b19b-116">Set-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b19b-117">将 DartConfiguration 对象应用于已安装的 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="4b19b-117">Applies a DartConfiguration object to a mounted Windows Image.</span></span> <span data-ttu-id="4b19b-118">这包括添加所有文件、配置和程序包依赖关系。</span><span class="sxs-lookup"><span data-stu-id="4b19b-118">This includes adding all files, configuration, and package dependencies.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4b19b-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="4b19b-119">Related topics</span></span>


[<span data-ttu-id="4b19b-120">使用 PowerShell 管理 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="4b19b-120">Administering DaRT 10 Using PowerShell</span></span>](administering-dart-10-using-powershell.md)

 

 





