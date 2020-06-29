---
title: 如何为 App-V Management Server 配置 Windows Server 2008
description: 如何为 App-V Management Server 配置 Windows Server 2008
author: dansimp
ms.assetid: 38b4016f-de82-4209-9159-387d20ddee25
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d1cd7e84ffc0036c98e70a9a0ee1fd3a4ade790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801531"
---
# <span data-ttu-id="f02f1-103">如何为 App-V Management Server 配置 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="f02f1-103">How to Configure Windows Server 2008 for App-V Management Servers</span></span>


<span data-ttu-id="f02f1-104">在其上安装 Microsoft Application Virtualization （App-v）管理 Web 服务的 Windows Server 2008 服务器上需要将 Internet Information Services （IIS）作为角色安装在服务器上。</span><span class="sxs-lookup"><span data-stu-id="f02f1-104">The Windows Server 2008 server on which you install the Microsoft Application Virtualization (App-V) Management Web Service requires Internet Information Services (IIS) to be installed as a role on the server.</span></span> <span data-ttu-id="f02f1-105">使用以下过程配置 Windows Server 2008 以支持应用 Vserver 安装。</span><span class="sxs-lookup"><span data-stu-id="f02f1-105">Use the following procedure to configure Windows Server 2008 to support App-Vserver installation.</span></span>

**<span data-ttu-id="f02f1-106">在 Windows Server2008 计算机上安装 IIS</span><span class="sxs-lookup"><span data-stu-id="f02f1-106">To install IIS on a Windows Server2008 computer</span></span>**

1.  <span data-ttu-id="f02f1-107">在 Windows Server2008 计算机上，单击 "**开始**"，单击 "**所有程序**"，单击 "**管理工具**"，然后单击 "**服务器管理器**" 以启动服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="f02f1-107">On the Windows Server2008 computer, click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Server Manager** to start Server Manager.</span></span> <span data-ttu-id="f02f1-108">在服务器管理器中，右键单击 "**角色**" 节点，然后单击 "**添加角色**" 以启动 "**添加角色向导**"。</span><span class="sxs-lookup"><span data-stu-id="f02f1-108">In Server Manager, right-click the **Roles** node, and click **Add Roles** to start the **Add Roles Wizard**.</span></span>

2.  <span data-ttu-id="f02f1-109">在 "**添加角色" 向导**的 "**选择服务器角色**" 页面上，选择 " **Web 服务器（IIS）**"。</span><span class="sxs-lookup"><span data-stu-id="f02f1-109">In the **Add Roles Wizard**, on the **Select Server Roles** page, select **Web Server (IIS)**.</span></span> <span data-ttu-id="f02f1-110">出现提示时，单击 "**添加所需功能**" 以添加相关功能。</span><span class="sxs-lookup"><span data-stu-id="f02f1-110">When prompted, click **Add Required Features** to add the dependent features.</span></span>

3.  <span data-ttu-id="f02f1-111">在 "**选择服务器角色**" 页面上，单击 "**下一步**"，然后再次单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f02f1-111">On the **Select Server Roles** page, Click **Next**, and then click **Next** again.</span></span>

4.  <span data-ttu-id="f02f1-112">在 "**添加角色" 向导**的 "**选择角色服务**" 页面上：</span><span class="sxs-lookup"><span data-stu-id="f02f1-112">In the **Add Roles Wizard**, on the **Select Role Services** page:</span></span>

    1.  <span data-ttu-id="f02f1-113">在 "**应用程序开发**" 下，选择 " **ASP.NET** "，然后在出现提示时单击 "**添加所需的角色服务**" 以添加从属角色服务和功能。</span><span class="sxs-lookup"><span data-stu-id="f02f1-113">Under **Application Development**, select **ASP.NET** and, when prompted, click **Add Required Role Services** to add the dependent roles services and features.</span></span>

    2.  <span data-ttu-id="f02f1-114">在 "**安全**" 下，选择 " **Windows 身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="f02f1-114">Under **Security**, select **Windows Authentication**.</span></span>

    3.  <span data-ttu-id="f02f1-115">在 "**管理工具**" 节点中，选择 " **IIS 管理脚本和工具**"。</span><span class="sxs-lookup"><span data-stu-id="f02f1-115">In the **Management Tools** node, select **IIS Management Scripts and Tools**.</span></span> <span data-ttu-id="f02f1-116">在 " **IIS6 管理兼容性**" 下，确保已选中**IIS6 配置数据库兼容性**和**IIS6 WMI 兼容性**，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f02f1-116">Under **IIS6 Management Compatibility**, ensure that both **IIS6 Metabase Compatibility** and **IIS6 WMI Compatibility** are selected, and then click **Next**.</span></span>

5.  <span data-ttu-id="f02f1-117">在 "**确认安装选择**" 页面上，单击 "**安装**"，然后完成向导的其余部分。</span><span class="sxs-lookup"><span data-stu-id="f02f1-117">On the **Confirm Installation Selections** page, click **Install**, and then complete the rest of the wizard.</span></span>

6.  <span data-ttu-id="f02f1-118">单击 "**关闭**" 以退出 "**添加角色向导**"，然后关闭 "服务器管理器"。</span><span class="sxs-lookup"><span data-stu-id="f02f1-118">Click **Close** to exit the **Add Roles Wizard**, and then close Server Manager.</span></span>

## <span data-ttu-id="f02f1-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="f02f1-119">Related topics</span></span>


[<span data-ttu-id="f02f1-120">Application Virtualization 部署要求</span><span class="sxs-lookup"><span data-stu-id="f02f1-120">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

[<span data-ttu-id="f02f1-121">Application Virtualization 部署和升级清单</span><span class="sxs-lookup"><span data-stu-id="f02f1-121">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





