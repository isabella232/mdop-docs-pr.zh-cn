---
title: 部署疑难解答
description: 部署疑难解答
author: dansimp
ms.assetid: 9ee980f2-4e77-4020-9f0e-8c2ffdc390ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe9677175c9538bc070d2adea17a96351397d9a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803260"
---
# <span data-ttu-id="ee0e1-103">部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="ee0e1-103">Deployment Troubleshooting</span></span>


<span data-ttu-id="ee0e1-104">本主题包含的信息可帮助你解决 Microsoft 企业桌面虚拟化（MED-V）2.0 中的部署问题。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-104">This topic includes information to help you troubleshoot deployment issues in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="ee0e1-105">对 MED-V 部署中的问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="ee0e1-105">Troubleshooting Issues in MED-V Deployment</span></span>


<span data-ttu-id="ee0e1-106">在部署 MED-V 时可能会出现以下问题。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-106">The following issue might occur when you deploy MED-V.</span></span> <span data-ttu-id="ee0e1-107">该解决方案可帮助解决此问题。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-107">The solution helps troubleshoot this issue.</span></span>

**<span data-ttu-id="ee0e1-108">如果仅为当前用户安装 MED-V，则会出现问题。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-108">Problems Occur if Installing MED-V for Current User Only.</span></span>** <span data-ttu-id="ee0e1-109">MED-V 仅支持安装用于所有用户的 MED-V 工作区包装程序、MED-V 主机代理和 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-109">MED-V only supports the installation of the MED-V Workspace Packager, the MED-V Host Agent, and the MED-V workspace for all users.</span></span> <span data-ttu-id="ee0e1-110">为当前用户安装仅会在组件安装和 MED-V 工作区的设置中导致失败。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-110">Installing for the current user only causes failures in the installation of the components and in the setup of the MED-V workspace.</span></span>

**<span data-ttu-id="ee0e1-111">解决方案</span><span class="sxs-lookup"><span data-stu-id="ee0e1-111">Solution</span></span>**

<span data-ttu-id="ee0e1-112">安装 MED-V 组件时，切勿使用 " **ALLUSERS =" "** 选项。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-112">Never use the option **ALLUSERS=””** when installing the MED-V components.</span></span>

**<span data-ttu-id="ee0e1-113">MED-V 需要以独占方式使用虚拟化堆栈。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-113">MED-V Requires Exclusive Use of the Virtualization Stack.</span></span>** <span data-ttu-id="ee0e1-114">一次只能在计算机上运行一个虚拟化堆栈。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-114">Only one virtualization stack can be run at a time on a computer.</span></span> <span data-ttu-id="ee0e1-115">Windows 虚拟 PC 必须使用虚拟堆栈，而 MED-V 依赖于 Windows 虚拟 PC。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-115">Windows Virtual PC must use the virtual stack, and MED-V depends on Windows Virtual PC.</span></span> <span data-ttu-id="ee0e1-116">因此，如果你尝试在运行使用虚拟堆栈的其他应用程序时尝试部署或使用 MED-V，则不能运行或成功安装 MED-V。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-116">Therefore, if you try to deploy or use MED-V when other applications are running that use the virtual stack, MED-V cannot run or be successfully installed.</span></span>

**<span data-ttu-id="ee0e1-117">解决方案</span><span class="sxs-lookup"><span data-stu-id="ee0e1-117">Solution</span></span>**

<span data-ttu-id="ee0e1-118">在安装或运行 MED-V 之前，请关闭运行使用虚拟化堆栈的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-118">Close any application that is running that uses the virtualization stack before you install or run MED-V.</span></span>

**<span data-ttu-id="ee0e1-119">卸载后，快捷方式仍然保留。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-119">Shortcuts Remain after Uninstall.</span></span>** <span data-ttu-id="ee0e1-120">默认情况下，卸载 MED-V 时，将删除最终用户的 "**开始**" 菜单中的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-120">By default, when you uninstall MED-V, shortcuts in the end user’s **Start** menu are removed.</span></span> <span data-ttu-id="ee0e1-121">但是，在某些情况下（例如，对于运行漫游配置文件的最终用户而言），MED-V 发布的应用程序的快捷方式将保留在最终用户的 "**开始**" 菜单中。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-121">However, in certain situations, such as for end users who are running roaming profiles, shortcuts to MED-V published applications remain in the end user’s **Start** menu.</span></span>

**<span data-ttu-id="ee0e1-122">解决方案</span><span class="sxs-lookup"><span data-stu-id="ee0e1-122">Solution</span></span>**

<span data-ttu-id="ee0e1-123">若要手动删除 "**开始**" 菜单上的剩余快捷方式，请右键单击快捷方式，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-123">To manually delete the remaining shortcuts on the **Start** menu, right-click the shortcuts, and then click **Remove**.</span></span>

**<span data-ttu-id="ee0e1-124">在 MED-V 工作区中禁用登录消息组策略设置。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-124">Disable Logon Message Group Policy Setting in the MED-V Workspace.</span></span>** <span data-ttu-id="ee0e1-125">如果在 MED-V 工作区中启用了 Windows XP 登录消息，则最终用户必须在每次需要打开 MED-V 虚拟应用程序时登录。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-125">If the Windows XP logon message is enabled in the MED-V workspace, the end user must log on every time they want to open a MED-V virtual application.</span></span> <span data-ttu-id="ee0e1-126">这会产生较差的用户体验。</span><span class="sxs-lookup"><span data-stu-id="ee0e1-126">This creates a poor user experience.</span></span>

**<span data-ttu-id="ee0e1-127">解决方案</span><span class="sxs-lookup"><span data-stu-id="ee0e1-127">Solution</span></span>**

<span data-ttu-id="ee0e1-128">在 MED-V 虚拟机中禁用以下组策略设置：</span><span class="sxs-lookup"><span data-stu-id="ee0e1-128">Disable the following Group Policy settings in the MED-V virtual machine:</span></span>

**<span data-ttu-id="ee0e1-129">交互式登录: 试图登录的用户的消息文本</span><span class="sxs-lookup"><span data-stu-id="ee0e1-129">Interactive logon: Message text for users attempting to log on</span></span>**

**<span data-ttu-id="ee0e1-130">交互式登录: 试图登录的用户的消息标题</span><span class="sxs-lookup"><span data-stu-id="ee0e1-130">Interactive logon: Message title for users attempting to log on</span></span>**

## <span data-ttu-id="ee0e1-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="ee0e1-131">Related topics</span></span>


[<span data-ttu-id="ee0e1-132">操作疑难解答</span><span class="sxs-lookup"><span data-stu-id="ee0e1-132">Operations Troubleshooting</span></span>](operations-troubleshooting-medv2.md)

 

 





