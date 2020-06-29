---
title: 如何通过使用 MED-V 工作区包装程序管理 URL 重定向
description: 如何通过使用 MED-V 工作区包装程序管理 URL 重定向
author: dansimp
ms.assetid: 1a8d25af-479f-42d3-bf5f-c7fd974bbf8c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 88167923e3bd47f2a3b0b3ada5e818715740dbe3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803644"
---
# <span data-ttu-id="99b08-103">如何通过使用 MED-V 工作区包装程序管理 URL 重定向</span><span class="sxs-lookup"><span data-stu-id="99b08-103">How to Manage URL Redirection by Using the MED-V Workspace Packager</span></span>


<span data-ttu-id="99b08-104">你可以使用 MED-V 工作区包装程序管理 MED-V 工作区中的 URL 重定向。</span><span class="sxs-lookup"><span data-stu-id="99b08-104">You can use the MED-V Workspace Packager to manage URL redirection in the MED-V workspace.</span></span>

**<span data-ttu-id="99b08-105">在 MED-V 工作区中管理 web 地址重定向</span><span class="sxs-lookup"><span data-stu-id="99b08-105">To manage web address redirection in a MED-V workspace</span></span>**

1.  <span data-ttu-id="99b08-106">若要打开**Med-v 工作区包装程序**，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 工作区包装程序**"。</span><span class="sxs-lookup"><span data-stu-id="99b08-106">To open the **MED-V Workspace Packager**, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager**.</span></span>

2.  <span data-ttu-id="99b08-107">在**Med-v 工作区包装**程序主面板上，单击 "**管理 Web 重定向**"。</span><span class="sxs-lookup"><span data-stu-id="99b08-107">On the **MED-V Workspace Packager** main panel, click **Manage Web Redirection**.</span></span>

3.  <span data-ttu-id="99b08-108">在 "**管理 Web 重定向**" 窗口中，可以键入、粘贴或导入在 med-v 工作区中重定向到 Internet Explorer 的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="99b08-108">In the **Manage Web Redirection** window, you can type, paste, or import a list of the URLs that are redirected to Internet Explorer in the MED-V workspace.</span></span>

    **<span data-ttu-id="99b08-109">注意</span><span class="sxs-lookup"><span data-stu-id="99b08-109">Note</span></span>**  
    <span data-ttu-id="99b08-110">MED-V 中的 URL 重定向仅支持 HTTP 和 HTTPS 协议。</span><span class="sxs-lookup"><span data-stu-id="99b08-110">URL redirection in MED-V only supports the protocols HTTP and HTTPS.</span></span> <span data-ttu-id="99b08-111">MED-V 不提供对 FTP 或任何其他协议的支持。</span><span class="sxs-lookup"><span data-stu-id="99b08-111">MED-V does not provide support for FTP or any other protocols.</span></span>



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



4. <span data-ttu-id="99b08-112">单击 "**另存为 ...** "</span><span class="sxs-lookup"><span data-stu-id="99b08-112">Click **Save as…**</span></span> <span data-ttu-id="99b08-113">将更新后的 URL 重定向文件保存在指定文件夹中。</span><span class="sxs-lookup"><span data-stu-id="99b08-113">to save the updated URL redirection files in the specified folder.</span></span> <span data-ttu-id="99b08-114">MED-V 将创建一个包含更新的 URL 重定向信息的注册表文件。</span><span class="sxs-lookup"><span data-stu-id="99b08-114">MED-V creates a registry file that contains the updated URL redirection information.</span></span> <span data-ttu-id="99b08-115">使用组策略部署更新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="99b08-115">Deploy the updated registry key by using Group Policy.</span></span> <span data-ttu-id="99b08-116">有关如何使用组策略的详细信息，请参阅[组策略软件安装](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="99b08-116">For more information about how to use Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

   <span data-ttu-id="99b08-117">MED-V 还会在指定文件夹中创建可用于重新创建更新的 MED-V 工作区程序包的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="99b08-117">MED-V also creates a Windows PowerShell script in the specified folder that you can use to re-create the updated MED-V workspace package.</span></span>

## <span data-ttu-id="99b08-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="99b08-118">Related topics</span></span>


[<span data-ttu-id="99b08-119">如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息</span><span class="sxs-lookup"><span data-stu-id="99b08-119">How to Add or Remove URL Redirection Information in a Deployed MED-V Workspace</span></span>](how-to-add-or-remove-url-redirection-information-in-a-deployed-med-v-workspace.md)

[<span data-ttu-id="99b08-120">管理 MED-V URL 重定向</span><span class="sxs-lookup"><span data-stu-id="99b08-120">Manage MED-V URL Redirection</span></span>](manage-med-v-url-redirection.md)









