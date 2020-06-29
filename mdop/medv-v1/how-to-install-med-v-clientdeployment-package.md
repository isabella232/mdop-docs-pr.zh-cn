---
title: 如何安装 MED-V 客户端
description: 如何安装 MED-V 客户端
author: dansimp
ms.assetid: bfac6de7-d96d-4b3e-bd8b-183e051e53c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2e4468b15c0c196bf605b1b5d129ab38678ec74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804119"
---
# <span data-ttu-id="8121b-103">如何安装 MED-V 客户端</span><span class="sxs-lookup"><span data-stu-id="8121b-103">How to Install MED-V Client</span></span>


<span data-ttu-id="8121b-104">在基于部署程序包的方案中，MED-V 客户端安装包含在部署程序包中并直接从程序包安装。</span><span class="sxs-lookup"><span data-stu-id="8121b-104">In a deployment package-based scenario, the MED-V client installation is included in the deployment package and installed directly from the package.</span></span>

**<span data-ttu-id="8121b-105">重要提示</span><span class="sxs-lookup"><span data-stu-id="8121b-105">Important</span></span>**  
<span data-ttu-id="8121b-106">使用不包含图像的部署包时，请确保在安装部署包之前将图像上载到 Web 或将其推送到前阶段文件夹。</span><span class="sxs-lookup"><span data-stu-id="8121b-106">When using a deployment package that does not include an image, ensure that the image is uploaded to the Web or pushed to the pre-stage folder prior to installing the deployment package.</span></span>



**<span data-ttu-id="8121b-107">安装部署程序包</span><span class="sxs-lookup"><span data-stu-id="8121b-107">To install a deployment package</span></span>**

1.  <span data-ttu-id="8121b-108">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8121b-108">Do one of the following:</span></span>

    -   <span data-ttu-id="8121b-109">从 Web 下载 MED-V 程序包。</span><span class="sxs-lookup"><span data-stu-id="8121b-109">Download the MED-V package from the Web.</span></span>

    -   <span data-ttu-id="8121b-110">将部署 USB 或 DVD 插入主驱动器。</span><span class="sxs-lookup"><span data-stu-id="8121b-110">Insert the deployment USB or DVD into the host drive.</span></span>

2.  <span data-ttu-id="8121b-111">如果 MED-V 不会自动启动，请双击 MED-VAutoInstaller.exe。</span><span class="sxs-lookup"><span data-stu-id="8121b-111">If MED-V does not launch automatically, double-click MED-VAutoInstaller.exe.</span></span>

    <span data-ttu-id="8121b-112">将出现一个对话框，其中列出了已安装的组件以及当前正在安装的组件。</span><span class="sxs-lookup"><span data-stu-id="8121b-112">A dialog box appears listing the components that are already installed and those that are currently being installed.</span></span>

    **<span data-ttu-id="8121b-113">注意</span><span class="sxs-lookup"><span data-stu-id="8121b-113">Note</span></span>**  
    <span data-ttu-id="8121b-114">如果主机上存在不受支持的 Microsoft 虚拟 PC 版本，则会显示一条消息，告知你卸载现有版本并再次运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="8121b-114">If a version of the Microsoft Virtual PC that is not supported exists on the host computer, a message will appear telling you to uninstall the existing version and run the installer again.</span></span>



~~~
**Note**  
If an older version of the MED-V client exists, it will prompt you asking whether you want to upgrade.



Depending on the components that have been installed, you might need to reboot. If rebooting is necessary, a message appears notifying you that you must reboot.
~~~

3. <span data-ttu-id="8121b-115">如有必要，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="8121b-115">If necessary, reboot the computer.</span></span>

   <span data-ttu-id="8121b-116">安装完成后，将启动 MED-V，并显示一条消息，通知您安装已完成。</span><span class="sxs-lookup"><span data-stu-id="8121b-116">When the installation is complete, MED-V starts and a message appears notifying you that the installation is complete.</span></span>

4. <span data-ttu-id="8121b-117">使用以下用户名和密码登录到 MED-V：</span><span class="sxs-lookup"><span data-stu-id="8121b-117">Log in to MED-V using the following user name and password:</span></span>

   -   <span data-ttu-id="8121b-118">键入允许使用 MED-V 的域用户的密码的域名和用户名，后跟您的密码。</span><span class="sxs-lookup"><span data-stu-id="8121b-118">Type in the domain name and user name followed by the password of the domain user who is permitted to work with MED-V.</span></span>

       <span data-ttu-id="8121b-119">示例： "domain \ _name \\user\ _name"，"密码"</span><span class="sxs-lookup"><span data-stu-id="8121b-119">Example: "domain\_name\\user\_name", "password"</span></span>

## <span data-ttu-id="8121b-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="8121b-120">Related topics</span></span>


[<span data-ttu-id="8121b-121">如何配置部署包</span><span class="sxs-lookup"><span data-stu-id="8121b-121">How to Configure a Deployment Package</span></span>](how-to-configure-a-deployment-package.md)

[<span data-ttu-id="8121b-122">如何将 MED-V 映像上传到服务器</span><span class="sxs-lookup"><span data-stu-id="8121b-122">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)

[<span data-ttu-id="8121b-123">客户端安装命令行参考</span><span class="sxs-lookup"><span data-stu-id="8121b-123">Client Installation Command Line Reference</span></span>](client-installation-command-line-reference.md)









