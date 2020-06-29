---
title: 如何使用命令行对新应用程序进行排序
description: 如何使用命令行对新应用程序进行排序
author: dansimp
ms.assetid: c3b5c842-6a91-4d0a-9a22-c7b8d1aeb09a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ea7b1222dc00a0a4649cb342ac1ba41338484889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801116"
---
# <span data-ttu-id="d7b32-103">如何使用命令行对新应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="d7b32-103">How to Sequence a New Application by Using the Command Line</span></span>


<span data-ttu-id="d7b32-104">可以使用命令行对新应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="d7b32-104">You can use a command line to sequence a new application.</span></span> <span data-ttu-id="d7b32-105">当必须创建大量虚拟应用程序或需要定期创建顺序应用程序时，使用命令行非常有用。</span><span class="sxs-lookup"><span data-stu-id="d7b32-105">Using a command line is useful when you have to create a large number of virtual applications or when you need to create sequenced applications on a recurring basis.</span></span>

**<span data-ttu-id="d7b32-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="d7b32-106">Important</span></span>**  
<span data-ttu-id="d7b32-107">命令行序列仅允许默认排序。</span><span class="sxs-lookup"><span data-stu-id="d7b32-107">Command-line sequencing allows for default sequencing only.</span></span> <span data-ttu-id="d7b32-108">如果需要更改要对其进行排序的应用程序的默认安装设置，则必须手动修改虚拟应用程序或使用应用程序虚拟化（app-v） Sequencer 更新虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7b32-108">If you need to change default installation settings for the application you are sequencing, you must either manually modify the virtual application or update the virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="d7b32-109">有关使用 App-v Sequencer 更新虚拟应用程序的详细信息，请参阅[如何升级现有虚拟应用程序](how-to-upgrade-an-existing-virtual-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b32-109">For more information about updating a virtual application by using the App-V Sequencer, see [How to Upgrade an Existing Virtual Application](how-to-upgrade-an-existing-virtual-application.md).</span></span>



<span data-ttu-id="d7b32-110">使用以下过程，使用命令行创建虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7b32-110">Use the following procedure to create a virtual application by using the command line.</span></span>

**<span data-ttu-id="d7b32-111">使用命令行对应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="d7b32-111">To sequence an application by using the command line</span></span>**

1.  <span data-ttu-id="d7b32-112">在运行 App-v 排序器的计算机上，通过选择 "**开始**"、"**运行**"，然后键入**cmd**来打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="d7b32-112">On the computer that is running the App-V Sequencer, open the command prompt by selecting **Start**, **Run**, and then type **cmd**.</span></span> <span data-ttu-id="d7b32-113">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d7b32-113">Click **OK**.</span></span>

2.  <span data-ttu-id="d7b32-114">使用命令提示符指定安装 app-v Sequencer 的位置。</span><span class="sxs-lookup"><span data-stu-id="d7b32-114">Use the command prompt to specify the location of where the App-V Sequencer is installed.</span></span> <span data-ttu-id="d7b32-115">例如，在命令提示符处，可以键入以下内容： **cd C:\\program files Files\\Microsoft Application Virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="d7b32-115">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="d7b32-116">在命令提示符处，键入以下命令，将引号中的文本替换为值：</span><span class="sxs-lookup"><span data-stu-id="d7b32-116">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /INSTALLPACKAGE:"pathtoMSI" /INSTALLPATH:"pathtopackageroot" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="d7b32-117">注意</span><span class="sxs-lookup"><span data-stu-id="d7b32-117">Note</span></span>**  
    <span data-ttu-id="d7b32-118">你可以使用命令行指定其他参数，具体取决于你正在对其进行排序的应用程序的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="d7b32-118">You can specify additional parameters by using the command line, depending on the complexity of the application you are sequencing.</span></span> <span data-ttu-id="d7b32-119">有关可用于 App-v Sequencer 的参数的完整列表，请参阅[Sequencer 命令行参数](sequencer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b32-119">For a complete list of parameters that are available for use with the App-V Sequencer, see [Sequencer Command-Line Parameters](sequencer-command-line-parameters.md).</span></span>



~~~
Use the value descriptions in the following table to help you determine the actual text you will use in the preceding command.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>pathtoMSI</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtopackageroot</em></p></td>
<td align="left"><p>Specify the package root directory.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. <span data-ttu-id="d7b32-120">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="d7b32-120">Press **Enter**.</span></span>

## <span data-ttu-id="d7b32-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7b32-121">Related topics</span></span>


[<span data-ttu-id="d7b32-122">如何使用 App-v Sequencer 创建或升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="d7b32-122">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[<span data-ttu-id="d7b32-123">Sequencer 命令行错误代码</span><span class="sxs-lookup"><span data-stu-id="d7b32-123">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

[<span data-ttu-id="d7b32-124">Sequencer 命令行参数</span><span class="sxs-lookup"><span data-stu-id="d7b32-124">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)









