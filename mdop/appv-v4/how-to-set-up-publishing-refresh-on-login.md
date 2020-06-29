---
title: 如何设置登录时发布刷新
description: 如何设置登录时发布刷新
author: dansimp
ms.assetid: 196448db-7645-4fd5-a854-ef6405b15db4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd131ab5acbb8224e60077dfcc4272d4aa132b5e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801064"
---
# <span data-ttu-id="da4fe-103">如何设置登录时发布刷新</span><span class="sxs-lookup"><span data-stu-id="da4fe-103">How to Set Up Publishing Refresh on Login</span></span>


<span data-ttu-id="da4fe-104">你可以使用以下过程配置应用程序虚拟化（app-v）客户端，以便在你每次登录计算机时刷新服务器中的发布信息。</span><span class="sxs-lookup"><span data-stu-id="da4fe-104">You can use the following procedure to configure the Application Virtualization (App-V) Client to refresh the publishing information from the server each time you log in to the computer.</span></span> <span data-ttu-id="da4fe-105">在配置客户端后，刷新操作为 "自动"。</span><span class="sxs-lookup"><span data-stu-id="da4fe-105">After the client is configured, the refresh operation is automatic.</span></span>

**<span data-ttu-id="da4fe-106">刷新登录时的发布信息</span><span class="sxs-lookup"><span data-stu-id="da4fe-106">To refresh the publishing information on login</span></span>**

1.  <span data-ttu-id="da4fe-107">单击 "**范围**" 窗格中的 "**发布服务器**"。</span><span class="sxs-lookup"><span data-stu-id="da4fe-107">Click **Publishing Servers** in the **Scope** pane.</span></span>

2.  <span data-ttu-id="da4fe-108">在 "**结果**" 窗格中，右键单击所需服务器，然后从弹出菜单中选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="da4fe-108">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up-menu.</span></span>

3.  <span data-ttu-id="da4fe-109">在 "**属性**" 对话框中的 "**刷新**" 选项卡上，选中 "**在用户登录时刷新配置服务器**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="da4fe-109">In the **Properties** dialog box, on the **Refresh** tab, select the **Refresh configuration server on user login** check box.</span></span>

4.  <span data-ttu-id="da4fe-110">单击 "**应用**" 以更改配置。</span><span class="sxs-lookup"><span data-stu-id="da4fe-110">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="da4fe-111">完成设置配置后，单击 **"确定"** 退出对话框并返回到应用程序虚拟化管理控制台。</span><span class="sxs-lookup"><span data-stu-id="da4fe-111">When you finish configuring the settings, click **OK** to exit the dialog box and return to the Application Virtualization Management Console.</span></span>

    <span data-ttu-id="da4fe-112">每当您登录到系统时，都将刷新发布信息。</span><span class="sxs-lookup"><span data-stu-id="da4fe-112">The publishing information will now be refreshed each time you log in to the system.</span></span>

## <span data-ttu-id="da4fe-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="da4fe-113">Related topics</span></span>


[<span data-ttu-id="da4fe-114">如何在 Application Virtualization Client Management Console 中配置客户端</span><span class="sxs-lookup"><span data-stu-id="da4fe-114">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





