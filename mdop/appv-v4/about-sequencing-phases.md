---
title: 关于排序阶段
description: 关于排序阶段
author: dansimp
ms.assetid: c1cb7b6c-204c-48f2-848c-4bd5a3d5ecb6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e3d1504f0af82f3d21806b38bb4640b6f7ebc45
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802443"
---
# <span data-ttu-id="90751-103">关于排序阶段</span><span class="sxs-lookup"><span data-stu-id="90751-103">About Sequencing Phases</span></span>


<span data-ttu-id="90751-104">排序是通过使用 Microsoft Application Virtualization （App-v） Sequencer 创建序列化应用程序包的过程。</span><span class="sxs-lookup"><span data-stu-id="90751-104">Sequencing is the process by which you create a sequenced application package by using the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="90751-105">在排序期间，Sequencer 将监视和记录应用程序的所有安装和设置进程，并创建以下文件： .ICO、OSD、SFT 和 SPRJ。</span><span class="sxs-lookup"><span data-stu-id="90751-105">During sequencing, the Sequencer monitors and records all installation and setup processes for an application and creates the following files: ICO, OSD, SFT, and SPRJ.</span></span> <span data-ttu-id="90751-106">这些文件包含有关应用程序的所有必要信息，并允许该应用程序在虚拟环境中运行。</span><span class="sxs-lookup"><span data-stu-id="90751-106">These files contain all the necessary information about an application, and they allow that application to run in a virtual environment.</span></span>

<span data-ttu-id="90751-107">序列化应用程序和创建虚拟应用程序包的四个阶段是安装、启动、自定义和保存。</span><span class="sxs-lookup"><span data-stu-id="90751-107">The four phases to sequencing an application and creating a virtual application package are installation, launch, customization, and save.</span></span> <span data-ttu-id="90751-108">下面的列表提供了每个阶段的相关信息：</span><span class="sxs-lookup"><span data-stu-id="90751-108">The following list provides information about each of the phases:</span></span>

1.  <span data-ttu-id="90751-109">**安装阶段**-在安装阶段，指定程序包名称和将与程序包关联的可选关联注释。</span><span class="sxs-lookup"><span data-stu-id="90751-109">**Installation phase**—During the installation phase, you specify the package name and an optional associated comment that will be associated with the package.</span></span> <span data-ttu-id="90751-110">您也可以在此阶段配置高级监视选项。</span><span class="sxs-lookup"><span data-stu-id="90751-110">You can also configure advanced monitoring options during this phase.</span></span> <span data-ttu-id="90751-111">高级监视选项包括指定块大小以及在监视期间是否将安装自动更新。</span><span class="sxs-lookup"><span data-stu-id="90751-111">Advanced monitoring options include specifying the block size and whether you will install automatic updates during monitoring.</span></span> <span data-ttu-id="90751-112">Sequencer 记录创建虚拟应用程序包以及关联的文件和注册表设置所需的所有必要信息和配置。</span><span class="sxs-lookup"><span data-stu-id="90751-112">The sequencer records all necessary information and configurations required to create a virtual application package and the associated file and registry settings.</span></span>

    <span data-ttu-id="90751-113">**重要提示** 若要查看高级选项，请选择 "**程序包信息**" 页面上的 "**显示高级监视选项**"。</span><span class="sxs-lookup"><span data-stu-id="90751-113">**Important** To view the advanced options select **Show Advanced Monitoring Options** on the **Package Information** page.</span></span>

     

2.  <span data-ttu-id="90751-114">**启动阶段**-在启动阶段，你可以指定应配置程序包的任何必需的文件关联和安全描述符。</span><span class="sxs-lookup"><span data-stu-id="90751-114">**Launch phase**—During the launch phase, you can specify any required file associations and security descriptors that should be configured with the package.</span></span> <span data-ttu-id="90751-115">你应根据需要多次打开应用程序，以确保应用程序功能和稳定性。</span><span class="sxs-lookup"><span data-stu-id="90751-115">You should open the application as many times as necessary to ensure application functionality and stability.</span></span>

3.  <span data-ttu-id="90751-116">**自定义阶段**——在自定义阶段，您可以使用关联的 .osd 文件配置程序包。</span><span class="sxs-lookup"><span data-stu-id="90751-116">**Customization phase**—During the customization phase, you can configure your package by using the associated .osd files.</span></span> <span data-ttu-id="90751-117">你可以指定是否应在虚拟环境内部或外部运行任何关联的脚本、指定应执行的其他操作、指定关联脚本的运行方式（同步或异步），以及指定应在用户上下文下运行的任何其他脚本。</span><span class="sxs-lookup"><span data-stu-id="90751-117">You can specify whether any associated scripts should run inside or outside of the virtual environment, specify additional actions that should be performed, specify how associated scripts run (synchronously or asynchronously), and specify any additional scripts that should be run under the user context.</span></span>

4.  <span data-ttu-id="90751-118">**保存阶段**-在保存阶段，创建虚拟应用程序包所需的所有文件。</span><span class="sxs-lookup"><span data-stu-id="90751-118">**Save phase**—During the save phase, all required files for the virtual application package are created.</span></span> <span data-ttu-id="90751-119">创建的文件为 sprj、sft、.osd、.ico、.xml 清单和 Windows installer （.msi）文件。</span><span class="sxs-lookup"><span data-stu-id="90751-119">The files created are .sprj, .sft, .osd, .ico, .xml manifest, and the Windows installer (.msi) file.</span></span>

## <span data-ttu-id="90751-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="90751-120">Related topics</span></span>


[<span data-ttu-id="90751-121">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="90751-121">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





