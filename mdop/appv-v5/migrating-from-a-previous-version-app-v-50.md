---
title: 从以前版本迁移
description: 从以前版本迁移
author: dansimp
ms.assetid: a13cd353-b22a-48f7-af1e-5d54ede2a7e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a05bbd498cdb77a1ddf694b1aab6aeb42124775b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798325"
---
# <span data-ttu-id="479ca-103">从以前版本迁移</span><span class="sxs-lookup"><span data-stu-id="479ca-103">Migrating from a Previous Version</span></span>


<span data-ttu-id="479ca-104">通过 app-v 5.0，你可以将现有的 App-v 4.6 基础结构迁移到更灵活、更集成且更易于管理的 app-v 5.0 基础结构。</span><span class="sxs-lookup"><span data-stu-id="479ca-104">With App-V 5.0 you can migrate your existing App-V 4.6 infrastructure to the more flexible, integrated, and easier to manage App-V 5.0 infrastructure.</span></span>

<span data-ttu-id="479ca-105">规划迁移策略时，请考虑以下几个部分：</span><span class="sxs-lookup"><span data-stu-id="479ca-105">Consider the following sections when you plan your migration strategy:</span></span>

<span data-ttu-id="479ca-106">**注意** 有关 App-v 4.6 和 App-v 5.0 之间的区别的详细信息，请参阅[关于 app-v 5.0](about-app-v-50.md)的**app-v 4.6 和 app-v 5.0 部分之间的差异**。</span><span class="sxs-lookup"><span data-stu-id="479ca-106">**Note** For more information about the differences between App-V 4.6 and App-V 5.0, see the **Differences between App-V 4.6 and App-V 5.0 section** of [About App-V 5.0](about-app-v-50.md).</span></span>

 

## <span data-ttu-id="479ca-107">转换使用早期版本的 App-v 创建的程序包</span><span class="sxs-lookup"><span data-stu-id="479ca-107">Converting packages created using a prior version of App-V</span></span>


<span data-ttu-id="479ca-108">使用程序包转换器实用工具升级使用早期版本的 App-v 创建的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-108">Use the package converter utility to upgrade virtual application packages created using previous versions of App-V.</span></span> <span data-ttu-id="479ca-109">程序包转换器使用 PowerShell 转换程序包，如果你有多个需要转换的程序包，则可以帮助自动处理该进程。</span><span class="sxs-lookup"><span data-stu-id="479ca-109">The package converter uses PowerShell to convert packages and can help automate the process if you have many packages that require conversion.</span></span>

<span data-ttu-id="479ca-110">**重要提示** 转换现有程序包后，应该先测试程序包，然后再部署程序包，以确保转换过程成功。</span><span class="sxs-lookup"><span data-stu-id="479ca-110">**Important** After you convert an existing package you should test the package prior to deploying the package to ensure the conversion process was successful.</span></span>

 

**<span data-ttu-id="479ca-111">转换现有程序包之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="479ca-111">What to know before you convert existing packages</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="479ca-112">问题</span><span class="sxs-lookup"><span data-stu-id="479ca-112">Issue</span></span></th>
<th align="left"><span data-ttu-id="479ca-113">解决方法</span><span class="sxs-lookup"><span data-stu-id="479ca-113">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="479ca-114">不转换程序包脚本。</span><span class="sxs-lookup"><span data-stu-id="479ca-114">Package scripts are not converted.</span></span></p></td>
<td align="left"><p><span data-ttu-id="479ca-115">测试转换后的程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-115">Test the converted package.</span></span> <span data-ttu-id="479ca-116">如果需要，请转换脚本。</span><span class="sxs-lookup"><span data-stu-id="479ca-116">If necessary convert the script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="479ca-117">不会转换程序包注册表设置替代。</span><span class="sxs-lookup"><span data-stu-id="479ca-117">Package registry setting overrides are not converted.</span></span></p></td>
<td align="left"><p><span data-ttu-id="479ca-118">测试转换后的程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-118">Test the converted package.</span></span> <span data-ttu-id="479ca-119">如有必要，请重新添加注册表覆盖。</span><span class="sxs-lookup"><span data-stu-id="479ca-119">If necessary, re-add registry overrides.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="479ca-120">转换后，使用 DSC 的虚拟包不会链接。</span><span class="sxs-lookup"><span data-stu-id="479ca-120">Virtual packages using DSC are not linked after conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="479ca-121">使用连接组链接程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-121">Link the packages using connection groups.</span></span> <span data-ttu-id="479ca-122">请参阅 <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)"> 管理连接组 </a> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-122">See <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)">Managing Connection Groups</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="479ca-123">在转换期间检测到环境变量冲突。</span><span class="sxs-lookup"><span data-stu-id="479ca-123">Environment variable conflicts are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="479ca-124">解决关联的 .osd 文件中的任何冲突 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-124">Resolve any conflicts in the associated <strong>.osd</strong> file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="479ca-125">在转换期间检测到硬编码路径。</span><span class="sxs-lookup"><span data-stu-id="479ca-125">Hard-coded paths are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="479ca-126">硬编码路径难以正确转换。</span><span class="sxs-lookup"><span data-stu-id="479ca-126">Hard-coded paths are difficult to convert correctly.</span></span> <span data-ttu-id="479ca-127">程序包转换器将检测并返回包含硬编码路径的文件的程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-127">The package converter will detect and return packages with files that contain hard-coded paths.</span></span> <span data-ttu-id="479ca-128">查看带有硬编码路径的文件，并确定软件包是否需要该文件。</span><span class="sxs-lookup"><span data-stu-id="479ca-128">View the file with the hard-coded path, and determine whether the package requires the file.</span></span> <span data-ttu-id="479ca-129">如果是这样，建议重新序列化程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-129">If so, it is recommended to re-sequence the package.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="479ca-130">转换程序包时，检查是否有失败的文件或快捷方式。</span><span class="sxs-lookup"><span data-stu-id="479ca-130">When converting a package check for failing files or shortcuts.</span></span> <span data-ttu-id="479ca-131">在 App-v 4.6 程序包中找到该项目。</span><span class="sxs-lookup"><span data-stu-id="479ca-131">Locate the item in App-V 4.6 package.</span></span> <span data-ttu-id="479ca-132">它可能是硬编码的路径。</span><span class="sxs-lookup"><span data-stu-id="479ca-132">It could possibly be hard-coded path.</span></span> <span data-ttu-id="479ca-133">转换路径。</span><span class="sxs-lookup"><span data-stu-id="479ca-133">Convert the path.</span></span>

<span data-ttu-id="479ca-134">**注意** 建议使用 app-v 5.0 sequencer 来转换需要利用功能的关键应用程序或应用程序。</span><span class="sxs-lookup"><span data-stu-id="479ca-134">**Note** It is recommended that you use the App-V 5.0 sequencer for converting critical applications or applications that need to take advantage of features.</span></span> <span data-ttu-id="479ca-135">请参阅[如何使用 app-v 5.0 对新应用程序进行排序](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="479ca-135">See, [How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md).</span></span>

<span data-ttu-id="479ca-136">如果转换后的程序包未打开，还建议使用 App-v 5.0 sequencer 对应用程序进行重新排序。</span><span class="sxs-lookup"><span data-stu-id="479ca-136">If a converted package does not open after you convert it, it is also recommended that you re-sequence the application using the App-V 5.0 sequencer.</span></span>

 

[<span data-ttu-id="479ca-137">如何转换在以前版本的 App-V 中创建的程序包</span><span class="sxs-lookup"><span data-stu-id="479ca-137">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

## <span data-ttu-id="479ca-138">迁移客户端</span><span class="sxs-lookup"><span data-stu-id="479ca-138">Migrating Clients</span></span>


<span data-ttu-id="479ca-139">下表显示了升级客户端的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="479ca-139">The following table displays the recommended method for upgrading clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="479ca-140">任务</span><span class="sxs-lookup"><span data-stu-id="479ca-140">Task</span></span></th>
<th align="left"><span data-ttu-id="479ca-141">详细信息</span><span class="sxs-lookup"><span data-stu-id="479ca-141">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="479ca-142">将环境升级到 App-v 4.6 SP2</span><span class="sxs-lookup"><span data-stu-id="479ca-142">Upgrade your environment to App-V4.6SP2</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="479ca-143">应用程序虚拟化部署和升级注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-143">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="479ca-144">安装支持共存的 app-v 5.0 客户端。</span><span class="sxs-lookup"><span data-stu-id="479ca-144">Install the App-V 5.0 client with co-existence enabled.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)"><span data-ttu-id="479ca-145">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-145">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="479ca-146">顺序和推出 app-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-146">Sequence and roll out App-V 5.0 packages.</span></span> <span data-ttu-id="479ca-147">根据需要，取消发布 app-v 4.6 程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-147">As needed, unpublish App-V 4.6 packages.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)"><span data-ttu-id="479ca-148">如何使用 App-v 5.0 对新应用程序进行排序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-148">How to Sequence a New Application with App-V 5.0</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="479ca-149">**重要提示** 必须运行 App-v 4.6 SP3 才能使用共存模式。</span><span class="sxs-lookup"><span data-stu-id="479ca-149">**Important** You must be running App-V4.6SP3 to use coexistence mode.</span></span> <span data-ttu-id="479ca-150">此外，在对程序包进行排序时，必须配置 "管理机构" 设置，该设置位于 **"用户\*\*\*\*配置**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="479ca-150">Additionally, when you sequence a package, you must configure the Managing Authority setting, which is in the **User Configuration** is located in the **User Configuration** section.</span></span>

 

## <span data-ttu-id="479ca-151">迁移 app-v 5.0 服务器的完整基础结构</span><span class="sxs-lookup"><span data-stu-id="479ca-151">Migrating the App-V 5.0 Server Full Infrastructure</span></span>


<span data-ttu-id="479ca-152">没有直接的方法可升级到完整的 app-v 5.0 基础结构。</span><span class="sxs-lookup"><span data-stu-id="479ca-152">There is no direct method to upgrade to a full App-V 5.0 infrastructure.</span></span> <span data-ttu-id="479ca-153">有关升级 app-v 服务器的信息，请使用以下部分中的信息。</span><span class="sxs-lookup"><span data-stu-id="479ca-153">Use the information in the following section for information about upgrading the App-V server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="479ca-154">任务</span><span class="sxs-lookup"><span data-stu-id="479ca-154">Task</span></span></th>
<th align="left"><span data-ttu-id="479ca-155">详细信息</span><span class="sxs-lookup"><span data-stu-id="479ca-155">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="479ca-156">将你的环境升级到 app-v 4.6 SP3。</span><span class="sxs-lookup"><span data-stu-id="479ca-156">Upgrade your environment to App-V4.6SP3.</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="479ca-157">应用程序虚拟化部署和升级注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-157">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="479ca-158">部署 app-v 5.0 版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="479ca-158">Deploy App-V 5.0 version of the client.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"><span data-ttu-id="479ca-159">如何部署 app-v 客户端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-159">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="479ca-160">安装 App-v 5.0 server。</span><span class="sxs-lookup"><span data-stu-id="479ca-160">Install App-V 5.0 server.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"><span data-ttu-id="479ca-161">如何部署 app-v 5.0 服务器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-161">How to Deploy the App-V 5.0 Server</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="479ca-162">迁移现有程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-162">Migrate existing packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="479ca-163">查看 <strong> 使用本文的早期版本 app-v 部分创建的转换程序包 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="479ca-163">See the <strong>Converting packages created using a prior version of App-V</strong> section of this article.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="479ca-164">其他迁移任务</span><span class="sxs-lookup"><span data-stu-id="479ca-164">Additional Migration tasks</span></span>


<span data-ttu-id="479ca-165">你还可以执行其他迁移任务，例如重新配置终结点，以及打开使用运行 App-v 5.0 客户端的计算机上的早期版本创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="479ca-165">You can also perform additional migration tasks such as reconfiguring end points as well as opening a package created using a prior version on a computer running the App-V 5.0 client.</span></span> <span data-ttu-id="479ca-166">以下链接提供了有关执行这些任务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="479ca-166">The following links provide more information about performing these tasks.</span></span>

[<span data-ttu-id="479ca-167">如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="479ca-167">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="479ca-168">如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="479ca-168">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

[<span data-ttu-id="479ca-169">如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="479ca-169">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="479ca-170">如何为特定用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="479ca-170">How to Revert Extension Points From an App-V 5.0 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-a-specific-user.md)







## <span data-ttu-id="479ca-171">用于执行 App-v 迁移任务的其他资源</span><span class="sxs-lookup"><span data-stu-id="479ca-171">Other resources for performing App-V migration tasks</span></span>


[<span data-ttu-id="479ca-172">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="479ca-172">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="479ca-173">简化的 Microsoft App-V 5.1 管理服务器升级过程</span><span class="sxs-lookup"><span data-stu-id="479ca-173">A simplified Microsoft App-V 5.1 Management Server upgrade procedure</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





