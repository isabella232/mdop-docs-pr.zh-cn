---
title: 如何设置定期发布刷新
description: 如何设置定期发布刷新
author: dansimp
ms.assetid: c358c765-cb88-4881-b4e7-0a2e87304870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5bbea1c661d6cb5a78f0bb9de29538e0222cda6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801063"
---
# <span data-ttu-id="996a1-103">如何设置定期发布刷新</span><span class="sxs-lookup"><span data-stu-id="996a1-103">How to Set Up Periodic Publishing Refresh</span></span>


<span data-ttu-id="996a1-104">你可以使用以下过程将客户端配置为定期刷新 App-v 服务器中的发布信息。</span><span class="sxs-lookup"><span data-stu-id="996a1-104">You can use the following procedure to configure the client to periodically refresh the publishing information from the App-V servers.</span></span> <span data-ttu-id="996a1-105">在配置客户端后，刷新操作为 "自动"。</span><span class="sxs-lookup"><span data-stu-id="996a1-105">After the client is configured, the refresh operation is automatic.</span></span> <span data-ttu-id="996a1-106">这些设置配置客户端的默认设置，以便此计算机上的所有用户都能看到相同的设置。</span><span class="sxs-lookup"><span data-stu-id="996a1-106">These settings configure the default settings for the client so that all users on this computer will see the same settings.</span></span>

<span data-ttu-id="996a1-107">**注意** 执行此过程后，在登录后首次刷新后，将根据新设置刷新发布信息。</span><span class="sxs-lookup"><span data-stu-id="996a1-107">**Note** After you have performed this procedure, the publishing information will be refreshed according to the new settings after the first refresh at login.</span></span> <span data-ttu-id="996a1-108">第一次刷新发生时，服务器可能会用不同的设置替代计算机设置，具体取决于其配置方式。</span><span class="sxs-lookup"><span data-stu-id="996a1-108">When this first refresh occurs, the server might override the computer settings with different settings, depending on how it is configured.</span></span> <span data-ttu-id="996a1-109">"**属性**" 对话框中的 "**刷新**" 选项卡显示本地配置的客户端计算机设置和可能已由发布服务器为用户配置的任何设置。</span><span class="sxs-lookup"><span data-stu-id="996a1-109">The **Refresh** tab in the **Properties** dialog box shows the locally configured client computer settings and any settings that might have been configured for the user by the publishing server.</span></span>

 

**<span data-ttu-id="996a1-110">定期刷新应用程序虚拟化服务器中的发布信息</span><span class="sxs-lookup"><span data-stu-id="996a1-110">To periodically refresh the publishing information from the Application Virtualization Servers</span></span>**

1.  <span data-ttu-id="996a1-111">单击 "**范围**" 窗格中的 "**发布服务器**"。</span><span class="sxs-lookup"><span data-stu-id="996a1-111">Click **Publishing Servers** in the **Scope** pane.</span></span>

2.  <span data-ttu-id="996a1-112">在 "**结果**" 窗格中，右键单击所需服务器，然后从弹出菜单中选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="996a1-112">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up-menu.</span></span>

3.  <span data-ttu-id="996a1-113">在 "**属性**" 对话框中的 "**刷新**" 选项卡上，选中 "**刷新配置间隔**" 复选框，然后输入一个表示字段中的频率的数字。</span><span class="sxs-lookup"><span data-stu-id="996a1-113">In the **Properties** dialog box, on the **Refresh** tab, select the **Refresh configuration every** check box and enter a number that represents the frequency in the field.</span></span> <span data-ttu-id="996a1-114">然后从下拉菜单中选择 "**分钟**"、"**小时**"、"**天**"。</span><span class="sxs-lookup"><span data-stu-id="996a1-114">Then select **Minutes**, **Hours**, **Days** from the drop-down menu.</span></span>

    <span data-ttu-id="996a1-115">**注意** 此设置将使客户在每次已配置的时间段内刷新发布信息。</span><span class="sxs-lookup"><span data-stu-id="996a1-115">**Note** This setting will cause the client to refresh publishing information every time the configured period elapses.</span></span> <span data-ttu-id="996a1-116">如果在执行刷新时用户未登录，则当用户下一次登录时，将发生刷新。</span><span class="sxs-lookup"><span data-stu-id="996a1-116">If the user is not logged in when it's time to do a refresh, the refresh will take place when the user next logs in.</span></span> <span data-ttu-id="996a1-117">随后将为下一期间再次启动计时器。</span><span class="sxs-lookup"><span data-stu-id="996a1-117">The timer is then started again for the next period.</span></span>

     

4.  <span data-ttu-id="996a1-118">单击 "**应用**" 以更改配置。</span><span class="sxs-lookup"><span data-stu-id="996a1-118">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="996a1-119">完成服务器配置后，单击 **"确定"** 退出对话框并返回到 Application Virtualization 客户端管理控制台。</span><span class="sxs-lookup"><span data-stu-id="996a1-119">When you finish configuring the server, click **OK** to exit the dialog box and return to the Application Virtualization Client Management Console.</span></span>

## <span data-ttu-id="996a1-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="996a1-120">Related topics</span></span>


[<span data-ttu-id="996a1-121">如何在 Application Virtualization Client Management Console 中配置客户端</span><span class="sxs-lookup"><span data-stu-id="996a1-121">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





