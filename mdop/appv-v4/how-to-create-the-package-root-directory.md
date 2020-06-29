---
title: 如何创建程序包根目录
description: 如何创建程序包根目录
author: dansimp
ms.assetid: bcfe3bd4-6c60-409a-8ffa-cc22f27194b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c9e1e7be71627d4e55eff7a4e2582a21b834876d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801492"
---
# <span data-ttu-id="76277-103">如何创建程序包根目录</span><span class="sxs-lookup"><span data-stu-id="76277-103">How to Create the Package Root Directory</span></span>


<span data-ttu-id="76277-104">程序包 root 目录是运行应用程序-V 排序器文件的计算机上安装了序列化应用程序的文件的目录。</span><span class="sxs-lookup"><span data-stu-id="76277-104">The package root directory is the directory on the computer running the App-V Sequencer where files for the sequenced application are installed.</span></span> <span data-ttu-id="76277-105">此目录还存在于将对序列化的应用程序进行流式处理的计算机上。</span><span class="sxs-lookup"><span data-stu-id="76277-105">This directory also exists virtually on the computer to which a sequenced application will be streamed.</span></span> <span data-ttu-id="76277-106">在监视新应用程序的安装之前，应创建程序包根目录。</span><span class="sxs-lookup"><span data-stu-id="76277-106">You should create the package root directory before you monitor the installation of a new application.</span></span>

<span data-ttu-id="76277-107">创建程序包根目录后，即可开始对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="76277-107">After you have created the package root directory, you can begin sequencing applications.</span></span> <span data-ttu-id="76277-108">有关对新应用程序进行序列化的详细信息，请参阅[如何安装 Sequencer](how-to-install-the-sequencer.md)。</span><span class="sxs-lookup"><span data-stu-id="76277-108">For more information about sequencing a new application, see [How to Install the Sequencer](how-to-install-the-sequencer.md).</span></span>

**<span data-ttu-id="76277-109">创建程序包根目录</span><span class="sxs-lookup"><span data-stu-id="76277-109">To create the package root directory</span></span>**

1.  <span data-ttu-id="76277-110">若要创建程序包根目录，请在运行 App-v Sequencer 的计算机上，将 Q:\\ 驱动器映射到指定的网络位置。</span><span class="sxs-lookup"><span data-stu-id="76277-110">To create the package root directory, on the computer running the App-V Sequencer, map the Q:\\ drive to the specified network location.</span></span> <span data-ttu-id="76277-111">你指定的位置应该有足够的空间来保存你正在排序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="76277-111">The location you specify should have sufficient space to save the application you are sequencing.</span></span>

2.  <span data-ttu-id="76277-112">若要创建可用于新虚拟应用程序的目录，请在 Q:\\ 驱动器上创建一个文件夹，然后为其分配一个名称。</span><span class="sxs-lookup"><span data-stu-id="76277-112">To create a directory that you can use for a new virtual application, create a folder on the Q:\\ drive and assign it a name.</span></span>

    <span data-ttu-id="76277-113">**重要提示** 分配给将保存在程序包根目录中的虚拟应用程序文件的名称应使用8.3 命名格式。</span><span class="sxs-lookup"><span data-stu-id="76277-113">**Important** The name you assign to virtual application files that will be saved in the package root directory should use the 8.3 naming format.</span></span> <span data-ttu-id="76277-114">文件名长度不应超过8个字符，并带有三个字符的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="76277-114">The file names should be no longer than 8 characters with a three-character file name extension.</span></span>

     

## <span data-ttu-id="76277-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="76277-115">Related topics</span></span>


[<span data-ttu-id="76277-116">Application Virtualization Sequencer 的任务</span><span class="sxs-lookup"><span data-stu-id="76277-116">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





