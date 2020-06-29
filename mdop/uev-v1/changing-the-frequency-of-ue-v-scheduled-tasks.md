---
title: 更改 UE-V 计划任务的频率
description: 更改 UE-V 计划任务的频率
author: dansimp
ms.assetid: 33c2674e-0df4-4717-9c3d-820a90b16e19
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ced608608ffae82a29fb5ca84cfca281082b8127
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803218"
---
# <span data-ttu-id="d022c-103">更改 UE-V 计划任务的频率</span><span class="sxs-lookup"><span data-stu-id="d022c-103">Changing the Frequency of UE-V Scheduled Tasks</span></span>


<span data-ttu-id="d022c-104">Microsoft 用户体验虚拟化（UE-V） Agent 安装程序 AgentSetup.exe 在 UE-V Agent 安装期间会创建两个计划任务。</span><span class="sxs-lookup"><span data-stu-id="d022c-104">The Microsoft User Experience Virtualization (UE-V) Agent installer, AgentSetup.exe, creates two scheduled tasks during the UE-V Agent installation.</span></span> <span data-ttu-id="d022c-105">这两个任务是**模板自动更新**任务和**设置存储位置状态**任务。</span><span class="sxs-lookup"><span data-stu-id="d022c-105">The two tasks are the **Template Auto Update** task and the **Setting Storage Location Status** task.</span></span> <span data-ttu-id="d022c-106">这些计划任务无法通过 UE-V 工具进行配置。</span><span class="sxs-lookup"><span data-stu-id="d022c-106">These scheduled tasks are not configurable with the UE-V tools.</span></span> <span data-ttu-id="d022c-107">希望更改这些项目的计划任务的管理员可以创建使用 Schtasks.exe 命令行选项的脚本。</span><span class="sxs-lookup"><span data-stu-id="d022c-107">Administrators who wish to change the scheduled task for these items can create a script that uses the Schtasks.exe command-line options.</span></span>

<span data-ttu-id="d022c-108">有关 Schtasks.exe 的详细信息，请参阅[如何使用 Schtasks、exe 在 Windows Server 2003 中安排任务](https://go.microsoft.com/fwlink/?LinkID=264854)。</span><span class="sxs-lookup"><span data-stu-id="d022c-108">For more information about Schtasks.exe, see [How to use Schtasks,exe to Schedule Tasks in Windows Server 2003](https://go.microsoft.com/fwlink/?LinkID=264854).</span></span>

## <span data-ttu-id="d022c-109">模板自动更新</span><span class="sxs-lookup"><span data-stu-id="d022c-109">Template Auto-Update</span></span>


<span data-ttu-id="d022c-110">**模板自动更新**任务检查设置模板目录中是否有新的、已更新或已删除的模板。</span><span class="sxs-lookup"><span data-stu-id="d022c-110">The **Template Auto Update** task checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="d022c-111">仅当配置了 SettingsTemplateCatalog 时，此任务才会运行。</span><span class="sxs-lookup"><span data-stu-id="d022c-111">This task only runs if the SettingsTemplateCatalog is configured.</span></span> <span data-ttu-id="d022c-112">**模板自动更新**任务运行 "ApplySettingsCatalog.exe" 文件，该文件位于 ue-v agent 安装目录中。</span><span class="sxs-lookup"><span data-stu-id="d022c-112">The **Template Auto Update** task runs the ApplySettingsCatalog.exe file, which is located in the UE-V Agent install directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d022c-113">任务名称</span><span class="sxs-lookup"><span data-stu-id="d022c-113">Task name</span></span></th>
<th align="left"><span data-ttu-id="d022c-114">默认触发器</span><span class="sxs-lookup"><span data-stu-id="d022c-114">Default trigger</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d022c-115">\Microsoft\UE-V\Template 自动更新</span><span class="sxs-lookup"><span data-stu-id="d022c-115">\Microsoft\UE-V\Template Auto Update</span></span></p></td>
<td align="left"><p><span data-ttu-id="d022c-116">每天3:30</span><span class="sxs-lookup"><span data-stu-id="d022c-116">3:30 AM every day</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="d022c-117">**示例：** 以下命令将代理配置为每小时检查设置模板目录存储。</span><span class="sxs-lookup"><span data-stu-id="d022c-117">**Example:** The following command configures the agent to check the settings template catalog store every hour.</span></span>

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

## <span data-ttu-id="d022c-118">设置存储位置状态</span><span class="sxs-lookup"><span data-stu-id="d022c-118">Settings Storage Location Status</span></span>


<span data-ttu-id="d022c-119">**设置存储位置状态**任务将执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d022c-119">The **Setting Storage Location Status** task performs the following actions:</span></span>

1.  <span data-ttu-id="d022c-120">进行检查以确保 UE-V 文件夹仍在 "脱机文件" 功能中固定或注册。</span><span class="sxs-lookup"><span data-stu-id="d022c-120">Checks to make sure the UE-V folders are still pinned or registered with the offline files feature.</span></span>

2.  <span data-ttu-id="d022c-121">检查设置存储位置是否处于离线状态或联机状态。</span><span class="sxs-lookup"><span data-stu-id="d022c-121">Checks whether the settings storage location is offline or online.</span></span>

3.  <span data-ttu-id="d022c-122">在指定间隔（而不是脱机文件的默认间隔）强制执行同步。</span><span class="sxs-lookup"><span data-stu-id="d022c-122">Forces a synchronization on the specified interval instead of the default interval for offline files.</span></span>

4.  <span data-ttu-id="d022c-123">同步配置为预回迁的所有设置包。</span><span class="sxs-lookup"><span data-stu-id="d022c-123">Synchronizes any settings packages that are configured to be pre-fetched.</span></span>

5.  <span data-ttu-id="d022c-124">检查 Active Directory 主目录路径是否已更改。</span><span class="sxs-lookup"><span data-stu-id="d022c-124">Checks if the Active Directory home directory path has changed.</span></span>

6.  <span data-ttu-id="d022c-125">将当前设置存储配置写入以下位置</span><span class="sxs-lookup"><span data-stu-id="d022c-125">Writes the current settings storage configuration under the following location</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="d022c-126">任务名称</span><span class="sxs-lookup"><span data-stu-id="d022c-126">Task name</span></span></th>
    <th align="left"><span data-ttu-id="d022c-127">默认触发器</span><span class="sxs-lookup"><span data-stu-id="d022c-127">Default trigger</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="d022c-128">\Microsoft\UE-V\Settings 存储位置状态</span><span class="sxs-lookup"><span data-stu-id="d022c-128">\Microsoft\UE-V\Settings Storage Location Status</span></span></p></td>
    <td align="left"><p><span data-ttu-id="d022c-129">在任何用户登录时，每隔30分钟（每隔30分钟）将无限期重复。</span><span class="sxs-lookup"><span data-stu-id="d022c-129">At logon of any user – After triggered, repeat every 30 minutes indefinitely.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

<span data-ttu-id="d022c-130">**示例：** 以下命令将代理配置为在每小时运行上述操作。</span><span class="sxs-lookup"><span data-stu-id="d022c-130">**Example:** The following command configures the agent to run the action above every hour.</span></span>

``` syntax
schtasks /change /tn "\Microsoft\UE-V\Settings Storage Location Status" /ri 60
```

## <span data-ttu-id="d022c-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="d022c-131">Related topics</span></span>


[<span data-ttu-id="d022c-132">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="d022c-132">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="d022c-133">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="d022c-133">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





