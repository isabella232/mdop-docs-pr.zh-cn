---
title: 如何配置客户端日志文件
description: 如何配置客户端日志文件
author: dansimp
ms.assetid: dd79f8ce-61e2-4dc8-af03-2a353554a1b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 729089d683c5d102eb7eb45314583023d3362639
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801560"
---
# <span data-ttu-id="cb045-103">如何配置客户端日志文件</span><span class="sxs-lookup"><span data-stu-id="cb045-103">How to Configure the Client Log File</span></span>


<span data-ttu-id="cb045-104">你可以使用以下过程配置应用程序虚拟化（app-v）客户端日志文件。</span><span class="sxs-lookup"><span data-stu-id="cb045-104">You can use the following procedures to configure the Application Virtualization (App-V) Client log file.</span></span>

**<span data-ttu-id="cb045-105">更改日志文件位置</span><span class="sxs-lookup"><span data-stu-id="cb045-105">To change the log file location</span></span>**

-   <span data-ttu-id="cb045-106">编辑以下注册表项值以指定日志文件的新路径。</span><span class="sxs-lookup"><span data-stu-id="cb045-106">Edit the following registry key value to specify the new path for the log file.</span></span> <span data-ttu-id="cb045-107">更改此值后，必须重新启动**sftlist**服务。</span><span class="sxs-lookup"><span data-stu-id="cb045-107">You must restart the **sftlist** service after changing this value.</span></span> <span data-ttu-id="cb045-108">此位置也可以在安装后以交互方式进行更改。</span><span class="sxs-lookup"><span data-stu-id="cb045-108">This location can also be changed interactively after installation.</span></span>

    <span data-ttu-id="cb045-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName</span><span class="sxs-lookup"><span data-stu-id="cb045-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName</span></span>

**<span data-ttu-id="cb045-110">更改日志报告级别</span><span class="sxs-lookup"><span data-stu-id="cb045-110">To change the log reporting level</span></span>**

-   <span data-ttu-id="cb045-111">默认情况下，写入日志的消息类型包括严重级别4（信息）或更高版本的所有事件。</span><span class="sxs-lookup"><span data-stu-id="cb045-111">By default, the type of messages that are written to the log include all events of severity level 4 (Informational) or higher.</span></span> <span data-ttu-id="cb045-112">严重级别存储在以下键值中。</span><span class="sxs-lookup"><span data-stu-id="cb045-112">The severity level is stored in the following key value.</span></span> <span data-ttu-id="cb045-113">将此项值设置为5以启用详细日志记录。</span><span class="sxs-lookup"><span data-stu-id="cb045-113">Set this key value to 5 to enable verbose logging.</span></span> <span data-ttu-id="cb045-114">在故障排除期间使用详细日志记录，因为它将生成大量的消息，并导致日志快速填充。</span><span class="sxs-lookup"><span data-stu-id="cb045-114">Use verbose logging only for short periods during troubleshooting because it will generate a very large volume of messages and cause the log to fill up quickly.</span></span>

    <span data-ttu-id="cb045-115">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMinSeverity</span><span class="sxs-lookup"><span data-stu-id="cb045-115">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMinSeverity</span></span>

**<span data-ttu-id="cb045-116">更改日志大小</span><span class="sxs-lookup"><span data-stu-id="cb045-116">To change the log size</span></span>**

-   <span data-ttu-id="cb045-117">在应用程序虚拟化（App-v）4.5 中，日志大小由以下注册表项值控制。</span><span class="sxs-lookup"><span data-stu-id="cb045-117">In Application Virtualization (App-V) 4.5, the log size is controlled by the following registry key value.</span></span> <span data-ttu-id="cb045-118">此值默认为256MB，定义在重置之前日志可以增长到的最大大小（以 MB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="cb045-118">This value defaults to 256MB and defines the maximum size, in MB, that the log can grow to before being reset.</span></span>

    <span data-ttu-id="cb045-119">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMaxSize</span><span class="sxs-lookup"><span data-stu-id="cb045-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMaxSize</span></span>

    <span data-ttu-id="cb045-120">**小心** 此注册表项值必须设置为大于零的值，以确保日志文件恢复正常。</span><span class="sxs-lookup"><span data-stu-id="cb045-120">**Caution** This registry key value must be set to a value greater than zero to ensure the log file does get reset.</span></span>

     

**<span data-ttu-id="cb045-121">更改备份副本的数量</span><span class="sxs-lookup"><span data-stu-id="cb045-121">To change the number of backup copies</span></span>**

-   <span data-ttu-id="cb045-122">当日志文件达到最大大小时，将在下次写入日志时发生强制重置。</span><span class="sxs-lookup"><span data-stu-id="cb045-122">When the log file reaches the maximum size, a reset is forced when the next write to the log occurs.</span></span> <span data-ttu-id="cb045-123">重置导致创建新的日志文件，并且旧文件被重命名为备份。</span><span class="sxs-lookup"><span data-stu-id="cb045-123">A reset causes a new log file to be created, and the old file is renamed as a backup.</span></span> <span data-ttu-id="cb045-124">以下注册表设置控制重置文件时保留的日志文件备份副本数。</span><span class="sxs-lookup"><span data-stu-id="cb045-124">The following registry setting controls the number of backup copies of the log file that are kept when the file is reset.</span></span> <span data-ttu-id="cb045-125">默认值为4。</span><span class="sxs-lookup"><span data-stu-id="cb045-125">The default value is 4.</span></span>

    <span data-ttu-id="cb045-126">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount</span><span class="sxs-lookup"><span data-stu-id="cb045-126">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount</span></span>

    <span data-ttu-id="cb045-127">备份日志文件的格式如下所示： **sftlog\_YYYYMMDD\_hhmmss-uuu.txt**和基于重置时间（采用协调世界时（UTC）。</span><span class="sxs-lookup"><span data-stu-id="cb045-127">The format of the backup log file names is: **sftlog\_YYYYMMDD\_hhmmss-uuu.txt** and is based on the reset time, in Universal Coordinated Time (UTC).</span></span> <span data-ttu-id="cb045-128">下表列出了用于创建文件名及其说明的符号。</span><span class="sxs-lookup"><span data-stu-id="cb045-128">The following table lists the symbols used in creating the file names and their descriptions.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="cb045-129">符号</span><span class="sxs-lookup"><span data-stu-id="cb045-129">Symbol</span></span></th>
    <th align="left"><span data-ttu-id="cb045-130">描述</span><span class="sxs-lookup"><span data-stu-id="cb045-130">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="cb045-131">YYYY</span><span class="sxs-lookup"><span data-stu-id="cb045-131">YYYY</span></span></p></td>
    <td align="left"><p><span data-ttu-id="cb045-132">4位数年份</span><span class="sxs-lookup"><span data-stu-id="cb045-132">4-digit year</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="cb045-133">分钟</span><span class="sxs-lookup"><span data-stu-id="cb045-133">MM</span></span></p></td>
    <td align="left"><p><span data-ttu-id="cb045-134">2位数的月份（01–12）</span><span class="sxs-lookup"><span data-stu-id="cb045-134">2-digit month (01–12)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="cb045-135">DD</span><span class="sxs-lookup"><span data-stu-id="cb045-135">DD</span></span></p></td>
    <td align="left"><p><span data-ttu-id="cb045-136">2位月的第几天（01–31）</span><span class="sxs-lookup"><span data-stu-id="cb045-136">2-digit day of the month (01–31)</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="cb045-137">h</span><span class="sxs-lookup"><span data-stu-id="cb045-137">hh</span></span></p></td>
    <td align="left"><p><span data-ttu-id="cb045-138">小时（00–23）</span><span class="sxs-lookup"><span data-stu-id="cb045-138">hour (00–23)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="cb045-139">分钟</span><span class="sxs-lookup"><span data-stu-id="cb045-139">mm</span></span></p></td>
    <td align="left"><p><span data-ttu-id="cb045-140">分钟（00–59）</span><span class="sxs-lookup"><span data-stu-id="cb045-140">minutes (00–59)</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="cb045-141">ss</span><span class="sxs-lookup"><span data-stu-id="cb045-141">ss</span></span></p></td>
    <td align="left"><p><span data-ttu-id="cb045-142">秒（00–59）</span><span class="sxs-lookup"><span data-stu-id="cb045-142">seconds (00–59)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="cb045-143">uuu</span><span class="sxs-lookup"><span data-stu-id="cb045-143">uuu</span></span></p></td>
    <td align="left"><p><span data-ttu-id="cb045-144">毫秒（000–999）</span><span class="sxs-lookup"><span data-stu-id="cb045-144">milliseconds (000–999)</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="cb045-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="cb045-145">Related topics</span></span>


[<span data-ttu-id="cb045-146">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="cb045-146">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





