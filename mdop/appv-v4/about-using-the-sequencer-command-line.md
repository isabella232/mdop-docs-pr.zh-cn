---
title: 关于使用 Sequencer 命令行
description: 关于使用 Sequencer 命令行
author: dansimp
ms.assetid: 0fd5f81b-17f9-4065-bce2-8785e8aac7c7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: afb3fb8608c78a3b9237a80529a6c22d792661ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802403"
---
# <span data-ttu-id="019dd-103">关于使用 Sequencer 命令行</span><span class="sxs-lookup"><span data-stu-id="019dd-103">About Using the Sequencer Command Line</span></span>


<span data-ttu-id="019dd-104">你可以使用命令行创建顺序应用程序包。</span><span class="sxs-lookup"><span data-stu-id="019dd-104">You can use the command line to create sequenced application packages.</span></span> <span data-ttu-id="019dd-105">在以下情况下使用命令行创建虚拟应用程序非常有用：</span><span class="sxs-lookup"><span data-stu-id="019dd-105">Using the command line to create virtual applications is useful in the following scenarios:</span></span>

-   <span data-ttu-id="019dd-106">您需要创建大量的顺序应用程序包。</span><span class="sxs-lookup"><span data-stu-id="019dd-106">You need to create a large number of sequenced application packages.</span></span>

-   <span data-ttu-id="019dd-107">你需要定期创建顺序应用程序包。</span><span class="sxs-lookup"><span data-stu-id="019dd-107">You need to create a sequenced application package on a recurring basis.</span></span>

<span data-ttu-id="019dd-108">**重要提示** 命令提示符处的排序仅允许默认排序。</span><span class="sxs-lookup"><span data-stu-id="019dd-108">**Important** Sequencing at the command prompt allows for default sequencing only.</span></span> <span data-ttu-id="019dd-109">如果需要更改默认的顺序参数，则必须手动修改序列化的应用程序包或重新对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="019dd-109">If you need to change default sequencing parameters, you must either manually modify a sequenced application package or re-sequence the application.</span></span>

 

<span data-ttu-id="019dd-110">必须使用排序向导来对现有的顺序应用程序包进行所有后续修改。</span><span class="sxs-lookup"><span data-stu-id="019dd-110">All subsequent modifications to existing sequenced application packages must be made using the sequencing wizard.</span></span>

## <span data-ttu-id="019dd-111">必备条件</span><span class="sxs-lookup"><span data-stu-id="019dd-111">Prerequisites</span></span>


<span data-ttu-id="019dd-112">若要使用命令提示符对应用程序进行排序，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="019dd-112">To sequence an application by using the command prompt, the following conditions must be met:</span></span>

-   <span data-ttu-id="019dd-113">要排序的应用程序不得要求在 "安装程序" 或 "Windows 安装程序" 程序包之外对其进行更改或解决方法。</span><span class="sxs-lookup"><span data-stu-id="019dd-113">The application that is about to be sequenced must not require changes or workarounds made to it outside the installer or Windows Installer package.</span></span>

-   <span data-ttu-id="019dd-114">在排序之前，必须准备批处理文件列表以创建顺序应用程序包。</span><span class="sxs-lookup"><span data-stu-id="019dd-114">Before sequencing, you must prepare a list of batch files for creating the sequenced application packages.</span></span>

-   <span data-ttu-id="019dd-115">查看有关命令行参数的详细信息，请参阅[命令行参数](command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="019dd-115">Review For more information about the command line parameters, see [Command-Line Parameters](command-line-parameters.md).</span></span>

-   <span data-ttu-id="019dd-116">查看使用命令行创建序列化应用程序包时可能会显示的错误。</span><span class="sxs-lookup"><span data-stu-id="019dd-116">Review the errors that might be displayed when creating a sequenced application package by using the command line.</span></span> <span data-ttu-id="019dd-117">有关详细信息，请参阅错误的[命令行错误](command-line-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="019dd-117">For more information, see these errors, see [Command-Line Errors](command-line-errors.md).</span></span>

## <span data-ttu-id="019dd-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="019dd-118">Related topics</span></span>


[<span data-ttu-id="019dd-119">如何使用命令行管理虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="019dd-119">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





