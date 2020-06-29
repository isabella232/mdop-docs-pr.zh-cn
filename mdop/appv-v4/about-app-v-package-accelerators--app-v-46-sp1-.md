---
title: 关于 App-V 包加速器 (App-V 4.6 SP1)
description: 关于 App-V 包加速器 (App-V 4.6 SP1)
author: manikadhiman
ms.assetid: fc2d2375-8f17-4a6d-b374-771cb947cb8c
ms.reviewer: ''
manager: dansimp
ms.author: v-madhi
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cb7b8e6fa9482838283257843caf4b291c03bf2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802479"
---
# <span data-ttu-id="6e955-103">关于 App-V 包加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="6e955-103">About App-V Package Accelerators (App-V 4.6 SP1)</span></span>


<span data-ttu-id="6e955-104">你可以使用 App-v 程序包加速器自动序列大型、复杂的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e955-104">You can use App-V Package Accelerators to automatically sequence large, complex applications.</span></span> <span data-ttu-id="6e955-105">此外，当你应用 app-v 包加速器时，并非始终需要手动安装应用程序来创建虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="6e955-105">Additionally, when you apply an App-V Package Accelerator, you are not always required to manually install an application to create the virtual application package.</span></span>

<span data-ttu-id="6e955-106">**注意** 在某些情况下，系统会提示你在运行 App-v Sequencer 的计算机本地安装应用程序，然后才能使用程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="6e955-106">**Note** In some cases, you are prompted to install an application locally to the computer running the App-V Sequencer before you can use the Package Accelerator.</span></span> <span data-ttu-id="6e955-107">如果必须安装应用程序，则必须将应用程序安装到应用程序的默认位置。</span><span class="sxs-lookup"><span data-stu-id="6e955-107">If you have to install an application, you must install the application to the application’s default location.</span></span> <span data-ttu-id="6e955-108">App-v Sequencer 不监视此安装。</span><span class="sxs-lookup"><span data-stu-id="6e955-108">This installation is not monitored by App-V Sequencer.</span></span> <span data-ttu-id="6e955-109">创建 app-v 包加速器时，程序包加速器的作者确定是否需要在本地安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e955-109">When the App-V Package Accelerator is created, the author of the Package Accelerator determines whether to install an application locally is required.</span></span>

 

<span data-ttu-id="6e955-110">App-v Sequencer 从 App-v 程序包加速器提取所需的文件，并从关联的安装媒体中提取所需的文件，以创建虚拟程序包，而无需监视应用程序的安装。</span><span class="sxs-lookup"><span data-stu-id="6e955-110">App-V Sequencer extracts the required files from the App-V Package Accelerator and associated installation media to create a virtual package without having to monitor the installation of the application.</span></span>

<span data-ttu-id="6e955-111">**重要提示** 免责声明： Microsoft Application Virtualization Sequencer 不向你提供用于创建程序包加速器的软件应用程序的许可证权利。</span><span class="sxs-lookup"><span data-stu-id="6e955-111">**Important** Disclaimer: The Microsoft Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="6e955-112">您必须遵守此类应用程序的所有最终用户许可条款。</span><span class="sxs-lookup"><span data-stu-id="6e955-112">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="6e955-113">您有责任确保软件应用程序的许可条款允许您使用 Application Virtualization Sequencer 创建软件包加速器。</span><span class="sxs-lookup"><span data-stu-id="6e955-113">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>

 

<span data-ttu-id="6e955-114">App-v 程序包加速器和项目模板彼此不同。</span><span class="sxs-lookup"><span data-stu-id="6e955-114">App-V Package Accelerators and project templates differ from each other.</span></span> <span data-ttu-id="6e955-115">程序包加速器特定于应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e955-115">Package Accelerators are application-specific.</span></span> <span data-ttu-id="6e955-116">项目模板使用户能够保存特定于某个组织的常用设置，并将其应用到多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e955-116">Project templates enable users to save commonly used settings specific to an organization and apply them to multiple applications.</span></span> <span data-ttu-id="6e955-117">你还可以在命令提示符处创建项目模板，而相反，你必须使用 App-v Sequencer 控制台创建程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="6e955-117">You can also create project templates at the command prompt, while in contrast, you must use the App-V Sequencer console to create Package Accelerators.</span></span> <span data-ttu-id="6e955-118">此外，不支持通过使用包加速器创建程序包和应用项目模板。</span><span class="sxs-lookup"><span data-stu-id="6e955-118">Additionally, creating a package by using a Package Accelerator and applying a project template is not supported.</span></span>

## <span data-ttu-id="6e955-119">共享 app-v 包加速器</span><span class="sxs-lookup"><span data-stu-id="6e955-119">Sharing App-V Package Accelerators</span></span>


<span data-ttu-id="6e955-120">本部分提供有关如何共享程序包加速器的最佳做法信息。</span><span class="sxs-lookup"><span data-stu-id="6e955-120">This section provides best practice information about how to share Package Accelerators.</span></span> <span data-ttu-id="6e955-121">如果你计划共享程序包加速器，则程序包加速器中可能包含计算机名称、用户帐户信息以及有关关联的应用程序的信息。以下列表介绍了创建包加速器时应考虑的方法：</span><span class="sxs-lookup"><span data-stu-id="6e955-121">If you plan to share Package Accelerators, information such as computer names, user account information, and information about the associated applications might be included in the Package Accelerators.The following list describes methods you should consider when creating Package Accelerators:</span></span>

-   <span data-ttu-id="6e955-122">**用户名**。</span><span class="sxs-lookup"><span data-stu-id="6e955-122">**User name**.</span></span> <span data-ttu-id="6e955-123">当你登录到运行 App-v Sequencer 的计算机时，你应该使用通用用户帐户，例如用于管理计算机/域的内置**管理员**帐户。</span><span class="sxs-lookup"><span data-stu-id="6e955-123">When you log on to the computer running App-V Sequencer, you should use a generic user account, such as the built-in **administrator** account for administering the computer / domain.</span></span> <span data-ttu-id="6e955-124">不应使用基于现有用户名的帐户。</span><span class="sxs-lookup"><span data-stu-id="6e955-124">You should not use an account that is based on an existing user name.</span></span>

-   <span data-ttu-id="6e955-125">**计算机名**。</span><span class="sxs-lookup"><span data-stu-id="6e955-125">**Computer Name**.</span></span> <span data-ttu-id="6e955-126">为运行 Sequencer 的计算机指定一般的、非标识的名称。</span><span class="sxs-lookup"><span data-stu-id="6e955-126">Specify a general, non-identifying name for the computer running the Sequencer.</span></span>

-   <span data-ttu-id="6e955-127">**服务器 URL**。</span><span class="sxs-lookup"><span data-stu-id="6e955-127">**Server URL**.</span></span> <span data-ttu-id="6e955-128">在 Sequencer 控制台中，在 "**部署**" 选项卡上，使用服务器 URL 配置信息的默认设置。</span><span class="sxs-lookup"><span data-stu-id="6e955-128">In the Sequencer console, on the **Deployment** tab, use the default settings for the server URL configuration information.</span></span>

-   <span data-ttu-id="6e955-129">**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6e955-129">**Applications**.</span></span> <span data-ttu-id="6e955-130">如果你不想共享在创建程序包加速器时运行 Sequencer 的计算机上安装的应用程序的列表，则必须删除**appv\_manifest.xml**文件。</span><span class="sxs-lookup"><span data-stu-id="6e955-130">If you do not want to share the list of applications that were installed on the computer running the Sequencer when you created the Package Accelerator, you must delete the **appv\_manifest.xml** file.</span></span> <span data-ttu-id="6e955-131">此文件位于虚拟应用程序包的程序包根目录中。</span><span class="sxs-lookup"><span data-stu-id="6e955-131">This file is located in the package root directory of the virtual application package.</span></span>

<span data-ttu-id="6e955-132">你还应查看与虚拟应用程序包关联的任何设置或配置文件，以确保应用不包含任何个人信息。</span><span class="sxs-lookup"><span data-stu-id="6e955-132">You should also review any settings or configuration files associated with the virtual application package to ensure the applications do not contain any personal information.</span></span>

## <span data-ttu-id="6e955-133">保护 app-v 程序包加速器</span><span class="sxs-lookup"><span data-stu-id="6e955-133">Securing App-V Package Accelerators</span></span>


<span data-ttu-id="6e955-134">始终将 App-v 程序包加速器和任何关联的安装媒体保存在网络上的安全位置，以保护 app-v 程序包加速器以及安装文件不会被篡改或损坏。</span><span class="sxs-lookup"><span data-stu-id="6e955-134">Always save App-V Package Accelerators and any associated installation media in a secure location on the network to protect the App-V Package Accelerators and the installation files from being tampered with or becoming corrupted.</span></span> <span data-ttu-id="6e955-135">由于程序包加速器还可以包含密码和特定于用户的信息，因此必须在安全位置保存 App-v 程序包加速器，并且在创建程序包加速器后必须对其进行数字签名，以便可以在应用程序包加速器时验证发布者。</span><span class="sxs-lookup"><span data-stu-id="6e955-135">Because Package Accelerators can also contain password and user-specific information, you must save App-V Package Accelerators in a secure location, and you must digitally sign the Package Accelerator after you create it so that the publisher can be verified when the Package Accelerator is applied.</span></span> <span data-ttu-id="6e955-136">有关数字签名的详细信息，请参阅[适用于通用条件安全性的数字签名做法的应用程序指南](https://go.microsoft.com/fwlink/?LinkId=204705)（ https://go.microsoft.com/fwlink/?LinkId=204705) 。</span><span class="sxs-lookup"><span data-stu-id="6e955-136">For more information about digital signatures, see [Application Guidelines on Digital Signature Practices for Common Criteria Security](https://go.microsoft.com/fwlink/?LinkId=204705) (https://go.microsoft.com/fwlink/?LinkId=204705).</span></span>

## <span data-ttu-id="6e955-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="6e955-137">Related topics</span></span>


[<span data-ttu-id="6e955-138">如何创建 App-V 包加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="6e955-138">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)

[<span data-ttu-id="6e955-139">如何应用程序包加速器以创建虚拟应用程序包（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="6e955-139">How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)</span></span>](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)

 

 





