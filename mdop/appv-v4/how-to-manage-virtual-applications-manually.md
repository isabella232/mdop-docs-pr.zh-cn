---
title: 如何手动管理虚拟应用程序
description: 如何手动管理虚拟应用程序
author: dansimp
ms.assetid: 583c5255-d3f4-4197-85cd-2a59868d85de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e8dd5bb9d62950ac1a03ad0ec14802d9e0ff56e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801287"
---
# <span data-ttu-id="50ab3-103">如何手动管理虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-103">How to Manage Virtual Applications Manually</span></span>


<span data-ttu-id="50ab3-104">你可以使用应用程序虚拟化（App-v）客户端管理控制台来管理应用 V 桌面客户端中的虚拟应用程序或远程桌面服务的 App-v 客户端（以前称为 "终端服务"）。</span><span class="sxs-lookup"><span data-stu-id="50ab3-104">You can use the Application Virtualization (App-V) Client Management Console to manage virtual applications in the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="50ab3-105">App-v 管理员可以使用执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="50ab3-105">App-V administrators can use perform the following tasks:</span></span>

## <span data-ttu-id="50ab3-106">如何加载或卸载 app-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-106">How to Load or Unload an App-V Application</span></span>


<span data-ttu-id="50ab3-107">你可以使用以下过程直接从应用程序虚拟化客户端管理控制台中的**应用程序**节点的 "**结果**" 窗格加载或卸载应用程序中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-107">You can use the following procedures to load or unload an application from the cache, directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="50ab3-108">选择此节点时，"**结果**" 窗格将显示应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="50ab3-108">When you select this node, the **Results** pane displays a list of applications.</span></span>

<span data-ttu-id="50ab3-109">**注意** 加载或卸载程序包时，程序包中的所有应用程序都将加载到或从缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="50ab3-109">**Note** When you load or unload a package, all the applications in the package are loaded into or removed from cache.</span></span> <span data-ttu-id="50ab3-110">加载程序包时，如果缓存中的空间不足，无法加载应用程序，请增加缓存大小。</span><span class="sxs-lookup"><span data-stu-id="50ab3-110">When loading a package, if you do not have adequate space in cache to load the applications, increase your cache size.</span></span> <span data-ttu-id="50ab3-111">有关缓存大小的详细信息，请参阅[如何更改缓存大小和驱动器号标识](how-to-change-the-cache-size-and-the-drive-letter-designation.md)。</span><span class="sxs-lookup"><span data-stu-id="50ab3-111">For more information about cache size, see [How to Change the Cache Size and the Drive Letter Designation](how-to-change-the-cache-size-and-the-drive-letter-designation.md).</span></span>

 

**<span data-ttu-id="50ab3-112">加载 app-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-112">To load an App-V application</span></span>**

1.  <span data-ttu-id="50ab3-113">将光标移动到 "**结果**" 窗格，右键单击所需的应用程序，然后从弹出菜单中选择 "**加载**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-113">Move the cursor to the **Results** pane, right-click the desired application, and select **Load** from the pop-up menu.</span></span>

2.  <span data-ttu-id="50ab3-114">将自动加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-114">The application is automatically loaded.</span></span> <span data-ttu-id="50ab3-115">在标记为 "**程序包状态**" 的列中跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="50ab3-115">The progress is tracked in the column labeled **Package Status**.</span></span> <span data-ttu-id="50ab3-116">必须刷新视图才能查看加载是否已完成或查看进度。</span><span class="sxs-lookup"><span data-stu-id="50ab3-116">You must refresh the view to see that the load is complete or to see the progress.</span></span>

**<span data-ttu-id="50ab3-117">卸载 app-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-117">To unload an App-V application</span></span>**

1.  <span data-ttu-id="50ab3-118">将光标移动到 "**结果**" 窗格，右键单击所需的应用程序，然后从弹出菜单中选择 "**卸载**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-118">Move the cursor to the **Results** pane, right-click the desired application, and select **Unload** from the pop-up menu.</span></span>

2.  <span data-ttu-id="50ab3-119">将自动卸载应用程序，并更新 "**程序包状态**" 列以反映更改。</span><span class="sxs-lookup"><span data-stu-id="50ab3-119">The application is automatically unloaded, and the **Package Status** column is updated to reflect the change.</span></span>

## <span data-ttu-id="50ab3-120">如何清除 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-120">How to clear an App-V application</span></span>


<span data-ttu-id="50ab3-121">你可以直接从应用程序虚拟化客户端管理控制台中的**应用程序**节点的 "**结果**" 窗格中清除来自控制台的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-121">You can clear an application from the console directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="50ab3-122">清除应用程序时，系统会删除对应于该应用程序的设置、快捷方式和文件类型关联，并且还会从用户的应用程序列表中删除该应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-122">When you clear an application, the system removes the settings, shortcuts, and file type associations that correspond to the application and also removes the application from the user’s list of applications.</span></span>

<span data-ttu-id="50ab3-123">**注意** 从控制台中清除应用程序后，您将无法再使用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-123">**Note** When you clear an application from the console, you can no longer use that application.</span></span> <span data-ttu-id="50ab3-124">但是，应用程序仍保留在缓存中，并且在同一系统上仍可供其他用户使用。</span><span class="sxs-lookup"><span data-stu-id="50ab3-124">However, the application remains in cache and is still available to other users on the same system.</span></span> <span data-ttu-id="50ab3-125">在发布刷新后，已清除的应用程序将再次变为可用。</span><span class="sxs-lookup"><span data-stu-id="50ab3-125">After a publishing refresh, the cleared applications will again become available to you.</span></span> <span data-ttu-id="50ab3-126">如果某个程序包中有多个应用程序，则在清除所有应用程序之前，不会删除用户的设置。</span><span class="sxs-lookup"><span data-stu-id="50ab3-126">If there are multiple applications in a package, the user's settings are not removed until all of the applications are cleared.</span></span>

 

**<span data-ttu-id="50ab3-127">从控制台中清除应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-127">To clear an application from the console</span></span>**

1.  <span data-ttu-id="50ab3-128">将光标移动到 "**结果**" 窗格，右键单击所需的应用程序，然后从弹出菜单中选择 "**清除**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-128">Move the cursor to the **Results** pane, right-click the desired application, and select **Clear** from the pop-up menu.</span></span>

2.  <span data-ttu-id="50ab3-129">出现确认提示时，单击 **"是"** 以删除应用程序，或单击 "**否**" 取消操作。</span><span class="sxs-lookup"><span data-stu-id="50ab3-129">At the confirmation prompt, click **Yes** to remove the application or click **No** to cancel the operation.</span></span>

## <span data-ttu-id="50ab3-130">如何修复 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-130">How to Repair an App-V application</span></span>


<span data-ttu-id="50ab3-131">若要修复选定的应用程序，你可以直接从应用程序虚拟化客户端管理控制台中的**应用程序**节点的 "**结果**" 窗格执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="50ab3-131">To repair a selected application, you can perform the following procedure directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="50ab3-132">修复应用程序时，删除任何自定义用户设置并还原默认设置。</span><span class="sxs-lookup"><span data-stu-id="50ab3-132">When you repair an application, you remove any custom user settings and restore the default settings.</span></span> <span data-ttu-id="50ab3-133">此操作不会更改或删除快捷方式或文件类型关联，也不会从缓存中删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-133">This action does not change or delete shortcuts or file type associations, and it does not remove the application from cache.</span></span>

**<span data-ttu-id="50ab3-134">修复 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-134">To repair an App-V application</span></span>**

1.  <span data-ttu-id="50ab3-135">将光标移动到 "**结果**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="50ab3-135">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="50ab3-136">右键单击所需的应用程序，然后从弹出菜单中选择 "**修复**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-136">Right-click the desired application, and select **Repair** from the pop-up menu.</span></span>

3.  <span data-ttu-id="50ab3-137">出现确认提示时，单击 **"是"** 修复应用程序，或单击 "**否**" 取消。</span><span class="sxs-lookup"><span data-stu-id="50ab3-137">At the confirmation prompt, click **Yes** to repair the application or **No** to cancel.</span></span>

## <span data-ttu-id="50ab3-138">如何导入 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-138">How to import an App-V application</span></span>


<span data-ttu-id="50ab3-139">你可以使用以下过程直接从应用程序虚拟化客户端管理控制台中的**应用程序**节点的 "**结果**" 窗格中将应用程序导入到缓存中。</span><span class="sxs-lookup"><span data-stu-id="50ab3-139">You can use the following procedure to import an application into the cache directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="50ab3-140">导入 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-140">To import an App-V application</span></span>**

1.  <span data-ttu-id="50ab3-141">将光标移动到 "**结果**" 窗格，右键单击所需的应用程序，然后从弹出菜单中选择 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-141">Move the cursor to the **Results** pane, right-click the desired application, and select **Import** from the pop-up menu.</span></span>

2.  <span data-ttu-id="50ab3-142">从 "**浏览**" 窗口中，导航到所需应用程序的程序包文件的位置，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="50ab3-142">From the **Browse** window, navigate to the location of the package file for the desired application, and then click **OK**.</span></span>

    <span data-ttu-id="50ab3-143">**注意** 如果您已经配置了导入搜索路径，或者 SFT 文件的路径与上一次成功导入相同，则不需要步骤2。</span><span class="sxs-lookup"><span data-stu-id="50ab3-143">**Note** If you have already configured an import search path or if the SFT file is in the same path as the last successful import, step 2 is not required.</span></span>

     

## <span data-ttu-id="50ab3-144">如何锁定或解锁 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-144">How to lock or unlock an App-V application</span></span>


<span data-ttu-id="50ab3-145">你可以使用以下过程锁定或解除锁定应用程序虚拟化桌面客户端缓存中的任何应用程序或远程桌面服务（以前称为终端服务）缓存的客户端中的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-145">You can use the following procedures to lock or unlock any application in the Application Virtualization Desktop Client cache or the Client for Remote Desktop Services (formerly Terminal Services) cache.</span></span> <span data-ttu-id="50ab3-146">无法从缓存中删除已锁定的应用程序，以便为新应用程序腾出空间。</span><span class="sxs-lookup"><span data-stu-id="50ab3-146">A locked application cannot be removed from the cache to make room for new applications.</span></span> <span data-ttu-id="50ab3-147">若要从应用程序虚拟化桌面客户端缓存或客户端中删除已锁定的应用程序以用于远程桌面服务缓存，必须首先将其解除锁定。</span><span class="sxs-lookup"><span data-stu-id="50ab3-147">To remove a locked application from the Application Virtualization Desktop Client cache or the Client for Remote Desktop Services cache, you must first unlock it.</span></span>

**<span data-ttu-id="50ab3-148">锁定应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-148">To lock an application</span></span>**

1.  <span data-ttu-id="50ab3-149">将光标移动到 "**结果**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="50ab3-149">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="50ab3-150">右键单击所需的应用程序，然后从弹出菜单中选择 "**锁定**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-150">Right-click the desired application, and select **Lock** from the pop-up menu.</span></span> <span data-ttu-id="50ab3-151">所选应用程序在缓存中被锁定。</span><span class="sxs-lookup"><span data-stu-id="50ab3-151">The selected application is locked in the cache.</span></span>

**<span data-ttu-id="50ab3-152">解锁应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-152">To unlock an application</span></span>**

1.  <span data-ttu-id="50ab3-153">将光标移动到 "**结果**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="50ab3-153">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="50ab3-154">右键单击所需的应用程序，然后从弹出菜单中选择 "**解锁**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-154">Right-click the desired application, and select **Unlock** from the pop-up menu.</span></span> <span data-ttu-id="50ab3-155">所选应用程序在缓存中解除锁定，并且可以删除。</span><span class="sxs-lookup"><span data-stu-id="50ab3-155">The selected application is unlocked in the cache and can be removed.</span></span>

## <span data-ttu-id="50ab3-156">如何删除 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-156">How to delete an App-V application</span></span>


<span data-ttu-id="50ab3-157">在应用程序虚拟化客户端管理控制台中选择**应用程序**节点时，"**结果**" 窗格将显示一个应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="50ab3-157">When you select the **Application** node in the Application Virtualization Client Management Console, the **Results** pane displays a list of applications.</span></span> <span data-ttu-id="50ab3-158">可以使用以下过程从 "**结果**" 窗格中删除应用程序，该操作还会从缓存中删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-158">You can use the following procedure to delete an application from the **Results** pane, which also removes the application from the cache.</span></span>

<span data-ttu-id="50ab3-159">**注意** 删除应用程序时，所选应用程序将不再可用于该客户端上的任何用户。</span><span class="sxs-lookup"><span data-stu-id="50ab3-159">**Note** When you delete an application, the selected application will no longer be available to any users on that client.</span></span> <span data-ttu-id="50ab3-160">隐藏快捷方式和文件类型关联，并从缓存中删除该应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-160">Shortcuts and file type associations are hidden, and the application is deleted from cache.</span></span> <span data-ttu-id="50ab3-161">但是，如果另一个应用程序引用所选应用程序的文件系统缓存数据中的数据，这些项目将不会被删除。</span><span class="sxs-lookup"><span data-stu-id="50ab3-161">However, if another application refers to data in the file system cache data for the selected application, these items will not be deleted.</span></span>

<span data-ttu-id="50ab3-162">在发布刷新后，已删除的应用程序将再次可供你使用。</span><span class="sxs-lookup"><span data-stu-id="50ab3-162">After a publishing refresh, the deleted applications will again become available to you.</span></span>

 

**<span data-ttu-id="50ab3-163">删除应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-163">To delete an application</span></span>**

1.  <span data-ttu-id="50ab3-164">将光标移动到 "**结果**" 窗格，右键单击所需的应用程序，然后从弹出菜单中选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-164">Move the cursor to the **Results** pane, right-click the desired application, and select **Delete** from the pop-up menu.</span></span>

2.  <span data-ttu-id="50ab3-165">出现确认提示时，单击 **"是"** 以删除应用程序，或单击 "**否**" 取消操作。</span><span class="sxs-lookup"><span data-stu-id="50ab3-165">At the confirmation prompt, click **Yes** to remove the application or click **No** to cancel the operation.</span></span>

## <span data-ttu-id="50ab3-166">如何更改 app-v 应用程序图标</span><span class="sxs-lookup"><span data-stu-id="50ab3-166">How to change an App-V application icon</span></span>


<span data-ttu-id="50ab3-167">你可以使用以下过程直接从应用程序虚拟化客户端管理控制台中的**应用程序**节点的 "**结果**" 窗格中更改与所选应用程序关联的图标。</span><span class="sxs-lookup"><span data-stu-id="50ab3-167">You can use the following procedure to change an icon associated with the selected application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="50ab3-168">更改应用程序图标</span><span class="sxs-lookup"><span data-stu-id="50ab3-168">To change an application icon</span></span>**

1.  <span data-ttu-id="50ab3-169">将光标移动到 "**结果**" 窗格，然后右键单击所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-169">Move the cursor to the **Results** pane, and right-click the desired application.</span></span>

2.  <span data-ttu-id="50ab3-170">选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-170">Select **Properties**.</span></span>

3.  <span data-ttu-id="50ab3-171">在 "**常规**" 选项卡上，单击 "**更改图标**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-171">On the **General** tab, click **Change Icon**.</span></span>

4.  <span data-ttu-id="50ab3-172">选择所需的图标，或浏览到另一个位置以选择图标。</span><span class="sxs-lookup"><span data-stu-id="50ab3-172">Select the desired icon, or browse to another location to select the icon.</span></span> <span data-ttu-id="50ab3-173">选择图标后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="50ab3-173">After you've selected the icon, click **OK**.</span></span> <span data-ttu-id="50ab3-174">新图标将显示在 "**结果**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="50ab3-174">The new icon appears in the **Results** pane.</span></span>

## <span data-ttu-id="50ab3-175">如何添加 App-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-175">How to add an App-V application</span></span>


<span data-ttu-id="50ab3-176">你可以使用以下过程直接从应用程序虚拟化客户端管理控制台中的**应用程序**节点的 "**结果**" 窗格添加应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-176">You can use the following procedure to add an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="50ab3-177">添加应用程序</span><span class="sxs-lookup"><span data-stu-id="50ab3-177">To add an application</span></span>**

1.  <span data-ttu-id="50ab3-178">在 "**结果**" 窗格中，右键单击，然后从弹出菜单中选择 "**新建应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-178">In the **Results** pane, right-click and select **New Application** from the pop-up menu.</span></span>

2.  <span data-ttu-id="50ab3-179">在向导页上，您可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="50ab3-179">On the wizard page, you can perform the following tasks:</span></span>

    1.  <span data-ttu-id="50ab3-180">"**更改" 图标**-显示标准的 Windows 图标浏览器。</span><span class="sxs-lookup"><span data-stu-id="50ab3-180">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="50ab3-181">通过浏览找到并选择所需的图标。</span><span class="sxs-lookup"><span data-stu-id="50ab3-181">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="50ab3-182">**OSD 文件路径或 URL**-输入本地绝对路径、完整 UNC 路径（网络上的共享文件或目录）或 HTTP URL。</span><span class="sxs-lookup"><span data-stu-id="50ab3-182">**OSD File Path or URL**—Enter a local absolute path, a full UNC path (shared file or directory on a network), or an HTTP URL.</span></span>

    3.  <span data-ttu-id="50ab3-183">**（OSD 浏览按钮）**-显示标准的 Windows "**打开文件**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="50ab3-183">**(OSD browse button)**—Displays the standard Windows **Open File** dialog box.</span></span> <span data-ttu-id="50ab3-184">通过浏览找到所需的文件。</span><span class="sxs-lookup"><span data-stu-id="50ab3-184">Browse to find the desired file.</span></span>

3.  <span data-ttu-id="50ab3-185">单击 "**完成**" 将应用程序添加到 "**结果**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="50ab3-185">Click **Finish** to add the application to the **Results** pane.</span></span>

## <span data-ttu-id="50ab3-186">如何发布 app-v 应用程序快捷方式</span><span class="sxs-lookup"><span data-stu-id="50ab3-186">How to publish an App-V application shortcut</span></span>


<span data-ttu-id="50ab3-187">你可以使用以下过程直接从应用程序虚拟化客户端管理控制台中的**应用程序**节点的 "**结果**" 窗格发布应用程序的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="50ab3-187">You can use the following procedure to publish shortcuts to an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="50ab3-188">发布应用程序快捷方式</span><span class="sxs-lookup"><span data-stu-id="50ab3-188">To publish application shortcuts</span></span>**

1.  <span data-ttu-id="50ab3-189">将光标移动到 "**结果**" 窗格，右键单击所需的应用程序，然后从弹出菜单中选择 "**新建快捷方式**" 以显示 "新建快捷方式" 向导。</span><span class="sxs-lookup"><span data-stu-id="50ab3-189">Move the cursor to the **Results** pane, right-click the desired application, and select **New Shortcut** from the pop-up menu to display the New Shortcut Wizard.</span></span>

2.  <span data-ttu-id="50ab3-190">在 "新建快捷方式" 向导的第一页上，选择一个图标并指定快捷方式的名称。</span><span class="sxs-lookup"><span data-stu-id="50ab3-190">On the first page of the New Shortcut Wizard, select an icon and specify a name for the shortcut.</span></span>

    1.  <span data-ttu-id="50ab3-191">"**更改" 图标**-显示标准的 Windows 图标浏览器。</span><span class="sxs-lookup"><span data-stu-id="50ab3-191">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="50ab3-192">通过浏览找到并选择所需的图标。</span><span class="sxs-lookup"><span data-stu-id="50ab3-192">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="50ab3-193">**快捷方式标题**-输入要赋予快捷方式的名称。</span><span class="sxs-lookup"><span data-stu-id="50ab3-193">**Shortcut Title**—Enter the name you want to give the shortcut.</span></span> <span data-ttu-id="50ab3-194">此字段默认为应用程序的现有名称和版本。</span><span class="sxs-lookup"><span data-stu-id="50ab3-194">This field defaults to the existing name and version of the application.</span></span>

3.  <span data-ttu-id="50ab3-195">在向导的第二页上，确定发布的快捷方式的位置。</span><span class="sxs-lookup"><span data-stu-id="50ab3-195">On the second page of the wizard, determine the location of the published shortcut.</span></span>

    1.  <span data-ttu-id="50ab3-196">**桌面**-选中此复选框以将快捷方式发布到桌面。</span><span class="sxs-lookup"><span data-stu-id="50ab3-196">**The Desktop**—Select this check box to publish the shortcut to the desktop.</span></span>

    2.  <span data-ttu-id="50ab3-197">**"快速启动" 工具栏**-选中此复选框可将快捷方式发布到 "快速启动" 工具栏。</span><span class="sxs-lookup"><span data-stu-id="50ab3-197">**The Quick Launch Toolbar**—Select this check box to publish the shortcut to the Quick Launch toolbar.</span></span>

    3.  <span data-ttu-id="50ab3-198">**"发送到" 菜单**-选中此复选框以将快捷方式发布到 "**发送到**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="50ab3-198">**The Send To Menu**—Select this check box to publish the shortcut to the **Send To** menu.</span></span>

    4.  <span data-ttu-id="50ab3-199">**"开始" 菜单中的程序**-选择 "**开始" 菜单**复选框后，此字段将变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="50ab3-199">**Programs in the Start Menu**—When you select the **Start Menu** check box, this field becomes active.</span></span> <span data-ttu-id="50ab3-200">将此字段保留为空以将快捷方式直接发布到 "程序" 文件夹的根，或者输入文件夹名称或层次结构，例如 "我的 _Computer \\Office 应用程序"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-200">Leave this field blank to publish the shortcut directly to the root of the Programs folder, or enter a folder name or hierarchy—for example, "My\_Computer\\Office Applications."</span></span> <span data-ttu-id="50ab3-201">以这种方式创建的快捷方式仅适用于当前用户。</span><span class="sxs-lookup"><span data-stu-id="50ab3-201">Shortcuts created this way are available only for the current user.</span></span>

    5.  <span data-ttu-id="50ab3-202">"**其他位置**" 和 "**浏览**" 按钮-选中 "**其他位置**" 复选框时，此字段将变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="50ab3-202">**Another location** and **Browse** button—When you select the **Another location** check box, this field becomes active.</span></span> <span data-ttu-id="50ab3-203">输入计算机上的任何有效位置或任何可用的 UNC 路径（网络上的共享文件或目录）。</span><span class="sxs-lookup"><span data-stu-id="50ab3-203">Enter any valid location on the computer or any available UNC path (shared file or directory on a network).</span></span> <span data-ttu-id="50ab3-204">"**浏览**" 按钮显示标准的 Windows**文件 "打开**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="50ab3-204">The **Browse** button displays a standard Windows **File Open** dialog box.</span></span>

4.  <span data-ttu-id="50ab3-205">在向导的第三页上，输入所需的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="50ab3-205">On the third page of the wizard, enter desired command-line parameters.</span></span>

5.  <span data-ttu-id="50ab3-206">单击 "**完成**" 以发布快捷方式并退出到 "**结果**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="50ab3-206">Click **Finish** to publish the shortcuts and exit to the **Results** pane.</span></span>

## <span data-ttu-id="50ab3-207">如何为 App-v 应用程序添加文件类型关联</span><span class="sxs-lookup"><span data-stu-id="50ab3-207">How to add a file type association for an App-V application</span></span>


<span data-ttu-id="50ab3-208">使用应用程序虚拟化客户端管理控制台中的 "**文件类型关联**" 节点，可以使用以下过程添加文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="50ab3-208">You can use the following procedure to add a file type association, using the **File Type Associations** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="50ab3-209">添加文件类型关联</span><span class="sxs-lookup"><span data-stu-id="50ab3-209">To add a file type association</span></span>**

1.  <span data-ttu-id="50ab3-210">右键单击 "**文件类型关联**" 节点，然后从弹出菜单中选择 "**新建关联**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-210">Right-click the **File Type Associations** node, and select **New Association** from the pop-up menu.</span></span>

2.  <span data-ttu-id="50ab3-211">通过完成以下信息完成对话框的第一个步骤，然后单击 "**下一**步"：</span><span class="sxs-lookup"><span data-stu-id="50ab3-211">Complete the first step of the dialog box by completing the following information, and then click **Next**:</span></span>

    1.  <span data-ttu-id="50ab3-212">**扩展名**-输入新的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="50ab3-212">**Extension**—Enter a new file name extension.</span></span> <span data-ttu-id="50ab3-213">默认情况下，此字段为空。</span><span class="sxs-lookup"><span data-stu-id="50ab3-213">This field is blank by default.</span></span>

    2.  <span data-ttu-id="50ab3-214">**使用此说明创建新的文件类型**-选择此单选按钮可在活动字段中输入新的文件类型说明。</span><span class="sxs-lookup"><span data-stu-id="50ab3-214">**Create a new file type with this description**—Select this radio button to enter a new file type description in the active field.</span></span> <span data-ttu-id="50ab3-215">默认情况下，此按钮处于选中状态，并且活动字段为空。</span><span class="sxs-lookup"><span data-stu-id="50ab3-215">This button is selected by default, and the active field is blank.</span></span>

    3.  <span data-ttu-id="50ab3-216">**将此文件类型应用于所有用户**-如果希望此关联为所有用户全局，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="50ab3-216">**Apply this file type to all users**—Select this check box when you want this association to be global for all users.</span></span> <span data-ttu-id="50ab3-217">默认情况下，此框已清除。</span><span class="sxs-lookup"><span data-stu-id="50ab3-217">By default, this box is cleared.</span></span>

    4.  <span data-ttu-id="50ab3-218">**使用现有文件类型链接此扩展名**-选择此单选按钮可将扩展名与现有文件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="50ab3-218">**Link this extension with an existing file type**—Select this radio button to associate the extension with an existing file type.</span></span> <span data-ttu-id="50ab3-219">从下拉列表中选择文件类型。</span><span class="sxs-lookup"><span data-stu-id="50ab3-219">Pick a file type from the drop-down list.</span></span> <span data-ttu-id="50ab3-220">选择此选项时，"**下一步**" 将更改为 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-220">When you choose this option, **Next** is changed to **Finish**.</span></span>

3.  <span data-ttu-id="50ab3-221">通过完成以下信息完成对话框的第二个步骤，然后单击 "**完成**" 以返回到客户端管理控制台：</span><span class="sxs-lookup"><span data-stu-id="50ab3-221">Complete the second step of the dialog box by completing the following information, and then click **Finish** to return to the Client Management Console:</span></span>

    1.  <span data-ttu-id="50ab3-222">"**更改" 图标**-单击此按钮可更改应用程序图标。</span><span class="sxs-lookup"><span data-stu-id="50ab3-222">**Change Icon**—Click this button to change the application icon.</span></span> <span data-ttu-id="50ab3-223">选择其中一个可用的图标，或浏览到新位置并选择一个图标。</span><span class="sxs-lookup"><span data-stu-id="50ab3-223">Select one of the available icons, or browse to a new location and select an icon.</span></span>

    2.  <span data-ttu-id="50ab3-224">**使用所选应用程序打开文件**-选择此单选按钮以使用现有应用程序打开文件。</span><span class="sxs-lookup"><span data-stu-id="50ab3-224">**Open files with the selected application**—Select this radio button to open the file with an existing application.</span></span> <span data-ttu-id="50ab3-225">从可用应用程序下拉列表中选择应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-225">Choose an application from the drop-down list of available applications.</span></span>

    3.  <span data-ttu-id="50ab3-226">**使用此 OSD 文件中描述的关联打开文件**-选择此单选按钮可指定一个开放软件描述符（OSD）文件，该文件确定用于打开文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50ab3-226">**Open file with the association described in this OSD file**—Select this radio button to specify an Open Software Descriptor (OSD) file that determines the application used to open the file.</span></span> <span data-ttu-id="50ab3-227">使用 "浏览" 按钮选择现有位置，或在此字段中输入路径或 HTTP 格式的 URL。</span><span class="sxs-lookup"><span data-stu-id="50ab3-227">Use the browse button to select an existing location, or enter a path or HTTP-formatted URL in this field.</span></span>

## <span data-ttu-id="50ab3-228">如何删除 App-v 应用程序的文件类型关联</span><span class="sxs-lookup"><span data-stu-id="50ab3-228">How to delete a file type association for an App-V application</span></span>


<span data-ttu-id="50ab3-229">你可以使用以下过程删除文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="50ab3-229">You can use the following procedure to delete a file type association.</span></span> <span data-ttu-id="50ab3-230">"**文件类型关联**" 节点位于 "**范围**" 窗格中 "**应用程序虚拟化**" 节点下的一个级别。</span><span class="sxs-lookup"><span data-stu-id="50ab3-230">The **File Type Associations** node is one level below the **Application Virtualization** node in the **Scope** pane.</span></span> <span data-ttu-id="50ab3-231">选择此节点时，"**结果**" 窗格将显示文件类型关联的列表。</span><span class="sxs-lookup"><span data-stu-id="50ab3-231">When you select this node, the **Results** pane displays a list of file type associations.</span></span>

**<span data-ttu-id="50ab3-232">删除文件类型关联</span><span class="sxs-lookup"><span data-stu-id="50ab3-232">To remove a file type association</span></span>**

1.  <span data-ttu-id="50ab3-233">在 "**结果**" 窗格中，右键单击要删除的文件类型关联的扩展名。</span><span class="sxs-lookup"><span data-stu-id="50ab3-233">In the **Results** pane, right-click the extension of the file type association you want to delete.</span></span>

2.  <span data-ttu-id="50ab3-234">从弹出菜单中选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="50ab3-234">Select **Delete** from the pop-up menu.</span></span>

3.  <span data-ttu-id="50ab3-235">单击 **"是"** 以删除关联，或单击 "**否**" 以返回到 "**结果**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="50ab3-235">Click **Yes** to delete the association, or click **No** to return to the **Results** pane.</span></span>

## <span data-ttu-id="50ab3-236">相关主题</span><span class="sxs-lookup"><span data-stu-id="50ab3-236">Related topics</span></span>


[<span data-ttu-id="50ab3-237">Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="50ab3-237">Application Virtualization Client</span></span>](application-virtualization-client.md)

 

 





