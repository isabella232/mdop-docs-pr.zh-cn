---
title: PUBLISH PACKAGE
description: PUBLISH PACKAGE
author: dansimp
ms.assetid: a33e72dd-194f-4283-8e99-4584ab13de53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00b63389986f495d9405939245a50575bae453f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798846"
---
# <span data-ttu-id="53737-103">PUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="53737-103">PUBLISH PACKAGE</span></span>


<span data-ttu-id="53737-104">发布整个程序包的内容。</span><span class="sxs-lookup"><span data-stu-id="53737-104">Publishes the contents of an entire package.</span></span>

`SFTMIME PUBLISH PACKAGE:package-name /MANIFEST manifest-path [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="53737-105">参数</span><span class="sxs-lookup"><span data-stu-id="53737-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="53737-106">描述</span><span class="sxs-lookup"><span data-stu-id="53737-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="53737-107">程序包： &lt; 软件包-name&gt;</span><span class="sxs-lookup"><span data-stu-id="53737-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="53737-108">程序包的用户可见名称和用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="53737-108">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="53737-109">/MANIFEST &lt; 清单-path&gt;</span><span class="sxs-lookup"><span data-stu-id="53737-109">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="53737-110">列出程序包中包含的应用程序及其所有发布信息的清单文件的路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="53737-110">The path or URL of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="53737-111">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="53737-111">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="53737-112">如果存在，则此计算机上的所有用户都可以使用该程序包。</span><span class="sxs-lookup"><span data-stu-id="53737-112">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="53737-113">/LOG</span><span class="sxs-lookup"><span data-stu-id="53737-113">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="53737-114">如果指定，输出将记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="53737-114">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="53737-115">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="53737-115">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="53737-116">如果指定，将在活动控制台窗口中显示输出（默认）。</span><span class="sxs-lookup"><span data-stu-id="53737-116">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="53737-117">/GUI</span><span class="sxs-lookup"><span data-stu-id="53737-117">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="53737-118">如果指定，将在 Windows 对话框中显示输出。</span><span class="sxs-lookup"><span data-stu-id="53737-118">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="53737-119">对于版本4.6，已添加以下选项。</span><span class="sxs-lookup"><span data-stu-id="53737-119">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="53737-120">/LOGU</span><span class="sxs-lookup"><span data-stu-id="53737-120">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="53737-121">如果指定，将以 UNICODE 格式将输出记录到指定的路径名称。</span><span class="sxs-lookup"><span data-stu-id="53737-121">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="53737-122">**重要提示** 该包必须已添加到应用程序虚拟化客户端，并且需要清单文件。</span><span class="sxs-lookup"><span data-stu-id="53737-122">**Important** The package must already have been added to the Application Virtualization Client, and the manifest file is required.</span></span>

<span data-ttu-id="53737-123">若要使用**全局**参数，必须以本地管理员身份运行 "发布包" 命令;否则，仅需要**ManageTypes**和**PublishShortcut**权限。</span><span class="sxs-lookup"><span data-stu-id="53737-123">To use the **GLOBAL** parameter, the PUBLISH PACKAGE command must be run as local Administrator; otherwise, only **ManageTypes** and **PublishShortcut** permissions are needed.</span></span>

<span data-ttu-id="53737-124">不带**全局**参数的发布授予用户对程序包中应用程序的访问权限，并将清单中列出的文件类型和快捷方式发布到用户的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="53737-124">Publishing without the **GLOBAL** parameter grants the user access to the applications in the package and publishes the file types and shortcuts listed in the manifest to the user’s profile.</span></span>

<span data-ttu-id="53737-125">通过**全局**参数进行发布将清单中列出的文件类型和快捷方式添加到 "所有用户" 配置文件。</span><span class="sxs-lookup"><span data-stu-id="53737-125">Publishing with the **GLOBAL** parameter adds the file types and shortcuts listed in the manifest to the “All Users” profile.</span></span>

<span data-ttu-id="53737-126">如果在呼叫和使用**全局**参数时程序包不是全局程序包，则会将该程序包设置为全局，并向所有用户提供。</span><span class="sxs-lookup"><span data-stu-id="53737-126">If the package is not global before the call and the **GLOBAL** parameter is used, the package is made global and available to all users.</span></span>

 

## <span data-ttu-id="53737-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="53737-127">Related topics</span></span>


[<span data-ttu-id="53737-128">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="53737-128">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





