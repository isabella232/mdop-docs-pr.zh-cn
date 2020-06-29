---
title: App-V 5.0 SP3 发行说明
description: App-V 5.0 SP3 发行说明
author: dansimp
ms.assetid: bc4806e0-2aba-4c7b-9ecc-1b2cc54af1d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b6d5834e4d0c953365f955922403c1a7a2058b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798267"
---
# <span data-ttu-id="d33c3-103">App-V 5.0 SP3 发行说明</span><span class="sxs-lookup"><span data-stu-id="d33c3-103">Release Notes for App-V 5.0 SP3</span></span>


<span data-ttu-id="d33c3-104">以下是 Microsoft Application Virtualization （App-v） 5.0 SP3 中的已知问题。</span><span class="sxs-lookup"><span data-stu-id="d33c3-104">The following are known issues in Microsoft Application Virtualization (App-V) 5.0 SP3.</span></span>

## <span data-ttu-id="d33c3-105">在新的 App-v 5.0 SP3 服务器安装之后，无法删除服务器文件</span><span class="sxs-lookup"><span data-stu-id="d33c3-105">Server files fail to get deleted after a new App-V 5.0 SP3 Server installation</span></span>


<span data-ttu-id="d33c3-106">如果卸载 V 5.0 SP1 服务器，然后安装 app-v 5.0 SP3 服务器，安装将失败，并且安装了错误版本的管理服务器。</span><span class="sxs-lookup"><span data-stu-id="d33c3-106">If you uninstall the App-V 5.0 SP1 Server and then install the App-V 5.0 SP3 Server, the installation fails and the wrong version of the Management server is installed.</span></span> <span data-ttu-id="d33c3-107">将显示以下错误：</span><span class="sxs-lookup"><span data-stu-id="d33c3-107">The following errors are displayed:</span></span>

`[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {bee44f0f-05be-48e4-81dd-d34a83600b95}, type: Upgrade, scope: PerMachine, version: 5.0.1218.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.``[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {e1ca9d65-0ebf-4fd5-98e5-00d6453967a4}, type: Upgrade, scope: PerMachine, version: 5.0.1224.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.`

<span data-ttu-id="d33c3-108">出现此问题的原因是，卸载 app-v 5.0 SP1 时未删除服务器文件，因此 App-v 5.0 SP3 安装过程错误地执行升级，而不是全新安装。</span><span class="sxs-lookup"><span data-stu-id="d33c3-108">The issue occurs because the Server files are not being deleted when you uninstall App-V 5.0 SP1, so the App-V 5.0 SP3 installation process erroneously does an upgrade instead of a new installation.</span></span>

<span data-ttu-id="d33c3-109">**解决方法**：在开始安装 APP-V 5.0 SP3 之前删除以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="d33c3-109">**Workaround**: Delete the following registry key before you start installing App-V 5.0 SP3:</span></span>

`HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## <span data-ttu-id="d33c3-110">查询 AD DS 可能导致某些应用程序无法正常工作</span><span class="sxs-lookup"><span data-stu-id="d33c3-110">Querying AD DS can cause some applications to work incorrectly</span></span>


<span data-ttu-id="d33c3-111">通过查询更新的组成员身份的 Active Directory 域服务接收更新的程序包时，如果应用程序依赖于用户的访问令牌，则可能会导致某些应用程序无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="d33c3-111">When you receive updated packages by querying Active Directory Domain Services for updated group memberships, it can cause some applications to work incorrectly if the applications depend on the user’s access token.</span></span> <span data-ttu-id="d33c3-112">此外，频繁的组成员身份查询可能导致域控制器超载。</span><span class="sxs-lookup"><span data-stu-id="d33c3-112">In addition, frequent group membership queries can cause the domain controller to overload.</span></span> <span data-ttu-id="d33c3-113">有关用户访问令牌的详细信息，请参阅[访问令牌](https://msdn.microsoft.com/library/windows/desktop/aa374909.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d33c3-113">For more information about user access tokens, see [Access Tokens](https://msdn.microsoft.com/library/windows/desktop/aa374909.aspx).</span></span>

<span data-ttu-id="d33c3-114">**解决方法**：等待用户注销，然后重新登录，然后再查询已更新的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d33c3-114">**Workaround**: Wait until the user logs off and then logs back on before you query for updated group memberships.</span></span> <span data-ttu-id="d33c3-115">请勿使用[Microsoft Application Virtualization 5.0 Service Pack 1 的修补程序包 2](https://support.microsoft.com/kb/2897087)中介绍的注册表项来查询已更新的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d33c3-115">Do not use the registry key, described in [Hotfix Package 2 for Microsoft Application Virtualization 5.0 Service Pack 1](https://support.microsoft.com/kb/2897087), to query for updated group memberships.</span></span>






## <span data-ttu-id="d33c3-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="d33c3-116">Related topics</span></span>


[<span data-ttu-id="d33c3-117">关于 App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="d33c3-117">About App-V 5.0 SP3</span></span>](about-app-v-50-sp3.md)

 

 





