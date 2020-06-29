---
title: 如何添加程序包
description: 如何添加程序包
author: dansimp
ms.assetid: 5407fdbe-e658-44f6-a9b8-a566b81dedce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c580d7d131017c52e278adda0208ffcb2e86ccf2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802960"
---
# <span data-ttu-id="eeb95-103">如何添加程序包</span><span class="sxs-lookup"><span data-stu-id="eeb95-103">How to Add a Package</span></span>


<span data-ttu-id="eeb95-104">你可以通过以下方式从应用程序虚拟化服务器管理控制台添加程序包：</span><span class="sxs-lookup"><span data-stu-id="eeb95-104">You can add a package from the Application Virtualization Server Management Console in the following ways:</span></span>

-   <span data-ttu-id="eeb95-105">导入应用程序，该应用程序将在进程中自动创建程序包。</span><span class="sxs-lookup"><span data-stu-id="eeb95-105">Import an application, which creates the package automatically in the process.</span></span>

-   <span data-ttu-id="eeb95-106">手动添加程序包。</span><span class="sxs-lookup"><span data-stu-id="eeb95-106">Add a package manually.</span></span>

<span data-ttu-id="eeb95-107">建议你导入应用程序，而不是手动添加它们。</span><span class="sxs-lookup"><span data-stu-id="eeb95-107">It is recommended that you import applications instead of adding them manually.</span></span> <span data-ttu-id="eeb95-108">有关导入应用程序的详细信息，请参阅[如何导入应用程序](how-to-import-an-applicationserver.md)。</span><span class="sxs-lookup"><span data-stu-id="eeb95-108">For more information about importing applications, see [How to Import an Application](how-to-import-an-applicationserver.md).</span></span>

**<span data-ttu-id="eeb95-109">手动添加程序包</span><span class="sxs-lookup"><span data-stu-id="eeb95-109">To add a package manually</span></span>**

1.  <span data-ttu-id="eeb95-110">在应用程序虚拟化服务器管理控制台中，右键单击左窗格中的 "**程序包**" 节点，然后选择 "**新建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="eeb95-110">In the Application Virtualization Server Management Console, right-click the **Packages** node in the left pane and choose **New Package**.</span></span>

2.  <span data-ttu-id="eeb95-111">在 "**新建程序包**" 对话框中，在 "**包名称**" 字段中键入名称。</span><span class="sxs-lookup"><span data-stu-id="eeb95-111">In the **New Package** dialog box, type a name in the **Package Name** field.</span></span>

3.  <span data-ttu-id="eeb95-112">在 "**文件包文件的完整路径**" 字段中，浏览或键入路径名称。</span><span class="sxs-lookup"><span data-stu-id="eeb95-112">Browse for or type a path name in the **Full path for package file** field.</span></span> <span data-ttu-id="eeb95-113">这必须是一个 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="eeb95-113">This must be an SFT file.</span></span>

    <span data-ttu-id="eeb95-114">**注意** 如果浏览到 SFT 文件，请将本地路径（如 C:\\program files Files\\User\ _Apps \\Virtual\ _App \ _Server \\content）替换为服务器的静态主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eeb95-114">**Note** If you browse to the SFT file, replace the local path (such as C:\\Program Files\\User\_Apps\\Virtual\_App\_Server\\content) with the server's static host name or IP address.</span></span> <span data-ttu-id="eeb95-115">使用变量 *% SFT \ _SOFTGRIDSERVER%* 需要每客户端计算机配置。</span><span class="sxs-lookup"><span data-stu-id="eeb95-115">Using the variable *%SFT\_SOFTGRIDSERVER%* requires per-client computer configuration.</span></span>

    <span data-ttu-id="eeb95-116">在引用虚拟应用程序服务器的对话框中，必须使用用户可以访问的网络位置，如服务器的静态主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eeb95-116">In dialog boxes that refer to Virtual Application Servers, you must use a network location, such as the server's static host name or IP address, that your users can access.</span></span> <span data-ttu-id="eeb95-117">应用程序的开放式软件描述符（OSD）文件可以将占位符变量 *% SFT \ _SOFTGRIDSERER%* 替换为服务器的静态主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eeb95-117">The application's Open Software Descriptor (OSD) file can replace the placeholder variable *%SFT\_SOFTGRIDSERER%* with the server's static host name or IP address.</span></span> <span data-ttu-id="eeb95-118">如果保留了占位符变量，则必须在将访问该服务器的每台客户端计算机上设置此变量。</span><span class="sxs-lookup"><span data-stu-id="eeb95-118">If you leave the placeholder variable, you must set this variable on each client computer that will access that server.</span></span> <span data-ttu-id="eeb95-119">在 SFT \ _SOFTGRIDSERVER 的每台计算机上设置一个用户或系统变量。</span><span class="sxs-lookup"><span data-stu-id="eeb95-119">Set a User or System variable on each computer for SFT\_SOFTGRIDSERVER.</span></span> <span data-ttu-id="eeb95-120">变量值必须是服务器的静态主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eeb95-120">The variable value must be the server's static host name or IP address.</span></span> <span data-ttu-id="eeb95-121">如果设置了变量，请退出客户端会话，注销并重新登录到 Microsoft Windows，然后在运行会话且具有变量集的每台计算机上重新启动会话。</span><span class="sxs-lookup"><span data-stu-id="eeb95-121">If you set a variable, exit the Client session, log out of and back into Microsoft Windows, and then restart the session on each computer that had a session running and had the variable set.</span></span>

     

4.  <span data-ttu-id="eeb95-122">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eeb95-122">Click **Next**.</span></span>

5.  <span data-ttu-id="eeb95-123">"**摘要**" 对话框显示文件位置，并提示您将文件复制到该位置（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="eeb95-123">The **Summary** dialog box shows the file location and prompts you to copy the file to the location if you have not already done so.</span></span> <span data-ttu-id="eeb95-124">验证信息后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="eeb95-124">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="eeb95-125">**注意** 如果你在远程服务器上管理应用程序，请在 "下一个" 对话框中，只键入相对于服务器的内容根的文件路径。</span><span class="sxs-lookup"><span data-stu-id="eeb95-125">**Note** If you are managing applications on a remote server, in the next dialog box, type only the path of the file relative to the server's content root.</span></span>

     

## <span data-ttu-id="eeb95-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="eeb95-126">Related topics</span></span>


[<span data-ttu-id="eeb95-127">如何导入应用程序</span><span class="sxs-lookup"><span data-stu-id="eeb95-127">How to Import an Application</span></span>](how-to-import-an-applicationserver.md)

[<span data-ttu-id="eeb95-128">如何在 Server Management Console 中管理程序包</span><span class="sxs-lookup"><span data-stu-id="eeb95-128">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





