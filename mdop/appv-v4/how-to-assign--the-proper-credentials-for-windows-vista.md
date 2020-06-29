---
title: 如何为 Windows Vista 分配正确的凭据
description: 如何为 Windows Vista 分配正确的凭据
author: dansimp
ms.assetid: cc11d2af-a350-4d16-ba7b-f9c1d89e14b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 111dafea505133f123cf8531a2891a452e725ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802954"
---
# <span data-ttu-id="af8fb-103">如何为 Windows Vista 分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="af8fb-103">How to Assign the Proper Credentials for Windows Vista</span></span>


<span data-ttu-id="af8fb-104">使用以下过程为正确的 WindowsVista 凭据配置 App-v 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="af8fb-104">Use the following procedure to configure the App-V Desktop Client for proper WindowsVista credentials.</span></span>

<span data-ttu-id="af8fb-105">**注意** 必须在每个未加入域的计算机上完成此过程。</span><span class="sxs-lookup"><span data-stu-id="af8fb-105">**Note** This procedure must be completed on each non-domain joined computer.</span></span> <span data-ttu-id="af8fb-106">根据你的环境中未加入域的计算机的数量，这可能是一项单调乏味的操作。</span><span class="sxs-lookup"><span data-stu-id="af8fb-106">Depending on the number of non-domain joined computers in your environment, this could be a very tedious operation.</span></span> <span data-ttu-id="af8fb-107">你可以使用 "凭据管理器" 的脚本和命令行界面帮助管理员自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="af8fb-107">You can use scripts and the command-line interface for Credential Manager to help administrators automate this process.</span></span>

 

**<span data-ttu-id="af8fb-108">为运行 Windows Vista 的 App-v 客户端分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="af8fb-108">To assign the proper credentials for App-V clients running Windows Vista</span></span>**

1.  <span data-ttu-id="af8fb-109">在运行 Windows Vista 的 App-v 桌面客户端上使用管理员权限，打开 "**用户帐户**" 控制面板（"经典控制面板"）。</span><span class="sxs-lookup"><span data-stu-id="af8fb-109">With administrator privileges on the App-V Desktop Client running Windows Vista, open the **User Accounts** control panel (Classic Control Panel).</span></span>

2.  <span data-ttu-id="af8fb-110">从 "左侧任务" 窗格中的 "**用户帐户**" 中选择 "**管理您的网络密码**"。</span><span class="sxs-lookup"><span data-stu-id="af8fb-110">Select **Manage your network passwords** from **User Accounts** in the left tasks pane.</span></span>

3.  <span data-ttu-id="af8fb-111">在 "存储的**用户名和密码**" 屏幕上选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="af8fb-111">Select **Add** on the **Stored User Names and Passwords** screen.</span></span>

4.  <span data-ttu-id="af8fb-112">在 "**存储的凭据属性**" 屏幕上，提供 app-v 基础结构的信息：</span><span class="sxs-lookup"><span data-stu-id="af8fb-112">On the **Stored Credential Properties** screen, provide the information for the App-V infrastructure:</span></span>

    1.  <span data-ttu-id="af8fb-113">**登录到：** 发布服务器的外部名称。</span><span class="sxs-lookup"><span data-stu-id="af8fb-113">**Log on to:** External name of the publishing server.</span></span>

    2.  <span data-ttu-id="af8fb-114">**用户名：** 表单 Domain\\Username. 中外部用户的用户名</span><span class="sxs-lookup"><span data-stu-id="af8fb-114">**User name:** User name for the external user in the form Domain\\Username.</span></span>

    3.  <span data-ttu-id="af8fb-115">**密码：** 在 "**用户名**" 字段中输入的用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="af8fb-115">**Password:** Password for the user account entered in the **User name** field.</span></span>

    4.  <span data-ttu-id="af8fb-116">选中 "保留**凭据类型**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="af8fb-116">Leave **Credential Type** selected, and click **OK**.</span></span>

5.  <span data-ttu-id="af8fb-117">单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="af8fb-117">Click **Close**.</span></span> <span data-ttu-id="af8fb-118">凭据存储在凭据存储中，以便对 app-v 基础结构进行正确身份验证。</span><span class="sxs-lookup"><span data-stu-id="af8fb-118">The credentials are stored in the credential store for proper authentication to the App-V infrastructure.</span></span>

## <span data-ttu-id="af8fb-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="af8fb-119">Related topics</span></span>


[<span data-ttu-id="af8fb-120">加入域和未加入域的客户端</span><span class="sxs-lookup"><span data-stu-id="af8fb-120">Domain-Joined and Non-Domain-Joined Clients</span></span>](domain-joined-and-non-domain-joined-clients.md)

[<span data-ttu-id="af8fb-121">如何为 Windows XP 分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="af8fb-121">How to Assign the Proper Credentials for Windows XP</span></span>](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





