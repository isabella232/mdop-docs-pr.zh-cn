---
title: 如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息
description: 如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息
author: dansimp
ms.assetid: bf55848d-bf77-452e-aaa5-4dd4868ff5bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: f0892b16bfc10e6b3f28fe99c51c2c5cedb73d7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803969"
---
# <span data-ttu-id="22412-103">如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息</span><span class="sxs-lookup"><span data-stu-id="22412-103">How to Add or Remove URL Redirection Information in a Deployed MED-V Workspace</span></span>


<span data-ttu-id="22412-104">若要在已部署的 MED-V 工作区中编辑 URL 重定向信息，建议使用组策略更新系统注册表。</span><span class="sxs-lookup"><span data-stu-id="22412-104">To edit URL redirection information in a deployed MED-V workspace, we recommend that you update the system registry by using Group Policy.</span></span> <span data-ttu-id="22412-105">虽然我们不建议这样做，但你也可以通过更新的 URL 重定向信息来重建和重新部署 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="22412-105">Although we do not recommend it, you can also rebuild and redeploy the MED-V workspace with the updated URL redirection information.</span></span>

<span data-ttu-id="22412-106">该注册表项通常位于：</span><span class="sxs-lookup"><span data-stu-id="22412-106">The registry key is usually located at:</span></span>

<span data-ttu-id="22412-107">Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span><span class="sxs-lookup"><span data-stu-id="22412-107">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

<span data-ttu-id="22412-108">必须存在以下多字符串值：</span><span class="sxs-lookup"><span data-stu-id="22412-108">The following multi-string value must be present:</span></span> `RedirectUrls`

<span data-ttu-id="22412-109">的值数据 `RedirectUrls` 是在使用**Med-v 工作区包装**程序构建 med-v 工作区程序包时为重定向指定的所有 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="22412-109">The value data for `RedirectUrls` is a list of all of the URLs that you specified for redirection when you built the MED-V workspace package by using the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="22412-110">有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="22412-110">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

<span data-ttu-id="22412-111">可以通过执行以下任务之一来添加和删除 URL 重定向信息：</span><span class="sxs-lookup"><span data-stu-id="22412-111">You can add and remove URL redirection information by performing one of the following tasks:</span></span>

-   [<span data-ttu-id="22412-112">编辑 URL 重定向注册表项并使用组策略进行部署</span><span class="sxs-lookup"><span data-stu-id="22412-112">Edit the URL Redirection Registry Key and Deploy Using Group Policy</span></span>](#bkmk-editreg)

-   [<span data-ttu-id="22412-113">编辑 URL 重定向文本文件并重建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="22412-113">Edit the URL Redirection Text File and Rebuild the MED-V Workspace</span></span>](#bkmk-edittext)

<a href="" id="bkmk-editreg"></a>**<span data-ttu-id="22412-114">使用组策略更新 URL 重定向信息</span><span class="sxs-lookup"><span data-stu-id="22412-114">To update URL Redirection information by using Group Policy</span></span>**

1.  <span data-ttu-id="22412-115">编辑名为的注册表项多字符串值 `RedirectUrls` 。</span><span class="sxs-lookup"><span data-stu-id="22412-115">Edit the registry key multi-string value that is named `RedirectUrls`.</span></span> <span data-ttu-id="22412-116">此值通常位于：</span><span class="sxs-lookup"><span data-stu-id="22412-116">This value is typically located at:</span></span>

    <span data-ttu-id="22412-117">Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span><span class="sxs-lookup"><span data-stu-id="22412-117">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

    <span data-ttu-id="22412-118">如果你要将 Url 添加到注册表项，请每行输入一个 Url，在你构建 MED-V 工作区程序包时是必需的。</span><span class="sxs-lookup"><span data-stu-id="22412-118">If you are adding URLs to the registry key, enter them one per line, as was required when you built the MED-V workspace package.</span></span> <span data-ttu-id="22412-119">有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="22412-119">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

2.  <span data-ttu-id="22412-120">使用组策略部署更新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="22412-120">Deploy the updated registry key by using Group Policy.</span></span> <span data-ttu-id="22412-121">有关如何使用组策略的详细信息，请参阅[组策略软件安装](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="22412-121">For more information about how to use Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

<span data-ttu-id="22412-122">**注意** 这种编辑 URL 重定向信息的方法是一种 MED-V 最佳做法。</span><span class="sxs-lookup"><span data-stu-id="22412-122">**Note** This method of editing URL redirection information is a MED-V best practice.</span></span>

 

<a href="" id="bkmk-edittext"></a>**<span data-ttu-id="22412-123">使用更新的 URL 文本文件重建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="22412-123">To rebuild the MED-V workspace by using an updated URL text file</span></span>**

-   <span data-ttu-id="22412-124">从重定向列表中添加和删除 Url 的另一种方法是更新 URL 重定向文本文件，然后使用该文件构建新的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="22412-124">Another method of adding and removing URLs from the redirection list is to update the URL redirection text file and then use it to build a new MED-V workspace.</span></span> <span data-ttu-id="22412-125">然后，你可以通过使用你的标准部署过程（如 ESD 系统）来重新部署 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="22412-125">You can then redeploy the MED-V workspace as before, by using your standard process of deployment, such as an ESD system.</span></span>

    <span data-ttu-id="22412-126">**重要提示** 我们不建议此方法来编辑 URL 重定向信息。</span><span class="sxs-lookup"><span data-stu-id="22412-126">**Important** We do not recommend this method of editing URL redirection information.</span></span> <span data-ttu-id="22412-127">此外，每当你重新部署 MED-V 工作区到你的企业时，第一次必须再次运行安装程序，并且虚拟机中保存的所有数据都将丢失。</span><span class="sxs-lookup"><span data-stu-id="22412-127">In addition, any time that you redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved in the virtual machine is lost.</span></span>

     

## <span data-ttu-id="22412-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="22412-128">Related topics</span></span>


[<span data-ttu-id="22412-129">如何测试 URL 重定向</span><span class="sxs-lookup"><span data-stu-id="22412-129">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="22412-130">管理部署到 MED-V 工作区的应用程序</span><span class="sxs-lookup"><span data-stu-id="22412-130">Managing Applications Deployed to MED-V Workspaces</span></span>](managing-applications-deployed-to-med-v-workspaces.md)

[<span data-ttu-id="22412-131">创建 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="22412-131">Create a MED-V Workspace Package</span></span>](create-a-med-v-workspace-package.md)

 

 





