---
title: 如何使用命令行升级已排序的应用程序包
description: 如何使用命令行升级已排序的应用程序包
author: dansimp
ms.assetid: 682fac46-c71d-4731-831b-81bfd5032764
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eade2ced43852419176f635918f0a6b7c3444aee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801036"
---
# <span data-ttu-id="6a651-103">如何使用命令行升级已排序的应用程序包</span><span class="sxs-lookup"><span data-stu-id="6a651-103">How to Upgrade a Sequenced Application Package Using the Command Line</span></span>


<span data-ttu-id="6a651-104">使用以下过程通过命令行升级虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a651-104">Use the following procedure to upgrade a virtual application by using a command line.</span></span> <span data-ttu-id="6a651-105">使用命令行升级现有虚拟应用程序包时，将删除该 sft 文件的原始版本。</span><span class="sxs-lookup"><span data-stu-id="6a651-105">When you upgrade an existing virtual application package by using the command line, the original version of the .sft file is deleted.</span></span> <span data-ttu-id="6a651-106">你应该先备份关联的 sft 文件，然后再使用命令行升级程序包。</span><span class="sxs-lookup"><span data-stu-id="6a651-106">You should back up the associated .sft file before upgrading the package by using the command line.</span></span>

**<span data-ttu-id="6a651-107">升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="6a651-107">To upgrade a virtual application</span></span>**

1.  <span data-ttu-id="6a651-108">在运行应用程序虚拟化（app-v）排序器的计算机上，若要打开命令提示符，请选择 "**开始**"、"**运行**"，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="6a651-108">On the computer that is running the Application Virtualization (App-V) Sequencer, to open the command prompt, select **Start**, **Run**, and type **cmd**.</span></span> <span data-ttu-id="6a651-109">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a651-109">Click **OK**.</span></span>

2.  <span data-ttu-id="6a651-110">在命令提示符处，指定安装 app-v Sequencer 的位置。</span><span class="sxs-lookup"><span data-stu-id="6a651-110">At the command prompt, specify the location where the App-V Sequencer is installed.</span></span> <span data-ttu-id="6a651-111">例如，在命令提示符处，可以键入以下内容： **cd C:\\program files Files\\Microsoft Application Virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="6a651-111">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="6a651-112">在命令提示符处，键入以下命令，将引号中的文本替换为值：</span><span class="sxs-lookup"><span data-stu-id="6a651-112">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="6a651-113">注意</span><span class="sxs-lookup"><span data-stu-id="6a651-113">Note</span></span>**  
    <span data-ttu-id="6a651-114">你可以使用命令行指定其他参数，具体取决于你要升级的应用程序的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="6a651-114">You can specify additional parameters by using the command line, depending on the complexity of the application you are upgrading.</span></span> <span data-ttu-id="6a651-115">有关可用于 App-v Sequencer 的参数的完整列表，请参阅[命令行参数](command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="6a651-115">For a complete list of parameters that are available for use with the App-V Sequencer, see [Command-Line Parameters](command-line-parameters.md).</span></span>



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
<td align="left"><p><em>pathtosourceSPRJ</em></p></td>
<td align="left"><p>Specifies the directory location of the virtual application to be upgraded.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtoUpgradeInstaller</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an upgrade to the application.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodecodefolder</em></p></td>
<td align="left"><p>Specify the directory in which to unpack the SFT file.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. <span data-ttu-id="6a651-116">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="6a651-116">Press **Enter**.</span></span>

## <span data-ttu-id="6a651-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="6a651-117">Related topics</span></span>


[<span data-ttu-id="6a651-118">如何使用命令行管理虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="6a651-118">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)









