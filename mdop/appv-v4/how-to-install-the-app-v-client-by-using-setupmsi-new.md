---
title: 如何使用 Setup.msi 安装 App-V Client
description: 如何使用 Setup.msi 安装 App-V Client
author: dansimp
ms.assetid: 7221f384-36d6-409a-94a2-86f54fd75322
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb3a145a6c57cccbae3f4e6b191b89d93278ff8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801375"
---
# <span data-ttu-id="3b631-103">如何使用 Setup.msi 安装 App-V Client</span><span class="sxs-lookup"><span data-stu-id="3b631-103">How to Install the App-V Client by Using Setup.msi</span></span>


<span data-ttu-id="3b631-104">本主题介绍了如何使用 setup.msi 程序安装 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="3b631-104">This topic describes how to install the App-V client by using the setup.msi program.</span></span> <span data-ttu-id="3b631-105">在使用 setup.msi 程序安装 app-v 客户端之前，必须首先确定是否必须安装任何必备软件，然后必须安装它。</span><span class="sxs-lookup"><span data-stu-id="3b631-105">Before you install the App-V client using the setup.msi program, you must first determine if any prerequisite software must be installed, and then you must install it.</span></span> <span data-ttu-id="3b631-106">若要安装必备软件，请参阅本主题的[安装必备软件](#prereq-sw)部分。</span><span class="sxs-lookup"><span data-stu-id="3b631-106">To install the prerequisite software, see the [Installing Prerequisite Software](#prereq-sw) section of this topic.</span></span> <span data-ttu-id="3b631-107">若要安装客户端软件，请参阅使用本主题的[Setup.msi 程序部分安装 App-v 客户端](#msi-setup)。</span><span class="sxs-lookup"><span data-stu-id="3b631-107">To install the client software, see the [Installing the App-V Client Using the Setup.msi Program](#msi-setup) section of this topic.</span></span>

## <a href="" id="prereq-sw"></a><span data-ttu-id="3b631-108">安装必备软件</span><span class="sxs-lookup"><span data-stu-id="3b631-108">Installing Prerequisite Software</span></span>


<span data-ttu-id="3b631-109">你可以使用以下过程来安装必备软件。</span><span class="sxs-lookup"><span data-stu-id="3b631-109">You can use the following procedures to install the prerequisite software.</span></span> <span data-ttu-id="3b631-110">可以创建命令文件并从命令提示符运行命令，也可以使用脚本语言（如 VBScript 或 Windows PowerShell）运行命令。</span><span class="sxs-lookup"><span data-stu-id="3b631-110">You can create a command file and run the commands from the command prompt, or you can use a scripting language such as VBScript or Windows PowerShell to run the commands.</span></span>

<span data-ttu-id="3b631-111">**注意** 适用于 App-v 客户端的 x86 和 x64 版本都需要以下软件的 x86 版本。</span><span class="sxs-lookup"><span data-stu-id="3b631-111">**Note** The x86 versions of the following software are required for both x86 and x64 versions of the App-V client.</span></span>

 

**<span data-ttu-id="3b631-112">安装 Microsoft VisualC + + 2005SP1 可再发行程序包（x86）</span><span class="sxs-lookup"><span data-stu-id="3b631-112">To install Microsoft VisualC++2005SP1 Redistributable Package (x86)</span></span>**

1. <span data-ttu-id="3b631-113">从 Microsoft 下载中心下载[Microsoft Visual c + + 2005 SP1 可再发行程序包（x86）](https://go.microsoft.com/fwlink/?LinkId=119961)软件包（ <https://go.microsoft.com/fwlink/?LinkId=119961> ）。</span><span class="sxs-lookup"><span data-stu-id="3b631-113">Download the [Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=119961) software package from the Microsoft Download Center (<https://go.microsoft.com/fwlink/?LinkId=119961>).</span></span> <span data-ttu-id="3b631-114">\ [模板令牌值 \] 对于应用-V 客户端的版本 4.5 SP2 和更高版本，请从[Microsoft Visual c + + 2005 Service Pack 1 可再发行软件包 1](https://go.microsoft.com/fwlink/?LinkId=169360)下载 vcredist\_x86.exe （ https://go.microsoft.com/fwlink/?LinkId=169360).\ [Template Token Value \]）下载</span><span class="sxs-lookup"><span data-stu-id="3b631-114">\[Template Token Value\] For version 4.5 SP2 and later of the App-V client, download vcredist\_x86.exe from [Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360) (https://go.microsoft.com/fwlink/?LinkId=169360).\[Template Token Value\]</span></span>

2. <span data-ttu-id="3b631-115">若要自行安装，请将命令行选项 "/Q" 与 vcredist\_x86.exe 结合使用，例如**vcredist\_x86.exe/q**。</span><span class="sxs-lookup"><span data-stu-id="3b631-115">To install silently, use the command-line option “/Q” with vcredist\_x86.exe—for example, **vcredist\_x86.exe /Q**.</span></span>

3. <span data-ttu-id="3b631-116">若要使用 vcredist\_x86.msi 文件安装软件，请使用命令行选项 "/C/T： &lt; fullpathtofolder &gt; " 提取文件 vcredist.msi 并 vcredis1.cab 从 vcredist\_x86.exe 到临时文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b631-116">To install the software by using the vcredist\_x86.msi file, use the command-line option “/C /T:&lt;fullpathtofolder&gt;” to extract the files vcredist.msi and vcredis1.cab from vcredist\_x86.exe to a temporary folder.</span></span> <span data-ttu-id="3b631-117">若要自行安装，请使用命令行选项/quiet，例如， **msiexec/i vcredist.msi** /quiet。</span><span class="sxs-lookup"><span data-stu-id="3b631-117">To install silently, use the command-line option /quiet—for example, **msiexec /i vcredist.msi** /quiet.</span></span>

### <span data-ttu-id="3b631-118">安装 Microsoft VisualC + + 2008SP1 可再发行程序包（x86）</span><span class="sxs-lookup"><span data-stu-id="3b631-118">To install Microsoft VisualC++2008SP1 Redistributable Package (x86)</span></span>

<span data-ttu-id="3b631-119">**重要提示** 对于应用程序-V 客户端的版本4.6 和更高版本，你还必须安装 Microsoft Visual c + + 2008 Service Pack 1 可再发行程序包 "ATL 安全更新"。</span><span class="sxs-lookup"><span data-stu-id="3b631-119">**Important** For version4.6 and later of the App-V client, you must also install the Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update.</span></span>

 

****

1.  <span data-ttu-id="3b631-120">从 Microsoft 下载中心下载[Microsoft Visual c + + 2008 Service Pack 1 可再发行软件包 "ATL 安全更新](https://go.microsoft.com/fwlink/?LinkId=150700)软件包" （ https://go.microsoft.com/fwlink/?LinkId=150700) 。</span><span class="sxs-lookup"><span data-stu-id="3b631-120">Download the [Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=150700) software package from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=150700).</span></span>

2.  <span data-ttu-id="3b631-121">若要自行安装，请将命令行选项 "/Q" 与 vcredist\_x86.exe 结合使用，例如**vcredist\_x86.exe/q**。</span><span class="sxs-lookup"><span data-stu-id="3b631-121">To install silently, use the command-line option “/Q” with vcredist\_x86.exe—for example, **vcredist\_x86.exe /Q**.</span></span>

### <span data-ttu-id="3b631-122">安装 Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）</span><span class="sxs-lookup"><span data-stu-id="3b631-122">To install Microsoft Core XML Services (MSXML)6.0SP1 (x86)</span></span>

****

1.  <span data-ttu-id="3b631-123">从 Microsoft 下载中心下载[Microsoft CORE XML Services （MSXML） 6.0 sp1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266)软件包（ https://go.microsoft.com/fwlink/?LinkId=63266) 。</span><span class="sxs-lookup"><span data-stu-id="3b631-123">Download the [Microsoft Core XML Services (MSXML)6.0SP1 (x86)](https://go.microsoft.com/fwlink/?LinkId=63266) software package from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=63266).</span></span>

2.  <span data-ttu-id="3b631-124">若要自行安装，请使用命令行选项/quiet，例如， **msiexec/i msxml6\_x86.msi/quiet**。</span><span class="sxs-lookup"><span data-stu-id="3b631-124">To install silently, use the command-line option /quiet—for example, **msiexec /i msxml6\_x86.msi /quiet**.</span></span>

### <span data-ttu-id="3b631-125">安装 Microsoft 应用程序错误报告</span><span class="sxs-lookup"><span data-stu-id="3b631-125">To install Microsoft Application Error Reporting</span></span>

<span data-ttu-id="3b631-126">安装 Microsoft 应用程序错误报告时，必须使用*APPGUID*参数来指定应用程序-V 产品代码。</span><span class="sxs-lookup"><span data-stu-id="3b631-126">When installing Microsoft Application Error Reporting, you must use the *APPGUID* parameter to specify the App-V product code.</span></span> <span data-ttu-id="3b631-127">产品代码对于每个 App-v 客户端类型和版本都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3b631-127">The product code is unique for each App-V client type and version.</span></span> <span data-ttu-id="3b631-128">从下表中选择正确的产品代码。</span><span class="sxs-lookup"><span data-stu-id="3b631-128">Select the correct product code from the following table.</span></span>

<span data-ttu-id="3b631-129">**重要提示** 对于 app-v 4.6 SP2 及更高版本，不再需要安装 Microsoft 应用程序错误报告（dw20shared.msi）。</span><span class="sxs-lookup"><span data-stu-id="3b631-129">**Important** For App-V4.6SP2 and later, you no longer need to install Microsoft Application Error Reporting (dw20shared.msi).</span></span> <span data-ttu-id="3b631-130">App-v 现在使用 Microsoft 错误报告。</span><span class="sxs-lookup"><span data-stu-id="3b631-130">App-V now uses Microsoft Error Reporting.</span></span>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3b631-131">版本</span><span class="sxs-lookup"><span data-stu-id="3b631-131">Version</span></span></th>
<th align="left"><span data-ttu-id="3b631-132">桌面客户端的产品代码</span><span class="sxs-lookup"><span data-stu-id="3b631-132">Product Code for Desktop Client</span></span></th>
<th align="left"><span data-ttu-id="3b631-133">适用于远程桌面服务客户端的产品代码</span><span class="sxs-lookup"><span data-stu-id="3b631-133">Product Code for Client for Remote Desktop Services</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3b631-134">App-v 4.5 CU1</span><span class="sxs-lookup"><span data-stu-id="3b631-134">App-V 4.5 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-135">FE495DBC-6D42-4698-B61F-86E655E0796D</span><span class="sxs-lookup"><span data-stu-id="3b631-135">FE495DBC-6D42-4698-B61F-86E655E0796D</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-136">8A97C241-D92A-47DC-B360-E716C1AAA929</span><span class="sxs-lookup"><span data-stu-id="3b631-136">8A97C241-D92A-47DC-B360-E716C1AAA929</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3b631-137">App-v 4.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3b631-137">App-V 4.5 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-138">93468B43-C19D-44F9-8BCC-114076DB0443</span><span class="sxs-lookup"><span data-stu-id="3b631-138">93468B43-C19D-44F9-8BCC-114076DB0443</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-139">0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</span><span class="sxs-lookup"><span data-stu-id="3b631-139">0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3b631-140">App-v 4.5 SP2</span><span class="sxs-lookup"><span data-stu-id="3b631-140">App-V 4.5 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-141">C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</span><span class="sxs-lookup"><span data-stu-id="3b631-141">C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-142">ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</span><span class="sxs-lookup"><span data-stu-id="3b631-142">ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3b631-143">App-v 4.6 x86</span><span class="sxs-lookup"><span data-stu-id="3b631-143">App-V 4.6 x86</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-144">9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</span><span class="sxs-lookup"><span data-stu-id="3b631-144">9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-145">439FAC21-B423-41D4-8126-54F9FCB70039</span><span class="sxs-lookup"><span data-stu-id="3b631-145">439FAC21-B423-41D4-8126-54F9FCB70039</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3b631-146">App-v 4.6 x64</span><span class="sxs-lookup"><span data-stu-id="3b631-146">App-V 4.6 x64</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-147">E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</span><span class="sxs-lookup"><span data-stu-id="3b631-147">E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-148">D2977C18-D88A-47CB-AFD8-652DD36F4D0D</span><span class="sxs-lookup"><span data-stu-id="3b631-148">D2977C18-D88A-47CB-AFD8-652DD36F4D0D</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3b631-149">App-v 4.6 x86 ¹</span><span class="sxs-lookup"><span data-stu-id="3b631-149">App-V 4.6 x86 ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-150">40C3258B-F9D1-46DF-AE97-72C1F86F2427</span><span class="sxs-lookup"><span data-stu-id="3b631-150">40C3258B-F9D1-46DF-AE97-72C1F86F2427</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-151">9915D911-CC73-4122-AF4F-564F89454655</span><span class="sxs-lookup"><span data-stu-id="3b631-151">9915D911-CC73-4122-AF4F-564F89454655</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3b631-152">App-v 4.6 x64 ¹</span><span class="sxs-lookup"><span data-stu-id="3b631-152">App-V 4.6 x64 ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-153">1650E31F-23B8-40B5-A60A-C5934F557E3B</span><span class="sxs-lookup"><span data-stu-id="3b631-153">1650E31F-23B8-40B5-A60A-C5934F557E3B</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-154">7580D918-C621-49E7-9877-3CC59F9BD1DA</span><span class="sxs-lookup"><span data-stu-id="3b631-154">7580D918-C621-49E7-9877-3CC59F9BD1DA</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3b631-155">App-v 4.6 x86 SP1</span><span class="sxs-lookup"><span data-stu-id="3b631-155">App-V 4.6 x86 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-156">DB9F70CD-29BC-480B-8BA2-C9C2232C4553</span><span class="sxs-lookup"><span data-stu-id="3b631-156">DB9F70CD-29BC-480B-8BA2-C9C2232C4553</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-157">1354855A-2298-4C73-9022-EF0686C65991</span><span class="sxs-lookup"><span data-stu-id="3b631-157">1354855A-2298-4C73-9022-EF0686C65991</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3b631-158">App-v 4.6 x64 SP1</span><span class="sxs-lookup"><span data-stu-id="3b631-158">App-V 4.6 x64 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-159">342C9BB8-65A0-46DE-AB7A-8031E151AF69</span><span class="sxs-lookup"><span data-stu-id="3b631-159">342C9BB8-65A0-46DE-AB7A-8031E151AF69</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b631-160">B2C6C8D5-FE76-4056-A326-EE5D633EA175</span><span class="sxs-lookup"><span data-stu-id="3b631-160">B2C6C8D5-FE76-4056-A326-EE5D633EA175</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3b631-161">¹ App-V "语言" 发布。</span><span class="sxs-lookup"><span data-stu-id="3b631-161">¹App-V “Languages” release.</span></span>

<span data-ttu-id="3b631-162">**注意** 如果需要查找产品代码，可以使用 Orca.exe 数据库编辑器或类似工具检查 Windows 安装程序文件以查找*ProductCode*属性的值。</span><span class="sxs-lookup"><span data-stu-id="3b631-162">**Note** If you need to find the product code, you can use the Orca.exe database editor or a similar tool to examine Windows Installer files to find the value of the *ProductCode* property.</span></span> <span data-ttu-id="3b631-163">有关使用 Orca.exe 的详细信息，请参阅[Windows Installer 开发工具](https://go.microsoft.com/fwlink/?LinkId=150008)（ https://go.microsoft.com/fwlink/?LinkId=150008) 。</span><span class="sxs-lookup"><span data-stu-id="3b631-163">For more information about using Orca.exe, see [Windows Installer Development Tools](https://go.microsoft.com/fwlink/?LinkId=150008) (https://go.microsoft.com/fwlink/?LinkId=150008).</span></span>

 

****

1.  <span data-ttu-id="3b631-164">找到 "Microsoft 应用程序错误报告安装程序" dw20shared.msi，可在发布媒体上的**Support\\Watson**文件夹中找到该程序。</span><span class="sxs-lookup"><span data-stu-id="3b631-164">Locate the Microsoft Application Error Reporting install program, dw20shared.msi, which can be found in the **Support\\Watson** folder on the release media.</span></span>

2.  <span data-ttu-id="3b631-165">若要安装该软件，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3b631-165">To install the software, run the following command:</span></span>

         **msiexec /i dw20shared.msi APPGUID={valuefromtable} REBOOT=Suppress REINSTALL=ALL REINSTALLMODE=vomus**

## <a href="" id="msi-setup"></a><span data-ttu-id="3b631-166">使用 Setup.msi 程序安装 App-v 客户端</span><span class="sxs-lookup"><span data-stu-id="3b631-166">Installing the App-V Client by Using the Setup.msi Program</span></span>


<span data-ttu-id="3b631-167">使用以下过程安装 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="3b631-167">Use the following procedure to install the App-V client.</span></span> <span data-ttu-id="3b631-168">确保已安装任何必需的必备软件。</span><span class="sxs-lookup"><span data-stu-id="3b631-168">Ensure that any necessary prerequisite software has been installed.</span></span> <span data-ttu-id="3b631-169">\ [模板令牌值 \] 对于应用程序-V 客户端的版本4.6 和更高版本，setup.msi 程序检查系统，并且如果未安装必备软件，它会生成一条错误消息，指示安装无法继续。</span><span class="sxs-lookup"><span data-stu-id="3b631-169">\[Template Token Value\] For version4.6 and later of the App-V client, the setup.msi program checks the system and if prerequisite software is not installed, it generates an error message indicating that installation cannot continue.</span></span> <span data-ttu-id="3b631-170">\ [模板令牌值 \]</span><span class="sxs-lookup"><span data-stu-id="3b631-170">\[Template Token Value\]</span></span>

**<span data-ttu-id="3b631-171">使用 Setup.msi 安装应用程序虚拟化客户端</span><span class="sxs-lookup"><span data-stu-id="3b631-171">To install the Application Virtualization Client by Using Setup.msi</span></span>**

1.  <span data-ttu-id="3b631-172">请确保使用具有计算机管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3b631-172">Make sure you are logged on with an account that has administrator rights on the computer.</span></span>

2.  <span data-ttu-id="3b631-173">使用提升的权限打开命令提示符窗口，然后将目录更改为包含安装程序文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b631-173">Open a Command Prompt window by using elevated rights, and then change the directory to the folder that contains the setup files.</span></span> <span data-ttu-id="3b631-174">在安装版本4.6 或更高版本的 App-v 客户端时，必须使用适用于计算机操作系统、32位或64位的正确安装程序。</span><span class="sxs-lookup"><span data-stu-id="3b631-174">When installing version4.6 or a later version of the App-V client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="3b631-175">如果你使用了错误的安装程序，安装将失败，并且将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="3b631-175">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

3.  <span data-ttu-id="3b631-176">在命令提示符处输入安装命令字符串。</span><span class="sxs-lookup"><span data-stu-id="3b631-176">Enter the install command string at the command prompt.</span></span> <span data-ttu-id="3b631-177">或者，你可以创建一个命令文件并从命令提示符处运行它。</span><span class="sxs-lookup"><span data-stu-id="3b631-177">Alternatively, you can create a command file and run it from the command prompt.</span></span> <span data-ttu-id="3b631-178">你还可以使用脚本语言（如 VBScript 或 Windows PowerShell）运行命令。</span><span class="sxs-lookup"><span data-stu-id="3b631-178">You can also use a scripting language such as VBScript or Windows PowerShell to run the command.</span></span>

4.  <span data-ttu-id="3b631-179">下面的命令行示例演示如何将 setup.msi 用于许多可选参数。</span><span class="sxs-lookup"><span data-stu-id="3b631-179">The following command-line example shows how setup.msi can be used with a number of optional parameters.</span></span> <span data-ttu-id="3b631-180">有关这些参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="3b631-180">For more information about these parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

    **<span data-ttu-id="3b631-181">msiexec.exe/i "setup.msi" SWICACHESIZE = "10240" SWIPUBSVRDISPLAY = "生产系统" SWIPUBSVRTYPE = "HTTP/secure" SWIPUBSVRHOST = "PRODSYS =" = "appsntype.xml SWIPUBSVRPORT =" SWIPUBSVRPATH = "/AppVirt/=" SWIPUBSVRREFRESH = "SWIGLOBALDATA =" D:\\AppVirt\\Global = "SWIUSERDATA =" LOCALAPPDATA = "S"%\\Windows\\Application ^ SWIFSDRIVE 虚拟化客户端 "=" S "/q</span><span class="sxs-lookup"><span data-stu-id="3b631-181">msiexec.exe /i "setup.msi" SWICACHESIZE="10240" SWIPUBSVRDISPLAY="Production System" SWIPUBSVRTYPE="HTTP /secure" SWIPUBSVRHOST="PRODSYS" SWIPUBSVRPORT="443" SWIPUBSVRPATH="/AppVirt/appsntype.xml" SWIPUBSVRREFRESH="on" SWIGLOBALDATA="D:\\AppVirt\\Global" SWIUSERDATA="^% LOCALAPPDATA^%\\Windows\\Application Virtualization Client" SWIFSDRIVE="S" /q</span></span>**

    **<span data-ttu-id="3b631-182">重要提示</span><span class="sxs-lookup"><span data-stu-id="3b631-182">Important</span></span>**  
    -   <span data-ttu-id="3b631-183">Windows Installer 开关 "**/q**" 用于将其设置为静默式安装。</span><span class="sxs-lookup"><span data-stu-id="3b631-183">The Windows Installer switch "**/q**" is used to make this a silent installation.</span></span>

    -   <span data-ttu-id="3b631-184">" **%** **% HomeDrive%**" 中的 "" 字符必须前面有 " **^** " 转义字符。</span><span class="sxs-lookup"><span data-stu-id="3b631-184">The "**%**" characters in "**%HomeDrive%**" must be preceded by the "**^**" escape character.</span></span> <span data-ttu-id="3b631-185">否则，Windows 命令外壳程序会将值设置为执行安装的用户的值。</span><span class="sxs-lookup"><span data-stu-id="3b631-185">Otherwise, the Windows command shell sets the value to that of the user who is performing the installation.</span></span>

    -   <span data-ttu-id="3b631-186">若要启用安装日志记录，请使用 msiexec 开关 **/l\ \* v 文件名 .log**。</span><span class="sxs-lookup"><span data-stu-id="3b631-186">To turn on installation logging, use the msiexec switch **/l\*v filename.log**.</span></span>

     

## <span data-ttu-id="3b631-187">相关主题</span><span class="sxs-lookup"><span data-stu-id="3b631-187">Related topics</span></span>


[<span data-ttu-id="3b631-188">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="3b631-188">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





