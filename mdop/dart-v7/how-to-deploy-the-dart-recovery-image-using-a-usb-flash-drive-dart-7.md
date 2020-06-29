---
title: 如何使用 U 盘部署 DaRT 恢复映像
description: 如何使用 U 盘部署 DaRT 恢复映像
author: dansimp
ms.assetid: 5b7aa843-731e-47e7-b5f9-48d08da732d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1228c9cb5f870162f285d726d48721dde1185107
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803414"
---
# <span data-ttu-id="66a2c-103">如何使用 U 盘部署 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="66a2c-103">How to Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>


<span data-ttu-id="66a2c-104">在完成运行**DaRT 恢复映像向导**后，您可以使用中的工具 <https://go.microsoft.com/fwlink/?LinkId=218888> 将 ISO 映像文件复制到 USB 闪存驱动器（UFD）。</span><span class="sxs-lookup"><span data-stu-id="66a2c-104">After you have finished running the **DaRT Recovery Image Wizard**, you can use the tool at <https://go.microsoft.com/fwlink/?LinkId=218888> to copy the ISO image file to a USB flash drive (UFD).</span></span>

<span data-ttu-id="66a2c-105">您也可以按照本部分中提供的步骤手动将 ISO 映像文件复制到 UFD。</span><span class="sxs-lookup"><span data-stu-id="66a2c-105">You can also manually copy the ISO image file to a UFD by following the steps provided in this section.</span></span>

**<span data-ttu-id="66a2c-106">将 DaRT 恢复映像保存到 USB 闪存驱动器</span><span class="sxs-lookup"><span data-stu-id="66a2c-106">To save the DaRT recovery image to a USB flash drive</span></span>**

1.  <span data-ttu-id="66a2c-107">格式化 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="66a2c-107">Format the USB flash drive.</span></span>

    1.  <span data-ttu-id="66a2c-108">在正在运行的有效操作系统或 WindowsPE 会话中，插入你的 UFD。</span><span class="sxs-lookup"><span data-stu-id="66a2c-108">From a running valid operating system or WindowsPE session, insert your UFD.</span></span>

    2.  <span data-ttu-id="66a2c-109">在具有管理员权限的命令提示符处，键入 " **DISKPART** "，然后键入 "**列出磁盘**"。</span><span class="sxs-lookup"><span data-stu-id="66a2c-109">At the command prompt with administrator permissions, type **DISKPART** and then type **LIST DISK**.</span></span>

        <span data-ttu-id="66a2c-110">命令提示符窗口显示 UFD 的磁盘号，例如**磁盘 1**。</span><span class="sxs-lookup"><span data-stu-id="66a2c-110">The Command Prompt window displays the disk number of your UFD, for example **DISK 1**.</span></span>

    3.  <span data-ttu-id="66a2c-111">在命令提示符处一次输入以下命令。</span><span class="sxs-lookup"><span data-stu-id="66a2c-111">Enter the following commands one at a time at the command prompt.</span></span>

        ``` syntax
        SELECT DISK 1
        CLEAN
        CREATE PARTITION PRIMARY
        SELECT PARTITION 1
        ACTIVE
        FORMAT FS=NTFS
        ASSIGN
        EXIT
        ```

        <span data-ttu-id="66a2c-112">**注意** 上面的代码示例假设 Disk1 是 UFD。</span><span class="sxs-lookup"><span data-stu-id="66a2c-112">**Note** The previous code example assumes Disk1 is the UFD.</span></span> <span data-ttu-id="66a2c-113">如果需要，请将磁盘1替换为您的磁盘号。</span><span class="sxs-lookup"><span data-stu-id="66a2c-113">If it is necessary, replace DISK 1 with your disk number.</span></span>

         

2.  <span data-ttu-id="66a2c-114">通过使用贵公司装载映像的首选方法，装载您在**DaRT 恢复映像向导**的 "**创建启动映像**" 对话框中创建的 ISO 图像文件。</span><span class="sxs-lookup"><span data-stu-id="66a2c-114">By using your company’s preferred method of mounting an image, mount the ISO image file that you created in the **Create Startup Image** dialog box of the **DaRT Recovery Image Wizard**.</span></span> <span data-ttu-id="66a2c-115">这要求你有一种可用于装载图像文件的方法。</span><span class="sxs-lookup"><span data-stu-id="66a2c-115">This requires that you have a method available to mount an image file.</span></span>

3.  <span data-ttu-id="66a2c-116">打开装载的 ISO 映像文件并将其所有内容复制到格式化的 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="66a2c-116">Open the mounted ISO image file and copy all its contents to the formatted USB flash drive.</span></span>

    <span data-ttu-id="66a2c-117">**注意** 如果刻录了恢复映像的 CD 或 DVD，则可以打开 CD 或 DVD 上的文件，并将内容复制到 UFD。</span><span class="sxs-lookup"><span data-stu-id="66a2c-117">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the contents to the UFD.</span></span> <span data-ttu-id="66a2c-118">这使你可以跳过装入映像的需要。</span><span class="sxs-lookup"><span data-stu-id="66a2c-118">This lets you skip the need to mount the image.</span></span>

     

## <span data-ttu-id="66a2c-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="66a2c-119">Related topics</span></span>


[<span data-ttu-id="66a2c-120">部署 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="66a2c-120">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





