---
title: 如何配置快捷方式和文件类型关联行为
description: 如何配置快捷方式和文件类型关联行为
author: dansimp
ms.assetid: d6fd1728-4de6-4066-b36b-d4837d593d40
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84e3e0cdd43cfc26cf56f1b5ac72560b1c702ae6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801607"
---
# <span data-ttu-id="06842-103">如何配置快捷方式和文件类型关联行为</span><span class="sxs-lookup"><span data-stu-id="06842-103">How to Configure Shortcut and File Type Association Behavior</span></span>


<span data-ttu-id="06842-104">快捷方式和文件类型关联（FTA）发布策略由发布 XML 文件定义和控制，发布 XML 文件在发布刷新操作期间由发布服务器发送给客户端。</span><span class="sxs-lookup"><span data-stu-id="06842-104">Shortcut and File Type Association (FTA) publishing policy is defined and controlled by the publishing XML file, which is sent to clients by a publishing server during a publishing refresh operation.</span></span> <span data-ttu-id="06842-105">当客户端收到此信息时，它将添加有关应用程序（如图标和 FTAs）的任何新发布的数据。</span><span class="sxs-lookup"><span data-stu-id="06842-105">When the client receives this information, it adds any newly published data about applications such as the icons and FTAs.</span></span> <span data-ttu-id="06842-106">然后，它会删除任何过时的发布数据。</span><span class="sxs-lookup"><span data-stu-id="06842-106">Then, it removes any outdated publishing data.</span></span>

<span data-ttu-id="06842-107">在 App-v 版本4.6 中，定义了两个注册表项值以使管理员能够控制此行为。</span><span class="sxs-lookup"><span data-stu-id="06842-107">In App-V version 4.6, two registry key values have been defined to enable administrators to control this behavior.</span></span> <span data-ttu-id="06842-108">默认情况下，使用客户端控制台在本地创建的快捷方式现在保留。</span><span class="sxs-lookup"><span data-stu-id="06842-108">By default, shortcuts that are created locally by using the client console are now retained.</span></span>

## <span data-ttu-id="06842-109">如何更改快捷方式和 FTA 行为</span><span class="sxs-lookup"><span data-stu-id="06842-109">How to Change Shortcut and FTA Behavior</span></span>


<span data-ttu-id="06842-110">已为客户端配置注册表项、"FileTypePolicy" 和 "ShortcutPolicy" 定义了两个新的 DWORD 注册表值。</span><span class="sxs-lookup"><span data-stu-id="06842-110">Two new DWORD registry values have been defined for the client Configuration registry key, “FileTypePolicy” and “ShortcutPolicy”.</span></span> <span data-ttu-id="06842-111">默认情况下不显示这些 DWORD 注册表值，但可以手动添加它们。</span><span class="sxs-lookup"><span data-stu-id="06842-111">These DWORD registry values are not present by default, but they can be added manually.</span></span> <span data-ttu-id="06842-112">配置注册表项位于 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\Configuration。</span><span class="sxs-lookup"><span data-stu-id="06842-112">The Configuration registry key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\[Wow6432Node\\\]Microsoft\\SoftGrid\\4.5\\Client\\Configuration.</span></span>

<span data-ttu-id="06842-113">下表中定义了四个策略值，它们均适用于两个注册表项值。</span><span class="sxs-lookup"><span data-stu-id="06842-113">There are four policy values defined in the following table and these apply to both registry key values.</span></span> <span data-ttu-id="06842-114">以下列表显示了注册表设置的数值，以及应用于发布刷新操作上的文件类型或快捷方式的行为。</span><span class="sxs-lookup"><span data-stu-id="06842-114">The following list shows the numeric values for the registry settings, and the behavior applied to file types or shortcuts on a publishing refresh operation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="06842-115">名称</span><span class="sxs-lookup"><span data-stu-id="06842-115">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-116">类型</span><span class="sxs-lookup"><span data-stu-id="06842-116">Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-117">数据（示例）</span><span class="sxs-lookup"><span data-stu-id="06842-117">Data (Examples)</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-118">描述</span><span class="sxs-lookup"><span data-stu-id="06842-118">Description</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="06842-119">FileTypePolicy</span><span class="sxs-lookup"><span data-stu-id="06842-119">FileTypePolicy</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-120">DWORD</span><span class="sxs-lookup"><span data-stu-id="06842-120">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-121">默认值 = 0x2 （App-v 4.6）</span><span class="sxs-lookup"><span data-stu-id="06842-121">Default=0x2 (App-V 4.6)</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-122">（0x0）-"ClientOnly"-删除同一发布信息源中的所有现有项目，并仅保留本地添加的项目</span><span class="sxs-lookup"><span data-stu-id="06842-122">(0x0) – “ClientOnly”- remove any existing items from the same publishing information source, and keep only items that are added locally</span></span></p>
<p><span data-ttu-id="06842-123">（0x1）-"ServerOnly"-从同一发布信息源和任何本地添加的项目中删除任何过时项目，并添加新项目</span><span class="sxs-lookup"><span data-stu-id="06842-123">(0x1) – “ServerOnly” - remove any outdated items from the same publishing information source and any items that are added locally, and add the new items</span></span></p>
<p><span data-ttu-id="06842-124">（0x2）-"ClientAndServer"-从同一发布信息源中删除任何过时的项目、将添加的项目保留在本地，并添加新项目（如果不存在，则默认为 app-v 4.6）</span><span class="sxs-lookup"><span data-stu-id="06842-124">(0x2) – “ClientAndServer”- remove any outdated items from the same publishing information source, keep items added locally, and add the new items (default if not present for App-V 4.6)</span></span></p>
<p><span data-ttu-id="06842-125">（0x3）-"NoChange"-不对文件类型或快捷方式进行任何更改</span><span class="sxs-lookup"><span data-stu-id="06842-125">(0x3) – “NoChange” - make no changes to file types or shortcuts</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="06842-126">ShortcutPolicy</span><span class="sxs-lookup"><span data-stu-id="06842-126">ShortcutPolicy</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-127">DWORD</span><span class="sxs-lookup"><span data-stu-id="06842-127">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-128">默认值 = 0x2</span><span class="sxs-lookup"><span data-stu-id="06842-128">Default=0x2</span></span></p></td>
<td align="left"><p><span data-ttu-id="06842-129">（0x0）-"ClientOnly"-删除同一发布信息源中的所有现有项目，并仅保留本地添加的项目</span><span class="sxs-lookup"><span data-stu-id="06842-129">(0x0) – “ClientOnly”- remove any existing items from the same publishing information source, and keep only items added locally</span></span></p>
<p><span data-ttu-id="06842-130">（0x1）-"ServerOnly"-删除同一发布信息源和本地添加的任何项目中的任何过时项目，并添加新项目</span><span class="sxs-lookup"><span data-stu-id="06842-130">(0x1) – “ServerOnly” - remove any outdated items from the same publishing information source and any items added locally, and add the new items</span></span></p>
<p><span data-ttu-id="06842-131">（0x2）-"ClientAndServer"-从同一发布信息源中删除任何过时项目，将项目添加到本地并添加新项目（如果不存在，则为默认值）</span><span class="sxs-lookup"><span data-stu-id="06842-131">(0x2) – “ClientAndServer”- remove any outdated items from the same publishing information source, keep items added locally, and add the new items (default if not present)</span></span></p>
<p><span data-ttu-id="06842-132">（0x3）-"NoChange"-不对文件类型或快捷方式进行任何更改</span><span class="sxs-lookup"><span data-stu-id="06842-132">(0x3) – “NoChange” - make no changes to file types or shortcuts</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="06842-133">**注意** 文本值指发布 XML 文件中的 XML 属性的值。</span><span class="sxs-lookup"><span data-stu-id="06842-133">**Note** The text values refer to the values for the XML attributes in the publishing XML file.</span></span><span data-ttu-id="06842-134">如果已实现自定义 HTTP 发布解决方案，则可以手动设置这些值。</span><span class="sxs-lookup"><span data-stu-id="06842-134"> You can set these values manually if you have implemented a custom HTTP publishing solution.</span></span>

 

 

 





