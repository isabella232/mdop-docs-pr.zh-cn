---
title: 如何为 MED-V 工作区配置 Web 设置
description: 如何为 MED-V 工作区配置 Web 设置
author: dansimp
ms.assetid: 9a6cd28f-7e4f-468f-830a-7b1d9abd3af3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 770d3fa9a03c9754db86ca348390d0b916de6d5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804094"
---
# <span data-ttu-id="64b5f-103">如何为 MED-V 工作区配置 Web 设置</span><span class="sxs-lookup"><span data-stu-id="64b5f-103">How to Configure Web Settings for a MED-V Workspace</span></span>


<span data-ttu-id="64b5f-104">仅可在较早版本的 Internet Explorer 中显示且不存在于主机操作系统中的网站可以在早期版本的 Internet Explorer 中在 MED-V 工作区中查看。</span><span class="sxs-lookup"><span data-stu-id="64b5f-104">Web sites that can only be displayed in older versions of Internet Explorer and that do not exist in the host operating system can be viewed in older versions of Internet Explorer within the MED-V workspace.</span></span> <span data-ttu-id="64b5f-105">用户无需在 MED-V 工作区中打开浏览器即可查看指定的网站。</span><span class="sxs-lookup"><span data-stu-id="64b5f-105">The user does not need to open a browser in the MED-V workspace to view the specified Web sites.</span></span> <span data-ttu-id="64b5f-106">用户可以打开主机上的浏览器，并自动重定向到 MED-V 工作区，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="64b5f-106">The user can open a browser on the host and automatically be redirected to the MED-V workspace and vice versa.</span></span>

<span data-ttu-id="64b5f-107">以下过程介绍了如何为 MED-V 工作区设置 Web 浏览规则列表。</span><span class="sxs-lookup"><span data-stu-id="64b5f-107">The following procedures describe how you can set a list of Web browsing rules for a MED-V workspace.</span></span> <span data-ttu-id="64b5f-108">这些规则中包含的所有网站均可在 MED-V 工作区或主机上浏览，如管理员定义。</span><span class="sxs-lookup"><span data-stu-id="64b5f-108">All sites included in the rules can be browsed either in the MED-V workspace or on the host, as defined by the administrator.</span></span> <span data-ttu-id="64b5f-109">在规则中未定义的所有网站从请求它们的环境中进行浏览。</span><span class="sxs-lookup"><span data-stu-id="64b5f-109">All sites not defined within the rules are browsed from the environment in which they were requested.</span></span> <span data-ttu-id="64b5f-110">但是，你也可以将它们配置为组，以便在 MED-V 工作区或主机中进行浏览。</span><span class="sxs-lookup"><span data-stu-id="64b5f-110">However, you can configure them as a group as well, to be browsed in the MED-V workspace or the host.</span></span>

**<span data-ttu-id="64b5f-111">注意</span><span class="sxs-lookup"><span data-stu-id="64b5f-111">Note</span></span>**  
<span data-ttu-id="64b5f-112">Web 设置仅应用于 Internet Explorer 和其他任何浏览器。</span><span class="sxs-lookup"><span data-stu-id="64b5f-112">Web settings are applied only to Internet Explorer and to no other browsers.</span></span>



<span data-ttu-id="64b5f-113">所有 Web 设置均在 " **web** " 选项卡上的 "**策略**" 模块中配置。</span><span class="sxs-lookup"><span data-stu-id="64b5f-113">All Web settings are configured in the **Policy** module, on the **Web** tab.</span></span>

## <span data-ttu-id="64b5f-114">如何配置 MED-V 工作区的 Web 设置</span><span class="sxs-lookup"><span data-stu-id="64b5f-114">How to Configure Web Settings for the MED-V Workspace</span></span>


**<span data-ttu-id="64b5f-115">配置 MED-V 工作区的 Web 设置</span><span class="sxs-lookup"><span data-stu-id="64b5f-115">To configure Web settings for the MED-V workspace</span></span>**

1.  <span data-ttu-id="64b5f-116">单击要配置的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="64b5f-116">Click the MED-V workspace to be configured.</span></span>

2.  <span data-ttu-id="64b5f-117">选中 "**浏览下表中定义的 url 列表**" 复选框，以便在用户浏览到符合指定 Web 规则的 URL 时，将用户重定向到 med-v 工作区或主机中的浏览器。</span><span class="sxs-lookup"><span data-stu-id="64b5f-117">Select the **Browse the list of URLs defined in the following table** check box to redirect the user to a browser within the MED-V workspace or host, when the user browses to a URL that conforms to the Web rules specified.</span></span>

3.  <span data-ttu-id="64b5f-118">单击下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="64b5f-118">Click one of the following:</span></span>

    -   <span data-ttu-id="64b5f-119">**在工作区中**-重定向到 med-v 工作区中的浏览器。</span><span class="sxs-lookup"><span data-stu-id="64b5f-119">**In the Workspace**—Redirect to a browser in the MED-V workspace.</span></span>

    -   <span data-ttu-id="64b5f-120">**在主机中**-重定向到主机上的浏览器。</span><span class="sxs-lookup"><span data-stu-id="64b5f-120">**In the host**—Redirect to a browser on the host.</span></span>

4.  <span data-ttu-id="64b5f-121">选中 "**浏览所有其他 url** " 复选框以将所有从 Web 规则中排除的 url 重定向到主机或 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="64b5f-121">Select the **Browse all other URLs** check box to redirect all URLs excluded from the Web rules to the host or MED-V workspace.</span></span>

5.  <span data-ttu-id="64b5f-122">单击下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="64b5f-122">Click one of the following:</span></span>

    -   <span data-ttu-id="64b5f-123">**在工作区中**-将所有其他 url 重定向到 med-v 工作区中的浏览器。</span><span class="sxs-lookup"><span data-stu-id="64b5f-123">**In the Workspace**—Redirect all other URLs to a browser in the MED-V workspace.</span></span>

    -   <span data-ttu-id="64b5f-124">**在主机中**，将所有其他 url 重定向到主机上的浏览器。</span><span class="sxs-lookup"><span data-stu-id="64b5f-124">**In the host**—Redirect all other URLs to a browser on the host.</span></span>

6.  <span data-ttu-id="64b5f-125">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="64b5f-125">On the **Policy** menu, select **Commit**.</span></span>

## <span data-ttu-id="64b5f-126">如何添加 Web 规则</span><span class="sxs-lookup"><span data-stu-id="64b5f-126">How to Add a Web Rule</span></span>


**<span data-ttu-id="64b5f-127">添加 Web 规则</span><span class="sxs-lookup"><span data-stu-id="64b5f-127">To add a Web rule</span></span>**

1.  <span data-ttu-id="64b5f-128">选中 "**浏览下表中定义的 url 列表**" 复选框以启用 Web 浏览规则。</span><span class="sxs-lookup"><span data-stu-id="64b5f-128">Select the **Browse the list of URLs defined in the following table** check box to enable the Web browsing rules.</span></span>

2.  <span data-ttu-id="64b5f-129">单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="64b5f-129">Click **Add**.</span></span>

    <span data-ttu-id="64b5f-130">添加了新的 Web 规则。</span><span class="sxs-lookup"><span data-stu-id="64b5f-130">A new Web rule is added.</span></span>

3.  <span data-ttu-id="64b5f-131">按下表所述配置 Web 规则属性。</span><span class="sxs-lookup"><span data-stu-id="64b5f-131">Configure the Web rule properties as described in the following table.</span></span>

4.  <span data-ttu-id="64b5f-132">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="64b5f-132">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="64b5f-133">MED-V 工作区 Web 属性</span><span class="sxs-lookup"><span data-stu-id="64b5f-133">MED-V Workspace Web Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64b5f-134">属性</span><span class="sxs-lookup"><span data-stu-id="64b5f-134">Property</span></span></th>
<th align="left"><span data-ttu-id="64b5f-135">描述</span><span class="sxs-lookup"><span data-stu-id="64b5f-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64b5f-136">类型</span><span class="sxs-lookup"><span data-stu-id="64b5f-136">Type</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="64b5f-137">域后缀 </strong> -访问以 "Value" 属性中指定的后缀结尾的任何主机地址 <strong> </strong> ，并根据 Web 浏览中的选项设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="64b5f-137">Domain suffix</strong>—Access to any host address ending with the suffix specified in the <strong>Value</strong> property and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="64b5f-138">IP 前缀 </strong> ——在 Value 属性中指定的前缀范围内访问任何完整或部分 IP 地址 <strong> </strong> ，并根据 Web 浏览中的选项设置 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="64b5f-138">IP Prefix</strong>—Access to any full or partial IP address in the range of the prefix specified in the <strong>Value</strong> property and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="64b5f-139">所有本地地址 </strong> —访问所有不带 &#39; 的地址。 &#39; 并根据 Web 浏览中设置的选项进行设置。 <strong> </strong></span><span class="sxs-lookup"><span data-stu-id="64b5f-139">All Local Addresses</strong>—Access to all addresses without a &#39;.&#39; and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64b5f-140">值</span><span class="sxs-lookup"><span data-stu-id="64b5f-140">Value</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="64b5f-141">如果在 <strong> </strong> "类型" 属性中选择了 "域后缀" <strong> </strong> ，请输入域后缀。</span><span class="sxs-lookup"><span data-stu-id="64b5f-141">If <strong>Domain suffix</strong> is selected in the <strong>Type</strong> property, enter a domain suffix.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="64b5f-142">注意</span><span class="sxs-lookup"><span data-stu-id="64b5f-142">Note</span></span></strong><br/><ul>
<li><p><span data-ttu-id="64b5f-143">不要 &quot; \* &quot; 在后缀前输入。</span><span class="sxs-lookup"><span data-stu-id="64b5f-143">Do not enter &quot;\*&quot; before the suffix.</span></span></p></li>
<li><p><span data-ttu-id="64b5f-144">域后缀也支持别名。</span><span class="sxs-lookup"><span data-stu-id="64b5f-144">Domain suffixes support aliases as well.</span></span></p></li>
</ul>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="64b5f-145">如果在 "类型" 属性中选择了 "IP 前缀 <strong> </strong> "，请输入完整或部分 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="64b5f-145">If IP Prefix is selected in the <strong>Type</strong> property, enter a full or partial IP address.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="64b5f-146">如何删除 Web 规则</span><span class="sxs-lookup"><span data-stu-id="64b5f-146">How to Delete a Web Rule</span></span>


**<span data-ttu-id="64b5f-147">删除 Web 规则</span><span class="sxs-lookup"><span data-stu-id="64b5f-147">To delete a Web rule</span></span>**

1.  <span data-ttu-id="64b5f-148">在 " **web** " 窗格中，选择要删除的 Web 规则。</span><span class="sxs-lookup"><span data-stu-id="64b5f-148">In the **Web** pane, select the Web rule to delete.</span></span>

2.  <span data-ttu-id="64b5f-149">单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="64b5f-149">Click **Remove**.</span></span>

    <span data-ttu-id="64b5f-150">Web 规则已删除。</span><span class="sxs-lookup"><span data-stu-id="64b5f-150">The Web rule is deleted.</span></span>

## <span data-ttu-id="64b5f-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="64b5f-151">Related topics</span></span>


[<span data-ttu-id="64b5f-152">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="64b5f-152">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="64b5f-153">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="64b5f-153">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)









