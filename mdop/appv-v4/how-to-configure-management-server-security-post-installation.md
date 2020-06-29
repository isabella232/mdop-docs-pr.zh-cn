---
title: 如何配置 Management Server 安装后的安全性
description: 如何配置 Management Server 安装后的安全性
author: dansimp
ms.assetid: 71979fa6-3d0b-4a8b-994e-cb728d013090
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 521e72ead78055a7d3261664ccb75d454c22e622
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801616"
---
# <span data-ttu-id="51c4e-103">如何配置 Management Server 安装后的安全性</span><span class="sxs-lookup"><span data-stu-id="51c4e-103">How to Configure Management Server Security Post-Installation</span></span>


<span data-ttu-id="51c4e-104">使用 App-v 管理控制台添加证书并配置 app-v 管理服务器以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="51c4e-104">Use the App-V Management Console to add the certificate and configure the App-V Management Server for enhanced security.</span></span> <span data-ttu-id="51c4e-105">你可以使用以下过程配置安全性后的安装。</span><span class="sxs-lookup"><span data-stu-id="51c4e-105">You can use the following procedure to configure security post-installation.</span></span>

**<span data-ttu-id="51c4e-106">配置管理服务器安全安装后</span><span class="sxs-lookup"><span data-stu-id="51c4e-106">To configure Management Server security post-installation</span></span>**

1.  <span data-ttu-id="51c4e-107">打开 app-v 管理控制台，并通过 App-v 管理员权限连接到**管理服务**。</span><span class="sxs-lookup"><span data-stu-id="51c4e-107">Open the App-V Management Console, and connect to the **Management Service** with App-V administrator privileges.</span></span>

2.  <span data-ttu-id="51c4e-108">展开 "服务器"，展开 "**服务器组**"，然后选择注册管理服务器的相应服务器组。</span><span class="sxs-lookup"><span data-stu-id="51c4e-108">Expand the server, expand **Server Groups**, and then select the appropriate server group with which the Management Server was registered.</span></span>

3.  <span data-ttu-id="51c4e-109">右键单击 "管理服务器" 对象，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="51c4e-109">Right-click the Management Server object, and select **Properties**.</span></span>

4.  <span data-ttu-id="51c4e-110">在 "**端口**" 选项卡上，单击 "**服务器证书**" 并完成向导，选择正确设置的证书。</span><span class="sxs-lookup"><span data-stu-id="51c4e-110">On the **Ports** tab, click **Server Certificate** and complete the wizard to select the properly provisioned certificate.</span></span>

    <span data-ttu-id="51c4e-111">**注意** 如果向导中未显示任何证书，则证书尚未设置，或者证书确实满足 App-v 的要求。</span><span class="sxs-lookup"><span data-stu-id="51c4e-111">**Note** If no certificates are displayed in the wizard, a certificate has not been provisioned or the certificate does meet the requirements of App-V.</span></span>

     

5.  <span data-ttu-id="51c4e-112">单击 "**下一步**" 继续**使用 "欢迎使用证书向导**" 页面。</span><span class="sxs-lookup"><span data-stu-id="51c4e-112">Click **Next** to continue on to the **Welcome To Certificate Wizard** page.</span></span>

6.  <span data-ttu-id="51c4e-113">在 "**可用证书**" 屏幕中选择正确的证书。</span><span class="sxs-lookup"><span data-stu-id="51c4e-113">Select the correct certificate in the **Available Certificates** screen.</span></span>

7.  <span data-ttu-id="51c4e-114">单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="51c4e-114">Click **Finish**.</span></span>

8.  <span data-ttu-id="51c4e-115">完成向导后，清除**RTSP**作为可用的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="51c4e-115">After completing the wizard, clear **RTSP** as an available listening port.</span></span> <span data-ttu-id="51c4e-116">这将阻止通过非安全通信通道进行连接。</span><span class="sxs-lookup"><span data-stu-id="51c4e-116">This prevents connections from being made over a non-secure communication channel.</span></span>

9.  <span data-ttu-id="51c4e-117">单击 "**应用**"，然后重新启动**Microsoft 虚拟应用程序服务器**服务。</span><span class="sxs-lookup"><span data-stu-id="51c4e-117">Click **Apply**, and restart the **Microsoft Virtual Application Server** service.</span></span> <span data-ttu-id="51c4e-118">使用服务的 MMC 管理单元完成此任务。</span><span class="sxs-lookup"><span data-stu-id="51c4e-118">Use the service’s MMC snap-in to accomplish this task.</span></span>

## <span data-ttu-id="51c4e-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="51c4e-119">Related topics</span></span>


[<span data-ttu-id="51c4e-120">如何配置 Streaming Server 安装后的安全性</span><span class="sxs-lookup"><span data-stu-id="51c4e-120">How to Configure Streaming Server Security Post-Installation</span></span>](how-to-configure-streaming-server-security-post-installation.md)

[<span data-ttu-id="51c4e-121">解决证书权限问题</span><span class="sxs-lookup"><span data-stu-id="51c4e-121">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)

 

 





