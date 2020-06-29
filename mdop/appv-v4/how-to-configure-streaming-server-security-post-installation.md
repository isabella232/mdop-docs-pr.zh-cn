---
title: 如何配置 Streaming Server 安装后的安全性
description: 如何配置 Streaming Server 安装后的安全性
author: dansimp
ms.assetid: 9bde3677-d1aa-4dcc-904e-bb49a268d748
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1945b38da5dd50c0bd2fb0c741bd92012e78586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801603"
---
# <span data-ttu-id="d237e-103">如何配置 Streaming Server 安装后的安全性</span><span class="sxs-lookup"><span data-stu-id="d237e-103">How to Configure Streaming Server Security Post-Installation</span></span>


<span data-ttu-id="d237e-104">通过注册表配置 app-v 流式处理服务器以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="d237e-104">Configure the App-V Streaming Server for enhanced security through the registry.</span></span> <span data-ttu-id="d237e-105">与 App-v 管理服务器一样，在完成以下安装后过程之前，必须使用正确的 "服务器身份验证" EKU 标识符正确设置证书。</span><span class="sxs-lookup"><span data-stu-id="d237e-105">As with the App-V Management Server, a certificate must be correctly provisioned with the correct EKU identifier for Server Authentication before you complete the following post-installation procedure.</span></span>

**<span data-ttu-id="d237e-106">配置流式服务器安全安装后的安全</span><span class="sxs-lookup"><span data-stu-id="d237e-106">To configure Streaming Server security post-installation</span></span>**

1.  <span data-ttu-id="d237e-107">创建 MMC，添加 "**证书**" 管理单元，然后选择 "**本地计算机证书存储**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-107">Create an MMC, add the **Certificates** snap-in, and select **Local Machine certificate store**.</span></span>

2.  <span data-ttu-id="d237e-108">打开计算机的**个人**证书，然后打开为 app-v 预配的证书。</span><span class="sxs-lookup"><span data-stu-id="d237e-108">Open the **Personal** certificates for the computer, and open the certificate provisioned for App-V.</span></span>

3.  <span data-ttu-id="d237e-109">在 "**详细信息**" 选项卡上，向下滚动到指纹，然后在 "详细信息" 窗格中复制哈希。</span><span class="sxs-lookup"><span data-stu-id="d237e-109">On the **Details** tab, scroll down to the thumbprint and copy the hash in the details pane.</span></span>

4.  <span data-ttu-id="d237e-110">打开注册表编辑器，然后导航到 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server` 。</span><span class="sxs-lookup"><span data-stu-id="d237e-110">Open the registry editor, and navigate to `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server`.</span></span>

5.  <span data-ttu-id="d237e-111">编辑 `X509CertHash` 值，在 "值" 字段中粘贴指纹哈希，然后删除所有空格。</span><span class="sxs-lookup"><span data-stu-id="d237e-111">Edit the `X509CertHash` value, paste the thumbprint hash in the value field, and remove all spaces.</span></span> <span data-ttu-id="d237e-112">单击 **"确定"** 接受编辑。</span><span class="sxs-lookup"><span data-stu-id="d237e-112">Click **OK** to accept the edit.</span></span>

6.  <span data-ttu-id="d237e-113">在注册表编辑器中，导航到 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts` 。</span><span class="sxs-lookup"><span data-stu-id="d237e-113">In the registry editor, navigate to `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts`.</span></span>

7.  <span data-ttu-id="d237e-114">创建一个名为 "322" 的新**DWORD**值，然后输入十进制值作为322或十六进制值作为142。</span><span class="sxs-lookup"><span data-stu-id="d237e-114">Create a new **DWORD** value named "322," and then enter the decimal value as 322 or the hexadecimal value as 142.</span></span>

8.  <span data-ttu-id="d237e-115">重新启动流服务。</span><span class="sxs-lookup"><span data-stu-id="d237e-115">Restart the streaming service.</span></span>

## <span data-ttu-id="d237e-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="d237e-116">Related topics</span></span>


[<span data-ttu-id="d237e-117">如何配置 Management Server 安装后的安全性</span><span class="sxs-lookup"><span data-stu-id="d237e-117">How to Configure Management Server Security Post-Installation</span></span>](how-to-configure-management-server-security-post-installation.md)

[<span data-ttu-id="d237e-118">解决证书权限问题</span><span class="sxs-lookup"><span data-stu-id="d237e-118">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)

 

 





