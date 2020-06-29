---
title: 如何使用命令行安装客户端
description: 如何使用命令行安装客户端
author: dansimp
ms.assetid: ed372403-64ff-48ff-a3cd-a46cad04a4d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca594e1399b4ca4f680f68efffcd011fdc5f042
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801371"
---
# <span data-ttu-id="e9c5b-103">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="e9c5b-103">How to Install the Client by Using the Command Line</span></span>


<span data-ttu-id="e9c5b-104">本部分中的主题包括使用 setup.exe 或 setup.msi 安装应用程序虚拟化（App-v）桌面客户端或远程桌面服务（以前称为终端服务）的 App-v 客户端的过程。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-104">The topics in this section include procedures to install either the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using either setup.exe or setup.msi.</span></span> <span data-ttu-id="e9c5b-105">需要具有管理员权限才能运行任一安装程序。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-105">Administrative rights are required to run either setup program.</span></span>

<span data-ttu-id="e9c5b-106">在安装期间，你可以使用可选的命令行参数对 App-v 客户端应用特定的配置设置。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-106">You can use optional command-line parameters to apply specific configuration settings to the App-V client during the installation.</span></span> <span data-ttu-id="e9c5b-107">有关使用参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-107">For more information about using parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span> <span data-ttu-id="e9c5b-108">如果在部署客户端之前已将注册表设置应用到计算机（例如，通过使用组策略），将保留这些设置并应用任何其他命令行参数。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-108">If you have applied registry settings to a computer before deploying a client—for example, by using Group Policy—these settings are retained and any additional command line parameters are applied.</span></span> <span data-ttu-id="e9c5b-109">命令行参数值将替换相同设置的任何现有值。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-109">Command line parameter values will replace any existing value for the same setting.</span></span>

<span data-ttu-id="e9c5b-110">**注意** 当安装与只读缓存（例如使用 VDI 服务器实现）一起使用的 app-v 客户端时，必须将*AUTOLOADTARGET*参数设置为 NONE，以防止客户端尝试在缓存为只读时尝试更新应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-110">**Note** When you install the App-V client to use with a read-only cache, for example with a VDI server implementation, you must set the *AUTOLOADTARGET* parameter to NONE to prevent the client from trying to update applications when the cache is read-only.</span></span>

 

<span data-ttu-id="e9c5b-111">有关在安装后设置这些参数值的详细信息，请参阅[如何使用命令行](https://go.microsoft.com/fwlink/?LinkId=169355)（ https://go.microsoft.com/fwlink/?LinkId=169355) 在 Application Virtualization （App-v）操作指南中配置 App-v Client 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-111">For more information about setting these parameter values after installation, see [How to Configure the App-V Client Registry Settings by Using the Command Line](https://go.microsoft.com/fwlink/?LinkId=169355) (https://go.microsoft.com/fwlink/?LinkId=169355) in the Application Virtualization (App-V) Operations Guide.</span></span>

<span data-ttu-id="e9c5b-112">**注意** 如果用户计算机上的配置设置取决于客户端安装路径，请注意应用程序虚拟化（app-v）4.5 客户端将其安装文件复制到与以前的版本不同的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-112">**Note** If a configuration setting on the user’s computer depends on the client installation path, note that the Application Virtualization (App-V)4.5 client copies its installation files to a different folder than previous versions did.</span></span> <span data-ttu-id="e9c5b-113">默认情况下，App-v 4.5 客户端的全新安装会将其安装文件复制到 \\Program Files\\Microsoft Application Virtualization Client 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-113">By default, a new installation of the App-V4.5 client will copy its installation files to the \\Program Files\\Microsoft Application Virtualization Client folder.</span></span> <span data-ttu-id="e9c5b-114">如果已安装较早版本的客户端，运行 app-v 4.5 客户端安装程序将使用现有安装文件夹执行现有客户端的升级。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-114">If an earlier version of the client is already installed, running the App-V 4.5 client installer will perform an upgrade of the existing client using the existing installation folder.</span></span>

 

<span data-ttu-id="e9c5b-115">\ [模板令牌值 \]</span><span class="sxs-lookup"><span data-stu-id="e9c5b-115">\[Template Token Value\]</span></span>

<span data-ttu-id="e9c5b-116">**注意** 对于 app-v 和更高版本，在安装 app-v 客户端时，SFTLDR.DLL 将复制到 Windows\\system32 目录。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-116">**Note** For App-V version4.6 and later, when the App-V client is installed, SFTLDR.DLL is copied to the Windows\\system32 directory.</span></span> <span data-ttu-id="e9c5b-117">如果在64位系统上安装了 app-v 客户端，SFTLDR\_WOW64.DLL 将复制到 Windows\\SysWOW64 目录。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-117">If the App-V client is installed on a 64-bit system, SFTLDR\_WOW64.DLL is copied to the Windows\\SysWOW64 directory.</span></span>

 

<span data-ttu-id="e9c5b-118">\ [模板令牌值 \]</span><span class="sxs-lookup"><span data-stu-id="e9c5b-118">\[Template Token Value\]</span></span>

## <span data-ttu-id="e9c5b-119">本部分内容</span><span class="sxs-lookup"><span data-stu-id="e9c5b-119">In This Section</span></span>


<span data-ttu-id="e9c5b-120">以下主题介绍如何使用 setup.exe 或 setup.msi 为远程桌面服务（以前称为终端服务）安装应用程序虚拟化（app-v）桌面客户端或 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-120">The following topics describe how to install either the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using either setup.exe or setup.msi.</span></span>

<a href="" id="how-to-install-the-app-v-client-by-using-setup-exe"></a>[<span data-ttu-id="e9c5b-121">如何使用 Setup.exe 安装 App-V Client</span><span class="sxs-lookup"><span data-stu-id="e9c5b-121">How to Install the App-V Client by Using Setup.exe</span></span>](how-to-install-the-app-v-client-by-using-setupexe-new.md)  
<span data-ttu-id="e9c5b-122">提供通过使用 setup.exe 程序安装 App-v 客户端的分步过程。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-122">Provides a step-by-step procedure for installing the App-V client by using the setup.exe program.</span></span>

<a href="" id="how-to-install-the-app-v-client-by-using-setup-msi"></a>[<span data-ttu-id="e9c5b-123">如何使用 Setup.msi 安装 App-V Client</span><span class="sxs-lookup"><span data-stu-id="e9c5b-123">How to Install the App-V Client by Using Setup.msi</span></span>](how-to-install-the-app-v-client-by-using-setupmsi-new.md)  
<span data-ttu-id="e9c5b-124">提供通过使用 setup.msi 程序安装任何必备软件和 App-v 客户端的分步过程。</span><span class="sxs-lookup"><span data-stu-id="e9c5b-124">Provides step-by-step procedures for installing any prerequisite software and also the App-V client by using the setup.msi program.</span></span>

## <span data-ttu-id="e9c5b-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="e9c5b-125">Related topics</span></span>


[<span data-ttu-id="e9c5b-126">Application Virtualization Client 安装程序命令行参数</span><span class="sxs-lookup"><span data-stu-id="e9c5b-126">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

[<span data-ttu-id="e9c5b-127">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="e9c5b-127">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="e9c5b-128">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="e9c5b-128">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="e9c5b-129">如何卸载 App-V Client</span><span class="sxs-lookup"><span data-stu-id="e9c5b-129">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)

 

 





