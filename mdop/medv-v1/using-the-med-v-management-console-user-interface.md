---
title: 使用 MED-V 管理控制台用户界面
description: 使用 MED-V 管理控制台用户界面
author: dansimp
ms.assetid: f42714d7-6f0c-4995-ab31-d4ef0845a22c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22fc98c3edbea48847e1a00369bea21a470e66b7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803850"
---
# <span data-ttu-id="423e0-103">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="423e0-103">Using the MED-V Management Console User Interface</span></span>


<span data-ttu-id="423e0-104">控制台用户界面分为以下几个部分：</span><span class="sxs-lookup"><span data-stu-id="423e0-104">The console user interface is divided into the following sections:</span></span>

-   <span data-ttu-id="423e0-105">以下**med-v 管理按钮**，对应于三个模块：</span><span class="sxs-lookup"><span data-stu-id="423e0-105">The following **MED-V management buttons**, which correspond to the three modules:</span></span>

    -   <span data-ttu-id="423e0-106">**策略**-**策略**模块用于定义 med-v 工作区及其相关的设置和权限。</span><span class="sxs-lookup"><span data-stu-id="423e0-106">**Policy**—The **Policy** module is used to define the MED-V workspaces and their related settings and permissions.</span></span>

    -   <span data-ttu-id="423e0-107">**图像**-**图像**模块用于管理 med-v 工作区图像。</span><span class="sxs-lookup"><span data-stu-id="423e0-107">**Images**—The **Images** module is used to manage MED-V workspace images.</span></span>

    -   <span data-ttu-id="423e0-108">**报表**-**报表**模块用于生成和查看 med-v 工作区报表。</span><span class="sxs-lookup"><span data-stu-id="423e0-108">**Reports**—The **Reports** module is used for generating and viewing MED-V workspace reports.</span></span>

-   <span data-ttu-id="423e0-109">**工具栏**显示与所选按钮相关的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="423e0-109">The **toolbar** displays shortcuts relevant to the button selected.</span></span>

-   <span data-ttu-id="423e0-110">"**显示" 窗格**将显示与所选按钮对应的模块。</span><span class="sxs-lookup"><span data-stu-id="423e0-110">The **display pane** displays a module corresponding to the button that is selected.</span></span>

![](images/medv-ui-console-general.gif)

## <span data-ttu-id="423e0-111">如何登录到 MED-V 管理控制台</span><span class="sxs-lookup"><span data-stu-id="423e0-111">How to Log In to the MED-V Management Console</span></span>


**<span data-ttu-id="423e0-112">打开 MED-V 管理控制台</span><span class="sxs-lookup"><span data-stu-id="423e0-112">To open the MED-V management console</span></span>**

-   <span data-ttu-id="423e0-113">在 Windows "**开始**" 菜单上，选择 "**所有程序" &gt; med-v &gt; med-v 管理**，或在桌面上双击 "med-v 管理" 图标。</span><span class="sxs-lookup"><span data-stu-id="423e0-113">On the Windows **Start** menu, select **All Programs &gt; MED-V &gt; MED-V Management**, or on the desktop, double-click the MED-V Management icon.</span></span>

    <span data-ttu-id="423e0-114">将显示 " **Med-v 管理登录**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="423e0-114">The **MED-V Management Login** window appears.</span></span>

<span data-ttu-id="423e0-115">**注意** 出于安全考虑，登录到 MED-V 管理控制台的第一个用户将成为该计算机上唯一允许访问管理控制台的用户。</span><span class="sxs-lookup"><span data-stu-id="423e0-115">**Note** For security reasons, the first user to log in to the MED-V management console will become the only user on that computer allowed to access the management console.</span></span>

 

**<span data-ttu-id="423e0-116">登录</span><span class="sxs-lookup"><span data-stu-id="423e0-116">To log in</span></span>**

1.  <span data-ttu-id="423e0-117">按以下格式键入您的域用户凭据：</span><span class="sxs-lookup"><span data-stu-id="423e0-117">Type in your domain user credentials in the following format:</span></span>

    <span data-ttu-id="423e0-118">"domain \ _name \\user\ _name"，"密码"</span><span class="sxs-lookup"><span data-stu-id="423e0-118">"domain\_name\\user\_name", "password"</span></span>

    <span data-ttu-id="423e0-119">**注意** 配置服务器时，将定义具有完全访问权限的用户和具有只读访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="423e0-119">**Note** When configuring the server, users with full access as well as users with read-only access are defined.</span></span> <span data-ttu-id="423e0-120">所有用户都必须是域用户。</span><span class="sxs-lookup"><span data-stu-id="423e0-120">All users must be domain users.</span></span> <span data-ttu-id="423e0-121">将域用户名和密码用于 MED-V 管理登录。</span><span class="sxs-lookup"><span data-stu-id="423e0-121">The domain user name and password is used for MED-V management login.</span></span>

     

2.  <span data-ttu-id="423e0-122">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="423e0-122">Click **OK**.</span></span>

    <span data-ttu-id="423e0-123">将显示 " **Med-v 管理**" 控制台。</span><span class="sxs-lookup"><span data-stu-id="423e0-123">The **MED-V Management** console appears.</span></span>

## <span data-ttu-id="423e0-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="423e0-124">Related topics</span></span>


[<span data-ttu-id="423e0-125">如何安装 MED-V 客户端和 MED-V 管理控制台</span><span class="sxs-lookup"><span data-stu-id="423e0-125">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

 

 





