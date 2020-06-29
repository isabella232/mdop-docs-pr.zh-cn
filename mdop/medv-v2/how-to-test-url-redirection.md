---
title: 如何测试 URL 重定向
description: 如何测试 URL 重定向
author: dansimp
ms.assetid: 38d80088-da1d-4098-b27e-76f9e78f81dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d964cf9d0114d3085d7e8952eebc82486b7b76cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803570"
---
# <span data-ttu-id="dfa9c-103">如何测试 URL 重定向</span><span class="sxs-lookup"><span data-stu-id="dfa9c-103">How to Test URL Redirection</span></span>


<span data-ttu-id="dfa9c-104">第一次测试完成后，你可以通过执行以下任务来验证 URL 重定向功能是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-104">After your test of first time setup finishes, you can verify that the URL redirection functionality is working as expected by performing the following tasks.</span></span>

<span data-ttu-id="dfa9c-105">**重要提示** 必须运行 MED-V 主机代理才能使 URL 重定向正常工作。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-105">**Important** The MED-V Host Agent must be running for URL redirection to function correctly.</span></span>

<a href="" id="bkmk-urlredir"></a>**<span data-ttu-id="dfa9c-106">测试 URL 重定向</span><span class="sxs-lookup"><span data-stu-id="dfa9c-106">To test URL Redirection</span></span>**

1.  <span data-ttu-id="dfa9c-107">在主计算机中打开 Internet Explorer 浏览器，然后输入您指定用于重定向的 URL。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-107">Open an Internet Explorer browser in the host computer and enter a URL that you specified for redirection.</span></span>

2.  <span data-ttu-id="dfa9c-108">验证网页是否已在来宾虚拟机上的 Internet Explorer 中打开。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-108">Verify that the webpage is opened in Internet Explorer on the guest virtual machine.</span></span>

3.  <span data-ttu-id="dfa9c-109">对要测试的每个 URL 重复此过程。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-109">Repeat this process for each URL that you want to test.</span></span>

**<span data-ttu-id="dfa9c-110">测试是否可以添加或删除 URL</span><span class="sxs-lookup"><span data-stu-id="dfa9c-110">To test that a URL can be added or removed</span></span>**

1.  <span data-ttu-id="dfa9c-111">从 MED-V 工作区添加或删除 URL。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-111">Add or remove a URL from the MED-V workspace.</span></span>

    <span data-ttu-id="dfa9c-112">有关如何在 MED-V 工作区上添加和删除要重定向的 Url 的信息，请参阅[管理 MED-V URL 重定向](manage-med-v-url-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-112">For information about how to add and remove URLs for redirection on a MED-V workspace, see [Manage MED-V URL Redirection](manage-med-v-url-redirection.md).</span></span>

2.  <span data-ttu-id="dfa9c-113">如果你已将 URL 添加到重定向列表，请重复执行 "[测试 URL 重定向](#bkmk-urlredir)" 中的步骤，以验证新 URL 是否按预期重定向。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-113">If you added a URL to the redirection list, repeat the steps in [To Test URL Redirection](#bkmk-urlredir) to verify that the new URL redirects as intended.</span></span>

3.  <span data-ttu-id="dfa9c-114">如果从重定向列表中删除了 URL，请按照以下步骤验证是否已删除 URL：</span><span class="sxs-lookup"><span data-stu-id="dfa9c-114">If you removed a URL from the redirection list, verify that it is removed by following these steps:</span></span>

    1.  <span data-ttu-id="dfa9c-115">在主计算机中打开 Internet Explorer 浏览器，然后输入从重定向列表中删除的 URL。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-115">Open an Internet Explorer browser in the host computer and enter the URL that you removed from the redirection list.</span></span>

    2.  <span data-ttu-id="dfa9c-116">验证网页是否已在主机计算机上的 Internet Explorer 中打开，而不是在来宾虚拟机上打开。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-116">Verify that the webpage is opened in Internet Explorer on the host computer instead of on the guest virtual machine.</span></span>

        <span data-ttu-id="dfa9c-117">**注意** 可能需要几秒钟才能使 URL 重定向发生更改。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-117">**Note** It can take several seconds for the URL redirection changes to take place.</span></span>

<span data-ttu-id="dfa9c-118">**注意** 如果您在验证 URL 重定向设置时遇到任何问题，请参阅[操作疑难解答](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-118">**Note** If you encounter any problems when verifying your URL redirection settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="dfa9c-119">在 MED-V 工作区中完成 URL 重定向测试后，可以测试其他配置以验证它们是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-119">After you have completed testing URL redirection in your MED-V workspace, you can test other configurations to verify that they function as intended.</span></span>

<span data-ttu-id="dfa9c-120">在完成对 MED-V 工作区程序包的测试并验证它是否按预期运行后，你可以将 MED-V 工作区部署到你的企业。</span><span class="sxs-lookup"><span data-stu-id="dfa9c-120">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="dfa9c-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="dfa9c-121">Related topics</span></span>

[<span data-ttu-id="dfa9c-122">如何测试应用程序发布</span><span class="sxs-lookup"><span data-stu-id="dfa9c-122">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="dfa9c-123">如何验证首次安装设置</span><span class="sxs-lookup"><span data-stu-id="dfa9c-123">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="dfa9c-124">部署 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="dfa9c-124">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

 

 





