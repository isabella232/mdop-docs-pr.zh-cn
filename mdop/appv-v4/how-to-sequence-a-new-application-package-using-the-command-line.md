---
title: 如何使用命令行对新应用程序包进行排序
description: 如何使用命令行对新应用程序包进行排序
author: dansimp
ms.assetid: de72912b-d9e7-45b5-a601-12528f1a4cac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2dd638a7e4765cedbf1d8050626fb8cc54b2ce8b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801112"
---
# <span data-ttu-id="57362-103">如何使用命令行对新应用程序包进行排序</span><span class="sxs-lookup"><span data-stu-id="57362-103">How to Sequence a New Application Package Using the Command Line</span></span>


<span data-ttu-id="57362-104">可以使用命令行对新应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="57362-104">You can use a command line to sequence a new application.</span></span> <span data-ttu-id="57362-105">当必须创建大量虚拟应用程序或需要定期创建顺序应用程序时，使用命令行非常有用。</span><span class="sxs-lookup"><span data-stu-id="57362-105">Using a command line is useful when you have to create a large number of virtual applications or when you need to create sequenced applications on a recurring basis.</span></span>

**<span data-ttu-id="57362-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="57362-106">Important</span></span>**  
<span data-ttu-id="57362-107">命令行序列仅允许默认排序。</span><span class="sxs-lookup"><span data-stu-id="57362-107">Command-line sequencing allows for default sequencing only.</span></span> <span data-ttu-id="57362-108">如果需要更改要对其进行排序的应用程序的默认安装设置，则必须手动修改虚拟应用程序或使用应用程序虚拟化（app-v） Sequencer 更新虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="57362-108">If you need to change default installation settings for the application you are sequencing, you must either manually modify the virtual application or update the virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="57362-109">有关使用 App-v Sequencer 更新虚拟应用程序的详细信息，请参阅[如何升级现有虚拟应用程序](how-to-upgrade-an-existing-virtual-application.md)。</span><span class="sxs-lookup"><span data-stu-id="57362-109">For more information about updating a virtual application by using the App-V Sequencer, see [How to Upgrade an Existing Virtual Application](how-to-upgrade-an-existing-virtual-application.md).</span></span>



<span data-ttu-id="57362-110">使用以下过程，使用命令行创建虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="57362-110">Use the following procedure to create a virtual application by using the command line.</span></span>

**<span data-ttu-id="57362-111">使用命令行对应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="57362-111">To sequence an application by using the command line</span></span>**

1.  <span data-ttu-id="57362-112">在运行 App-v 排序器的计算机上，通过选择 "**开始**"、"**运行**"，然后键入**cmd**来打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="57362-112">On the computer that is running the App-V Sequencer, open the command prompt by selecting **Start**, **Run**, and then type **cmd**.</span></span> <span data-ttu-id="57362-113">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57362-113">Click **OK**.</span></span>

2.  <span data-ttu-id="57362-114">使用命令提示符指定安装 app-v Sequencer 的位置。</span><span class="sxs-lookup"><span data-stu-id="57362-114">Use the command prompt to specify the location of where the App-V Sequencer is installed.</span></span> <span data-ttu-id="57362-115">例如，在命令提示符处，可以键入以下内容： **cd C:\\program files Files\\Microsoft Application Virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="57362-115">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="57362-116">在命令提示符处，键入以下命令，将引号中的文本替换为值：</span><span class="sxs-lookup"><span data-stu-id="57362-116">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /INSTALLPACKAGE:"pathtoMSI" /INSTALLPATH:"pathtopackageroot" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="57362-117">注意</span><span class="sxs-lookup"><span data-stu-id="57362-117">Note</span></span>**  
    <span data-ttu-id="57362-118">你可以使用命令行指定其他参数，具体取决于你正在对其进行排序的应用程序的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="57362-118">You can specify additional parameters by using the command line, depending on the complexity of the application you are sequencing.</span></span> <span data-ttu-id="57362-119">有关可用于 App-v Sequencer 的参数的完整列表，请参阅[应用程序虚拟化 Sequencer 命令行](application-virtualization-sequencer-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="57362-119">For a complete list of parameters that are available for use with the App-V Sequencer, see [Application Virtualization Sequencer Command Line](application-virtualization-sequencer-command-line.md).</span></span>



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
<td align="left"><p>Specifies the package root directory.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. <span data-ttu-id="57362-120">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="57362-120">Press **Enter**.</span></span>

## <span data-ttu-id="57362-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="57362-121">Related topics</span></span>


[<span data-ttu-id="57362-122">如何使用命令行管理虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="57362-122">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)









