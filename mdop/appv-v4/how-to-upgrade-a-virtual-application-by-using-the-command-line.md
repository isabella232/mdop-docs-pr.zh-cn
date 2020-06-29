---
title: 如何使用命令行升级虚拟应用程序
description: 如何使用命令行升级虚拟应用程序
author: dansimp
ms.assetid: 83c97767-6ea1-42aa-b411-ccc9fa61cf81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8612deb31a1692dd85cfee88ca4b18cbc5ac2ab2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801027"
---
# <span data-ttu-id="f9d0c-103">如何使用命令行升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="f9d0c-103">How to Upgrade a Virtual Application by Using the Command Line</span></span>


<span data-ttu-id="f9d0c-104">使用以下过程通过命令行升级虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-104">Use the following procedure to upgrade a virtual application by using a command line.</span></span>

**<span data-ttu-id="f9d0c-105">升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="f9d0c-105">To upgrade a virtual application</span></span>**

1.  <span data-ttu-id="f9d0c-106">在运行应用程序虚拟化（app-v）排序器的计算机上，若要打开命令提示符，请选择 "**开始**"、"**运行**"，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-106">On the computer that is running the Application Virtualization (App-V) Sequencer, to open the command prompt, select **Start**, **Run**, and type **cmd**.</span></span> <span data-ttu-id="f9d0c-107">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-107">Click **OK**.</span></span>

2.  <span data-ttu-id="f9d0c-108">在命令提示符处，指定安装 app-v Sequencer 的位置。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-108">At the command prompt, specify the location where the App-V Sequencer is installed.</span></span> <span data-ttu-id="f9d0c-109">例如，在命令提示符处，可以键入以下内容： **cd C:\\program files Files\\Microsoft Application Virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-109">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="f9d0c-110">在命令提示符处，键入以下命令，将引号中的文本替换为值：</span><span class="sxs-lookup"><span data-stu-id="f9d0c-110">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="f9d0c-111">注意</span><span class="sxs-lookup"><span data-stu-id="f9d0c-111">Note</span></span>**  
    <span data-ttu-id="f9d0c-112">你可以使用命令行指定其他参数，具体取决于你要升级的应用程序的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-112">You can specify additional parameters by using the command line, depending on the complexity of the application you are upgrading.</span></span> <span data-ttu-id="f9d0c-113">有关可用于 App-v Sequencer 的参数的完整列表，请参阅[Sequencer 命令行参数](sequencer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-113">For a complete list of parameters that are available for use with the App-V Sequencer, see [Sequencer Command-Line Parameters](sequencer-command-line-parameters.md).</span></span>



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



4. <span data-ttu-id="f9d0c-114">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="f9d0c-114">Press **Enter**.</span></span>

## <span data-ttu-id="f9d0c-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="f9d0c-115">Related topics</span></span>


[<span data-ttu-id="f9d0c-116">如何使用 App-v Sequencer 创建或升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="f9d0c-116">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[<span data-ttu-id="f9d0c-117">Sequencer 命令行错误代码</span><span class="sxs-lookup"><span data-stu-id="f9d0c-117">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

[<span data-ttu-id="f9d0c-118">Sequencer 命令行参数</span><span class="sxs-lookup"><span data-stu-id="f9d0c-118">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)









