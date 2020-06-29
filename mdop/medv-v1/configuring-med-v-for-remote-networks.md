---
title: 配置 MED-V 以启用远程网络
description: 配置 MED-V 以启用远程网络
author: dansimp
ms.assetid: 4d2f0081-622f-4a6f-8d73-f8c2108036e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328376046ee5213f3d5bb09be7adf8c81f8508b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804025"
---
# <span data-ttu-id="0c218-103">配置 MED-V 以启用远程网络</span><span class="sxs-lookup"><span data-stu-id="0c218-103">Configuring MED-V for Remote Networks</span></span>


<span data-ttu-id="0c218-104">你可以将 MED-V 配置为在网络内部、远程或远程从网络内部进行工作。</span><span class="sxs-lookup"><span data-stu-id="0c218-104">You can configure MED-V to work from inside a network, remotely, or both from inside the network and remotely.</span></span>

## <a href="" id="bkmk-howtoconfiguremedvtoworkfrominsideanetworkorremotely"></a>


**<span data-ttu-id="0c218-105">将 MED-V 配置为从网络内部工作</span><span class="sxs-lookup"><span data-stu-id="0c218-105">To configure MED-V to work from inside a network</span></span>**

-   <span data-ttu-id="0c218-106">在网络内配置 MED-V 服务器和映像分布。</span><span class="sxs-lookup"><span data-stu-id="0c218-106">Configure a MED-V server and image distribution inside the network.</span></span>

**<span data-ttu-id="0c218-107">将 MED-V 配置为远程工作</span><span class="sxs-lookup"><span data-stu-id="0c218-107">To configure MED-V to work remotely</span></span>**

1.  <span data-ttu-id="0c218-108">配置从 Internet 访问的 MED-V 服务器和图像分发服务器。</span><span class="sxs-lookup"><span data-stu-id="0c218-108">Configure a MED-V server and an image distribution server that are accessible from the Internet.</span></span>

2.  <span data-ttu-id="0c218-109">如果需要，请配置外围网络（也称为 DMZ）反向代理。</span><span class="sxs-lookup"><span data-stu-id="0c218-109">If needed, configure a perimeter network (also called a DMZ) reverse proxy.</span></span>

3.  <span data-ttu-id="0c218-110">在 " *ClientSettings.xml* " 文件中设置身份验证方法，该方法可在**Servers\\Configuration Server\\**文件夹中找到。</span><span class="sxs-lookup"><span data-stu-id="0c218-110">Set the authentication method, in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

**<span data-ttu-id="0c218-111">将 MED-V 配置为从网络内部和远程处理</span><span class="sxs-lookup"><span data-stu-id="0c218-111">To configure MED-V to work both from inside a network and remotely</span></span>**

1.  <span data-ttu-id="0c218-112">在网络内配置 MED-V 服务器和图像分发服务器。</span><span class="sxs-lookup"><span data-stu-id="0c218-112">Configure a MED-V server and image distribution server inside the network.</span></span>

2.  <span data-ttu-id="0c218-113">确保可以从 Internet 访问服务器。</span><span class="sxs-lookup"><span data-stu-id="0c218-113">Ensure that the servers are accessible from the Internet.</span></span>

3.  <span data-ttu-id="0c218-114">配置 DNS 解析，以便当客户端尝试连接到服务器时，它会根据客户端位置自动连接到正确的服务器（位于网络或 Internet 内）。</span><span class="sxs-lookup"><span data-stu-id="0c218-114">Configure the DNS resolution so that when the client attempts to connect to a server, it automatically connects to the correct server (within the network or over the Internet) based on the client location.</span></span>

4.  <span data-ttu-id="0c218-115">如果需要，请配置外围网络反向代理。</span><span class="sxs-lookup"><span data-stu-id="0c218-115">If needed, configure a perimeter network reverse proxy.</span></span>

5.  <span data-ttu-id="0c218-116">在 " *ClientSettings.xml* " 文件中设置身份验证方法，该方法可在**Servers\\Configuration Server\\**文件夹中找到。</span><span class="sxs-lookup"><span data-stu-id="0c218-116">Set the authentication method, in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

<span data-ttu-id="0c218-117">**注意** 应用新设置时，必须重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="0c218-117">**Note** When applying new settings, the service must be restarted.</span></span>

 

-   <span data-ttu-id="0c218-118">你可以将 IIS 身份验证方案更改为下列之一：基本、摘要式、NTLM 或 NEGOTIATE。</span><span class="sxs-lookup"><span data-stu-id="0c218-118">You can change the IIS authentication scheme to one of the following: BASIC, DIGEST, NTLM, or NEGOTIATE.</span></span> <span data-ttu-id="0c218-119">默认为 "协商"，并使用以下条目：</span><span class="sxs-lookup"><span data-stu-id="0c218-119">The default is NEGOTIATE and uses the following entry:</span></span>

    ```xml
    <ImageDistribution>
    <!-- The authentication used for image download. Basic and digest authentication should be used only under SSL.-->
       <!-- The line below can be one of the following: -->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_BASIC</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_DIGEST</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NTLM</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME-->
       <Authentication type="Kidaro.Foundation.Bits.BG_AUTH_SCHEME">
          <BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME>
       </Authentication>
    </ImageDistribution>
    ```

## <span data-ttu-id="0c218-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c218-120">Related topics</span></span>


[<span data-ttu-id="0c218-121">MED-V 基础结构规划和设计</span><span class="sxs-lookup"><span data-stu-id="0c218-121">MED-V Infrastructure Planning and Design</span></span>](med-v-infrastructure-planning-and-design.md)

 

 





