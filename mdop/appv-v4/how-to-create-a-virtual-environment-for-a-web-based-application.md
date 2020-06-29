---
title: 如何为基于 Web 的应用程序创建虚拟环境
description: 如何为基于 Web 的应用程序创建虚拟环境
author: dansimp
ms.assetid: d2b16e9d-369c-4bd6-b2a0-16dd24c0e32c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a53bec6869b3af9666775600b181c57eec3be93
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801507"
---
# <span data-ttu-id="ac6b4-103">如何为基于 Web 的应用程序创建虚拟环境</span><span class="sxs-lookup"><span data-stu-id="ac6b4-103">How to Create a Virtual Environment for a Web-Based Application</span></span>


<span data-ttu-id="ac6b4-104">你可以为你希望隔离的 web 应用程序创建单独的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-104">You can create separate virtual environments for web applications you want to isolate.</span></span> <span data-ttu-id="ac6b4-105">如果基于 web 的应用程序需要具有相互冲突的配置的插件，创建单独的 web 环境将非常有用。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-105">Creating separate web environments is useful if the web-based applications require plug-ins of have configurations that conflict with each other.</span></span>

**<span data-ttu-id="ac6b4-106">为基于 Web 的应用程序创建虚拟环境</span><span class="sxs-lookup"><span data-stu-id="ac6b4-106">To create a virtual environment for a Web-based application</span></span>**

1.  <span data-ttu-id="ac6b4-107">打开序列化向导。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-107">Open the sequencing wizard.</span></span> <span data-ttu-id="ac6b4-108">有关对应用程序进行排序的详细信息，请参阅[如何对新应用程序进行](how-to-sequence-a-new-application.md)排序。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-108">For more information about sequencing an application see [How to Sequence a New Application](how-to-sequence-a-new-application.md).</span></span>

2.  <span data-ttu-id="ac6b4-109">在 "**监视器安装**" 页面上，若要开始监视应用程序的安装，请单击 "**开始监视**"。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-109">On the **Monitor Installation** page, to start monitoring the installation of the application, click **Begin Monitoring**.</span></span> <span data-ttu-id="ac6b4-110">打开 web 浏览器并导航到与该应用程序关联的安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-110">Open a web browser and navigate to the installer file associated with the application.</span></span> <span data-ttu-id="ac6b4-111">安装应用程序，并执行任何所需的安装后配置任务。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-111">Install the application, and perform any required post installation configuration tasks.</span></span>

3.  <span data-ttu-id="ac6b4-112">若要确保应用程序启动，请打开该应用程序三次。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-112">To ensure the applications starts, open the application three times.</span></span>

4.  <span data-ttu-id="ac6b4-113">安装和配置需要驻留在同一虚拟环境中的任何其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-113">Install and configure any additional applications that need to reside in the same virtual environment.</span></span>

5.  <span data-ttu-id="ac6b4-114">完成排序向导的其余部分。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-114">Complete the remainder of the Sequencing Wizard.</span></span>

6.  <span data-ttu-id="ac6b4-115">若要保存应用程序，请选择 "**文件**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ac6b4-115">To save the application, select **File**, and click **Save**.</span></span>

## <span data-ttu-id="ac6b4-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="ac6b4-116">Related topics</span></span>


[<span data-ttu-id="ac6b4-117">Application Virtualization Sequencer 的任务</span><span class="sxs-lookup"><span data-stu-id="ac6b4-117">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





