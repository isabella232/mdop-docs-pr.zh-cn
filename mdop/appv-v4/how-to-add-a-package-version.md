---
title: 如何添加程序包版本
description: 如何添加程序包版本
author: dansimp
ms.assetid: dbb829c1-e5cb-4a2f-bc17-9a9bb50c671c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a60252e8b43af61ad548df30a93d8fbc9bae0cb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802961"
---
# <span data-ttu-id="ae358-103">如何添加程序包版本</span><span class="sxs-lookup"><span data-stu-id="ae358-103">How to Add a Package Version</span></span>


<span data-ttu-id="ae358-104">在应用程序虚拟化服务器管理控制台中，当你 resequence 程序包时，可以使用以下过程将新版本添加到服务器以进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="ae358-104">In the Application Virtualization Server Management Console, when you resequence a package, you can use the following procedure to add the new version to your servers for streaming.</span></span>

<span data-ttu-id="ae358-105">**注意** 使用新版本升级程序包时，可以保留现有版本或将其删除，仅保留最新版本。</span><span class="sxs-lookup"><span data-stu-id="ae358-105">**Note** When you upgrade a package with a new version, you can leave the existing version in place or delete it and leave only the newest one.</span></span> <span data-ttu-id="ae358-106">你可能希望保留旧版本以实现与旧版文档的兼容性，以便你可以在将新版本提供给所有用户之前对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="ae358-106">You might want to leave the old version in place for compatibility with legacy documents or so that you can test the new version before making it available to all users.</span></span>

 

**<span data-ttu-id="ae358-107">添加程序包版本</span><span class="sxs-lookup"><span data-stu-id="ae358-107">To add a package version</span></span>**

1.  <span data-ttu-id="ae358-108">将新的 SFT 文件复制到应用服务器的内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="ae358-108">Copy the new SFT file to the application server's content folder.</span></span> <span data-ttu-id="ae358-109">如果 resequencing 未将更改添加到打开的软件描述符（OSD）、图标（.ICO）或 Sequencer 项目（SPRJ）文件中，则无需复制这些更改。</span><span class="sxs-lookup"><span data-stu-id="ae358-109">If resequencing did not add changes to the Open Software Descriptor (OSD), icon (ICO), or Sequencer Project (SPRJ) files, you do not need to copy those.</span></span> <span data-ttu-id="ae358-110">如果您希望所有文件都显示相同的日期，则可以包含这些文件。</span><span class="sxs-lookup"><span data-stu-id="ae358-110">You can include those files if you want all the files to display the same date.</span></span>

2.  <span data-ttu-id="ae358-111">在应用程序虚拟化服务器管理控制台的左窗格中，展开 "**程序包**" 节点。</span><span class="sxs-lookup"><span data-stu-id="ae358-111">In left pane of the Application Virtualization Server Management Console, expand the **Packages** node.</span></span>

3.  <span data-ttu-id="ae358-112">右键单击要升级的程序包，然后选择 "**添加版本**"。</span><span class="sxs-lookup"><span data-stu-id="ae358-112">Right-click the package you want to upgrade, and choose **Add Version**.</span></span>

4.  <span data-ttu-id="ae358-113">在 "**添加程序包版本**" 对话框中，在 "**程序包文件的完整路径**" 字段中浏览或键入新应用程序文件的路径名称。</span><span class="sxs-lookup"><span data-stu-id="ae358-113">In the **Add Package Version** dialog box, browse for or type the path name for the new application file in the **Full path for package file** field.</span></span> <span data-ttu-id="ae358-114">这必须是一个 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="ae358-114">This must be an SFT file.</span></span>

5.  <span data-ttu-id="ae358-115">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ae358-115">Click **Next**.</span></span>

6.  <span data-ttu-id="ae358-116">"**摘要**" 对话框显示文件位置，并提示您将文件复制到该位置（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="ae358-116">The **Summary** dialog box shows the file location and prompts you to copy the file there if you have not already done so.</span></span> <span data-ttu-id="ae358-117">验证信息后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="ae358-117">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="ae358-118">新版本现已完成，准备好流。</span><span class="sxs-lookup"><span data-stu-id="ae358-118">The new version is now complete and ready to stream.</span></span>

## <span data-ttu-id="ae358-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="ae358-119">Related topics</span></span>


[<span data-ttu-id="ae358-120">如何删除程序包</span><span class="sxs-lookup"><span data-stu-id="ae358-120">How to Delete a Package</span></span>](how-to-delete-a-packageserver.md)

[<span data-ttu-id="ae358-121">如何在 Server Management Console 中管理程序包</span><span class="sxs-lookup"><span data-stu-id="ae358-121">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





