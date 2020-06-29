---
title: 如何使用 SQL 脚本部署 App-V 数据库
description: 如何使用 SQL 脚本部署 App-V 数据库
author: dansimp
ms.assetid: 23637936-475f-4ca5-adde-76bb27d2372b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 511d1020571eead25af9e9591fe1834a9f97f068
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798464"
---
# <span data-ttu-id="00fae-103">如何使用 SQL 脚本部署 App-V 数据库</span><span class="sxs-lookup"><span data-stu-id="00fae-103">How to Deploy the App-V Databases by Using SQL Scripts</span></span>


<span data-ttu-id="00fae-104">按照以下说明使用 SQL 脚本（而不是 Windows 安装程序）执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00fae-104">Use the following instructions to use SQL scripts, rather than the Windows Installer, to:</span></span>

-   <span data-ttu-id="00fae-105">安装 app-v 5.0 数据库</span><span class="sxs-lookup"><span data-stu-id="00fae-105">Install the App-V 5.0 databases</span></span>

-   <span data-ttu-id="00fae-106">将5.0 数据库升级到更高版本</span><span class="sxs-lookup"><span data-stu-id="00fae-106">Upgrade the 5.0 databases to a later version</span></span>

**<span data-ttu-id="00fae-107">如何使用 SQL 脚本安装 app-v 数据库</span><span class="sxs-lookup"><span data-stu-id="00fae-107">How to install the App-V databases by using SQL scripts</span></span>**

1. <span data-ttu-id="00fae-108">在安装数据库脚本之前，请检查并保留 App-v 许可证条款的副本。</span><span class="sxs-lookup"><span data-stu-id="00fae-108">Before you install the database scripts, review and keep a copy of the App-V license terms.</span></span> <span data-ttu-id="00fae-109">运行数据库脚本即已同意许可条款。</span><span class="sxs-lookup"><span data-stu-id="00fae-109">By running the database scripts, you are agreeing to the license terms.</span></span> <span data-ttu-id="00fae-110">如果您不接受这些功能，则不应使用本软件。</span><span class="sxs-lookup"><span data-stu-id="00fae-110">If you do not accept them, you should not use this software.</span></span>

2. <span data-ttu-id="00fae-111">将**appv\_server\_setup.exe**从 app-v 版本媒体复制到临时位置。</span><span class="sxs-lookup"><span data-stu-id="00fae-111">Copy the **appv\_server\_setup.exe** from the App-V release media to a temporary location.</span></span>

3. <span data-ttu-id="00fae-112">在命令提示符处，运行**appv\_server\_setup.exe**并指定用于提取数据库脚本的临时位置。</span><span class="sxs-lookup"><span data-stu-id="00fae-112">From a command prompt, run **appv\_server\_setup.exe** and specify a temporary location for extracting the database scripts.</span></span>

   <span data-ttu-id="00fae-113">示例： appv\_server\_setup.exe/layout c:\\ &lt; 临时位置路径&gt;</span><span class="sxs-lookup"><span data-stu-id="00fae-113">Example: appv\_server\_setup.exe /layout c:\\&lt;temporary location path&gt;</span></span>

4. <span data-ttu-id="00fae-114">通过浏览找到您创建的临时位置，打开解压缩的**DatabaseScripts**文件夹，然后查看相应的 Readme.txt 文件，了解有关说明：</span><span class="sxs-lookup"><span data-stu-id="00fae-114">Browse to the temporary location that you created, open the extracted **DatabaseScripts** folder, and review the appropriate Readme.txt file for instructions:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="00fae-115">数据库</span><span class="sxs-lookup"><span data-stu-id="00fae-115">Database</span></span></th>
   <th align="left"><span data-ttu-id="00fae-116">要使用 Readme.txt 文件的位置</span><span class="sxs-lookup"><span data-stu-id="00fae-116">Location of Readme.txt file to use</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="00fae-117">管理数据库</span><span class="sxs-lookup"><span data-stu-id="00fae-117">Management database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="00fae-118">ManagementDatabase 子文件夹</span><span class="sxs-lookup"><span data-stu-id="00fae-118">ManagementDatabase subfolder</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="00fae-119">重要提示</span><span class="sxs-lookup"><span data-stu-id="00fae-119">Important</span></span></strong><br/><p><span data-ttu-id="00fae-120">如果要升级到或安装 app-v 5.0 SP3 管理数据库，请参阅 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安装或升级 app-v 5.0 Sp3 管理服务器数据库失败的 SQL 脚本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="00fae-120">If you are upgrading to or installing the App-V 5.0 SP3 Management database, see <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)">SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="00fae-121">报告数据库</span><span class="sxs-lookup"><span data-stu-id="00fae-121">Reporting database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="00fae-122">ReportingDatabase 子文件夹</span><span class="sxs-lookup"><span data-stu-id="00fae-122">ReportingDatabase subfolder</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="00fae-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="00fae-123">Related topics</span></span>


[<span data-ttu-id="00fae-124">部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="00fae-124">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

[<span data-ttu-id="00fae-125">如何部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="00fae-125">How to Deploy the App-V 5.0 Server</span></span>](how-to-deploy-the-app-v-50-server-50sp3.md)









