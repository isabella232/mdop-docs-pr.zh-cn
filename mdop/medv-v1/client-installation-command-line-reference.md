---
title: 客户端安装命令行参考
description: 客户端安装命令行参考
author: dansimp
ms.assetid: 122a593d-3314-4e9b-858a-08a25ed00c32
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 708daf82699c63dfaa1f99ae595911cf6bad3737
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804026"
---
# <span data-ttu-id="c7834-103">客户端安装命令行参考</span><span class="sxs-lookup"><span data-stu-id="c7834-103">Client Installation Command Line Reference</span></span>


**<span data-ttu-id="c7834-104">从命令行安装 MED-V</span><span class="sxs-lookup"><span data-stu-id="c7834-104">To install MED-V from the command line</span></span>**

1.  <span data-ttu-id="c7834-105">从命令行运行 MED-V 程序包，后跟下表中所述的任何可选参数。</span><span class="sxs-lookup"><span data-stu-id="c7834-105">From the command line, run the MED-V .msi package followed by any of the optional parameters described in the following table.</span></span>

2.  <span data-ttu-id="c7834-106">MED-V 程序包称为 " *MED-V\_x.msi*"，其中*x*是版本号。</span><span class="sxs-lookup"><span data-stu-id="c7834-106">The MED-V .msi package is called *MED-V\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="c7834-107">例如， *MED-V\_1.0.65.msi*。</span><span class="sxs-lookup"><span data-stu-id="c7834-107">For example, *MED-V\_1.0.65.msi*.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c7834-108">参数</span><span class="sxs-lookup"><span data-stu-id="c7834-108">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c7834-109">值</span><span class="sxs-lookup"><span data-stu-id="c7834-109">Value</span></span></th>
<th align="left"><span data-ttu-id="c7834-110">描述</span><span class="sxs-lookup"><span data-stu-id="c7834-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c7834-111">/quiet</span><span class="sxs-lookup"><span data-stu-id="c7834-111">/quiet</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="c7834-112">无提示安装</span><span class="sxs-lookup"><span data-stu-id="c7834-112">Silent installation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c7834-113">/log &lt; 日志文件的完整路径&gt;</span><span class="sxs-lookup"><span data-stu-id="c7834-113">/log &lt;full path to log file&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c7834-114">日志文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="c7834-114">The full path to the log file.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c7834-115">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="c7834-115">INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="c7834-116">安装目录的完整路径。</span><span class="sxs-lookup"><span data-stu-id="c7834-116">The full path to the installation directory.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c7834-117">VMSFOLDER</span><span class="sxs-lookup"><span data-stu-id="c7834-117">VMSFOLDER</span></span></p></td>
<td align="left"><p><span data-ttu-id="c7834-118">虚拟机文件夹的完整路径。</span><span class="sxs-lookup"><span data-stu-id="c7834-118">The full path to the virtual machine folder.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c7834-119">INSTALL_ADMIN_TOOLS</span><span class="sxs-lookup"><span data-stu-id="c7834-119">INSTALL_ADMIN_TOOLS</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="c7834-120">1,0</span><span class="sxs-lookup"><span data-stu-id="c7834-120">1,0</span></span></strong></p>
<p><span data-ttu-id="c7834-121">默认值： <strong> 0</span><span class="sxs-lookup"><span data-stu-id="c7834-121">Default: <strong>0</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c7834-122">安装 MED-V 管理工具。</span><span class="sxs-lookup"><span data-stu-id="c7834-122">Installs MED-V administration tools.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c7834-123">START_AUTOMATICALLY</span><span class="sxs-lookup"><span data-stu-id="c7834-123">START_AUTOMATICALLY</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="c7834-124">1,0</span><span class="sxs-lookup"><span data-stu-id="c7834-124">1,0</span></span></strong></p>
<p><span data-ttu-id="c7834-125">默认值： <strong> 0</span><span class="sxs-lookup"><span data-stu-id="c7834-125">Default: <strong>0</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c7834-126">每次用户登录到 Windows 时，都将自动启动 MED-V-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="c7834-126">Automatically starts MED-V client every time the user logs on to Windows.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c7834-127">SERVER_ADDRESS</span><span class="sxs-lookup"><span data-stu-id="c7834-127">SERVER_ADDRESS</span></span></p></td>
<td align="left"><p><span data-ttu-id="c7834-128">主机名或 IP</span><span class="sxs-lookup"><span data-stu-id="c7834-128">host name or IP</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c7834-129">SERVER_PORT</span><span class="sxs-lookup"><span data-stu-id="c7834-129">SERVER_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c7834-130">端口</span><span class="sxs-lookup"><span data-stu-id="c7834-130">port</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c7834-131">SERVER_SSL</span><span class="sxs-lookup"><span data-stu-id="c7834-131">SERVER_SSL</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="c7834-132">1,0</span><span class="sxs-lookup"><span data-stu-id="c7834-132">1,0</span></span></strong></p>
<p><span data-ttu-id="c7834-133">对于 <strong> https </strong> 或 <strong> http</span><span class="sxs-lookup"><span data-stu-id="c7834-133">for <strong>https</strong> or <strong>http</span></span></strong></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c7834-134">START_MEDV</span><span class="sxs-lookup"><span data-stu-id="c7834-134">START_MEDV</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="c7834-135">1,0</span><span class="sxs-lookup"><span data-stu-id="c7834-135">1,0</span></span></strong></p>
<p><span data-ttu-id="c7834-136">默认值： <strong> 1</span><span class="sxs-lookup"><span data-stu-id="c7834-136">Default: <strong>1</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c7834-137">在 MED-V 安装完成后启动 MED-V。</span><span class="sxs-lookup"><span data-stu-id="c7834-137">Starts MED-V at the completion of the MED-V installation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c7834-138">注意</span><span class="sxs-lookup"><span data-stu-id="c7834-138">Note</span></span></strong><br/><p><span data-ttu-id="c7834-139">建议在系统安装 "MED-V" 时设置 START_MEDV = 0。</span><span class="sxs-lookup"><span data-stu-id="c7834-139">It is recommended to set START_MEDV=0 in case MED-V is installed by the system.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c7834-140">DESKTOP_SHORTCUT</span><span class="sxs-lookup"><span data-stu-id="c7834-140">DESKTOP_SHORTCUT</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="c7834-141">1,0</span><span class="sxs-lookup"><span data-stu-id="c7834-141">1,0</span></span></strong></p>
<p><span data-ttu-id="c7834-142">默认值： <strong> 1</span><span class="sxs-lookup"><span data-stu-id="c7834-142">Default: <strong>1</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c7834-143">在桌面上创建快捷方式，这将启动 MED-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="c7834-143">Creates a shortcut on the desktop, which starts MED-V client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c7834-144">MINIMAL_RAM_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="c7834-144">MINIMAL_RAM_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c7834-145">RAM （MB）</span><span class="sxs-lookup"><span data-stu-id="c7834-145">RAM in MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="c7834-146">安装 MED-V 时，检查计算机是否具有指定的最小 RAM 数量。</span><span class="sxs-lookup"><span data-stu-id="c7834-146">When installing MED-V, checks whether the computer has the minimum amount of RAM specified.</span></span> <span data-ttu-id="c7834-147">如果不是，则中止安装。</span><span class="sxs-lookup"><span data-stu-id="c7834-147">If not, installation is aborted.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c7834-148">SKIP_OS_CHECK</span><span class="sxs-lookup"><span data-stu-id="c7834-148">SKIP_OS_CHECK</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="c7834-149">1,0</span><span class="sxs-lookup"><span data-stu-id="c7834-149">1,0</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c7834-150">省略操作系统验证。</span><span class="sxs-lookup"><span data-stu-id="c7834-150">Omits the operating system validation.</span></span></p></td>
</tr>
</tbody>
</table>











