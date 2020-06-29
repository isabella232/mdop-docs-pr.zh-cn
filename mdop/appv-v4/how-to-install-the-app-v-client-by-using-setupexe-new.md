---
title: 如何使用 Setup.exe 安装 App-V Client
description: 如何使用 Setup.exe 安装 App-V Client
author: dansimp
ms.assetid: 106a5d97-b5f6-4a16-bf52-a84f4d558c74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60f79a2d2f74848ab121ba13cdf8c215088d54db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801376"
---
# <span data-ttu-id="a7a31-103">如何使用 Setup.exe 安装 App-V Client</span><span class="sxs-lookup"><span data-stu-id="a7a31-103">How to Install the App-V Client by Using Setup.exe</span></span>


<span data-ttu-id="a7a31-104">本主题介绍了如何使用 setup.exe 程序安装 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="a7a31-104">This topic describes how to install the App-V client by using the setup.exe program.</span></span> <span data-ttu-id="a7a31-105">使用 setup.exe 程序安装 App-v 客户端时，安装程序确定需要哪些必备软件，并在安装客户端之前自动安装该软件。</span><span class="sxs-lookup"><span data-stu-id="a7a31-105">When you install the App-V client using the setup.exe program, the installer determines which prerequisite software is needed and installs it automatically before it installs the client.</span></span>

**<span data-ttu-id="a7a31-106">使用 Setup.exe 安装应用程序虚拟化客户端</span><span class="sxs-lookup"><span data-stu-id="a7a31-106">To install the Application Virtualization Client by Using Setup.exe</span></span>**

1.  <span data-ttu-id="a7a31-107">请确保使用具有计算机管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a7a31-107">Make sure you are logged on with an account that has administrator rights on the computer.</span></span>

2.  <span data-ttu-id="a7a31-108">打开命令提示符窗口，然后将目录更改为包含安装程序文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7a31-108">Open a Command Prompt window, and then change the directory to the folder that contains the setup files.</span></span> <span data-ttu-id="a7a31-109">在安装版本4.6 或更高版本的 App-v 客户端时，必须使用适用于计算机操作系统、32位或64位的正确安装程序。</span><span class="sxs-lookup"><span data-stu-id="a7a31-109">When installing version4.6 or a later version of the App-V client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="a7a31-110">如果你使用了错误的安装程序，安装将失败，并且将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a7a31-110">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

3.  <span data-ttu-id="a7a31-111">在命令提示符处输入安装命令字符串。</span><span class="sxs-lookup"><span data-stu-id="a7a31-111">Enter the install command string at the command prompt.</span></span> <span data-ttu-id="a7a31-112">或者，你可以创建一个命令文件并从命令提示符处运行它。</span><span class="sxs-lookup"><span data-stu-id="a7a31-112">Alternatively, you can create a command file and run it from the command prompt.</span></span> <span data-ttu-id="a7a31-113">你还可以使用脚本语言（如 VBScript 或 Windows PowerShell）运行命令。</span><span class="sxs-lookup"><span data-stu-id="a7a31-113">You can also use a scripting language such as VBScript or Windows PowerShell to run the command.</span></span>

4.  <span data-ttu-id="a7a31-114">下面的命令行示例演示如何将 setup.exe 用于许多可选参数。</span><span class="sxs-lookup"><span data-stu-id="a7a31-114">The following command-line example shows how setup.exe can be used with a number of optional parameters.</span></span> <span data-ttu-id="a7a31-115">有关这些参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a7a31-115">For more information about these parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

    **<span data-ttu-id="a7a31-116">"setup.exe"/s/v "/qn SWICACHESIZE = \ \" SWIPUBSVRDISPLAY = \ "=" SWIPUBSVRTYPE = \ "HTTP/secure\\" SWIPUBSVRHOST = \ "PRODSYS\\" SWIPUBSVRPORT = \ \ "" SWIPUBSVRPATH = \\ "/AppVirt/appsntype.xml \" SWIPUBSVRREFRESH = \ \ "on\\" SWIGLOBALDATA = \ \ "D:\\AppVirt\\Global\\" SWIUSERDATA = \ "^% LOCALAPPDATA ^%\\Windows\\Application 虚拟化 Client\\" SWIFSDRIVE = \ \ "Q\\" "</span><span class="sxs-lookup"><span data-stu-id="a7a31-116">"setup.exe" /s /v"/qn SWICACHESIZE=\\"10240\\" SWIPUBSVRDISPLAY=\\"Production System\\" SWIPUBSVRTYPE=\\"HTTP /secure\\" SWIPUBSVRHOST=\\"PRODSYS\\" SWIPUBSVRPORT=\\"443\\" SWIPUBSVRPATH=\\"/AppVirt/appsntype.xml\\" SWIPUBSVRREFRESH=\\"on\\" SWIGLOBALDATA=\\"D:\\AppVirt\\Global\\" SWIUSERDATA=\\"^% LOCALAPPDATA ^%\\Windows\\Application Virtualization Client\\" SWIFSDRIVE=\\"Q\\""</span></span>**

    **<span data-ttu-id="a7a31-117">重要提示</span><span class="sxs-lookup"><span data-stu-id="a7a31-117">Important</span></span>**  
    -   <span data-ttu-id="a7a31-118">"**/V**" 部分中显示的引号必须被视为特殊字符，并使用前面的 " **\\** " 输入。</span><span class="sxs-lookup"><span data-stu-id="a7a31-118">The quotation marks that appear in the "**/v**" section must be treated as special characters and entered with a preceding "**\\**".</span></span> <span data-ttu-id="a7a31-119">只有当值包含空格时，才需要使用引号。但是，为了保持一致性，上述示例中的所有实例都显示为带有引号。</span><span class="sxs-lookup"><span data-stu-id="a7a31-119">The quotation marks are required only when the value contains a space; however, for consistency, all the instances in the preceding example are shown as having quotation marks.</span></span>

    -   <span data-ttu-id="a7a31-120">" **%** **% HomeDrive%**" 中的 "" 字符必须前面有 " **^** " 转义字符。</span><span class="sxs-lookup"><span data-stu-id="a7a31-120">The "**%**" characters in "**%HomeDrive%**" must be preceded by the "**^**" escape character.</span></span> <span data-ttu-id="a7a31-121">否则，Windows 命令外壳程序会将值设置为执行安装的用户的值。</span><span class="sxs-lookup"><span data-stu-id="a7a31-121">Otherwise, the Windows command shell sets the value to that of the user who is performing the installation.</span></span>

    -   <span data-ttu-id="a7a31-122">需要使用**InstallShield**开关 **/s**和 **/qn**将其设置为静默安装。</span><span class="sxs-lookup"><span data-stu-id="a7a31-122">The **InstallShield** switches **/s** and **/qn** are needed to make this a silent install.</span></span> <span data-ttu-id="a7a31-123">**/Qn**开关必须跟在 **/v**开关之后，由不带空格的引号字符分隔。</span><span class="sxs-lookup"><span data-stu-id="a7a31-123">The **/qn** switch must follow the **/v** switch, separated by only a quote character with no intervening spaces.</span></span>

    -   <span data-ttu-id="a7a31-124">在**SWIGLOBALDATA**值中指定的文件夹必须已存在。</span><span class="sxs-lookup"><span data-stu-id="a7a31-124">The folder specified in the **SWIGLOBALDATA** value must already exist.</span></span>

     

5.  <span data-ttu-id="a7a31-125">安装完成后，我们建议你运行 Microsoft 更新扫描以确保安装最新的更新。</span><span class="sxs-lookup"><span data-stu-id="a7a31-125">When the installation is complete, we recommend that you run a Microsoft Update scan to ensure the latest updates are installed.</span></span>

## <span data-ttu-id="a7a31-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="a7a31-126">Related topics</span></span>


[<span data-ttu-id="a7a31-127">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="a7a31-127">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





