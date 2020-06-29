---
title: 如何使用“打开程序包”命令升级程序包
description: 如何使用“打开程序包”命令升级程序包
author: dansimp
ms.assetid: 67c10440-de8a-4547-a34b-f83206d0cc3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cca438fe90373e8f934d1d790246544cdf46fa18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801048"
---
# <span data-ttu-id="2ff91-103">如何使用“打开程序包”命令升级程序包</span><span class="sxs-lookup"><span data-stu-id="2ff91-103">How to Upgrade a Package Using the Open Package Command</span></span>


<span data-ttu-id="2ff91-104">使用 "打开程序包" 命令将更新升级或应用到顺序应用程序包。</span><span class="sxs-lookup"><span data-stu-id="2ff91-104">Use the Open Package command to upgrade or apply an update to a sequenced application package.</span></span> <span data-ttu-id="2ff91-105">使用命令行升级现有虚拟应用程序包时，将删除该 sft 文件的原始版本。</span><span class="sxs-lookup"><span data-stu-id="2ff91-105">When you upgrade an existing virtual application package using the command line, the original version of the .sft file is deleted.</span></span> <span data-ttu-id="2ff91-106">你应该先备份关联的 sft 文件，然后再使用命令行升级程序包。</span><span class="sxs-lookup"><span data-stu-id="2ff91-106">You should backup the associated .sft file before upgrading the package using the command line.</span></span>

**<span data-ttu-id="2ff91-107">使用 "打开包" 命令升级程序包</span><span class="sxs-lookup"><span data-stu-id="2ff91-107">To upgrade a package using the Open Package command</span></span>**

1.  <span data-ttu-id="2ff91-108">若要打开要升级的程序包，请在 "应用程序虚拟化（App-v）" 控制台中选择 "**文件**"，**打开 "升级程序包**"。</span><span class="sxs-lookup"><span data-stu-id="2ff91-108">To open the package that will be upgraded, in the Application Virtualization (App-V) console select **File**, **Open Package for Upgrade**.</span></span> <span data-ttu-id="2ff91-109">在 "**打开**" 对话框中，选择将升级的程序包。</span><span class="sxs-lookup"><span data-stu-id="2ff91-109">In the **Open** dialog box, select the package that will be upgraded.</span></span>

2.  <span data-ttu-id="2ff91-110">若要启动**顺序**向导，请选择 "**工具**"、"**序列化向导**"。</span><span class="sxs-lookup"><span data-stu-id="2ff91-110">To start the **Sequencing** wizard, select **Tools**, **Sequencing Wizard**.</span></span> <span data-ttu-id="2ff91-111">完成向导应用配置更改，以保存新的顺序应用程序，请选择 "**文件**"，"**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2ff91-111">Complete the wizard applying the configuration changes, to save the new sequenced application, select **File**, **Save**.</span></span>

3.  <span data-ttu-id="2ff91-112">若要将版本号追加到程序包名称，请在 Sequencer 控制台中选择 "**工具**"、"**选项**"。</span><span class="sxs-lookup"><span data-stu-id="2ff91-112">To append the version number to the package name, in the Sequencer console, select **Tools**, **Options**.</span></span> <span data-ttu-id="2ff91-113">选择 "**将包版本附加到文件名**"。</span><span class="sxs-lookup"><span data-stu-id="2ff91-113">Select **Append Package Version to Filename**.</span></span> <span data-ttu-id="2ff91-114">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ff91-114">Click **OK**.</span></span>

    <span data-ttu-id="2ff91-115">**重要提示** 若要成功完成升级，更新程序包版本的文件名是必需的。</span><span class="sxs-lookup"><span data-stu-id="2ff91-115">**Important** Updating the file name with the package version is essential to successfully completing the upgrade.</span></span>

     

## <span data-ttu-id="2ff91-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="2ff91-116">Related topics</span></span>


[<span data-ttu-id="2ff91-117">如何使用命令行管理虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="2ff91-117">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





