---
title: 如何使用命令行打开已排序的应用程序
description: 如何使用命令行打开已排序的应用程序
author: dansimp
ms.assetid: dc23ee65-8aea-470e-bb3f-a2f2b06cb241
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c99ab6b41947fc255afa9cad5b3ed2e22e672c3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801208"
---
# <span data-ttu-id="97f7a-103">如何使用命令行打开已排序的应用程序</span><span class="sxs-lookup"><span data-stu-id="97f7a-103">How to Open a Sequenced Application Using the Command Line</span></span>


<span data-ttu-id="97f7a-104">可以使用命令行打开虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="97f7a-104">You can open virtual application packages using the command line.</span></span> <span data-ttu-id="97f7a-105">您必须以管理员身份运行**cmd**提示符。</span><span class="sxs-lookup"><span data-stu-id="97f7a-105">You must run the **cmd** prompt as an administrator.</span></span>

<span data-ttu-id="97f7a-106">使用以下过程使用命令行打开序列化的应用程序包</span><span class="sxs-lookup"><span data-stu-id="97f7a-106">Use the following procedure to open sequenced application packages using the command line</span></span>

**<span data-ttu-id="97f7a-107">使用命令行打开序列化的应用程序</span><span class="sxs-lookup"><span data-stu-id="97f7a-107">To open a sequenced application using the command line</span></span>**

1.  <span data-ttu-id="97f7a-108">若要打开命令提示符，请单击 "**开始**"，然后选择 "**运行**"，键入**Cmd**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="97f7a-108">To open the command prompt, click **Start**, and select **Run**, type **cmd**, and click **OK**.</span></span>

2.  <span data-ttu-id="97f7a-109">在命令提示符处，键入**cd\\**并指定安装 Sequencer 的目录的路径，然后按**Enter。**</span><span class="sxs-lookup"><span data-stu-id="97f7a-109">At a command prompt, type **cd\\** and specify the path to the directory where the Sequencer is installed and then press **Enter.**</span></span>

3.  <span data-ttu-id="97f7a-110">在命令提示符处，键入以下命令，将斜体文本替换为值：</span><span class="sxs-lookup"><span data-stu-id="97f7a-110">At the command prompt, type the following command, replacing the italicized text with your values:</span></span>

    <span data-ttu-id="97f7a-111">SFTSequencer/OPEN：*"指定要打开的 sprj 文件"*</span><span class="sxs-lookup"><span data-stu-id="97f7a-111">SFTSequencer /OPEN:*”specifies the .sprj file to open"*</span></span>

    <span data-ttu-id="97f7a-112">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="97f7a-112">Press **Enter**.</span></span>

4.  <span data-ttu-id="97f7a-113">你还可以指定以下可选参数。</span><span class="sxs-lookup"><span data-stu-id="97f7a-113">You can also specify the following optional parameters.</span></span> <span data-ttu-id="97f7a-114">在命令提示符处，键入以下命令，将斜体文本替换为值：</span><span class="sxs-lookup"><span data-stu-id="97f7a-114">At the command prompt, type the following commands, replacing the italicized text with your values:</span></span>

    <span data-ttu-id="97f7a-115">/PACKAGENAME： "*指定程序包名称"*</span><span class="sxs-lookup"><span data-stu-id="97f7a-115">/PACKAGENAME:"*specifies the package name"*</span></span>

    <span data-ttu-id="97f7a-116">/MSI-指定生成关联的 Microsoft Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="97f7a-116">/MSI - specifies generating an associated Microsoft Windows Installer.</span></span>

    <span data-ttu-id="97f7a-117">/COMPRESS –指定是否将压缩程序包。</span><span class="sxs-lookup"><span data-stu-id="97f7a-117">/COMPRESS – specifies if the package will be compressed.</span></span> <span data-ttu-id="97f7a-118">默认情况下，不压缩程序包。</span><span class="sxs-lookup"><span data-stu-id="97f7a-118">By default, packages are not compressed.</span></span>

    <span data-ttu-id="97f7a-119">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="97f7a-119">Press **Enter**.</span></span>

    <span data-ttu-id="97f7a-120">**注意** 如果安装程序或 Windows 安装程序包具有图形用户界面，则在指定命令行参数后将显示该界面。</span><span class="sxs-lookup"><span data-stu-id="97f7a-120">**Note** If the installer or Windows Installer package has a graphical user interface, it will be displayed after you specify the command-line parameters.</span></span>

     

## <span data-ttu-id="97f7a-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="97f7a-121">Related topics</span></span>


[<span data-ttu-id="97f7a-122">如何使用命令行管理虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="97f7a-122">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





