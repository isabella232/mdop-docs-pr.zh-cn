---
title: 关于“共享包加速器”页
description: 关于“共享包加速器”页
author: dansimp
ms.assetid: 9630cde0-e2c3-476f-8fa1-58b3c9f7d3f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 34fe55d910a7532f011b239ff5b8162aa9240f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802439"
---
# <span data-ttu-id="70398-103">关于“共享包加速器”页</span><span class="sxs-lookup"><span data-stu-id="70398-103">About Sharing Package Accelerators Page</span></span>


<span data-ttu-id="70398-104">以下信息提供了有关如何共享程序包加速器的最佳做法信息。</span><span class="sxs-lookup"><span data-stu-id="70398-104">This following information provides best practice information about how to share Package Accelerators.</span></span> <span data-ttu-id="70398-105">如果你计划共享程序包加速器文件，则程序包加速器文件中可能包含计算机名、用户帐户信息以及有关转换中包含的应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="70398-105">If you plan to share Package Accelerators files, information such as computer names, user account information, and information about applications included in the transforms might be included in the Package Accelerators file.</span></span> <span data-ttu-id="70398-106">你应该检查与虚拟应用程序包关联的任何设置或配置文件，以确保应用不包含任何个人信息。此页面包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="70398-106">You should review any settings or configuration files associated with the virtual application package to ensure the applications do not contain any personal information.This page contains the following elements.</span></span>

-   <span data-ttu-id="70398-107">**用户名**。</span><span class="sxs-lookup"><span data-stu-id="70398-107">**Username**.</span></span> <span data-ttu-id="70398-108">当您登录到运行 Microsoft App-v 排序器的计算机时，应使用通用用户帐户，例如内置**管理员**帐户。</span><span class="sxs-lookup"><span data-stu-id="70398-108">When you log on to the computer running the Microsoft App-V Sequencer, you should use a generic user account, such as the built-in **administrator** account.</span></span> <span data-ttu-id="70398-109">不应使用基于现有用户名的帐户。</span><span class="sxs-lookup"><span data-stu-id="70398-109">You should not use an account that is based on an existing user name.</span></span>

-   <span data-ttu-id="70398-110">**计算机名**。</span><span class="sxs-lookup"><span data-stu-id="70398-110">**Computer Name**.</span></span> <span data-ttu-id="70398-111">指定运行 Sequencer 的计算机的常规、非标识名称。</span><span class="sxs-lookup"><span data-stu-id="70398-111">Specify a general, non-identifying name of the computer running the Sequencer.</span></span>

-   <span data-ttu-id="70398-112">**服务器 URL**。</span><span class="sxs-lookup"><span data-stu-id="70398-112">**Server URL**.</span></span> <span data-ttu-id="70398-113">在 App-v Sequencer 控制台中的 "**部署**" 选项卡上，使用服务器 URL 配置信息的默认设置。</span><span class="sxs-lookup"><span data-stu-id="70398-113">In the App-V Sequencer console, on the **Deployment** tab, use the default settings for the server URL configuration information.</span></span>

-   <span data-ttu-id="70398-114">**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="70398-114">**Applications**.</span></span> <span data-ttu-id="70398-115">如果你不想共享在创建程序包加速器时运行 Sequencer 的计算机上安装的应用程序的列表，则必须删除**appv\_manifest.xml**文件。</span><span class="sxs-lookup"><span data-stu-id="70398-115">If you do not want to share the list of applications that were installed on the computer running the Sequencer when you created the Package Accelerator, you must delete the **appv\_manifest.xml** file.</span></span> <span data-ttu-id="70398-116">此文件位于虚拟应用程序包的程序包根目录中。</span><span class="sxs-lookup"><span data-stu-id="70398-116">This file is located in the package root directory of the virtual application package.</span></span>

## <span data-ttu-id="70398-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="70398-117">Related topics</span></span>


[<span data-ttu-id="70398-118">“创建包加速器”向导 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="70398-118">Create Package Accelerator Wizard (AppV 4.6 SP1)</span></span>](create-package-accelerator-wizard--appv-46-sp1-.md)

[<span data-ttu-id="70398-119">关于 App-V 包加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="70398-119">About App-V Package Accelerators (App-V 4.6 SP1)</span></span>](about-app-v-package-accelerators--app-v-46-sp1-.md)

 

 





