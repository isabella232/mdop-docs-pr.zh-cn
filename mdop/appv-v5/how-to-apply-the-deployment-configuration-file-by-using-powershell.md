---
title: 如何使用 PowerShell 应用部署配置文件
description: 如何使用 PowerShell 应用部署配置文件
author: dansimp
ms.assetid: 5df5d5bc-6c72-4087-8b93-d6d4b502a1f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b6764f07dfe8cff1fb30c354937a405202468428
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798547"
---
# <span data-ttu-id="eb025-103">如何使用 PowerShell 应用部署配置文件</span><span class="sxs-lookup"><span data-stu-id="eb025-103">How to Apply the Deployment Configuration File by Using PowerShell</span></span>


<span data-ttu-id="eb025-104">在发布程序包之前，如果将程序包添加或设置为运行 app-v 5.0 客户端的计算机，则应用动态部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="eb025-104">The dynamic deployment configuration file is applied when a package is added or set to a computer running the App-V 5.0 client before the package has been published.</span></span> <span data-ttu-id="eb025-105">该文件为运行 App-v 5.0 客户端的计算机上的所有用户配置程序包的默认设置。</span><span class="sxs-lookup"><span data-stu-id="eb025-105">The file configures the default settings for package for all users on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="eb025-106">本节介绍用于使用部署配置文件的步骤。</span><span class="sxs-lookup"><span data-stu-id="eb025-106">This section describes the steps used to use a deployment configuration file.</span></span> <span data-ttu-id="eb025-107">该过程基于以下示例，并假定计算机上存在以下程序包和配置文件：</span><span class="sxs-lookup"><span data-stu-id="eb025-107">The procedure is based on the following example and assumes the following package and configuration files exist on a computer:</span></span>

**<span data-ttu-id="eb025-108">c:\\Packages\\Contoso\\MyApp.appv</span><span class="sxs-lookup"><span data-stu-id="eb025-108">c:\\Packages\\Contoso\\MyApp.appv</span></span>**

**<span data-ttu-id="eb025-109">c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="eb025-109">c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**

**<span data-ttu-id="eb025-110">使用 PowerShell 应用部署配置文件</span><span class="sxs-lookup"><span data-stu-id="eb025-110">To Apply the Deployment Configuration File Using PowerShell</span></span>**

-   <span data-ttu-id="eb025-111">若要为将在特定计算机上运行程序包的所有用户指定新的默认配置集，请使用 PowerShell 控制台键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="eb025-111">To specify a new default set of configurations for all users who will run the package on a specific computer, using a PowerShell console type the following:</span></span>

    **<span data-ttu-id="eb025-112">AppVClientPackage-Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="eb025-112">Add-AppVClientPackage –Path c:\\Packages\\Contoso\\MyApp.appv -DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**

    **<span data-ttu-id="eb025-113">注意</span><span class="sxs-lookup"><span data-stu-id="eb025-113">Note</span></span>**  
    <span data-ttu-id="eb025-114">此命令将生成的对象捕获到 $pkg 中。</span><span class="sxs-lookup"><span data-stu-id="eb025-114">This command captures the resulting object into $pkg.</span></span> <span data-ttu-id="eb025-115">如果计算机上已存在该程序包，则可以使用**AppVclientPackage** cmdlet 应用部署配置文档：</span><span class="sxs-lookup"><span data-stu-id="eb025-115">If the package is already present on the computer, the **Set-AppVclientPackage** cmdlet can be used to apply the deployment configuration document:</span></span>

    **<span data-ttu-id="eb025-116">设置-AppVClientPackage-Name Myapp-Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="eb025-116">Set-AppVClientPackage –Name Myapp –Path c:\\Packages\\Contoso\\MyApp.appv -DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="eb025-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="eb025-117">Related topics</span></span>


[<span data-ttu-id="eb025-118">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="eb025-118">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









