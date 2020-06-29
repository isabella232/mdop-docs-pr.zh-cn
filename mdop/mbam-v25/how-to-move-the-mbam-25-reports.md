---
title: 如何移动 MBAM 2.5 报告
description: 如何移动 MBAM 2.5 报告
author: dansimp
ms.assetid: c8223656-ca9d-41c8-94a3-64d07a6b99e9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1cdef260b4381671a1b9de66565ece0b70876200
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798034"
---
# <span data-ttu-id="db87b-103">如何移动 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="db87b-103">How to Move the MBAM 2.5 Reports</span></span>


<span data-ttu-id="db87b-104">使用这些过程将 "报告" 功能从一台计算机移动到另一台计算机，即将 "报告" 功能从服务器 A 移动到服务器 B。</span><span class="sxs-lookup"><span data-stu-id="db87b-104">Use these procedures to move the Reports feature from one computer to another, that is, to move the Reports feature from Server A to Server B.</span></span>

<span data-ttu-id="db87b-105">移动 "报表" 功能的高级步骤如下：</span><span class="sxs-lookup"><span data-stu-id="db87b-105">The high-level steps for moving the Reports feature are:</span></span>

1.  <span data-ttu-id="db87b-106">停止 MBAM 管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="db87b-106">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>

2.  <span data-ttu-id="db87b-107">在服务器 B 上安装 MBAM 2.5 服务器软件并在服务器 B 上配置 "报告" 功能。</span><span class="sxs-lookup"><span data-stu-id="db87b-107">Install the MBAM 2.5 Server software on Server B and configure the Reports feature on Server B.</span></span>

3.  <span data-ttu-id="db87b-108">在 MBAM 管理和监视服务器上更新报表连接数据。</span><span class="sxs-lookup"><span data-stu-id="db87b-108">Update the reports connection data on the MBAM Administration and Monitoring servers.</span></span>

4.  <span data-ttu-id="db87b-109">恢复 MBAM 管理和监视网站的实例。</span><span class="sxs-lookup"><span data-stu-id="db87b-109">Resume the instance of the MBAM Administration and Monitoring Website.</span></span>

<span data-ttu-id="db87b-110">**注意** 若要运行本主题中的示例 Windows PowerShell 脚本，必须更新 Windows PowerShell 执行策略以允许运行脚本。</span><span class="sxs-lookup"><span data-stu-id="db87b-110">**Note** To run the example Windows PowerShell scripts in this topic, you must update the Windows PowerShell execution policy to enable scripts to be run.</span></span> <span data-ttu-id="db87b-111">有关说明，请参阅[运行 Windows PowerShell 脚本](https://technet.microsoft.com/library/ee176949.aspx)。</span><span class="sxs-lookup"><span data-stu-id="db87b-111">See [Running Windows PowerShell Scripts](https://technet.microsoft.com/library/ee176949.aspx) for instructions.</span></span>

 

**<span data-ttu-id="db87b-112">停止 MBAM 管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="db87b-112">Stop the MBAM Administration and Monitoring Website</span></span>**

-   <span data-ttu-id="db87b-113">在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台停止管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="db87b-113">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

    <span data-ttu-id="db87b-114">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="db87b-114">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    ``` syntax
    PS C:\> Stop-Website "Microsoft BitLocker Administration and Monitoring"
    ```

**<span data-ttu-id="db87b-115">安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导</span><span class="sxs-lookup"><span data-stu-id="db87b-115">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>**

1.  <span data-ttu-id="db87b-116">在服务器 B 上安装 MBAM Server 软件。有关说明，请参阅[安装 MBAM 2.5 Server 软件](installing-the-mbam-25-server-software.md)。</span><span class="sxs-lookup"><span data-stu-id="db87b-116">Install the MBAM Server software on Server B. For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="db87b-117">在服务器 B 上，启动 "MBAM 服务器配置向导"，单击 "**添加新功能**"，然后仅选择 "**报表**" 功能。</span><span class="sxs-lookup"><span data-stu-id="db87b-117">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Reports** feature.</span></span>

    <span data-ttu-id="db87b-118">或者，你可以使用**Enable-MbamReport** Windows PowerShell cmdlet 来配置报告。</span><span class="sxs-lookup"><span data-stu-id="db87b-118">Alternatively, you can use the **Enable-MbamReport** Windows PowerShell cmdlet to configure the Reports.</span></span>

    <span data-ttu-id="db87b-119">有关如何配置报表的说明，请参阅[如何配置 MBAM 2.5 报表](how-to-configure-the-mbam-25-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="db87b-119">For instructions on how to configure the Reports, see [How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md).</span></span>

**<span data-ttu-id="db87b-120">更新管理和监视服务器上的报表连接数据</span><span class="sxs-lookup"><span data-stu-id="db87b-120">Update the reports connection data on the Administration and Monitoring Server</span></span>**

1.  <span data-ttu-id="db87b-121">在运行 "报表" 功能的服务器上，使用 "Internet 信息服务（IIS）管理器" 控制台更新报表 URL。</span><span class="sxs-lookup"><span data-stu-id="db87b-121">On the server that is running the Reports feature, use the Internet Information Services (IIS) Manager console to update the Reports URL.</span></span>

2.  <span data-ttu-id="db87b-122">展开 " **Microsoft BitLocker 管理和监视**"，然后选择 "**帮助台**" 节点。</span><span class="sxs-lookup"><span data-stu-id="db87b-122">Expand **Microsoft BitLocker Administration and Monitoring**, and then select the **HelpDesk** node.</span></span>

3.  <span data-ttu-id="db87b-123">在 "**功能" 视图**的 "**管理**" 部分中，选择 "**配置编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="db87b-123">In the **Management** section of the **Features View**, select **Configuration Editor**.</span></span>

4.  <span data-ttu-id="db87b-124">在 "**分区**" 字段中，选择 " **appSettings**"。</span><span class="sxs-lookup"><span data-stu-id="db87b-124">In the **Section** field, select **appSettings**.</span></span>

5.  <span data-ttu-id="db87b-125">选择 "**集合**" 行，然后单击窗格最右侧的 "省略号" 按钮 **（...）** 以打开**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="db87b-125">Select the **Collection** row, and then click the "ellipses" button **(…)** at the far right of the pane to open the **Collection Editor**.</span></span>

6.  <span data-ttu-id="db87b-126">在**集合编辑器**中，选择包含**Mbam**的行，并更新**Mbam**的值，以反映服务器 B 的服务器名称的值的名称。</span><span class="sxs-lookup"><span data-stu-id="db87b-126">In the **Collection Editor**, select the row that contains **Microsoft.Mbam.Reports.Url**, and update the value for **Microsoft.Mbam.Reports.Url** to reflect the server name for Server B.</span></span>

    <span data-ttu-id="db87b-127">如果以前在 SQL Server Reporting Services 的命名实例上配置了 "报表" 功能，请在 URL 中添加或更新实例的名称，例如：</span><span class="sxs-lookup"><span data-stu-id="db87b-127">If you previously configured the Reports feature on a named instance of SQL Server Reporting Services, add or update the name of the instance to the URL, for example:</span></span>

    `http://$SERVERNAME$/ReportServer_$SQLSRSINSTANCENAME$/Pages....)`

7.  <span data-ttu-id="db87b-128">若要自动执行此过程，你可以使用 Windows PowerShell 在管理和监视服务器上运行与以下代码示例类似的命令。</span><span class="sxs-lookup"><span data-stu-id="db87b-128">To automate this procedure, you can use Windows PowerShell to run a command on the Administration and Monitoring Server that is similar to the following code example.</span></span>

    ``` syntax
    PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\\sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value "http://$SERVERNAME$/ReportServer[_$SRSINSTANCENAME$]/Pages/ReportViewer.aspx?/Microsoft+BitLocker+Administration+and+Monitoring/"
    ```

    <span data-ttu-id="db87b-129">使用下表中的说明，将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="db87b-129">Using the descriptions in the following table, replace the values in the code example with values that match your environment.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="db87b-130">参数</span><span class="sxs-lookup"><span data-stu-id="db87b-130">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="db87b-131">描述</span><span class="sxs-lookup"><span data-stu-id="db87b-131">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="db87b-132">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="db87b-132">$SERVERNAME$</span></span></p></td>
    <td align="left"><p><span data-ttu-id="db87b-133">报告已移动到的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="db87b-133">Name of the server to which the Reports were moved.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="db87b-134">$SRSINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="db87b-134">$SRSINSTANCENAME$</span></span></p></td>
    <td align="left"><p><span data-ttu-id="db87b-135">报告已移动到的 SQL Server Reporting Services 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="db87b-135">Name of the instance of SQL Server Reporting Services to which the Reports were moved.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="db87b-136">恢复管理和监视网站的实例</span><span class="sxs-lookup"><span data-stu-id="db87b-136">Resume the instance of the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="db87b-137">在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台启动 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="db87b-137">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

2.  <span data-ttu-id="db87b-138">若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="db87b-138">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

    ``` syntax
    PS C:\> Start-Website "Microsoft BitLocker Administration and Monitoring"
    ```

    <span data-ttu-id="db87b-139">**注意** 若要运行此命令，必须将适用于 Windows PowerShell 的 IIS 模块添加到 Windows PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="db87b-139">**Note** To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

     



## <span data-ttu-id="db87b-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="db87b-140">Related topics</span></span>


[<span data-ttu-id="db87b-141">如何配置 MBAM 2.5 报告</span><span class="sxs-lookup"><span data-stu-id="db87b-141">How to Configure the MBAM 2.5 Reports</span></span>](how-to-configure-the-mbam-25-reports.md)

[<span data-ttu-id="db87b-142">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="db87b-142">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[<span data-ttu-id="db87b-143">将 MBAM 2.5 功能移动到另一个服务器上</span><span class="sxs-lookup"><span data-stu-id="db87b-143">Moving MBAM 2.5 Features to Another Server</span></span>](moving-mbam-25-features-to-another-server.md)

 
## <span data-ttu-id="db87b-144">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="db87b-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="db87b-145">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="db87b-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="db87b-146">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="db87b-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





