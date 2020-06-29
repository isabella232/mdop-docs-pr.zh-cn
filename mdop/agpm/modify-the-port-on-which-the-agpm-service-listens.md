---
title: 修改 AGPM 服务侦听的端口
description: 修改 AGPM 服务侦听的端口
author: dansimp
ms.assetid: a82c6873-e916-4a04-b263-aa612cd6956b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2af79ecb9bd05acbc55083163903ae14ab44d06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802636"
---
# <span data-ttu-id="9e63f-103">修改 AGPM 服务侦听的端口</span><span class="sxs-lookup"><span data-stu-id="9e63f-103">Modify the Port on Which the AGPM Service Listens</span></span>


<span data-ttu-id="9e63f-104">AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对存档和生产环境中的组策略对象（Gpo）的访问。</span><span class="sxs-lookup"><span data-stu-id="9e63f-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="9e63f-105">默认情况下，AGPM 服务在端口4600上侦听。</span><span class="sxs-lookup"><span data-stu-id="9e63f-105">By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="9e63f-106">你可以通过修改每个存档的高级组策略管理（AGPM）存档索引文件来更改此端口。</span><span class="sxs-lookup"><span data-stu-id="9e63f-106">You can change this port by modifying the Advanced Group Policy Management (AGPM) archive index file for each archive.</span></span>

<span data-ttu-id="9e63f-107">**注意** 在修改 AGPM 服务侦听的端口之前，建议备份 AGPM 存档索引文件（gpostate.xml）。</span><span class="sxs-lookup"><span data-stu-id="9e63f-107">**Note** Before modifying the port on which the AGPM Service listens, it is recommended that you back up the AGPM archive index file (gpostate.xml).</span></span> <span data-ttu-id="9e63f-108">在安装高级组策略管理-服务器期间，此文件位于输入为存档路径的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9e63f-108">This file is located in the folder entered as the archive path during the installation of Advanced Group Policy Management - Server.</span></span> <span data-ttu-id="9e63f-109">默认情况下，此文件的此位置为 AGPM 服务器上% CommonAppData% \\Microsoft\\AGPM\\gpostate.xml%。</span><span class="sxs-lookup"><span data-stu-id="9e63f-109">By default, this location of this file is %CommonAppData%\\Microsoft\\AGPM\\gpostate.xml on the AGPM Server.</span></span> <span data-ttu-id="9e63f-110">如果不知道哪些计算机托管存档，则可以按照修改存档路径的过程显示当前的存档路径。</span><span class="sxs-lookup"><span data-stu-id="9e63f-110">If you do not know which computer hosts the archive, you can follow the procedure for modifying the archive path to display the current archive path.</span></span> <span data-ttu-id="9e63f-111">有关详细信息，请参阅[修改存档路径](modify-the-archive-path.md)。</span><span class="sxs-lookup"><span data-stu-id="9e63f-111">For more information, see [Modify the Archive Path](modify-the-archive-path.md).</span></span>

 

<span data-ttu-id="9e63f-112">有权访问 AGPM 服务器（安装了 AGPM 服务的计算机）的用户帐户，需要存档索引文件才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="9e63f-112">A user account with access to the AGPM Server (the computer on which the AGPM Service is installed) and the archive index file is required to complete this procedure.</span></span>

**<span data-ttu-id="9e63f-113">修改 AGPM 服务侦听的端口</span><span class="sxs-lookup"><span data-stu-id="9e63f-113">To modify the port on which the AGPM Service listens</span></span>**

1.  <span data-ttu-id="9e63f-114">在托管存档的计算机上，在文本编辑器中打开存档索引文件（gpostate.xml）。</span><span class="sxs-lookup"><span data-stu-id="9e63f-114">On the computer hosting the archive, open the archive index file (gpostate.xml) in a text editor.</span></span>

2.  <span data-ttu-id="9e63f-115">在文件中，搜索 " **agpm： port =" 4600 "**。</span><span class="sxs-lookup"><span data-stu-id="9e63f-115">In the file, search for **agpm:port="4600"**.</span></span>

3.  <span data-ttu-id="9e63f-116">将**4600**替换为应侦听的 AGPM 服务的端口;然后，保存并关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="9e63f-116">Replace **4600** with the port on which the AGPM Service should listen; then, save and close the file.</span></span>

4.  <span data-ttu-id="9e63f-117">在 AGPM 服务器上，重新启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="9e63f-117">On the AGPM Server, restart the AGPM Service.</span></span> <span data-ttu-id="9e63f-118">（有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service.md)。）</span><span class="sxs-lookup"><span data-stu-id="9e63f-118">(For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service.md).)</span></span>

5.  <span data-ttu-id="9e63f-119">在 AGPM 服务器连接中修改每个组策略管理员的端口。</span><span class="sxs-lookup"><span data-stu-id="9e63f-119">Modify the port in the AGPM Server connection for each Group Policy administrator.</span></span> <span data-ttu-id="9e63f-120">（有关详细信息，请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。）</span><span class="sxs-lookup"><span data-stu-id="9e63f-120">(For more information, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).)</span></span>

6.  <span data-ttu-id="9e63f-121">对每个存档和 AGPM 服务器重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="9e63f-121">Repeat for each archive and AGPM Server.</span></span>

### <span data-ttu-id="9e63f-122">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="9e63f-122">Additional references</span></span>

-   [<span data-ttu-id="9e63f-123">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="9e63f-123">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





