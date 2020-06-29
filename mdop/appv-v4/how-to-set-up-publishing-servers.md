---
title: 如何设置发布服务器
description: 如何设置发布服务器
author: dansimp
ms.assetid: 2111f079-c202-4c49-b2a6-f4237068b2dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f060d862fd1449f5240ad495b53a1fa4e97697f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801052"
---
# <span data-ttu-id="4b2f7-103">如何设置发布服务器</span><span class="sxs-lookup"><span data-stu-id="4b2f7-103">How to Set Up Publishing Servers</span></span>


<span data-ttu-id="4b2f7-104">你可以使用以下过程直接从客户端管理控制台添加和配置应用程序虚拟化服务器。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-104">You can use the following procedures to add and configure Application Virtualization Servers directly from the Client Management Console.</span></span>

**<span data-ttu-id="4b2f7-105">添加应用程序发布服务器</span><span class="sxs-lookup"><span data-stu-id="4b2f7-105">To add an application publishing server</span></span>**

1.  <span data-ttu-id="4b2f7-106">在 "**结果**" 窗格中，右键单击并从弹出菜单中选择 "**新建服务器**" 以启动 "新建应用程序虚拟服务器" 向导，或者右键单击 "**发布服务器**" 节点，然后从弹出菜单中选择 "**新建服务器**"。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-106">In the **Results** pane, right-click and select **New Server** from the pop-up-menu to start the New Application Virtualization Server Wizard, or alternatively, right-click the **Publishing Server** node and select **New Server** from the pop-up-menu.</span></span>

2.  <span data-ttu-id="4b2f7-107">在向导的第一页上，在 "**显示名称**" 字段中输入服务器的名称，然后从 "**类型**" 下拉列表中选择服务器类型。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-107">On page one of the wizard, enter the name of the server in the **Display Name** field and select the server type from the **Type** drop-down list.</span></span> <span data-ttu-id="4b2f7-108">你可以从服务器类型的下拉列表中选择 "**应用程序虚拟化服务器**"、"**增强的安全应用程序虚拟化服务器**"、"**标准 HTTP 服务器**" 或 "**增强的安全 HTTP 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-108">You can choose **Application Virtualization Server**, **Enhanced Security Application Virtualization Server**, **Standard HTTP Server**, or **Enhanced Security HTTP Server** from the drop-down list of server types.</span></span>

3.  <span data-ttu-id="4b2f7-109">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-109">Click **Next**.</span></span>

4.  <span data-ttu-id="4b2f7-110">在向导的第二页上，在 "**主机名**" 和 "**端口**" 字段中键入相应信息。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-110">On page two of the wizard, type the appropriate information into the **Host Name** and **Port** fields.</span></span> <span data-ttu-id="4b2f7-111">应用程序虚拟化服务器无法编辑 "**路径**" 字段。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-111">The **Path** field is not editable for Application Virtualization Servers.</span></span> <span data-ttu-id="4b2f7-112">必须输入标准 HTTP 服务器或增强的安全 HTTP 服务器的路径。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-112">You must enter a path for Standard HTTP Server or Enhanced Security HTTP Server.</span></span>

5.  <span data-ttu-id="4b2f7-113">单击 "**完成**" 以添加服务器。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-113">Click **Finish** to add the server.</span></span>

**<span data-ttu-id="4b2f7-114">设置应用程序发布服务器</span><span class="sxs-lookup"><span data-stu-id="4b2f7-114">To set up an application publishing server</span></span>**

1.  <span data-ttu-id="4b2f7-115">在 "**结果**" 窗格中，右键单击所需服务器，然后从弹出菜单中选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-115">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="4b2f7-116">单击 "**常规**" 选项卡，您可以在其中更改服务器名称，从服务器类型的下拉列表中选择一种类型，然后指定主机名和端口。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-116">Click the **General** tab, where you can change the server name, select a type from the drop-down list of server types, and specify the host name and port.</span></span> <span data-ttu-id="4b2f7-117">当服务器类型是标准 HTTP 服务器或增强的安全 HTTP 服务器时，**路径**字段也是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-117">When the server type is Standard HTTP Server or Enhanced Security HTTP Server, the **Path** field is also editable.</span></span>

3.  <span data-ttu-id="4b2f7-118">单击 "**刷新**" 选项卡，默认情况下，"**在用户登录时刷新发布**" 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-118">Click the **Refresh** tab, where the **Refresh publishing on user login** check box is selected by default.</span></span> <span data-ttu-id="4b2f7-119">若要更改刷新率，请选中 "**刷新发布时间间隔**" 复选框，然后输入一个代表字段中的频率的数字。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-119">To change the refresh rate, select the **Refresh publishing every** check box and enter a number that represents the frequency in the field.</span></span> <span data-ttu-id="4b2f7-120">然后从下拉菜单中选择 "**分钟**"、"**小时**"、"**天**"。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-120">Then select **Minutes**, **Hours**, **Days** from the drop-down menu.</span></span> <span data-ttu-id="4b2f7-121">（您可以输入的最短时间为30分钟。）</span><span class="sxs-lookup"><span data-stu-id="4b2f7-121">(The minimum amount of time you can enter is 30 minutes.)</span></span>

4.  <span data-ttu-id="4b2f7-122">单击 "**应用**" 以更改配置。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-122">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="4b2f7-123">完成发布后，单击 **"确定"** 退出对话框并返回 "客户端管理" 控制台。</span><span class="sxs-lookup"><span data-stu-id="4b2f7-123">When you are finished publishing, click **OK** to exit the dialog box and return to the Client Management Console.</span></span>

## <span data-ttu-id="4b2f7-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="4b2f7-124">Related topics</span></span>


[<span data-ttu-id="4b2f7-125">如何禁用或修改断开连接操作模式设置</span><span class="sxs-lookup"><span data-stu-id="4b2f7-125">How to Disable or Modify Disconnected Operation Mode Settings</span></span>](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





