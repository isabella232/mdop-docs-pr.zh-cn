---
title: 如何为 Windows XP 分配正确的凭据
description: 如何为 Windows XP 分配正确的凭据
author: dansimp
ms.assetid: cddbd556-d8f9-4981-a947-6e8e3f552b70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81581b75a9b7d5ce35e1c50fd01e0b7bbd3f7ef5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802171"
---
# <span data-ttu-id="9152c-103">如何为 Windows XP 分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="9152c-103">How to Assign the Proper Credentials for Windows XP</span></span>


<span data-ttu-id="9152c-104">使用以下过程为正确的 WindowsXP 凭据配置 App-v 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="9152c-104">Use the following procedure to configure the App-V Desktop Client for proper WindowsXP credentials.</span></span>

<span data-ttu-id="9152c-105">**注意** 完成此过程后，非域加入的客户端可以在不加入域的情况下执行发布刷新。</span><span class="sxs-lookup"><span data-stu-id="9152c-105">**Note** After finishing this procedure, the non-domain joined client can perform a publishing refresh without being joined to a domain.</span></span>

 

**<span data-ttu-id="9152c-106">为运行 WindowsXP 的 App-v 客户端分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="9152c-106">To assign the proper credentials for App-V clients running WindowsXP</span></span>**

1.  <span data-ttu-id="9152c-107">在运行 WindowsXP 的 App-v 客户端上使用管理员权限，打开 "**用户帐户**" 控制面板（经典控制面板）。</span><span class="sxs-lookup"><span data-stu-id="9152c-107">With administrator privileges on the App-V Client running WindowsXP, open the **User Accounts** control panel (Classic Control Panel).</span></span>

2.  <span data-ttu-id="9152c-108">单击 "**高级" 选项卡**，然后选择 "**管理密码**"。</span><span class="sxs-lookup"><span data-stu-id="9152c-108">Click the **Advanced Tab**, and select **Manage Passwords**.</span></span>

3.  <span data-ttu-id="9152c-109">在 "**存储的用户名和密码**" 屏幕上，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9152c-109">On the **Stored User Names and Passwords** screen, click **Add**.</span></span>

4.  <span data-ttu-id="9152c-110">在 "**登录信息属性**" 屏幕上，利用 app-v 基础结构中的信息填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="9152c-110">On the **Logon Information Properties** screen, fill out the following fields with information from the App-V infrastructure:</span></span>

    1.  <span data-ttu-id="9152c-111">**服务器：** 发布服务器外部名称的名称。</span><span class="sxs-lookup"><span data-stu-id="9152c-111">**Server:** Name of publishing server external name.</span></span>

    2.  <span data-ttu-id="9152c-112">**用户名：** 表单 Domain\\username. 中外部用户的用户名</span><span class="sxs-lookup"><span data-stu-id="9152c-112">**User name:** User name for external user in the form Domain\\username.</span></span>

    3.  <span data-ttu-id="9152c-113">**密码：** 在 "**用户名**" 字段中输入的用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="9152c-113">**Password:** Password for the user account entered in the **User name** field.</span></span>

5.  <span data-ttu-id="9152c-114">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9152c-114">Click **OK**.</span></span> <span data-ttu-id="9152c-115">凭据将存储在客户端上。</span><span class="sxs-lookup"><span data-stu-id="9152c-115">The credentials will be stored on the client.</span></span>

## <span data-ttu-id="9152c-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="9152c-116">Related topics</span></span>


[<span data-ttu-id="9152c-117">加入域和未加入域的客户端</span><span class="sxs-lookup"><span data-stu-id="9152c-117">Domain-Joined and Non-Domain-Joined Clients</span></span>](domain-joined-and-non-domain-joined-clients.md)

[<span data-ttu-id="9152c-118">如何为 Windows Vista 分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="9152c-118">How to Assign the Proper Credentials for Windows Vista</span></span>](how-to-assign--the-proper-credentials-for-windows-vista.md)

 

 





