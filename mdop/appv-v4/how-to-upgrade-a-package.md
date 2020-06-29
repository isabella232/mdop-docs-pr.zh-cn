---
title: 如何升级程序包
description: 如何升级程序包
author: dansimp
ms.assetid: 831c7556-6f6c-4b3a-aefb-26889094dc1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a9b3eca2c996337d79e551784818a421f495316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801043"
---
# <span data-ttu-id="96a53-103">如何升级程序包</span><span class="sxs-lookup"><span data-stu-id="96a53-103">How to Upgrade a Package</span></span>


<span data-ttu-id="96a53-104">自动升级的过程与在应用程序虚拟化服务器管理控制台中添加程序包版本的过程相同。</span><span class="sxs-lookup"><span data-stu-id="96a53-104">The process for an automatic upgrade is the same as for adding a package version in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="96a53-105">当你在现有程序包中 resequence 应用程序时，将执行自动升级。</span><span class="sxs-lookup"><span data-stu-id="96a53-105">An automatic upgrade is performed when you resequence the application in an existing package.</span></span> <span data-ttu-id="96a53-106">然后，你可以将此新版本添加到你的服务器以进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="96a53-106">Then you can add this new version to your servers for streaming.</span></span>

<span data-ttu-id="96a53-107">使用新版本升级程序包时，可以保留现有版本或将其删除，仅保留最新版本。</span><span class="sxs-lookup"><span data-stu-id="96a53-107">When you upgrade a package with a new version, you can leave the existing version in place or delete it and leave only the newest one.</span></span> <span data-ttu-id="96a53-108">你可能希望保留旧版本以实现与旧版文档的兼容性，以便你可以在将新版本提供给所有用户之前对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="96a53-108">You might want to leave the old version in place for compatibility with legacy documents or so that you can test the new version before making it available to all users.</span></span>

**<span data-ttu-id="96a53-109">自动升级程序包</span><span class="sxs-lookup"><span data-stu-id="96a53-109">To upgrade a package automatically</span></span>**

1.  <span data-ttu-id="96a53-110">将新的 SFT 文件复制到 Application Virtualization 服务器的内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="96a53-110">Copy the new SFT file to the Application Virtualization Server's content folder.</span></span>

    <span data-ttu-id="96a53-111">**注意** 如果 resequencing 未添加已更改开放软件描述符（OSD）、图标（.ICO）或 Sequencer 项目（SPRJ）文件的功能，则无需复制这些功能。</span><span class="sxs-lookup"><span data-stu-id="96a53-111">**Note** If resequencing did not add features that changed the Open Software Descriptor (OSD), icon (ICO), or Sequencer Project (SPRJ) files, you do not need to copy those.</span></span> <span data-ttu-id="96a53-112">如果您希望所有这些文件都显示相同的日期，则可以包含这些文件。</span><span class="sxs-lookup"><span data-stu-id="96a53-112">You can include these files if you want all these files to display the same date.</span></span>

     

2.  <span data-ttu-id="96a53-113">在应用程序虚拟化服务器管理控制台的左窗格中，展开 "**程序包**"。</span><span class="sxs-lookup"><span data-stu-id="96a53-113">In left pane of the Application Virtualization Server Management Console, expand **Packages**.</span></span>

3.  <span data-ttu-id="96a53-114">右键单击要升级的程序包，然后选择 "**添加版本**"。</span><span class="sxs-lookup"><span data-stu-id="96a53-114">Right-click the package you want to upgrade, and select **Add Version**.</span></span>

4.  <span data-ttu-id="96a53-115">在 "**添加包版本**" 对话框中，在 "文件" 字段的 "**完整路径**" 中，浏览或键入新应用程序版本的完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="96a53-115">In the **Add Package Version** dialog box, browse for or type the full path name for the new application version in the **Full Path for the file** field.</span></span> <span data-ttu-id="96a53-116">这必须是一个 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="96a53-116">This must be an SFT file.</span></span>

5.  <span data-ttu-id="96a53-117">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="96a53-117">Click **Next**.</span></span>

6.  <span data-ttu-id="96a53-118">"**摘要**" 对话框显示文件位置，并提示您将文件复制到该位置（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="96a53-118">The **Summary** dialog box shows the file location and prompts you to copy the file there if you have not already done so.</span></span> <span data-ttu-id="96a53-119">验证信息后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="96a53-119">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="96a53-120">新版本现已完成，准备好流。</span><span class="sxs-lookup"><span data-stu-id="96a53-120">The new version is now complete and ready to stream.</span></span>

## <span data-ttu-id="96a53-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="96a53-121">Related topics</span></span>


[<span data-ttu-id="96a53-122">如何在 Server Management Console 中管理程序包</span><span class="sxs-lookup"><span data-stu-id="96a53-122">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





