---
title: 如何使用文本编辑器编辑 OSD 文件
description: 如何使用文本编辑器编辑 OSD 文件
author: dansimp
ms.assetid: f4263a1b-824f-49b9-8060-b8229c9d9960
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c83547b38cee7e91e8348689583e0542a88dab83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801419"
---
# <span data-ttu-id="18e87-103">如何使用文本编辑器编辑 OSD 文件</span><span class="sxs-lookup"><span data-stu-id="18e87-103">How to Edit an OSD File Using a Text Editor</span></span>


<span data-ttu-id="18e87-104">使用以下过程，使用文本编辑器编辑打开的软件描述符（OSD）文件。</span><span class="sxs-lookup"><span data-stu-id="18e87-104">Use the following procedure to edit an Open Software Descriptor (OSD) file by using a text editor.</span></span>

**<span data-ttu-id="18e87-105">使用文本编辑器编辑 OSD 文件</span><span class="sxs-lookup"><span data-stu-id="18e87-105">To edit an OSD file by using a text editor</span></span>**

1.  <span data-ttu-id="18e87-106">使用任何 XML 或 ASCII 文本编辑器（如 Microsoft 记事本）打开 OSD 文件。</span><span class="sxs-lookup"><span data-stu-id="18e87-106">Open the OSD file using any XML or ASCII text editor—for example, Microsoft Notepad.</span></span>

    <span data-ttu-id="18e87-107">**注意** 在修改 OSD 文件之前，请阅读安装目录中由 XSD 文件指定的架构。</span><span class="sxs-lookup"><span data-stu-id="18e87-107">**Note** Before modifying the OSD file, read the schema prescribed by the XSD file in the install directory.</span></span> <span data-ttu-id="18e87-108">无法关注此架构可能会引入错误，从而阻止序列化的应用程序成功启动。</span><span class="sxs-lookup"><span data-stu-id="18e87-108">Failing to follow this schema might introduce errors that prevent a sequenced application from starting successfully.</span></span>

     

2.  <span data-ttu-id="18e87-109">使用所选的 XML 或 ASCII 文本编辑器编辑 OSD 文件，遵循指定的架构和以下准则：</span><span class="sxs-lookup"><span data-stu-id="18e87-109">Edit the OSD file using your XML or ASCII text editor of choice, adhering to the prescribed schema and the following guidelines:</span></span>

    1.  <span data-ttu-id="18e87-110">确保命名的元素嵌套在 &lt; SOFTPKG &gt; 根元素中。</span><span class="sxs-lookup"><span data-stu-id="18e87-110">Ensure that named elements are nested within the &lt;SOFTPKG&gt; root element.</span></span>

    2.  <span data-ttu-id="18e87-111">确保元素名称全部为大写字母。</span><span class="sxs-lookup"><span data-stu-id="18e87-111">Ensure that element names are in all uppercase letters.</span></span>

    3.  <span data-ttu-id="18e87-112">请注意，属性值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="18e87-112">Be aware that attribute values are case sensitive.</span></span>

    4.  <span data-ttu-id="18e87-113">请仔细键入，并遵守 XML 规范。</span><span class="sxs-lookup"><span data-stu-id="18e87-113">Type carefully, and observe the XML specifications.</span></span>

## <span data-ttu-id="18e87-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="18e87-114">Related topics</span></span>


[<span data-ttu-id="18e87-115">关于“OSD”选项卡</span><span class="sxs-lookup"><span data-stu-id="18e87-115">About the OSD Tab</span></span>](about-the-osd-tab.md)

[<span data-ttu-id="18e87-116">如何编辑 OSD 文件</span><span class="sxs-lookup"><span data-stu-id="18e87-116">How to Edit an OSD File</span></span>](how-to-edit-an-osd-file.md)

[<span data-ttu-id="18e87-117">OSD 文件元素</span><span class="sxs-lookup"><span data-stu-id="18e87-117">OSD File Elements</span></span>](osd-file-elements.md)

 

 





