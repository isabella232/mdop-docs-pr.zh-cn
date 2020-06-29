---
title: 如何部署 App-V 5.1 Server
description: 如何部署 App-V 5.1 Server
author: dansimp
ms.assetid: 4729beda-b98f-481b-ae74-ad71c59b1d69
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4a367be7db4cea1835124657dbdfa3375474228e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798469"
---
# <span data-ttu-id="56fdc-103">如何部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="56fdc-103">How to Deploy the App-V 5.1 Server</span></span>


<span data-ttu-id="56fdc-104">使用以下过程安装 Microsoft Application Virtualization （App-v）5.1 服务器。</span><span class="sxs-lookup"><span data-stu-id="56fdc-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.1 server.</span></span> <span data-ttu-id="56fdc-105">有关部署 app-v 5.1 服务器的信息，请参阅[关于 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)。</span><span class="sxs-lookup"><span data-stu-id="56fdc-105">For information about deploying the App-V 5.1 Server, see [About App-V 5.1](about-app-v-51.md#bkmk-migrate-to-51).</span></span>

**<span data-ttu-id="56fdc-106">开始之前：</span><span class="sxs-lookup"><span data-stu-id="56fdc-106">Before you start:</span></span>**

-   <span data-ttu-id="56fdc-107">确保安装了必备软件。</span><span class="sxs-lookup"><span data-stu-id="56fdc-107">Ensure that you’ve installed prerequisite software.</span></span> <span data-ttu-id="56fdc-108">请参阅[App-V 5.1 先决条件](app-v-51-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="56fdc-108">See [App-V 5.1 Prerequisites](app-v-51-prerequisites.md).</span></span>

-   <span data-ttu-id="56fdc-109">查看[app-v 5.1 安全注意事项](app-v-51-security-considerations.md)的 "服务器" 部分。</span><span class="sxs-lookup"><span data-stu-id="56fdc-109">Review the server section of [App-V 5.1 Security Considerations](app-v-51-security-considerations.md).</span></span>

-   <span data-ttu-id="56fdc-110">指定将托管每个组件的端口。</span><span class="sxs-lookup"><span data-stu-id="56fdc-110">Specify a port where each component will be hosted.</span></span>

-   <span data-ttu-id="56fdc-111">添加防火墙规则以允许传入请求访问指定的端口。</span><span class="sxs-lookup"><span data-stu-id="56fdc-111">Add firewall rules to allow incoming requests to access the specified ports.</span></span>

-   <span data-ttu-id="56fdc-112">如果使用 SQL 脚本（而不是 Windows 安装程序）设置管理数据库或报告数据库，则必须先运行 SQL 脚本，然后再安装管理服务器或报告服务器。</span><span class="sxs-lookup"><span data-stu-id="56fdc-112">If you use SQL scripts, instead of the Windows Installer, to set up the Management database or Reporting database, you must run the SQL scripts before installing the Management Server or Reporting Server.</span></span> <span data-ttu-id="56fdc-113">请参阅[如何使用 SQL 脚本部署 App-v 数据库](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md)。</span><span class="sxs-lookup"><span data-stu-id="56fdc-113">See [How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md).</span></span>

**<span data-ttu-id="56fdc-114">安装 app-v 5.1 服务器</span><span class="sxs-lookup"><span data-stu-id="56fdc-114">To install the App-V 5.1 server</span></span>**

1. <span data-ttu-id="56fdc-115">将 app-v 5.1 服务器安装文件复制到要在其上安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="56fdc-115">Copy the App-V 5.1 server installation files to the computer on which you want to install it.</span></span>

2. <span data-ttu-id="56fdc-116">右键单击并以管理员身份运行**appv\_server\_setup.exe** ，启动 app-v 5.1 服务器安装，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="56fdc-116">Start the App-V 5.1 server installation by right-clicking and running **appv\_server\_setup.exe** as an administrator, and then click **Install**.</span></span>

3. <span data-ttu-id="56fdc-117">查看并接受许可条款，并选择是否启用 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="56fdc-117">Review and accept the license terms, and choose whether to enable Microsoft updates.</span></span>

4. <span data-ttu-id="56fdc-118">在 "**功能选择**" 页面上，选择以下所有组件。</span><span class="sxs-lookup"><span data-stu-id="56fdc-118">On the **Feature Selection** page, select all of the following components.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="56fdc-119">组件</span><span class="sxs-lookup"><span data-stu-id="56fdc-119">Component</span></span></th>
   <th align="left"><span data-ttu-id="56fdc-120">描述</span><span class="sxs-lookup"><span data-stu-id="56fdc-120">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="56fdc-121">管理服务器</span><span class="sxs-lookup"><span data-stu-id="56fdc-121">Management server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-122">提供 app-v 基础结构的总体管理功能。</span><span class="sxs-lookup"><span data-stu-id="56fdc-122">Provides overall management functionality for the App-V infrastructure.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="56fdc-123">管理数据库</span><span class="sxs-lookup"><span data-stu-id="56fdc-123">Management database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-124">为 App-v 管理简化数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="56fdc-124">Facilitates database predeployments for App-V management.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="56fdc-125">发布服务器</span><span class="sxs-lookup"><span data-stu-id="56fdc-125">Publishing server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-126">提供虚拟应用程序的托管和流功能。</span><span class="sxs-lookup"><span data-stu-id="56fdc-126">Provides hosting and streaming functionality for virtual applications.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="56fdc-127">报表服务器</span><span class="sxs-lookup"><span data-stu-id="56fdc-127">Reporting server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-128">提供 app-v 5.1 reporting services。</span><span class="sxs-lookup"><span data-stu-id="56fdc-128">Provides App-V 5.1 reporting services.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="56fdc-129">报告数据库</span><span class="sxs-lookup"><span data-stu-id="56fdc-129">Reporting database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-130">为 App-v 报告简化数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="56fdc-130">Facilitates database predeployments for App-V reporting.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

5. <span data-ttu-id="56fdc-131">在 "**安装位置**" 页面上，接受将安装所选组件的默认位置，或通过在 "**安装位置**" 行中键入新路径来更改位置。</span><span class="sxs-lookup"><span data-stu-id="56fdc-131">On the **Installation Location** page, accept the default location where the selected components will be installed, or change the location by typing a new path on the **Installation Location** line.</span></span>

6. <span data-ttu-id="56fdc-132">在初始的 "新建**管理数据库**" 页面上，通过选择相应的选项来配置**Microsoft SQL Server 实例**和**管理服务器数据库**。</span><span class="sxs-lookup"><span data-stu-id="56fdc-132">On the initial **Create New Management Database** page, configure the **Microsoft SQL Server instance** and **Management Server database** by selecting the appropriate option below.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="56fdc-133">方法</span><span class="sxs-lookup"><span data-stu-id="56fdc-133">Method</span></span></th>
   <th align="left"><span data-ttu-id="56fdc-134">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="56fdc-134">What you need to do</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="56fdc-135">你使用的是自定义 Microsoft SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="56fdc-135">You are using a custom Microsoft SQL Server instance.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-136">选择 <strong> "使用自定义实例" </strong> ，然后键入实例的名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-136">Select <strong>Use the custom instance</strong>, and type the name of the instance.</span></span></p>
   <p><span data-ttu-id="56fdc-137">使用格式 " <strong> INSTANCENAME" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="56fdc-137">Use the format <strong>INSTANCENAME</strong>.</span></span> <span data-ttu-id="56fdc-138">假定的安装位置是本地计算机。</span><span class="sxs-lookup"><span data-stu-id="56fdc-138">The assumed installation location is the local computer.</span></span></p>
   <p><span data-ttu-id="56fdc-139">不支持：使用格式 <strong> ServerName </strong> &lt; 强 &gt; 实例的服务器名称 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="56fdc-139">Not supported: A server name using the format <strong>ServerName</strong>&lt;strong&gt;INSTANCE</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="56fdc-140">您使用的是自定义数据库名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-140">You are using a custom database name.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-141">选择 <strong> "自定义配置 </strong> "，然后键入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-141">Select <strong>Custom configuration</strong> and type the database name.</span></span></p>
   <p><span data-ttu-id="56fdc-142">数据库名称必须是唯一的，否则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="56fdc-142">The database name must be unique, or the installation will fail.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="56fdc-143">在 "**配置**" 页面上，接受默认值 "**使用此本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="56fdc-143">On the **Configure** page, accept the default value **Use this local computer**.</span></span>

   **<span data-ttu-id="56fdc-144">注意</span><span class="sxs-lookup"><span data-stu-id="56fdc-144">Note</span></span>**  
   <span data-ttu-id="56fdc-145">如果并排安装管理服务器和管理数据库，则此页面上的某些选项不可用。</span><span class="sxs-lookup"><span data-stu-id="56fdc-145">If you are installing the Management server and Management database side by side, some options on this page are not available.</span></span> <span data-ttu-id="56fdc-146">在这种情况下，默认情况下将选中相应的选项，并且不能更改。</span><span class="sxs-lookup"><span data-stu-id="56fdc-146">In this case, the appropriate options are selected by default and cannot be changed.</span></span>

     

8. <span data-ttu-id="56fdc-147">在初始的 "**创建新的报表数据库**" 页面上，通过选择相应的选项来配置**Microsoft SQL Server 实例**和**报告服务器数据库**。</span><span class="sxs-lookup"><span data-stu-id="56fdc-147">On the initial **Create New Reporting Database** page, configure the **Microsoft SQL Server instance** and **Reporting Server database** by selecting the appropriate option below.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="56fdc-148">方法</span><span class="sxs-lookup"><span data-stu-id="56fdc-148">Method</span></span></th>
   <th align="left"><span data-ttu-id="56fdc-149">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="56fdc-149">What you need to do</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="56fdc-150">你使用的是自定义 Microsoft SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="56fdc-150">You are using a custom Microsoft SQL Server instance.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-151">选择 <strong> "使用自定义实例" </strong> ，然后键入实例的名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-151">Select <strong>Use the custom instance</strong>, and type the name of the instance.</span></span></p>
   <p><span data-ttu-id="56fdc-152">使用格式 " <strong> INSTANCENAME" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="56fdc-152">Use the format <strong>INSTANCENAME</strong>.</span></span> <span data-ttu-id="56fdc-153">假定的安装位置是本地计算机。</span><span class="sxs-lookup"><span data-stu-id="56fdc-153">The assumed installation location is the local computer.</span></span></p>
   <p><span data-ttu-id="56fdc-154">不支持：使用格式 <strong> ServerName </strong> &lt; 强 &gt; 实例的服务器名称 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="56fdc-154">Not supported: A server name using the format <strong>ServerName</strong>&lt;strong&gt;INSTANCE</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="56fdc-155">您使用的是自定义数据库名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-155">You are using a custom database name.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="56fdc-156">选择 <strong> "自定义配置 </strong> "，然后键入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-156">Select <strong>Custom configuration</strong> and type the database name.</span></span></p>
   <p><span data-ttu-id="56fdc-157">数据库名称必须是唯一的，否则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="56fdc-157">The database name must be unique, or the installation will fail.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

9. <span data-ttu-id="56fdc-158">在 "**配置**" 页面上，接受默认值：**使用此本地计算机**。</span><span class="sxs-lookup"><span data-stu-id="56fdc-158">On the **Configure** page, accept the default value: **Use this local computer**.</span></span>

   **<span data-ttu-id="56fdc-159">注意</span><span class="sxs-lookup"><span data-stu-id="56fdc-159">Note</span></span>**  
   <span data-ttu-id="56fdc-160">如果并排安装管理服务器和管理数据库，则此页面上的某些选项不可用。</span><span class="sxs-lookup"><span data-stu-id="56fdc-160">If you are installing the Management server and Management database side by side, some options on this page are not available.</span></span> <span data-ttu-id="56fdc-161">在这种情况下，默认情况下将选中相应的选项，并且不能更改。</span><span class="sxs-lookup"><span data-stu-id="56fdc-161">In this case, the appropriate options are selected by default and cannot be changed.</span></span>

     

10. <span data-ttu-id="56fdc-162">在 "**配置**（管理服务器配置）" 页面上，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="56fdc-162">On the **Configure** (Management Server Configuration) page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="56fdc-163">要配置的项目</span><span class="sxs-lookup"><span data-stu-id="56fdc-163">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="56fdc-164">描述和示例</span><span class="sxs-lookup"><span data-stu-id="56fdc-164">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="56fdc-165">键入具有管理 App-v 环境的足够权限的广告组。</span><span class="sxs-lookup"><span data-stu-id="56fdc-165">Type the AD group with sufficient permissions to manage the App-V environment.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-166">示例： MyDomain\MyUser</span><span class="sxs-lookup"><span data-stu-id="56fdc-166">Example: MyDomain\MyUser</span></span></p>
    <p><span data-ttu-id="56fdc-167">安装后，你可以使用管理控制台添加其他用户或组。</span><span class="sxs-lookup"><span data-stu-id="56fdc-167">After installation, you can add additional users or groups by using the Management console.</span></span> <span data-ttu-id="56fdc-168">但是，全局安全组和 Active Directory 域服务（AD DS）通讯组不受支持。</span><span class="sxs-lookup"><span data-stu-id="56fdc-168">However, global security groups and Active Directory Domain Services (AD DS) distribution groups are not supported.</span></span> <span data-ttu-id="56fdc-169">要 <strong> 执行此操作，必须使用域本地 </strong> 或 <strong> 通用 </strong> 组。</span><span class="sxs-lookup"><span data-stu-id="56fdc-169">You must use <strong>Domain local</strong> or <strong>Universal</strong> groups are required to perform this action.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="56fdc-170">网站名称 </strong> ：指定将用于运行发布服务的自定义名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-170">Website name</strong>: Specify the custom name that will be used to run the publishing service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-171">如果您没有自定义名称，请不要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="56fdc-171">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="56fdc-172">端口绑定 </strong> ：指定将由 app-v 使用的唯一端口号。</span><span class="sxs-lookup"><span data-stu-id="56fdc-172">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-173">示例： <strong> 12345</span><span class="sxs-lookup"><span data-stu-id="56fdc-173">Example: <strong>12345</span></span></strong></p>
    <p><span data-ttu-id="56fdc-174">确保指定的端口未被其他网站使用。</span><span class="sxs-lookup"><span data-stu-id="56fdc-174">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

11. <span data-ttu-id="56fdc-175">在 "**配置\*\*\*\*发布服务器配置**" 页面上，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="56fdc-175">On the **Configure** **Publishing Server Configuration** page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="56fdc-176">要配置的项目</span><span class="sxs-lookup"><span data-stu-id="56fdc-176">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="56fdc-177">描述和示例</span><span class="sxs-lookup"><span data-stu-id="56fdc-177">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="56fdc-178">指定管理服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="56fdc-178">Specify the URL for the management service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-179">上例<a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</span><span class="sxs-lookup"><span data-stu-id="56fdc-179">Example: <a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</span></span></a></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="56fdc-180">网站名称 </strong> ：指定将用于运行发布服务的自定义名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-180">Website name</strong>: Specify the custom name that will be used to run the publishing service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-181">如果您没有自定义名称，请不要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="56fdc-181">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="56fdc-182">端口绑定 </strong> ：指定将由 app-v 使用的唯一端口号。</span><span class="sxs-lookup"><span data-stu-id="56fdc-182">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-183">示例：54321</span><span class="sxs-lookup"><span data-stu-id="56fdc-183">Example: 54321</span></span></p>
    <p><span data-ttu-id="56fdc-184">确保指定的端口未被其他网站使用。</span><span class="sxs-lookup"><span data-stu-id="56fdc-184">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

12. <span data-ttu-id="56fdc-185">在 "**报告服务器**" 页面上，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="56fdc-185">On the **Reporting Server** page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="56fdc-186">要配置的项目</span><span class="sxs-lookup"><span data-stu-id="56fdc-186">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="56fdc-187">描述和示例</span><span class="sxs-lookup"><span data-stu-id="56fdc-187">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="56fdc-188">网站名称 </strong> ：指定将用于运行报告服务的自定义名称。</span><span class="sxs-lookup"><span data-stu-id="56fdc-188">Website name</strong>: Specify the custom name that will be used to run the Reporting Service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-189">如果您没有自定义名称，请不要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="56fdc-189">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="56fdc-190">端口绑定 </strong> ：指定将由 app-v 使用的唯一端口号。</span><span class="sxs-lookup"><span data-stu-id="56fdc-190">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="56fdc-191">示例：55555</span><span class="sxs-lookup"><span data-stu-id="56fdc-191">Example: 55555</span></span></p>
    <p><span data-ttu-id="56fdc-192">确保指定的端口未被其他网站使用。</span><span class="sxs-lookup"><span data-stu-id="56fdc-192">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

13. <span data-ttu-id="56fdc-193">若要开始安装，请单击 "**准备就绪**" 页面上的 "**安装**"，然后单击 "**完成**" 页面上的 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="56fdc-193">To start the installation, click **Install** on the **Ready** page, and then click **Close** on the **Finished** page.</span></span>

14. <span data-ttu-id="56fdc-194">若要验证安装程序是否已成功完成，请打开 web 浏览器，然后键入以下 URL：</span><span class="sxs-lookup"><span data-stu-id="56fdc-194">To verify that the setup completed successfully, open a web browser, and type the following URL:</span></span>

    <span data-ttu-id="56fdc-195">**http:// &lt;管理服务器计算机名称 &gt; ： &lt; 管理服务端口号 &gt; /Console.html**。</span><span class="sxs-lookup"><span data-stu-id="56fdc-195">**http://&lt;Management server machine name&gt;:&lt;Management service port number&gt;/Console.html**.</span></span>

    <span data-ttu-id="56fdc-196">示例： **http://localhost:12345/console.html** 。</span><span class="sxs-lookup"><span data-stu-id="56fdc-196">Example: **http://localhost:12345/console.html**.</span></span> <span data-ttu-id="56fdc-197">如果安装成功，将显示 app-v 管理控制台，没有任何错误。</span><span class="sxs-lookup"><span data-stu-id="56fdc-197">If the installation succeeded, the App-V Management console is displayed with no errors.</span></span>

    <span data-ttu-id="56fdc-198">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="56fdc-198">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="56fdc-199">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="56fdc-199">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="56fdc-200">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="56fdc-200">Got an App-V issue?</span></span>** <span data-ttu-id="56fdc-201">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="56fdc-201">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="56fdc-202">相关主题</span><span class="sxs-lookup"><span data-stu-id="56fdc-202">Related topics</span></span>


[<span data-ttu-id="56fdc-203">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="56fdc-203">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="56fdc-204">如何在单独的计算机上从管理和报告服务安装管理和报告数据库</span><span class="sxs-lookup"><span data-stu-id="56fdc-204">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[<span data-ttu-id="56fdc-205">如何在远程计算机上安装发布服务器</span><span class="sxs-lookup"><span data-stu-id="56fdc-205">How to Install the Publishing Server on a Remote Computer</span></span>](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[<span data-ttu-id="56fdc-206">如何使用脚本部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="56fdc-206">How to Deploy the App-V 5.1 Server Using a Script</span></span>](how-to-deploy-the-app-v-51-server-using-a-script.md)

 

 





