---
title: 如何为 App-V 配置 Windows Server 2008 防火墙
description: 如何为 App-V 配置 Windows Server 2008 防火墙
author: dansimp
ms.assetid: 57f4ed17-0651-4a3c-be1e-29d9520c6aeb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 19e4cda9ac3b908f68e4f69b9663033d8a21ae41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801528"
---
# <span data-ttu-id="95fc3-103">如何为 App-V 配置 Windows Server 2008 防火墙</span><span class="sxs-lookup"><span data-stu-id="95fc3-103">How to Configure Windows Server 2008 Firewall for App-V</span></span>


<span data-ttu-id="95fc3-104">随着 Windows Server2008 的推出，将防火墙和 IPsec 组件合并到一个服务中，并增强了此服务的功能。</span><span class="sxs-lookup"><span data-stu-id="95fc3-104">With the introduction of Windows Server2008, the firewall and IPsec components were merged into one service, and the capabilities of this service were enhanced.</span></span> <span data-ttu-id="95fc3-105">新的防火墙服务支持传入和传出状态检查。</span><span class="sxs-lookup"><span data-stu-id="95fc3-105">The new firewall service supports incoming and outgoing stateful inspection.</span></span> <span data-ttu-id="95fc3-106">此外，你可以通过组策略配置特定防火墙规则和 IPsec 策略。</span><span class="sxs-lookup"><span data-stu-id="95fc3-106">Also, you can configure specific firewall rules and IPsec policies through group policies.</span></span> <span data-ttu-id="95fc3-107">有关 Windows Server2008 中的 Windows 防火墙的其他信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151980> 。</span><span class="sxs-lookup"><span data-stu-id="95fc3-107">For additional information about the Windows firewall in Windows Server2008, see <https://go.microsoft.com/fwlink/?LinkId=151980>.</span></span>

<span data-ttu-id="95fc3-108">以下过程不包括通过 SMB 或 HTTP/HTTPS 为 .ICO 和 OSD 发布添加例外。</span><span class="sxs-lookup"><span data-stu-id="95fc3-108">The following procedure does not include adding an exception for ICO and OSD publishing through SMB or HTTP/HTTPS.</span></span> <span data-ttu-id="95fc3-109">这些例外会根据安装在 Windows Server 2008 防火墙上的网络配置文件和角色自动添加。</span><span class="sxs-lookup"><span data-stu-id="95fc3-109">Those exceptions are automatically added based on the network profile and roles installed on the Windows Server 2008 firewall.</span></span>

<span data-ttu-id="95fc3-110">**注意** 如果管理服务器配置为使用 RTSP，请重复此过程以将程序添加 `sghwsvr.exe` 为例外。</span><span class="sxs-lookup"><span data-stu-id="95fc3-110">**Note** If the Management Server is configured to use RTSP, repeat this procedure to add the `sghwsvr.exe` program as an exception.</span></span>

<span data-ttu-id="95fc3-111">对于 RTSPS 通信，app-v 流服务器需要程序异常 `sglwdsptr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="95fc3-111">The App-V Streaming Server requires the program exception `sglwdsptr.exe` for RTSPS communication.</span></span> <span data-ttu-id="95fc3-112">使用 RTSP 进行通信的 app-v 流式处理服务器还需要程序例外 `sglwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="95fc3-112">An App-V Streaming Server that uses RTSP for communication also requires a program exception for `sglwsvr.exe`.</span></span>

 

**<span data-ttu-id="95fc3-113">为 App-v 配置 Windows Server2008 防火墙</span><span class="sxs-lookup"><span data-stu-id="95fc3-113">To configure Windows Server2008 firewall for App-V</span></span>**

1.  <span data-ttu-id="95fc3-114">通过 "控制面板" 或在 "运行" 行上键入 **，打开具有高级安全**管理控制台的 Windows 防火墙 `wf.msc` 。</span><span class="sxs-lookup"><span data-stu-id="95fc3-114">Open the **Windows Firewall with Advanced Security** management console through the Control Panel or by typing `wf.msc` on the Run line.</span></span>

2.  <span data-ttu-id="95fc3-115">创建新的入站规则，然后选择 "**程序**"。</span><span class="sxs-lookup"><span data-stu-id="95fc3-115">Create a new inbound rule, and select **Program**.</span></span>

3.  <span data-ttu-id="95fc3-116">选择程序路径并浏览到 `sghwdsptr.exe` ，默认情况下位于的位置 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。</span><span class="sxs-lookup"><span data-stu-id="95fc3-116">Select the program path, and browse to `sghwdsptr.exe`, which is located by default at `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin`.</span></span>

4.  <span data-ttu-id="95fc3-117">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="95fc3-117">Click **Next**.</span></span>

5.  <span data-ttu-id="95fc3-118">在 "**操作**" 页面上，选择 "**允许连接**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="95fc3-118">On the **Action** page, select **Allow the connection**, and then click **Next**.</span></span>

6.  <span data-ttu-id="95fc3-119">选择相应的**配置文件**以应用于入站规则。</span><span class="sxs-lookup"><span data-stu-id="95fc3-119">Select the appropriate **Profiles** to apply to the inbound rule.</span></span>

7.  <span data-ttu-id="95fc3-120">提供规则的名称和说明，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="95fc3-120">Provide a name and description for the rule, and click **Finish**.</span></span>

## <span data-ttu-id="95fc3-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="95fc3-121">Related topics</span></span>


[<span data-ttu-id="95fc3-122">如何为 App-V 配置 Windows Server 2003 防火墙</span><span class="sxs-lookup"><span data-stu-id="95fc3-122">How to Configure Windows Server 2003 Firewall for App-V</span></span>](how-to-configure-windows-server-2003-firewall-for-app-v.md)

 

 





