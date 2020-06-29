---
title: 如何在客户端上发布虚拟应用程序
description: 如何在客户端上发布虚拟应用程序
author: dansimp
ms.assetid: 90af843e-b5b3-4a71-a3a1-fa5f4c087f28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5585f82150db69929ccedbee3aecab969c5e7dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801191"
---
# <span data-ttu-id="0659f-103">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="0659f-103">How to Publish a Virtual Application on the Client</span></span>


<span data-ttu-id="0659f-104">使用电子软件分发系统部署应用程序虚拟化时，可以使用以下过程之一将应用程序包发布给用户。</span><span class="sxs-lookup"><span data-stu-id="0659f-104">When you deploy Application Virtualization by using an electronic software distribution system, you can use one of the following procedures to publish an application package to your users.</span></span>

**<span data-ttu-id="0659f-105">使用独立的 Windows Installer 文件发布程序包</span><span class="sxs-lookup"><span data-stu-id="0659f-105">To publish a package using a stand-alone Windows Installer file</span></span>**

1.  <span data-ttu-id="0659f-106">应安装客户端，将*REQUIREAUTHORIZATIONIFCACHED*参数设置为0（零）。</span><span class="sxs-lookup"><span data-stu-id="0659f-106">The client should be installed with the *REQUIREAUTHORIZATIONIFCACHED* parameter set to 0 (zero).</span></span> <span data-ttu-id="0659f-107">有关设置此参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="0659f-107">For more information about setting this parameter, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md)</span></span>

2.  <span data-ttu-id="0659f-108">将 Windows Installer 文件和 SFT 文件复制到目标计算机上的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0659f-108">Copy the Windows Installer file and the SFT file to same folder on the target computer.</span></span>

3.  <span data-ttu-id="0659f-109">在计算机上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0659f-109">Run the following command on the computer:</span></span>

    `Msiexec.exe /I "packagename.msi" /q`

**<span data-ttu-id="0659f-110">使用 Windows Installer 和程序包清单发布程序包</span><span class="sxs-lookup"><span data-stu-id="0659f-110">To publish a package using Windows Installer and the package manifest</span></span>**

1.  <span data-ttu-id="0659f-111">将 Windows Installer 文件复制到目标计算机，然后将 SFT 文件复制到流服务器上的内容共享。</span><span class="sxs-lookup"><span data-stu-id="0659f-111">Copy the Windows Installer file to the target computer and the SFT file to the CONTENT share on the streaming server.</span></span>

2.  <span data-ttu-id="0659f-112">在每个用户的计算机上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0659f-112">Run the following command on each user’s computer:</span></span>

    `Msiexec.exe /I "\\pathtomsi\packagename.msi" MODE=STREAMING  OVERRIDEURL="\\\\server\\share\\package.sft" LOAD=TRUE /q`

    <span data-ttu-id="0659f-113">**重要提示** 对于 OVERRIDEURL，所有反斜杠字符必须使用前面的反斜杠进行转义，否则将不会正确分析 OVERRIDEURL 路径。</span><span class="sxs-lookup"><span data-stu-id="0659f-113">**Important** For OVERRIDEURL all backslash characters must be escaped using a preceding backslash, or the OVERRIDEURL path will not be parsed correctly.</span></span> <span data-ttu-id="0659f-114">此外，必须以大写形式输入属性和值，除非值是文件的路径。</span><span class="sxs-lookup"><span data-stu-id="0659f-114">Also, properties and values must be entered as uppercase except where the value is a path to a file.</span></span>

     

**<span data-ttu-id="0659f-115">使用 SFTMIME 发布程序包</span><span class="sxs-lookup"><span data-stu-id="0659f-115">To publish a package using SFTMIME</span></span>**

-   <span data-ttu-id="0659f-116">有关如何为计算机上的所有用户发布应用程序的示例，请在用户的计算机上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0659f-116">For an example of how to publish an application for all users on a computer, run the following command on the user’s computer:</span></span>

    `SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

    <span data-ttu-id="0659f-117">有关这些和其他 SFTMIME 命令的其他详细信息，请参阅[SFTMIME 命令参考](sftmime--command-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="0659f-117">For additional details about these and other SFTMIME commands, see [SFTMIME Command Reference](sftmime--command-reference.md).</span></span>

## <span data-ttu-id="0659f-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="0659f-118">Related topics</span></span>


[<span data-ttu-id="0659f-119">确定发布方法</span><span class="sxs-lookup"><span data-stu-id="0659f-119">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

[<span data-ttu-id="0659f-120">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="0659f-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="0659f-121">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="0659f-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

[<span data-ttu-id="0659f-122">适用于 Application Virtualization Client 的独立传递方案</span><span class="sxs-lookup"><span data-stu-id="0659f-122">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





