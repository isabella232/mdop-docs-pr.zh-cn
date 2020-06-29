---
title: 如何应用 App-V 项目模板 (App-V 4.6 SP1)
description: 如何应用 App-V 项目模板 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 8ef120ab-8cfb-438c-8136-671167b7bd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b5f04f3f31838bfb13c19eee5f2314c3a3d291f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802955"
---
# <span data-ttu-id="4c255-103">如何应用 App-V 项目模板 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="4c255-103">How to Apply an App-V Project Template (App-V 4.6 SP1)</span></span>


<span data-ttu-id="4c255-104">你可以使用 App-v 项目模板将与现有虚拟应用程序包关联的通用设置应用于新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="4c255-104">You can use an App-V project template to apply common settings associated with an existing virtual application package to a new virtual application package.</span></span> <span data-ttu-id="4c255-105">使用 app-v 项目模板，可以通过在开始对应用程序进行序列化之前配置常规设置来帮助简化创建虚拟应用程序包的过程。</span><span class="sxs-lookup"><span data-stu-id="4c255-105">Using App-V project templates can help streamline the process of creating virtual application packages by configuring common settings before you begin sequencing an application.</span></span>

<span data-ttu-id="4c255-106">**注意** 仅当创建新的虚拟应用程序包时，才能应用 V 项目模板。</span><span class="sxs-lookup"><span data-stu-id="4c255-106">**Note** You can only apply an App-V project template when you are creating a new virtual application package.</span></span> <span data-ttu-id="4c255-107">不支持将项目模板应用于现有虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="4c255-107">Applying project templates to existing virtual application packages is not supported.</span></span> <span data-ttu-id="4c255-108">此外，不能将项目模板与包加速器结合使用。</span><span class="sxs-lookup"><span data-stu-id="4c255-108">Additionally, you cannot use a project template in conjunction with a Package Accelerator.</span></span>

 

<span data-ttu-id="4c255-109">有关创建 App-v 项目模板的详细信息，请参阅[如何创建应用程序 v 项目模板（app-v 4.6 SP1）](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="4c255-109">For more information about creating App-V project templates, see [How to Create an App-V Project Template (App-V 4.6 SP1)](how-to-create-an-app-v-project-template--app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="4c255-110">应用 app-v 项目模板</span><span class="sxs-lookup"><span data-stu-id="4c255-110">To apply an App-V project template</span></span>**

1.  <span data-ttu-id="4c255-111">若要启动 Microsoft application Virtualization 排序器，请在安装了 app-v Sequencer 的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="4c255-111">To start the Microsoft Application Virtualization Sequencer, on the computer on which App-V Sequencer is installed, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="4c255-112">若要使用 app-v 项目模板创建新的虚拟应用程序包，请单击 " **File**  /  **从模板新建**文件"。</span><span class="sxs-lookup"><span data-stu-id="4c255-112">To create a new virtual application package by using an App-V project template, click **File** / **New From Template**.</span></span>

3.  <span data-ttu-id="4c255-113">若要选择要使用的项目模板，请浏览到保存项目模板的目录，选择项目模板，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="4c255-113">To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.</span></span>

4.  <span data-ttu-id="4c255-114">创建新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="4c255-114">Create the new virtual application package.</span></span> <span data-ttu-id="4c255-115">与指定模板一起保存的设置将应用于您创建的新虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="4c255-115">The settings saved with the specified template will be applied to the new virtual application package that you are creating.</span></span> <span data-ttu-id="4c255-116">有关创建新的虚拟应用程序包的详细信息，请参阅[如何确定要序列化的应用程序类型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)，然后选择相应的过程。</span><span class="sxs-lookup"><span data-stu-id="4c255-116">For more information about creating a new virtual application package, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md), and select the appropriate procedure.</span></span>

## <span data-ttu-id="4c255-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="4c255-117">Related topics</span></span>


[<span data-ttu-id="4c255-118">Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="4c255-118">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="4c255-119">如何创建 App-V 项目模板 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="4c255-119">How to Create an App-V Project Template (App-V 4.6 SP1)</span></span>](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)

 

 





